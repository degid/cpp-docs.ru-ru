---
title: _malloca
ms.date: 11/04/2016
api_name:
- _malloca
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
- malloca
- _malloca
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
ms.openlocfilehash: d4604a6e2dfb00502e3c942c9735a077e1632843
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232499"
---
# <a name="_malloca"></a>_malloca

Выделение памяти в стеке. Это версия функции [_alloca](alloca.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
void *_malloca(
   size_t size
);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Байты, которые нужно выделить из стека.

## <a name="return-value"></a>Возвращаемое значение

**_Malloca** подпрограммы возвращает **`void`** указатель на выделенное пространство, которое гарантированно согласуется для хранения любого типа объекта. Если *Размер* равен 0, **_malloca** выделяет элемент нулевой длины и возвращает допустимый указатель на этот элемент.

Если *Размер* больше **_ALLOCA_S_THRESHOLD**, **_malloca** пытается выделить память в куче и возвращает пустой указатель, если пространство невозможно выделить. Если *Размер* меньше или равен **_ALLOCA_S_THRESHOLD**, **_malloca** пытается выделить значение в стеке, и создается исключение переполнения стека, если не удается выделить пространство. Исключение переполнения стека не является исключением C++; это структурированное исключение. Вместо использования обработки исключений C++ необходимо использовать [структурированную обработку исключений](../../cpp/structured-exception-handling-c-cpp.md) (SEH) для перехвата этого исключения.

## <a name="remarks"></a>Примечания

**_malloca** выделяет байты *размера* из стека программы или кучи, если запрос превышает определенный размер в байтах, заданный в **_ALLOCA_S_THRESHOLD**. Различие между **_malloca** и **_alloca** заключается в том, что **_alloca** всегда выделяется в стеке независимо от размера. В отличие от **_alloca**, в которых не требуется или не разрешен вызов **для освобождения** памяти, чтобы освободить память, **_malloca** требует использования [_freea](freea.md) для освобождения памяти. В режиме отладки **_malloca** всегда выделяет память из кучи.

Существуют ограничения на явный вызов **_malloca** в обработчике исключений (EH). Подпрограммы обработки исключений, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции. Наиболее распространенные реализации включают выражения структурной обработки исключений (SEH) Windows NT и выражения catch языка C++. Таким образом, явный вызов **_malloca** в любом из следующих сценариев приводит к сбою программы во время возврата в вызывающую подпрограмму EH:

- Выражение фильтра исключений SEH Windows NT: **`__except`** ( `_malloca ()` )

- Завершающий обработчик исключений Windows NT SEH: **`__finally`** { `_malloca ()` }

- Выражение catch обработки исключений языка C++

Однако **_malloca** можно вызывать непосредственно из подпрограммы EH или из предоставленного приложением обратного вызова, который вызывается одним из сценариев EH, приведенных выше.

> [!IMPORTANT]
> В Windows XP, если **_malloca** вызывается внутри блока try/catch, необходимо вызвать [_resetstkoflw](resetstkoflw.md) в блоке catch.

В дополнение к указанным выше ограничениям при использовании параметра [/CLR (компиляция среды CLR)](../../build/reference/clr-common-language-runtime-compilation.md) **_malloca** нельзя использовать в **`__except`** блоках. Для получения дополнительной информации см. [/clr Restrictions](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_malloca**|\<malloc.h>|

## <a name="example"></a>Пример

```C
// crt_malloca_simple.c
#include <stdio.h>
#include <malloc.h>

void Fn()
{
   char * buf = (char *)_malloca( 100 );
   // do something with buf
   _freea( buf );
}

int main()
{
   Fn();
}
```

## <a name="example"></a>Пример

```C
// crt_malloca_exception.c
// This program demonstrates the use of
// _malloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size;
    int     numberRead = 0;
    int     errcode = 0;
    void    *p = NULL;
    void    *pMarker = NULL;

    while (numberRead == 0)
    {
        printf_s("Enter the number of bytes to allocate "
                 "using _malloca: ");
        numberRead = scanf_s("%d", &size);
    }

    // Do not use try/catch for _malloca,
    // use __try/__except, since _malloca throws
    // Structured Exceptions, not C++ exceptions.

    __try
    {
        if (size > 0)
        {
            p =  _malloca( size );
        }
        else
        {
            printf_s("Size must be a positive number.");
        }
        _freea( p );
    }

    // Catch any exceptions that may occur.
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_malloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf("Could not reset the stack!");
            _exit(1);
        }
    };
}
```

### <a name="input"></a>Входные данные

```Input
1000
```

### <a name="sample-output"></a>Пример выходных данных

```Output
Enter the number of bytes to allocate using _malloca: 1000
```

## <a name="see-also"></a>См. также раздел

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
