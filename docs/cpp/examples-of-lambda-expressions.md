---
title: Примеры лямбда-выражений
ms.date: 05/07/2019
helpviewer_keywords:
- lambda expressions [C++], examples
ms.assetid: 52506b15-0771-4190-a966-2f302049ca86
ms.openlocfilehash: 585e76119b0e848e322c88ad0149ebb42c6b5b1d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221605"
---
# <a name="examples-of-lambda-expressions"></a>Примеры лямбда-выражений

В данной статье приводится описание методов использования лямбда-выражений в программах. Общие сведения о лямбда-выражениях см. в разделе [лямбда-выражения](../cpp/lambda-expressions-in-cpp.md). Дополнительные сведения о структуре лямбда-выражения см. в разделе [синтаксис лямбда-выражения](../cpp/lambda-expression-syntax.md).

## <a name="declaring-lambda-expressions"></a><a name="declaringLambdaExpressions"></a>Объявление лямбда-выражений

### <a name="example-1"></a>Пример 1

Поскольку лямбда-выражение типизировано, его можно назначить **`auto`** переменной или [`function`](../standard-library/function-class.md) объекту, как показано ниже:

### <a name="code"></a>Код

```cpp
// declaring_lambda_expressions1.cpp
// compile with: /EHsc /W4
#include <functional>
#include <iostream>

int main()
{

    using namespace std;

    // Assign the lambda expression that adds two numbers to an auto variable.
    auto f1 = [](int x, int y) { return x + y; };

    cout << f1(2, 3) << endl;

    // Assign the same lambda expression to a function object.
    function<int(int, int)> f2 = [](int x, int y) { return x + y; };

    cout << f2(3, 4) << endl;
}
```

### <a name="output"></a>Выходные данные

```Output
5
7
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [`auto`](../cpp/auto-cpp.md) , [ `function` класс](../standard-library/function-class.md)и [вызов функции](../cpp/function-call-cpp.md).

Хотя лямбда-выражения чаще всего объявляются в теле функции, можно объявлять их в любом месте, где можно инициализировать переменные.

### <a name="example-2"></a>Пример 2

Компилятор Microsoft C++ привязывает лямбда-выражение к захваченным переменным при объявлении выражения, а не при вызове выражения. В следующем примере содержится лямбда-выражение, которое фиксирует локальную переменную `i` по значению, а локальную переменную `j` — по ссылке. Поскольку лямбда-выражение захватывает `i` по значению, переопределение `i` далее в программе не влияет на результат выражения. Однако, поскольку лямбда-выражение захватывает `j` по ссылке, переопределение `j` влияет на результат выражения.

### <a name="code"></a>Код

```cpp
// declaring_lambda_expressions2.cpp
// compile with: /EHsc /W4
#include <functional>
#include <iostream>

int main()
{
   using namespace std;

   int i = 3;
   int j = 5;

   // The following lambda expression captures i by value and
   // j by reference.
   function<int (void)> f = [i, &j] { return i + j; };

   // Change the values of i and j.
   i = 22;
   j = 44;

   // Call f and print its result.
   cout << f() << endl;
}
```

### <a name="output"></a>Выходные данные

```Output
47
```

[[В этой статье](#top)]

## <a name="calling-lambda-expressions"></a><a name="callingLambdaExpressions"></a>Вызов лямбда-выражений

Можно вызывать лямбда-выражение сразу же, как показано в следующем фрагменте кода. Во втором фрагменте показано, как передать лямбда-выражение в качестве аргумента в алгоритмы стандартной библиотеки C++, такие как `find_if` .

### <a name="example-1"></a>Пример 1

В этом примере объявляется лямбда-выражение, которое возвращает сумму двух целых чисел и сразу же вызывает выражение с аргументами `5` и `4`.

### <a name="code"></a>Код

```cpp
// calling_lambda_expressions1.cpp
// compile with: /EHsc
#include <iostream>

