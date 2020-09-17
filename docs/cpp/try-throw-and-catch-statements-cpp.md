---
title: Операторы try, throw и catch (C++)
ms.date: 11/04/2016
f1_keywords:
- catch_cpp
- try_cpp
- throw_cpp
helpviewer_keywords:
- catch keyword [C++]
- keywords [C++], exception handling
- C++ exception handling, statement syntax
- try-catch keyword [C++], about try-catch exception handling
- throw keyword [C++]
- try-catch keyword [C++]
- try-catch keyword [C++], exception handling
- throwing exceptions [C++], throw keyword
- try-catch keyword [C++], throw keyword [C++]s
- throwing exceptions [C++], implementing C++ exception handling
- throwing exceptions [C++]
- throw keyword [C++], throw() vs. throw(...)
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
ms.openlocfilehash: 4108d24b2c285b9d55d514dffae7b2efda1b3f86
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227066"
---
# <a name="try-throw-and-catch-statements-c"></a>Операторы try, throw и catch (C++)

Для реализации обработки исключений в C++ используются **`try`** **`throw`** выражения, и **`catch`** .

Во-первых, используйте **`try`** блок, чтобы заключить одну или несколько инструкций, которые могут вызвать исключение.

**`throw`** Выражение сигнализирует о том, что в блоке встречается исключительная ситуация — часто возникает ошибка **`try`** . В качестве операнда выражения можно использовать объект любого типа **`throw`** . Обычно этот объект используется для передачи информации об ошибке. В большинстве случаев рекомендуется использовать класс [std::exception](../standard-library/exception-class.md) или один из производных классов, определенных в стандартной библиотеке. Если один из них не подходит, рекомендуется создать собственный производный класс исключений из `std::exception`.

Чтобы обрабатывать исключения, которые могут быть вызваны, реализуйте один или несколько **`catch`** блоков сразу после **`try`** блока. Каждый **`catch`** блок указывает тип исключения, которое может быть обработано.

В этом примере показан **`try`** блок и его обработчики. Предположим, `GetNetworkResource()` получает данные через сетевое подключение, а 2 типа исключений являются определенными пользователем классами, производными от `std::exception`. Обратите внимание, что исключения перехватываются по **`const`** ссылке в **`catch`** инструкции. Рекомендуется создавать исключения по значению и захватывать их ссылкой константы.

## <a name="example"></a>Пример

```cpp
MyData md;
try {
   // Code that could throw an exception
   md = GetNetworkResource();
}
catch (const networkIOException& e) {
   // Code that executes when an exception of type
   // networkIOException is thrown in the try block
   // ...
   // Log error message in the exception object
   cerr << e.what();
}
catch (const myDataFormatException& e) {
   // Code that handles another exception type
   // ...
   cerr << e.what();
}

// The following syntax shows a throw expression
MyData GetNetworkResource()
{
   // ...
   if (IOSuccess == false)
      throw networkIOException("Unable to connect");
   // ...
   if (readError)
      throw myDataFormatException("Format error");
   // ...
}
```

## <a name="remarks"></a>Примечания

Код после **`try`** предложения является защищенным разделом кода. **`throw`** Выражение вызывает *,* то есть вызывает исключение. Блок кода после **`catch`** предложения является обработчиком исключений. Это обработчик, который *перехватывает* исключение, возникающее, если типы в **`throw`** **`catch`** выражениях и совместимы. Список правил, регулирующих сопоставление типов в **`catch`** блоках, см. в разделе [Вычисление блоков catch](../cpp/how-catch-blocks-are-evaluated-cpp.md). Если **`catch`** оператор задает многоточие (...) вместо типа, **`catch`** блок обрабатывает каждый тип исключения. При компиляции с параметром [/EHa](../build/reference/eh-exception-handling-model.md) они могут включать структурированные исключения C и созданные системой или асинхронные исключения, такие как защита памяти, деление на ноль и нарушения операций с плавающей запятой. Поскольку **`catch`** блоки обрабатываются в порядке программ для поиска соответствующего типа, обработчик многоточия должен быть последним обработчиком для связанного **`try`** блока. Используйте `catch(...)` осторожно, не позволяйте программе продолжать выполнение, если блоку catch не известно, как обработать конкретное перехваченное исключение. Как правило, блок `catch(...)` используется для ведения журнала ошибок и выполнения специальной очистки перед остановкой выполнения программы.

**`throw`** Выражение, не имеющее операнда, повторно создает исключение, которое сейчас обрабатывается. Рекомендуется использовать эту форму при повторном создании исключения, поскольку это позволяет сохранить исходные сведения полиморфного типа исключения. Такое выражение должно использоваться только в **`catch`** обработчике или в функции, которая вызывается из **`catch`** обработчика. Вновь созданный объект исключения представляет собой исходный объект исключения, а не его копию.

```cpp
try {
   throw CSomeOtherException();
}
catch(...) {
   // Catch all exceptions - dangerous!!!
   // Respond (perhaps only partially) to the exception, then
   // re-throw to pass the exception to some other handler
   // ...
   throw;
}
```

## <a name="see-also"></a>См. также статью

[Современные рекомендации по C++ для исключений и обработки ошибок](../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Необработанные исключения C++](../cpp/unhandled-cpp-exceptions.md)<br/>
[__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)
