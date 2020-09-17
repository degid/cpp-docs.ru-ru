---
title: va_arg, va_copy, va_end, va_start
ms.date: 11/04/2016
api_name:
- va_arg
- va_end
- va_copy
- va_start
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
- va_arg
- va_start
- va_list
- va_alist
- va_dcl
- va_copy
- va_end
helpviewer_keywords:
- variable argument lists, accessing
- va_start macro
- va_arg macro
- va_end macro
- arguments [C++], argument lists
- va_list macro
- va_dcl macro
- va_alist macro
- va_copy macro
ms.assetid: a700dbbd-bfe5-4077-87b6-3a07af74a907
ms.openlocfilehash: d35cf3aea99b7e832afb7d2a8e0aaa9d008226fa
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231290"
---
# <a name="va_arg-va_copy-va_end-va_start"></a>va_arg, va_copy, va_end, va_start

Обращается к списку с переменным количеством аргументов.

## <a name="syntax"></a>Синтаксис

```C
type va_arg(
   va_list arg_ptr,
   type
);
void va_copy(
   va_list dest,
   va_list src
); // (ISO C99 and later)
void va_end(
   va_list arg_ptr
);
void va_start(
   va_list arg_ptr,
   prev_param
); // (ANSI C89 and later)
void va_start(
   arg_ptr
);  // (deprecated Pre-ANSI C89 standardization version)
```

### <a name="parameters"></a>Параметры

*type*<br/>
Тип аргумента, который требуется извлечь.

*arg_ptr*<br/>
Указатель на список аргументов.

*dest*<br/>
Указатель на список аргументов, которые должны быть инициализированы из *src*

*src*<br/>
Указатель на инициализированный список аргументов для копирования в *dest*.

*prev_param*<br/>
Параметр, который предшествует первому необязательному аргументу.

## <a name="return-value"></a>Возвращаемое значение

**va_arg** возвращает текущий аргумент. **va_copy**, **va_start** и **va_end** не возвращают значения.

## <a name="remarks"></a>Примечания

Макросы **va_arg**, **va_copy**, **va_end**и **va_start** предоставляют переносимый способ доступа к аргументам функции, когда функция принимает переменное число аргументов. Предусмотрены две версии макросов: макросы, определенные в STDARG.H, соответствуют стандарту ISO C99; макросы, определенные в VARARGS.H, не рекомендуется использовать, но они сохранены для обратной совместимости с кодом, написанным до появления стандарта ANSI C89.

Эти макросы предполагают, что функции принимают фиксированное число обязательных аргументов, за которыми следует переменное число необязательных аргументов. Обязательные аргументы объявляются как обычные параметры для функции и доступ к ним возможен через имена параметров. Доступ к необязательным аргументам осуществляется через макросы в STDARG.H (или VARARGS.H для кода, написанного до появления стандарта ANSI C89), которые задают указатель на первый необязательный аргумент в списке аргументов, извлекают аргументы из списка и сбрасывают указатель после завершения обработки аргументов.

Стандартные макросы языка C, которые определены в STDARG.H, используются следующим образом:

- **va_start** задает *arg_ptr* первый необязательный аргумент в списке аргументов, передаваемых функции. Аргумент *arg_ptr* должен иметь тип **va_list** . Аргумент *prev_param* является именем обязательного параметра, который непосредственно предшествует первому необязательному аргументу в списке аргументов. Если *prev_param* объявляется с помощью класса хранилища Register, поведение макроса не определено. **va_start** необходимо использовать до первого использования **va_arg** .

- **va_arg** извлекает значение *типа* из расположения, которое задается *arg_ptr*, и увеличивает *arg_ptr* , чтобы указать следующий аргумент в списке, используя размер *типа* , чтобы определить, где начинается следующий аргумент. **va_arg** можно использовать любое количество раз в функции для получения аргументов из списка.

