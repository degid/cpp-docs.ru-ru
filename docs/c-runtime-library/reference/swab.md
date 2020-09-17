---
title: _swab
ms.date: 4/2/2020
api_name:
- _swab
- stdlib/_swab
- _o__swab
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
- api-ms-win-crt-utility-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _swab
- stdlib/_swab
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
ms.openlocfilehash: 7353081fab92fcc3324a214688be28a4f651b05f
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912415"
---
# <a name="_swab"></a>_swab

Меняет местами байты.

## <a name="syntax"></a>Синтаксис

```C
void _swab(
   char *src,
   char *dest,
   int n
);
```

## <a name="parameters"></a>Параметры

*src*<br/>
Данные, которые следует скопировать и поменять местами.

*dest*<br/>
Место хранения для переставленных местами данных.

*n*<br/>
Число байтов, которые следует скопировать и поменять местами.

## <a name="return-value"></a>Возвращаемое значение

Функция **сваб** не возвращает значение. Функция задает значение **еинвал** **, если** указатель *src* или *dest* имеет значение null или *n* меньше нуля, и вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).

Дополнительные сведения об этих и других кодах возврата см. в статьях [_doserrno, пере_sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Примечания

Если *n* является четным, функция **_swab** копирует *n* байт из *src*, меняет местами каждую пару смежных байтов и сохраняет результат в *dest*. Если *n* является нечетным, **_swab** копирует и меняет местами первые *n*-1 байта *src*, а последний байт не копируется. Функция **_swab** обычно используется для подготовки двоичных данных для перемещения на компьютер, использующий другой порядок байтов.

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_swab**|C: \<stdlib.h> C++: \<cstdlib> или \<stdlib.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```C
// crt_swab.c

#include <stdlib.h>
#include <stdio.h>

char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";
char to[] =   "...........................";

int main()
{
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);
    _swab(from, to, sizeof(from));
    printf("After:  %s\n        %s\n\n", from, to);
}
```

```Output
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes
        ...........................

After:  BADCFEHGJILKNMPORQTSVUXWZY
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.
```

## <a name="see-also"></a>См. также раздел

[Манипуляция буфером](../../c-runtime-library/buffer-manipulation.md)<br/>
