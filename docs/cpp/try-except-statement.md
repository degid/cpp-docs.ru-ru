---
title: Оператор try-except
description: Справочник по Microsoft C++ к __try и __except структурированным операторам обработки исключений.
ms.date: 08/25/2020
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- _exception_info
- __except
- _except
- _exception_code
- __except_cpp
- _exception_info_cpp
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
ms.openlocfilehash: 226c3a3df39f284d9c1267051114fc39db358f55
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898615"
---
# <a name="try-except-statement"></a>инструкция `try-except`

`try-except`Оператор — это расширение для **Microsoft** , которое поддерживает структурированную обработку исключений в языках C и C++.

```cpp
    // . . .
    __try {
        // guarded code
    }
    __except ( /* filter expression */ ) {
        // termination code
    }
    // . . .
```

## <a name="grammar"></a>Грамматика

> *`try-except-statement`*:\
> &emsp;**`__try`** *`compound-statement`* **`__except (`**  *`expression`*  **`)`** *`compound-statement`*

## <a name="remarks"></a>Примечания

`try-except`Оператор является расширением Microsoft для языков C и C++. Она позволяет целевым приложениям получать контроль над возникновением событий, которые обычно завершают выполнение программы. Такие события называются *структурированными исключениями*или *исключениями* для коротких. Механизм, который обрабатывает эти исключения, называется *структурной обработкой исключений* (SEH).

Связанные сведения см. в описании [оператора try-finally](../cpp/try-finally-statement.md).

Исключения могут быть основаны на оборудовании или программном обеспечении. Структурированная обработка исключений полезна даже в том случае, когда приложения не могут полностью восстанавливаться после исключений оборудования или программного обеспечения. SEH позволяет отображать сведения об ошибках и захватывать внутреннее состояние приложения, чтобы помочь в диагностике проблемы. Это особенно полезно для периодических проблем, которые не очень просты в воспроизведении.

> [!NOTE]
> Структурированная обработка исключений поддерживается в Win32 для исходных файлов как на C, так и на C++. Однако он не предназначен специально для C++. Для того чтобы ваш код лучше переносился, лучше использовать механизм обработки исключений языка C++. Кроме того, этот механизм отличается большей гибкостью, поскольку может обрабатывать исключения любого типа. Для программ на C++ рекомендуется использовать собственные операторы обработки исключений C++: [try, catch и Throw](../cpp/try-throw-and-catch-statements-cpp.md) .

Составной оператор после **`__try`** предложения — *тело* или *защищенный* раздел. **`__except`** Выражение также называется критерием *фильтра* . Его значение определяет, как обрабатываются исключения. Составной оператор после предложения **`__except`** является обработчиком исключения. Обработчик задает действия, выполняемые при возникновении исключения во время выполнения раздела body. Выполнение происходит следующим образом:

1. Сначала выполняется защищенный раздел.

1. Если исключение при этом не возникает, выполнение переходит в инструкцию, стоящую после предложения **`__except`** .

1. Если во время выполнения защищенного раздела возникает исключение или в любой подпрограмме вызывается защищенный раздел, **`__except`** выражение вычисляется. Возможны три значения.

   - `EXCEPTION_CONTINUE_EXECUTION` (-1) Исключение закрыто. Выполнение продолжается в точке, в которой возникло исключение.

   - `EXCEPTION_CONTINUE_SEARCH` (0) исключение не распознано. Продолжайте выполнять поиск обработчика в стеке, сначала для содержащихся `try-except` инструкций, а затем для обработчиков со следующим высшим приоритетом.

   - `EXCEPTION_EXECUTE_HANDLER` (1) распознано исключение. Передайте управление обработчику исключений, выполнив **`__except`** составной оператор, а затем продолжайте выполнение после **`__except`** блока.

**`__except`** Выражение вычисляется как выражение C. Оно ограничено одним значением, оператором условного выражения или оператором-запятой. Если требуется более сложная обработка, выражение может вызывать процедуру, которая возвращает одно из этих трех значений.

Каждое приложение может иметь свой собственный обработчик исключений.