- **va_copy** создает копию списка аргументов в его текущем состоянии. Параметр *src* уже должен быть инициализирован с помощью **va_start**; возможно, он был обновлен с помощью вызовов **va_arg** , но не должен быть сброшен с **va_end**. Следующий аргумент, полученный **va_arg** из *dest* , совпадает со следующим аргументом, полученным из *src*.

- После получения всех аргументов **va_end** сбрасывает указатель на **null**. **va_end** необходимо вызывать в каждом списке аргументов, который инициализируется с помощью **va_start** или **va_copy** перед возвратом функции.

> [!NOTE]
> Макросы в VARARGS.H использовать не рекомендуется; они сохранены только для обратной совместимости с кодом, который написан до появления стандарта ANSI C89. Во всех остальных случаях используйте макросы из файла STDARGS.H.

При компилировании с параметром [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) программы, использующие эти макросы, могут давать непредвиденный результат из-за различий между собственной системой типов и системой типов среды CLR. Рассмотрим следующую программу:

```C
#include <stdio.h>
#include <stdarg.h>

void testit (int i, ...)
{
    va_list argptr;
    va_start(argptr, i);

    if (i == 0)
    {
        int n = va_arg(argptr, int);
        printf("%d\n", n);
    }
    else
    {
        char *s = va_arg(argptr, char*);
        printf("%s\n", s);
    }

    va_end(argptr);
}

int main()
{
    testit(0, 0xFFFFFFFF); // 1st problem: 0xffffffff is not an int
    testit(1, NULL);       // 2nd problem: NULL is not a char*
}
```

Обратите внимание, что **тестит** принимает второй параметр как **`int`** или **`char*`** . Передаваемые аргументы: 0xFFFFFFFF ( **`unsigned int`** , Not **`int`** ) и **null** (фактически **`int`** , а не **`char*`** ). Когда программа скомпилирована для неуправляемого кода, она дает следующий результат:

```Output
-1

(null)
```

## <a name="requirements"></a>Требования

**Заголовок:** \<stdio.h> перетаскивани\<stdarg.h>

**Нерекомендуемый заголовок:**\<varargs.h>

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

```C
// crt_va.c
// Compile with: cl /W3 /Tc crt_va.c
// The program below illustrates passing a variable
// number of arguments using the following macros:
//      va_start            va_arg              va_copy
//      va_end              va_list

#include <stdio.h>
#include <stdarg.h>
#include <math.h>

double deviation(int first, ...);

int main( void )
{
    /* Call with 3 integers (-1 is used as terminator). */
    printf("Deviation is: %f\n", deviation(2, 3, 4, -1 ));

    /* Call with 4 integers. */
    printf("Deviation is: %f\n", deviation(5, 7, 9, 11, -1));

    /* Call with just -1 terminator. */
    printf("Deviation is: %f\n", deviation(-1));
}

/* Returns the standard deviation of a variable list of integers. */
double deviation(int first, ...)
{
    int count = 0, i = first;
    double mean = 0.0, sum = 0.0;
    va_list marker;
    va_list copy;

    va_start(marker, first);     /* Initialize variable arguments. */
    va_copy(copy, marker);       /* Copy list for the second pass */
    while (i != -1)
    {
        sum += i;
        count++;
        i = va_arg(marker, int);
    }
    va_end(marker);              /* Reset variable argument list. */
    mean = sum ? (sum / count) : 0.0;

    i = first;                  /* reset to calculate deviation */
    sum = 0.0;
    while (i != -1)
    {
        sum += (i - mean)*(i - mean);
        i = va_arg(copy, int);
    }
    va_end(copy);               /* Reset copy of argument list. */
    return count ? sqrt(sum / count) : 0.0;
}
```

```Output
Deviation is: 0.816497
Deviation is: 2.236068
Deviation is: 0.000000
```

## <a name="see-also"></a>См. также раздел

[Доступ к аргументам](../../c-runtime-library/argument-access.md)<br/>
[vfprintf, _vfprintf_l, vfwprintf, _vfwprintf_l](vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)<br/>
