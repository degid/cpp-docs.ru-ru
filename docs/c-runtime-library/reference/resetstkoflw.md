---
title: _resetstkoflw
ms.date: 4/2/2020
api_name:
- _resetstkoflw
- _o__resetstkoflw
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- resetstkoflw
- _resetstkoflw
helpviewer_keywords:
- resetstkoflw function
- stack overflow
- stack, recovering
- _resetstkoflw function
ms.assetid: 319529cd-4306-4d22-810b-2063f3ad9e14
ms.openlocfilehash: 6f4d5d930ebdc487c3c2bcc2f93494a25528c438
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216782"
---
# <a name="_resetstkoflw"></a>_resetstkoflw

Выполняет восстановление после переполнения стека.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _resetstkoflw( void );
```

## <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция завершается успешно; в противном случае — ноль.

## <a name="remarks"></a>Примечания

Функция **_resetstkoflw** восстанавливается из состояния переполнения стека, что позволяет программе продолжать работу вместо сбоя с неустранимой ошибкой исключения. Если функция **_resetstkoflw** не вызывается, то после предыдущего исключения страницы защиты отсутствуют. При последующем переполнении стека исключений не будет, и процесс завершится без предупреждения.

Если поток в приложении вызывает исключение **EXCEPTION_STACK_OVERFLOW**, поток оставил свой стек в поврежденном состоянии. Этим данное исключение отличается от других исключений, таких как **EXCEPTION_ACCESS_VIOLATION** или **EXCEPTION_INT_DIVIDE_BY_ZERO**, при которых стек не повреждается. При первой загрузке программы для стека задается произвольная небольшая величина. Затем стек увеличивается по требованию, чтобы отвечать потребностям потока. Это реализуется путем размещения страницы с параметром доступа PAGE_GUARD в конце текущего стека. Дополнительные сведения см. в разделе [Creating Guard Pages](/windows/win32/Memory/creating-guard-pages).

Если код приводит к тому, что указатель стека указывает на адрес на этой странице, возникает исключение и система выполняет три указанных ниже действия.

- Удаляет защиту PAGE_GUARD на защитной странице, чтобы поток мог считывать и записывать данные в память.

- Создает новую защитную страницу, расположенную на одну страницу ниже последней.

- Повторно выполняет инструкцию, которая вызвала исключение.

Таким образом система может увеличивать размер стека для потока автоматически. Каждый поток в процессе имеет максимальный размер стека. Размер стека устанавливается во время компиляции оператором [/STACK (Выделения памяти в стеке)](../../build/reference/stack-stack-allocations.md) или [STACKSIZE](../../build/reference/stacksize.md) в DEF-файле проекта.

Если превышен максимальный размер стека, система выполняет три указанные ниже действия.

- Удаляет защиту PAGE_GUARD на защитной странице, как описано выше.

- Пытается выделить новую защитную страницу после последней. Однако это не удается, поскольку превышен максимальный размер стека.

- Создает исключение, чтобы поток смог его обработать в блоке исключения.

Обратите внимание, что в этот момент в стеке уже нет защитной страницы. В следующий раз, когда программа наращивает стек до его конца, где должна быть защитная страница, программа записывает за пределы стека и вызывает нарушение доступа.

Вызовите **_resetstkoflw** , чтобы восстановить страницу защиты, когда восстановление выполняется после исключения переполнения стека. Эта функция может быть вызвана внутри основного текста **`__except`** блока или за пределами **`__except`** блока. Однако существуют некоторые ограничения на момент ее использования. **_resetstkoflw** никогда не должны вызываться из:

- выражения фильтра;

- функции фильтра;

- функции, вызываемой из функции фильтра;

- **`catch`** Блок.

- **`__finally`** Блок.

На этих этапах стек еще недостаточно раскручен.

Исключения переполнения стека создаются как структурированные исключения, а не исключения C++, поэтому **_resetstkoflw** не используется в обычном **`catch`** блоке, так как не перехватывает исключение переполнения стека. Однако если функция [_set_se_translator](set-se-translator.md) используется для реализации преобразователя структурированного исключения, который генерирует исключения C++ (как во втором примере), исключение переполнения стека приводит к исключению C++, которое может быть обработано блоком catch C++.

Вызывать функцию **_resetstkoflw** в блоке catch C++, переход в который выполнен из исключения, созданного функцией преобразователя структурированного исключения, небезопасно. В этом случае пространство стека не освобождается и указатель стека не сбрасывается до выхода из блока catch, даже если были вызваны деструкторы всех разрушаемых объектов перед блоком catch. Эта функция не должна вызываться до освобождения пространства стека и сброса указателя стека. Следовательно, она должна вызываться только после выхода из блока catch. В блоке catch должно использоваться как можно меньшее пространство стека, так как невозможно восстановление после переполнения стека, возникшего в блоке catch, в котором производится попытка восстановления после предыдущего переполнения стека, что может стать причиной зависания программы, так как переполнение в блоке catch вызывает исключение, которое обрабатывается этим же блоком catch.

Существуют ситуации, когда **_resetstkoflw** могут завершиться сбоем, даже если они используются в правильном расположении, например в **`__except`** блоке. Если даже после очистки стека не хватает пространства стека для выполнения функции **_resetstkoflw** без записи в последнюю страницу стека, то функции **_resetstkoflw** не удается восстановить последнюю страницу стека как защитную и она возвращает 0, что указывает на сбой. Поэтому для безопасного использования этой функции необходимо проверять возвращаемое значение, а не предполагать, что стеком можно безопасно пользоваться.

Структурированная обработка исключений не будет перехватывать исключение **STATUS_STACK_OVERFLOW** при компиляции приложения с параметром **/CLR** (см. раздел [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md)).

По умолчанию глобальное состояние этой функции ограничивается приложением. Чтобы изменить это, см. раздел [глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_resetstkoflw**|\<malloc.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

**Библиотеки:** все версии [функций библиотеки CRT](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Пример

В следующем примере показано рекомендуемое использование функции **_resetstkoflw** .

```C
// crt_resetstkoflw.c
// Launch program with and without arguments to observe
// the difference made by calling _resetstkoflw.