int main()
{
   using namespace std;
   int n = [] (int x, int y) { return x + y; }(5, 4);
   cout << n << endl;
}
```

### <a name="output"></a>Выходные данные

```Output
9
```

### <a name="example-2"></a>Пример 2

В этом примере лямбда-выражение передается в качестве аргумента функции `find_if`. Лямбда-выражение возвращает значение, **`true`** если его параметр имеет четное число.

### <a name="code"></a>Код

```cpp
// calling_lambda_expressions2.cpp
// compile with: /EHsc /W4
#include <list>
#include <algorithm>
#include <iostream>

int main()
{
    using namespace std;

    // Create a list of integers with a few initial elements.
    list<int> numbers;
    numbers.push_back(13);
    numbers.push_back(17);
    numbers.push_back(42);
    numbers.push_back(46);
    numbers.push_back(99);

    // Use the find_if function and a lambda expression to find the
    // first even number in the list.
    const list<int>::const_iterator result =
        find_if(numbers.begin(), numbers.end(),[](int n) { return (n % 2) == 0; });

    // Print the result.
    if (result != numbers.end()) {
        cout << "The first even number in the list is " << *result << "." << endl;
    } else {
        cout << "The list contains no even numbers." << endl;
    }
}
```

### <a name="output"></a>Выходные данные

```Output
The first even number in the list is 42.
```

### <a name="remarks"></a>Примечания

Дополнительные сведения о `find_if` функции см. в разделе [`find_if`](../standard-library/algorithm-functions.md#find_if) . Дополнительные сведения о функциях стандартной библиотеки C++, которые выполняют стандартные алгоритмы, см. в разделе [`<algorithm>`](../standard-library/algorithm.md) .

[[В этой статье](#top)]

## <a name="nesting-lambda-expressions"></a><a name="nestingLambdaExpressions"></a>Вложенные лямбда-выражения

### <a name="example"></a>Пример

Можно вложить одно лямбда-выражение в другое, как показано в следующем примере. Внутреннее лямбда-выражение умножает его аргумент на 2 и возвращает результат. Внешнее лямбда-выражение вызывает внутреннее лямбда-выражение с использованием его аргумента и добавляет к результату 3.

### <a name="code"></a>Код

```cpp
// nesting_lambda_expressions.cpp
// compile with: /EHsc /W4
#include <iostream>

int main()
{
    using namespace std;

    // The following lambda expression contains a nested lambda
    // expression.
    int timestwoplusthree = [](int x) { return [](int y) { return y * 2; }(x) + 3; }(5);

    // Print the result.
    cout << timestwoplusthree << endl;
}
```

### <a name="output"></a>Выходные данные

```Output
13
```

### <a name="remarks"></a>Примечания

В этом примере значение параметра `[](int y) { return y * 2; }` является вложенным лямбда-выражением.

[[В этой статье](#top)]

## <a name="higher-order-lambda-functions"></a><a name="higherOrderLambdaExpressions"></a>Лямбда-функции высшего порядка

### <a name="example"></a>Пример

Многие языки программирования поддерживают концепцию *функции более высокого порядка.* Функция высшего порядка представляет собой лямбда-выражение, которое принимает другое лямбда-выражение в качестве аргумента или возвращает лямбда-выражение. Класс можно использовать, [`function`](../standard-library/function-class.md) чтобы разрешить лямбда-выражение C++ работать как функция высшего порядка. В следующем примере показано лямбда-выражение, которое возвращает объект `function`, и лямбда-выражение, которое принимает объект `function` в качестве аргумента.

### <a name="code"></a>Код

```cpp
// higher_order_lambda_expression.cpp
// compile with: /EHsc /W4
#include <iostream>
#include <functional>

