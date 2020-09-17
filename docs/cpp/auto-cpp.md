---
title: auto (C++)
ms.date: 12/10/2019
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
ms.openlocfilehash: 675f6919b6804cfb1d2c5395d046cb5fa39e625d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229198"
---
# <a name="auto-c"></a>`auto` (C++)

Выводит тип объявленной переменной из выражения инициализации.

> [!NOTE]
> Стандарт C++ определяет исходное и измененное значение для этого ключевого слова. До Visual Studio 2010 **`auto`** ключевое слово объявляет переменную в *автоматическом* классе хранения, то есть переменную с локальным временем существования. Начиная с Visual Studio 2010, **`auto`** ключевое слово объявляет переменную, тип которой выведен из выражения инициализации в его объявлении. Параметр компилятора [ `/Zc:auto`&#91;-&#93;](../build/reference/zc-auto-deduce-variable-type.md) определяет значение **`auto`** ключевого слова.

## <a name="syntax"></a>Синтаксис

> **`auto`***инициализатор* *декларатора***`;`**

> **`[](auto`***param1* **`, auto`** *Param2***`) {};`**

## <a name="remarks"></a>Примечания

**`auto`** Ключевое слово направляет компилятору использование выражения инициализации объявленной переменной или параметра лямбда-выражения, чтобы вывести его тип.

Рекомендуется использовать **`auto`** ключевое слово для большинства ситуаций, если только не требуется преобразование, так как оно предоставляет следующие преимущества:

- **Надежность:** Если тип выражения изменился — это включает в себя изменение типа возвращаемого значения функции — это просто работает.

- **Производительность:** Вы гарантируете, что преобразование не будет выполнено.

- **Удобство использования:** Не нужно беспокоиться о неправильном написании имени типа и опечатке.

- **Эффективность:** Написание кода может быть более эффективным.

Варианты преобразования, в которых может не потребоваться использовать **`auto`** :

- Если необходимо получить конкретный тип.

- Вспомогательные типы шаблона выражения, например `(valarray+valarray)` .

Чтобы использовать **`auto`** ключевое слово, используйте его вместо типа для объявления переменной и укажите выражение инициализации. Кроме того, можно изменить **`auto`** ключевое слово с помощью описателей и деклараторов, таких как **`const`** , **`volatile`** , указателя ( **`*`** ), ссылки ( **`&`** ) и ссылки rvalue ( **`&&`** ). Компилятор вычисляет выражение инициализации, а затем использует эти сведения, чтобы вывести тип переменной.

Выражением инициализации может быть присваивание (синтаксис равенства-знака), прямая инициализация (синтаксис в стиле функции), [`operator new`](new-operator-cpp.md) выражение или выражение инициализации может быть параметром *объявления для диапазона* в операторе [на основе диапазона `for` (C++)](../cpp/range-based-for-statement-cpp.md) . Дополнительные сведения см. в разделе [инициализаторы](../cpp/initializers.md) и примеры кода далее в этом документе.

**`auto`** Ключевое слово является заполнителем для типа, но не является типом. Поэтому **`auto`** ключевое слово не может использоваться в приведениях или операторах, таких как [`sizeof`](../cpp/sizeof-operator.md) и (для C++/CLI) [`typeid`](../extensions/typeid-cpp-component-extensions.md) .

## <a name="usefulness"></a>Удобство

**`auto`** Ключевое слово — это простой способ объявления переменной, имеющей сложный тип. Например, можно использовать **`auto`** для объявления переменной, в которой выражение инициализации включает шаблоны, указатели на функции или указатели на члены.

Можно также использовать **`auto`** для объявления и инициализации переменной в лямбда-выражении. Вы не сможете самостоятельно объявить тип переменной, поскольку тип лямбда-выражения известен только компилятору. Дополнительные сведения см. в разделе [Примеры лямбда-выражений](../cpp/examples-of-lambda-expressions.md).

## <a name="trailing-return-types"></a>Отслеживание возвращаемых типов

**`auto`** **`decltype`** Для создания библиотек шаблонов можно использовать вместе с описателем типа. Используйте **`auto`** и **`decltype`** для объявления функции шаблона, тип возвращаемого значения которого зависит от типов своих аргументов шаблона. Или используйте **`auto`** и **`decltype`** для объявления функции-шаблона, которая создает оболочку для вызова другой функции, а затем возвращает все, что является типом возвращаемого значения этой функции. Дополнительные сведения см. на веб-сайте [`decltype`](../cpp/decltype-cpp.md).

## <a name="references-and-cv-qualifiers"></a>Ссылки и cv-квалификаторы

Обратите внимание, что использование удаления **`auto`** ссылок, **`const`** квалификаторов и **`volatile`** квалификаторов. Рассмотрим следующий пример:

```cpp
// cl.exe /analyze /EHsc /W4
#include <iostream>

using namespace std;

int main( )
{
    int count = 10;
    int& countRef = count;
    auto myAuto = countRef;

    countRef = 11;
    cout << count << " ";

    myAuto = 12;
    cout << count << endl;
}
```

В предыдущем примере Мяуто — это, а **`int`** не **`int`** ссылка, поэтому выходные данные не так, `11 11` `11 12` как будто квалификатор ссылки не был удален с помощью **`auto`** .

## <a name="type-deduction-with-braced-initializers-c14"></a>Выведение типа с инициализаторами в фигурных скобках (C++ 14)

В следующем примере кода показано, как инициализировать **`auto`** переменную с помощью фигурных скобок. Обратите внимание на разницу между B и C и между A и E.

```cpp
#include <initializer_list>

int main()
{
    // std::initializer_list<int>
    auto A = { 1, 2 };

    // std::initializer_list<int>
    auto B = { 3 };

    // int
    auto C{ 4 };

    // C3535: cannot deduce type for 'auto' from initializer list'
    auto D = { 5, 6.7 };

    // C3518 in a direct-list-initialization context the type for 'auto'
    // can only be deduced from a single initializer expression
    auto E{ 8, 9 };

    return 0;
}
```

## <a name="restrictions-and-error-messages"></a>Ограничения и сообщения об ошибках

В следующей таблице перечислены ограничения на использование **`auto`** ключевого слова и соответствующее сообщение об ошибке диагностики, выдаваемое компилятором.

|Номер ошибки|Описание:|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|**`auto`** Ключевое слово не может использоваться вместе с любым другим описателем типа.|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|Символ, объявленный с **`auto`** ключевым словом, должен иметь инициализатор.|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|Вы неправильно использовали **`auto`** ключевое слово для объявления типа. Например, был объявлен тип возвращаемого значения метода или массив.|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Параметр или аргумент шаблона не может быть объявлен с **`auto`** ключевым словом.|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Невозможно объявить метод или параметр шаблона с **`auto`** ключевым словом.|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Символ не может быть использован до инициализации. Практически это означает, что переменную нельзя использовать для инициализации самой себя.|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|Нельзя привести к типу, объявленному с **`auto`** ключевым словом.|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|Все символы в списке деклараторов, объявленном с **`auto`** ключевым словом, должны разрешаться в один и тот же тип. Дополнительные сведения см. в разделе [объявления и определения](declarations-and-definitions-cpp.md).|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|Операторы [sizeof](../cpp/sizeof-operator.md) и [typeid](../extensions/typeid-cpp-component-extensions.md) не могут применяться к символам, объявленным с **`auto`** ключевым словом.|

## <a name="examples"></a>Примеры

Эти фрагменты кода иллюстрируют некоторые способы **`auto`** использования ключевого слова.

Следующие объявления эквивалентны. В первом операторе переменная `j` объявлена как тип **`int`** . Во второй инструкции переменная `k` выведена как тип, **`int`** поскольку выражение инициализации (0) является целым числом.

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

Следующие объявления эквивалентны, но второе объявление проще первого. Одной из наиболее интересных причин использования **`auto`** ключевого слова является простота.

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

В следующем фрагменте кода объявляется тип переменных `iter` и `elem` при **`for`** **`for`** запуске циклов и диапазонов.

```cpp
// cl /EHsc /nologo /W4
#include <deque>
using namespace std;

int main()
{
    deque<double> dqDoubleData(10, 0.1);

    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)
    { /* ... */ }

    // prefer range-for loops with the following information in mind
    // (this applies to any range-for with auto, not just deque)

    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples
    { /* ... */ }

    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE
    { /* ... */ }

    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE
    { /* ... */ }
}
```

В следующем фрагменте кода используется **`new`** объявление оператора и указателя для объявления указателей.

```cpp
double x = 12.34;
auto *y = new auto(x), **z = new auto(&x);
```

В следующем примере кода объявлено несколько символов в каждом операторе объявления. Обратите внимание, что все символы во всех операторах разрешаются к одному и тому же типу.

```cpp
auto x = 1, *y = &x, **z = &y; // Resolves to int.
auto a(2.01), *b (&a);         // Resolves to double.
auto c = 'a', *d(&c);          // Resolves to char.
auto m = 1, &n = m;            // Resolves to int.
```

В этом примере кода используется условный оператор (`?:`). Переменная `x` здесь объявляется как целочисленная переменная со значением 200.

```cpp
int v1 = 100, v2 = 200;
auto x = v1 > v2 ? v1 : v2;
```

Следующий фрагмент кода инициализирует переменную `x` для типа **`int`** , переменную `y` на ссылку на тип **`const int`** , а переменная — `fp` на указатель на функцию, которая возвращает тип **`int`** .

```cpp
int f(int x) { return x; }
int main()
{
    auto x = f(0);
    const auto& y = f(1);
    int (*p)(int x);
    p = f;
    auto fp = p;
    //...
}
```

## <a name="see-also"></a>См. также статью

[`auto`This](../cpp/auto-keyword.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[`/Zc:auto`(Вывод типа переменной)](../build/reference/zc-auto-deduce-variable-type.md)<br/>
[`sizeof`Станции](../cpp/sizeof-operator.md)<br/>
[`typeid`](../extensions/typeid-cpp-component-extensions.md)<br/>
[`operator new`](new-operator-cpp.md)<br/>
[Объявления и определения](declarations-and-definitions-cpp.md)<br/>
[Примеры лямбда-выражений](../cpp/examples-of-lambda-expressions.md)<br/>
[Инициализаторы](../cpp/initializers.md)<br/>
[`decltype`](../cpp/decltype-cpp.md)
