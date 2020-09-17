---
title: _alloca
ms.date: 11/04/2016
api_name:
- _alloca
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
- _alloca
- alloca
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
ms.openlocfilehash: 159f474927b4aaf364ad6972450edbe513a3c0b0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218745"
---
# <a name="_alloca"></a>_alloca

Выделение памяти в стеке. Эта функция является устаревшей, так как доступна более безопасная версия. см. [_malloca](malloca.md).

## <a name="syntax"></a>Синтаксис

```C
void *_alloca(
   size_t size
);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Байты, которые нужно выделить из стека.

## <a name="return-value"></a>Возвращаемое значение

**_Alloca** подпрограммы возвращает **`void`** указатель на выделенное пространство, которое гарантированно согласуется для хранения любого типа объекта. Если *Размер* равен 0, **_alloca** выделяет элемент нулевой длины и возвращает допустимый указатель на этот элемент.

Если выделить место в памяти невозможно, создается исключение переполнения стека. Исключение переполнения стека не является исключением C++; это структурированное исключение. Вместо использования обработки исключений C++ необходимо использовать [структурированную обработку исключений](../../cpp/structured-exception-handling-c-cpp.md) (SEH).

## <a name="remarks"></a>Примечания

**_alloca** выделяет байты *размера* из стека программы. Выделенное пространство автоматически освобождается при выходе из вызывающей функции (а не в том случае, если распределение просто выходит за пределы области). Поэтому не следует передавать значение указателя, возвращаемое **_alloca** , в качестве аргумента для [освобождения](free.md).

Существуют ограничения на явный вызов **_alloca** в обработчике исключений (EH). Подпрограммы обработки исключений, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции. Наиболее распространенные реализации включают выражения структурной обработки исключений (SEH) Windows NT и выражения catch языка C++. Таким образом, явный вызов **_alloca** в любом из следующих сценариев приводит к сбою программы во время возврата в вызывающую подпрограмму EH:

- Выражение фильтра исключений SEH Windows NT:`__except ( _alloca() )`

- Завершающий обработчик исключений Windows NT SEH:`__finally { _alloca() }`

- Выражение catch обработки исключений языка C++

Однако **_alloca** можно вызывать непосредственно из подпрограммы EH или из предоставленного приложением обратного вызова, который вызывается одним из сценариев EH, приведенных выше.

> [!IMPORTANT]
> В Windows XP, если **_alloca** вызывается внутри блока try/catch, необходимо вызвать [_resetstkoflw](resetstkoflw.md) в блоке catch.

В дополнение к указанным выше ограничениям при использовании параметра[/CLR (компиляция среды CLR)](../../build/reference/clr-common-language-runtime-compilation.md) **_alloca** нельзя использовать в **`__except`** блоках. Для получения дополнительной информации см. [/clr Restrictions](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_alloca**|\<malloc.h>|

## <a name="example"></a>Пример

```C
// crt_alloca.c
// This program demonstrates the use of
// _alloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size = 1000;
    int     errcode = 0;
    void    *pData = NULL;

    // Note: Do not use try/catch for _alloca,
    // use __try/__except, since _alloca throws
    // Structured Exceptions, not C++ exceptions.

    __try {
        // An unbounded _alloca can easily result in a
        // stack overflow.
        // Checking for a size < 1024 bytes is recommended.
        if (size > 0 && size < 1024)
        {
            pData = _alloca( size );
            printf_s( "Allocated %d bytes of stack at 0x%p",
                      size, pData);
        }
        else
        {
            printf_s("Tried to allocate too many bytes.\n");
        }
    }

    // If an exception occurred with the _alloca function
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_alloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf_s("Could not reset the stack!\n");
            _exit(1);
        }
    };
}
```

```Output
Allocated 1000 bytes of stack at 0x0012FB50
```

## <a name="see-also"></a>См. также раздел

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
[_malloca](malloca.md)<br/>