int main()
{
    using namespace std;

    // The following code declares a lambda expression that returns
    // another lambda expression that adds two numbers.
    // The returned lambda expression captures parameter x by value.
    auto addtwointegers = [](int x) -> function<int(int)> {
        return [=](int y) { return x + y; };
    };

    // The following code declares a lambda expression that takes another
    // lambda expression as its argument.
    // The lambda expression applies the argument z to the function f
    // and multiplies by 2.
    auto higherorder = [](const function<int(int)>& f, int z) {
        return f(z) * 2;
    };

    // Call the lambda expression that is bound to higherorder.
    auto answer = higherorder(addtwointegers(7), 8);

    // Print the result, which is (7+8)*2.
    cout << answer << endl;
}
```

### <a name="output"></a>Выходные данные

```Output
30
```

[[В этой статье](#top)]

## <a name="using-a-lambda-expression-in-a-function"></a><a name="methodLambdaExpressions"></a>Использование лямбда-выражения в функции

### <a name="example"></a>Пример

Лямбда-выражения можно использовать в теле функции. Лямбда-выражение может получать доступ к любой функции или данным-членам, которые способна использовать включающая функция. Можно явно или неявно захватывать указатель, **`this`** чтобы предоставить доступ к функциям и элементам данных включающего класса.
**Visual Studio 2017 версии 15,3 и более поздних версий** (доступно с [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): захват **`this`** по значению ( `[*this]` ), если лямбда-выражение будет использоваться в асинхронных или параллельных операциях, где код может быть выполнен после того, как исходный объект выходит из области действия.

Указатель можно использовать **`this`** явно в функции, как показано ниже:

```cpp
// capture "this" by reference
void ApplyScale(const vector<int>& v) const
{
   for_each(v.begin(), v.end(),
      [this](int n) { cout << n * _scale << endl; });
}

// capture "this" by value (Visual Studio 2017 version 15.3 and later)
void ApplyScale2(const vector<int>& v) const
{
   for_each(v.begin(), v.end(),
      [*this](int n) { cout << n * _scale << endl; });
}
```

Кроме того, указатель можно захватывать **`this`** неявно:

```cpp
void ApplyScale(const vector<int>& v) const
{
   for_each(v.begin(), v.end(),
      [=](int n) { cout << n * _scale << endl; });
}
```

В следующем примере показан класс `Scale`, который инкапсулирует значение масштаба.

```cpp
// function_lambda_expression.cpp
// compile with: /EHsc /W4
#include <algorithm>
#include <iostream>
#include <vector>

using namespace std;

class Scale
{
public:
    // The constructor.
    explicit Scale(int scale) : _scale(scale) {}

    // Prints the product of each element in a vector object
    // and the scale value to the console.
    void ApplyScale(const vector<int>& v) const
    {
        for_each(v.begin(), v.end(), [=](int n) { cout << n * _scale << endl; });
    }

private:
    int _scale;
};

int main()
{
    vector<int> values;
    values.push_back(1);
    values.push_back(2);
    values.push_back(3);
    values.push_back(4);

    // Create a Scale object that scales elements by 3 and apply
    // it to the vector object. Does not modify the vector.
    Scale s(3);
    s.ApplyScale(values);
}
```

### <a name="output"></a>Выходные данные

```Output
3
6
9
12
```

### <a name="remarks"></a>Примечания

Функция `ApplyScale` использует лямбда-выражение для выведения произведения масштаба на каждый элемент объекта `vector`. Лямбда-выражение неявно захватывает, **`this`** чтобы он мог получить доступ к `_scale` элементу.

[[В этой статье](#top)]

## <a name="using-lambda-expressions-with-templates"></a><a name="templateLambdaExpressions"></a>Использование лямбда-выражений с шаблонами

### <a name="example"></a>Пример

Поскольку лямбда-выражения имеют тип, их можно использовать с шаблонами C++. В следующем примере показаны функции `negate_all` и `print_all`. `negate_all`Функция применяет унарный **`operator-`** к каждому элементу в `vector` объекте. Функция `print_all` печатает каждый элемент в объекте `vector` в консоли.

### <a name="code"></a>Код

```cpp
// template_lambda_expression.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <iostream>

using namespace std;

// Negates each element in the vector object. Assumes signed data type.
template <typename T>
void negate_all(vector<T>& v)
{
    for_each(v.begin(), v.end(), [](T& n) { n = -n; });
}

// Prints to the console each element in the vector object.
template <typename T>
void print_all(const vector<T>& v)
{
    for_each(v.begin(), v.end(), [](const T& n) { cout << n << endl; });
}

