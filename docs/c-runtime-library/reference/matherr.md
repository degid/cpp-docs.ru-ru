---
title: _matherr
ms.date: 04/05/2018
api_name:
- _matherr
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _matherr
- matherr
helpviewer_keywords:
- _matherr function
- matherr function
ms.assetid: b600d66e-165a-4608-a856-8fb418d46760
ms.openlocfilehash: 340e3b8562e1f0f564810bc63cf6bd2e87ffdf63
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952761"
---
# <a name="_matherr"></a>_matherr

Обрабатывает математические ошибки.

## <a name="syntax"></a>Синтаксис

```C
int _matherr( struct _exception * except );
```

### <a name="parameters"></a>Параметры

*except*<br/>
Указатель на структуру, содержащую сведения об ошибке.

## <a name="return-value"></a>Возвращаемое значение

**_matherr** возвращает 0, чтобы указать ошибку, или ненулевое значение, указывающее на успешное выполнение. Если **_matherr** возвращает 0, может отобразиться сообщение об ошибке, **а для** свойства "вывод" задано соответствующее значение ошибки. Если **_matherr** возвращает ненулевое значение, сообщение об ошибке не отображается, а переводится в **неизменном** виде.

Дополнительные сведения об этом и других кодах возврата см. в статье [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Примечания

Функция **_matherr** обрабатывает ошибки, создаваемые функциями с плавающей запятой математических библиотек. Эти функции вызывают **_matherr** при обнаружении ошибки.

Для специальной обработки ошибок можно указать другое определение **_matherr**. При использовании динамически связанной версии библиотеки времени выполнения C (CRT) можно заменить подпрограмму **_matherr** по умолчанию в клиентском исполняемом файле, используя определенную пользователем версию. Однако нельзя заменить подпрограммы **_matherr** по умолчанию в клиенте DLL библиотеки DLL CRT.

При возникновении ошибки в математических подпрограммых **_matherr** вызывается с указателем на структуру типа **_exception** (определенную \<в Math.h >) в качестве аргумента. Структура **_exception** содержит следующие элементы.

```C
struct _exception
{
    int    type;   // exception type - see below
    char*  name;   // name of function where error occurred
    double arg1;   // first argument to function
    double arg2;   // second argument (if any) to function
    double retval; // value to be returned by function
};
```

Член **типа** указывает тип математической ошибки. Это одно из следующих значений, определенных в \<Math.h >:

|Макрос|Значение|
|-|-|
| **_DOMAIN** | Ошибка домена аргумента |
| **_SING** | Единственность аргумента |
| **_OVERFLOW** | Ошибка переполнения диапазона |
| **_PLOSS** | Частичная утрата значимости |
| **_TLOSS** | Общая потери значимости |
| **_UNDERFLOW** | Результат слишком мал для представления. (Данное условие в настоящий момент не поддерживается.) |

Элемент структуры**name** является указателем на строку, завершающуюся нуль-символом и содержащую имя функции, которая вызвала ошибку. Элементы структуры **arg1** и **arg2** определяют значения, вызвавшие ошибку. Если задан только один аргумент, он сохраняется в **arg1**.

Возвращаемое значение по умолчанию для данной ошибки равно **retval**. Если вы измените возвращаемое значение, оно должно определять, действительно ли произошла ошибка.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_matherr**|\<math.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_matherr.c
/* illustrates writing an error routine for math
* functions. The error function must be:
*      _matherr
*/

#include <math.h>
#include <string.h>
#include <stdio.h>

int main()
{
    /* Do several math operations that cause errors. The _matherr
     * routine handles _DOMAIN errors, but lets the system handle
     * other errors normally.
     */
    printf( "log( -2.0 ) = %e\n", log( -2.0 ) );
    printf( "log10( -5.0 ) = %e\n", log10( -5.0 ) );
    printf( "log( 0.0 ) = %e\n", log( 0.0 ) );
}

/* Handle several math errors caused by passing a negative argument
* to log or log10 (_DOMAIN errors). When this happens, _matherr
* returns the natural or base-10 logarithm of the absolute value
* of the argument and suppresses the usual error message.
*/
int _matherr( struct _exception *except )
{
    /* Handle _DOMAIN errors for log or log10. */
    if( except->type == _DOMAIN )
    {
        if( strcmp( except->name, "log" ) == 0 )
        {
            except->retval = log( -(except->arg1) );
            printf( "Special: using absolute value: %s: _DOMAIN "
                     "error\n", except->name );
            return 1;
        }
        else if( strcmp( except->name, "log10" ) == 0 )
        {
            except->retval = log10( -(except->arg1) );
            printf( "Special: using absolute value: %s: _DOMAIN "
                     "error\n", except->name );
            return 1;
        }
    }
    printf( "Normal: " );
    return 0;    /* Else use the default actions */
}
```

```Output
Special: using absolute value: log: _DOMAIN error
log( -2.0 ) = 6.931472e-01
Special: using absolute value: log10: _DOMAIN error
log10( -5.0 ) = 6.989700e-01
Normal: log( 0.0 ) = -inf
```

## <a name="see-also"></a>См. также

[Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)<br/>