Не допускается переход к **`__try`** оператору, но он допустим для перехода из одной инструкции. Обработчик исключений не вызывается, если процесс завершается в процессе выполнения `try-except` инструкции.

Для совместимости с предыдущими версиями **_try**, **_except**и **_leave** являются синонимами для **`__try`** , **`__except`** и, если не **`__leave`** задан параметр компилятора [/Za \( Отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

### <a name="the-__leave-keyword"></a><a name="__leave"></a>`__leave`Ключевое слово

**`__leave`** Ключевое слово допустимо только в защищенном разделе `try-except` оператора, и его результат — переход к концу защищенного раздела. Выполнение продолжается с первого оператора, следующего за обработчиком исключений.

**`goto`** Оператор также может перейти из защищенного раздела и не снизит производительность, как это делается в операторе **try-finally** . Это связано с тем, что очистка стека не происходит. Однако рекомендуется использовать **`__leave`** ключевое слово, а не **`goto`** оператор. Причина заключается в том, что вы менее вероятно намерены создать ошибку программирования, если защищенный раздел большой или сложный.

### <a name="structured-exception-handling-intrinsic-functions"></a>Встроенные функции обработки структурированных исключений

Структурированная обработка исключений предоставляет две встроенные функции, которые можно использовать с `try-except` инструкцией: [GetExceptionCode](/windows/win32/Debug/getexceptioncode) и [жетексцептионинформатион](/windows/win32/Debug/getexceptioninformation).

`GetExceptionCode` Возвращает код (32-разрядное целое число) исключения.

Встроенная функция `GetExceptionInformation` возвращает указатель на структуру [EXCEPTION_POINTERS](/windows/win32/api/winnt/ns-winnt-exception_pointers) , содержащую дополнительные сведения об исключении. Через этот указатель можно обращаться к состоянию компьютера, которое существовало в момент возникновения аппаратного исключения. Его структура выглядит следующим образом.

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

Типы указателей `PEXCEPTION_RECORD` и определяются `PCONTEXT` в включаемом файле \<winnt.h> и `_EXCEPTION_RECORD` `_CONTEXT` определяются в включаемом файле. \<excpt.h>

Можно использовать `GetExceptionCode` в обработчике исключений. Однако можно использовать `GetExceptionInformation` только в пределах выражения фильтра исключений. Информация, на которую он указывает, обычно находится в стеке и больше недоступна при передаче управления в обработчик исключений.

Встроенная функция [абнормалтерминатион](/windows/win32/Debug/abnormaltermination) доступна в обработчике завершения. Он возвращает 0, если тело оператора **try-finally** завершается последовательно. В остальных случаях функция возвращает 1.

\<excpt.h> определяет некоторые альтернативные имена для этих встроенных функций:

`GetExceptionCode` — это эквивалент `_exception_code`

`GetExceptionInformation` — это эквивалент `_exception_info`

`AbnormalTermination` — это эквивалент `_abnormal_termination`

## <a name="example"></a>Пример

```cpp
// exceptions_try_except_Statement.cpp
// Example of try-except and try-finally statements
#include <stdio.h>
#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION
#include <excpt.h>

int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep)
{
    puts("in filter.");
    if (code == EXCEPTION_ACCESS_VIOLATION)
    {
        puts("caught AV as expected.");
        return EXCEPTION_EXECUTE_HANDLER;
    }
    else
    {
        puts("didn't catch AV, unexpected.");
        return EXCEPTION_CONTINUE_SEARCH;
    };
}

int main()
{
    int* p = 0x00000000;   // pointer to NULL
    puts("hello");
    __try
    {
        puts("in try");
        __try
        {
            puts("in try");
            *p = 13;    // causes an access violation exception;
        }
        __finally
        {
            puts("in finally. termination: ");
            puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");
        }
    }
    __except(filter(GetExceptionCode(), GetExceptionInformation()))
    {
        puts("in except");
    }
    puts("world");
}
```

### <a name="output"></a>Вывод

```Output
hello
in try
in try
in filter.
caught AV as expected.
in finally. termination:
        abnormal
in except
world
```

## <a name="see-also"></a>См. также

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