int main()
{
    // Create a vector of signed integers with a few elements.
    vector<int> v;
    v.push_back(34);
    v.push_back(-43);
    v.push_back(56);

    print_all(v);
    negate_all(v);
    cout << "After negate_all():" << endl;
    print_all(v);
}
```

### <a name="output"></a>Выходные данные

```Output
34
-43
56
After negate_all():
-34
43
-56
```

### <a name="remarks"></a>Примечания

Дополнительные сведения о шаблонах C++ см. в разделе [шаблоны](../cpp/templates-cpp.md).

[[В этой статье](#top)]

## <a name="handling-exceptions"></a><a name="ehLambdaExpressions"></a>Обработка исключений

### <a name="example"></a>Пример

Тело лямбда-выражения выполняет правила как для структурированной обработки исключений (SEH), так и для обработки исключений C++. Можно обработать возникшее исключение в теле лямбда-выражения или перенести обработку исключения во включающий фрагмент. В следующем примере используется **`for_each`** функция и лямбда-выражение для заполнения `vector` объекта значениями другого. Он использует **`try`** / **`catch`** блок для управления недопустимым доступом к первому вектору.

### <a name="code"></a>Код

```cpp
// eh_lambda_expression.cpp
// compile with: /EHsc /W4
#include <vector>
#include <algorithm>
#include <iostream>
using namespace std;

int main()
{
    // Create a vector that contains 3 elements.
    vector<int> elements(3);

    // Create another vector that contains index values.
    vector<int> indices(3);
    indices[0] = 0;
    indices[1] = -1; // This is not a valid subscript. It will trigger an exception.
    indices[2] = 2;

    // Use the values from the vector of index values to
    // fill the elements vector. This example uses a
    // try/catch block to handle invalid access to the
    // elements vector.
    try
    {
        for_each(indices.begin(), indices.end(), [&](int index) {
            elements.at(index) = index;
        });
    }
    catch (const out_of_range& e)
    {
        cerr << "Caught '" << e.what() << "'." << endl;
    };
}
```

### <a name="output"></a>Выходные данные

```Output
Caught 'invalid vector<T> subscript'.
```

### <a name="remarks"></a>Примечания

Дополнительные сведения об обработке исключений см. в разделе [обработка исключений](../cpp/exception-handling-in-visual-cpp.md).

[[В этой статье](#top)]

## <a name="using-lambda-expressions-with-managed-types-ccli"></a><a name="managedLambdaExpressions"></a>Использование лямбда-выражений с управляемыми типами (C++/CLI)

### <a name="example"></a>Пример

Предложение захвата лямбда-выражения не может содержать переменную, которая имеет управляемый тип. Однако можно передать аргумент с управляемым типом в список параметров лямбда-выражения. В следующем примере содержится лямбда-выражение, которое захватывает локальную неуправляемую переменную `ch` по значению и принимает объект <xref:System.String?displayProperty=fullName> в качестве параметра.

### <a name="code"></a>Код

```cpp
// managed_lambda_expression.cpp
// compile with: /clr
using namespace System;

int main()
{
    char ch = '!'; // a local unmanaged variable

    // The following lambda expression captures local variables
    // by value and takes a managed String object as its parameter.
    [=](String ^s) {
        Console::WriteLine(s + Convert::ToChar(ch));
    }("Hello");
}
```

### <a name="output"></a>Выходные данные

```Output
Hello!
```

### <a name="remarks"></a>Примечания

Можно также использовать лямбда-выражения с библиотекой STL/CLR. Дополнительные сведения см. в разделе [Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md).

> [!IMPORTANT]
> Лямбда-выражения не поддерживаются в следующих управляемых сущностях среды CLR: **`ref class`** , **`ref struct`** , **`value class`** и **`value struct`** .

[[В этой статье](#top)]

## <a name="see-also"></a>См. также раздел

[Лямбда-выражения](../cpp/lambda-expressions-in-cpp.md)<br/>
[Синтаксис лямбда-выражений](../cpp/lambda-expression-syntax.md)<br/>
[`auto`](../cpp/auto-cpp.md)<br/>
[`function`См](../standard-library/function-class.md)<br/>
[`find_if`](../standard-library/algorithm-functions.md#find_if)<br/>
[`<algorithm>`](../standard-library/algorithm.md)<br/>
[Вызов функции](../cpp/function-call-cpp.md)<br/>
[См](../cpp/templates-cpp.md)<br/>
[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)<br/>
[Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)