#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void recursive(int recurse)
{
   _alloca(2000);
   if (recurse)
      recursive(recurse);
}

// Filter for the stack overflow exception.
// This function traps the stack overflow exception, but passes
// all other exceptions through.
int stack_overflow_exception_filter(int exception_code)
{
   if (exception_code == EXCEPTION_STACK_OVERFLOW)
   {
       // Do not call _resetstkoflw here, because
       // at this point, the stack is not yet unwound.
       // Instead, signal that the handler (the __except block)
       // is to be executed.
       return EXCEPTION_EXECUTE_HANDLER;
   }
   else
       return EXCEPTION_CONTINUE_SEARCH;
}

int main(int ac)
{
   int i = 0;
   int recurse = 1, result = 0;

   for (i = 0 ; i < 10 ; i++)
   {
      printf("loop #%d\n", i + 1);
      __try
      {
         recursive(recurse);

      }

      __except(stack_overflow_exception_filter(GetExceptionCode()))
      {
         // Here, it is safe to reset the stack.

         if (ac >= 2)
         {
            puts("resetting stack overflow");
            result = _resetstkoflw();
         }
      }

      // Terminate if _resetstkoflw failed (returned 0)
      if (!result)
         return 3;
   }

   return 0;
}
```

Пример выходных данных без аргументов программы:

```Output
loop #1
```

Программа перестает отвечать без выполнения дальнейших итераций.

С аргументами программы:

```Output
loop #1
resetting stack overflow
loop #2
resetting stack overflow
loop #3
resetting stack overflow
loop #4
resetting stack overflow
loop #5
resetting stack overflow
loop #6
resetting stack overflow
loop #7
resetting stack overflow
loop #8
resetting stack overflow
loop #9
resetting stack overflow
loop #10
resetting stack overflow
```

### <a name="description"></a>Описание

В следующем примере показано рекомендуемое использование **_resetstkoflw** в программе, в которой структурированные исключения преобразуются в исключения C++.

### <a name="code"></a>Код

```cpp
// crt_resetstkoflw2.cpp
// compile with: /EHa
// _set_se_translator requires the use of /EHa
#include <malloc.h>
#include <stdio.h>
#include <windows.h>
#include <eh.h>

class Exception { };

class StackOverflowException : Exception { };

// Because the overflow is deliberate, disable the warning that
// this function will cause a stack overflow.
#pragma warning (disable: 4717)
void CauseStackOverflow (int i)
{
    // Overflow the stack by allocating a large stack-based array
    // in a recursive function.
    int a[10000];
    printf("%d ", i);
    CauseStackOverflow (i + 1);
}

void __cdecl SEHTranslator (unsigned int code, _EXCEPTION_POINTERS*)
{
    // For stack overflow exceptions, throw our own C++
    // exception object.
    // For all other exceptions, throw a generic exception object.
    // Use minimal stack space in this function.
    // Do not call _resetstkoflw in this function.

    if (code == EXCEPTION_STACK_OVERFLOW)
        throw StackOverflowException ( );
    else
        throw Exception( );
}

int main ( )
{
    bool stack_reset = false;
    bool result = false;

    // Set up a function to handle all structured exceptions,
    // including stack overflow exceptions.
    _set_se_translator (SEHTranslator);

    try
    {
        CauseStackOverflow (0);
    }
    catch (StackOverflowException except)
    {
        // Use minimal stack space here.
        // Do not call _resetstkoflw here.
        printf("\nStack overflow!\n");
        stack_reset = true;
    }
    catch (Exception except)
    {
        // Do not call _resetstkoflw here.
        printf("\nUnknown Exception!\n");
    }
    if (stack_reset)
    {
        result = _resetstkoflw();
        // If stack reset failed, terminate the application.
        if (result == 0)
            exit(1);
    }

    void* pv = _alloca(100000);
    printf("Recovered from stack overflow and allocated 100,000 bytes"
           " using _alloca.");

    return 0;
}
```

```Output
0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24
Stack overflow!
Recovered from stack overflow and allocated 100,000 bytes using _alloca.
```

## <a name="see-also"></a>См. также раздел

[_alloca](alloca.md)<br/>
