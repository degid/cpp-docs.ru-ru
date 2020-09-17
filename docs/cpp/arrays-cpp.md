---
title: Массивы (C++)
ms.date: 08/03/2020
helpviewer_keywords:
- declaring arrays [C++], about declaring arrays
- multidimensional arrays [C++]
- arrays [C++]
ms.assetid: 3f5986aa-485c-4ba4-9502-67e2ef924238
ms.openlocfilehash: cb949f9a17a6b751dae40202bf82e6cb321b526b
ms.sourcegitcommit: 4eda68a0b3c23d8cefa56b7ba11583412459b32f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87565967"
---
# <a name="arrays-c"></a>Массивы (C++)

Массив — это последовательность объектов того же типа, которые занимают смежную область памяти. Традиционные массивы в стиле C являются источником многих ошибок, но по-прежнему являются общими, особенно в старых базах кода. В современных C++ мы настоятельно рекомендуем использовать [std::vector](../standard-library/vector-class.md) или [std::array](../standard-library/array-class-stl.md) вместо массивов в стиле C, описанных в этом разделе. Оба этих типа стандартных библиотек хранят свои элементы в виде непрерывного блока памяти. Однако они обеспечивают гораздо большую безопасность типов и итераторы поддержки, которые гарантированно указывают на допустимое расположение в последовательности. Дополнительные сведения см. в разделе [контейнеры (современный C++)](containers-modern-cpp.md).

## <a name="stack-declarations"></a>Объявления стека

В объявлении массива C++ размер массива указывается после имени переменной, а не после имени типа, как в некоторых других языках. В следующем примере объявляется массив значений типа Double 1000, которые будут выделяться в стеке. Число элементов должно быть указано как целочисленный литерал или else в качестве константного выражения. Это обусловлено тем, что компилятору необходимо выяснить, сколько пространства стека следует выделить; оно не может использовать значение, вычисленное во время выполнения. Каждому элементу массива присваивается значение по умолчанию 0. Если не назначить значение по умолчанию, каждый элемент изначально будет содержать случайные значения, находящимся в этой области памяти.

```cpp
    constexpr size_t size = 1000;

    // Declare an array of doubles to be allocated on the stack
    double numbers[size] {0};

    // Assign a new value to the first element
    numbers[0] = 1;

    // Assign a value to each subsequent element
    // (numbers[1] is the second element in the array.)
    for (size_t i = 1; i < size; i++)
    {
        numbers[i] = numbers[i-1] * 1.1;
    }

    // Access each element
    for (size_t i = 0; i < size; i++)
    {
        std::cout << numbers[i] << " ";
    }
```

Первый элемент в массиве является элементом начальном. Последним элементом является элемент (*n*-1), где *n* — число элементов, которые может содержать массив. Число элементов в объявлении должно иметь целочисленный тип и должно быть больше 0. Вы обязаны убедиться, что программа никогда не передает значение оператору индекса, который больше `(size - 1)` .

Массив нулевого размера допустим только в том случае, если массив является последним полем в **`struct`** или **`union`** и если расширения Microsoft включены ( **`/Za`** или **`/permissive-`** не заданы).

Массивы на основе стека быстрее выделяются и получают доступ, чем массивы на основе кучи. Однако пространство стека ограничено. Число элементов массива не может быть настолько большим, что в нем используется слишком много памяти стека. Насколько сильно зависит от программы. Для определения того, является ли массив слишком большим, можно использовать средства профилирования.

## <a name="heap-declarations"></a>Объявления кучи

Может потребоваться, чтобы массив был слишком большим для выделения в стеке или его размер не известен во время компиляции. Можно выделить этот массив в куче с помощью [`new[]`](new-operator-cpp.md) выражения. Оператор возвращает указатель на первый элемент. Оператор индекса работает с переменной-указателем так же, как и с массивом на основе стека. Также можно использовать [арифметические операции с указателями](../c-language/pointer-arithmetic.md) для перемещения указателя на произвольные элементы в массиве. Вы обязаны убедиться в том, что:

- всегда сохраняется копия адреса исходного указателя, чтобы можно было удалить память, когда массив больше не нужен.
- Вы не увеличиваете или уменьшаете адрес указателя после границ массива.

В следующем примере показано, как определить массив в куче во время выполнения. В нем показано, как получить доступ к элементам массива с помощью оператора индекса и с помощью арифметики указателей:

```cpp

void do_something(size_t size)
{
    // Declare an array of doubles to be allocated on the heap
    double* numbers = new double[size]{ 0 };

    // Assign a new value to the first element
    numbers[0] = 1;

    // Assign a value to each subsequent element
    // (numbers[1] is the second element in the array.)
    for (size_t i = 1; i < size; i++)
    {
        numbers[i] = numbers[i - 1] * 1.1;
    }

    // Access each element with subscript operator
    for (size_t i = 0; i < size; i++)
    {
        std::cout << numbers[i] << " ";
    }

    // Access each element with pointer arithmetic
    // Use a copy of the pointer for iterating
    double* p = numbers;

    for (size_t i = 0; i < size; i++)
    {
        // Dereference the pointer, then increment it
        std::cout << *p++ << " ";
    }

    // Alternate method:
    // Reset p to numbers[0]:
    p = numbers;

    // Use address of pointer to compute bounds.
    // The compiler computes size as the number
    // of elements * (bytes per element).
    while (p < (numbers + size))
    {
        // Dereference the pointer, then increment it
        std::cout << *p++ << " ";
    }

    delete[] numbers; // don't forget to do this!

}
int main()
{
    do_something(108);
}

```

## <a name="initializing-arrays"></a>Инициализация массивов

Можно инициализировать массив в цикле, по одному элементу за раз или в одной инструкции. Содержимое следующих двух массивов идентично:

```cpp
    int a[10];
    for (int i = 0; i < 10; ++i)
    {
        a[i] = i + 1;
    }

    int b[10]{ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
```

## <a name="passing-arrays-to-functions"></a>Передача массивов в функции

Когда массив передается в функцию, он передается в качестве указателя на первый элемент, независимо от того, является ли он массивом на основе стека или кучи. Указатель не содержит дополнительных сведений о размере или типе. Такое поведение называется *указателем Decay*. При передаче массива в функцию необходимо всегда указывать количество элементов в отдельном параметре. Такое поведение также подразумевает, что элементы массива не копируются, когда массив передается в функцию. Чтобы запретить функции изменять элементы, укажите параметр в качестве указателя на **`const`** элементы.

В следующем примере показана функция, которая принимает массив и длину. Указатель указывает на исходный массив, а не на копию. Поскольку параметр не **`const`** имеет значение, функция может изменять элементы массива.

```cpp
void process(double p*, const size_t len)
{
    std::cout << "process:\n";
    for (size_t i = 0; i < len; ++i)
    {
        // do something with p[i]
    }
}
```

Объявите массив как константу, чтобы сделать его только для чтения в блоке функции:

```cpp
void process(const double p*, const size_t len);
```

Одна и та же функция может также быть объявлена в таких случаях без изменения поведения. Массив по-прежнему передается в качестве указателя на первый элемент:

```cpp
// Unsized array
void process(const double p[], const size_t len);

// Fixed-size array. Length must still be specified explicitly.
void process(const double p[1000], const size_t len);
```

## <a name="multidimensional-arrays"></a>Многомерные массивы

Массивы, созданные из других массивов, являются многомерными. Такие многомерные массивы определяются путем последовательного размещения нескольких константных выражений, заключенных в квадратные скобки. Рассмотрим, например, следующее объявление:

```cpp
int i2[5][7];
```

Он задает массив типа, по **`int`** сути упорядоченный в двумерной матрице из пяти строк и семи столбцов, как показано на следующем рисунке.

![Концептуальный макет многомерного массива&#45;](../cpp/media/vc38rc1.gif "Концептуальный макет многомерного массива&#45;") <br/>
Концептуальная структура многомерного массива

Можно объявить многомерные массивы, имеющие список инициализаторов (как описано в разделе [инициализаторы](../cpp/initializers.md)). В этих объявлениях константное выражение, указывающее границы для первого измерения, может быть опущено. Пример:

```cpp
// arrays2.cpp
// compile with: /c
const int cMarkets = 4;
// Declare a float that represents the transportation costs.
double TransportCosts[][cMarkets] = {
   { 32.19, 47.29, 31.99, 19.11 },
   { 11.29, 22.49, 33.47, 17.29 },
   { 41.97, 22.09,  9.76, 22.55 }
};
```

В показанном выше объявлении определяется массив, состоящий из трех строк и четырех столбцов. Строки представляют фабрики, а столбцы — рынки, на которые фабрики поставляют свою продукцию. Значения — это стоимости транспортировки с фабрик на рынки. Первое измерение массива опущено, но компилятор заполняет его, проверяя инициализатор.

Использование оператора косвенного обращения (*) в n-мерном массиве приводит к получению n-1 многомерного массива. Если n равно 1, создается скаляр (или элемент массива).

Массивы C++ размещаются в памяти по срокам. Построчный порядок означает, что быстрее всего изменяется последний индекс.

## <a name="example"></a>Пример

Можно также опустить спецификацию границ для первого измерения многомерного массива в объявлениях функций, как показано ниже:

```cpp
// multidimensional_arrays.cpp
// compile with: /EHsc
// arguments: 3
#include <limits>   // Includes DBL_MAX
#include <iostream>

const int cMkts = 4, cFacts = 2;

// Declare a float that represents the transportation costs
double TransportCosts[][cMkts] = {
   { 32.19, 47.29, 31.99, 19.11 },
   { 11.29, 22.49, 33.47, 17.29 },
   { 41.97, 22.09,  9.76, 22.55 }
};

// Calculate size of unspecified dimension
const int cFactories = sizeof TransportCosts /
                  sizeof( double[cMkts] );

double FindMinToMkt( int Mkt, double myTransportCosts[][cMkts], int mycFacts);

using namespace std;

int main( int argc, char *argv[] ) {
   double MinCost;

   if (argv[1] == 0) {
      cout << "You must specify the number of markets." << endl;
      exit(0);
   }
   MinCost = FindMinToMkt( *argv[1] - '0', TransportCosts, cFacts);
   cout << "The minimum cost to Market " << argv[1] << " is: "
       << MinCost << "\n";
}

double FindMinToMkt(int Mkt, double myTransportCosts[][cMkts], int mycFacts) {
   double MinCost = DBL_MAX;

   for( size_t i = 0; i < cFacts; ++i )
      MinCost = (MinCost < TransportCosts[i][Mkt]) ?
         MinCost : TransportCosts[i][Mkt];

   return MinCost;
}
```

```Output
The minimum cost to Market 3 is: 17.29
```

Эта функция `FindMinToMkt` написана таким, что добавление новых фабрик не требует каких-либо изменений кода, а только перекомпиляции.

## <a name="initializing-arrays"></a>Инициализация массивов

Массивы объектов, имеющих конструктор класса, инициализируются конструктором. Если в списке инициализаторов меньше элементов, чем элементов массива, то для остальных элементов используется конструктор по умолчанию. Если для класса не определен конструктор по умолчанию, список инициализаторов должен быть *завершен*, то есть должен быть один инициализатор для каждого элемента в массиве.

Рассмотрим класс `Point`, определяющий два конструктора:

```cpp
// initializing_arrays1.cpp
class Point
{
public:
   Point()   // Default constructor.
   {
   }
   Point( int, int )   // Construct from two ints
   {
   }
};

// An array of Point objects can be declared as follows:
Point aPoint[3] = {
   Point( 3, 3 )     // Use int, int constructor.
};

int main()
{
}
```

Первый элемент `aPoint` создается с помощью конструктора `Point( int, int )`, а оставшиеся два элемента — с помощью конструктора по умолчанию.

Статические массивы членов ( **`const`** вне зависимости от объявления класса) могут быть инициализированы в своих определениях. Пример:

```cpp
// initializing_arrays2.cpp
class WindowColors
{
public:
    static const char *rgszWindowPartList[7];
};

const char *WindowColors::rgszWindowPartList[7] = {
    "Active Title Bar", "Inactive Title Bar", "Title Bar Text",
    "Menu Bar", "Menu Bar Text", "Window Background", "Frame"   };
int main()
{
}
```

## <a name="accessing-array-elements"></a>Доступ к элементам массива

К отдельным элементам массива можно обращаться при помощи оператора индекса массива (`[ ]`). При использовании имени одномерного массива без индекса он вычисляется как указатель на первый элемент массива.

```cpp
// using_arrays.cpp
int main() {
   char chArray[10];
   char *pch = chArray;   // Evaluates to a pointer to the first element.
   char   ch = chArray[0];   // Evaluates to the value of the first element.
   ch = chArray[3];   // Evaluates to the value of the fourth element.
}
```

Если используются многомерные массивы, в выражениях можно использовать различные сочетания.

```cpp
// using_arrays_2.cpp
// compile with: /EHsc /W1
#include <iostream>
using namespace std;
int main() {
   double multi[4][4][3];   // Declare the array.
   double (*p2multi)[3];
   double (*p1multi);

   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.
   p2multi = multi[3];               // Make p2multi point to
                                     // fourth "plane" of multi.
   p1multi = multi[3][2];            // Make p1multi point to
                                     // fourth plane, third row
                                     // of multi.
}
```

В приведенном выше коде `multi` является трехмерным массивом типа **`double`** . `p2multi`Указатель указывает на массив типа, размер которого равен **`double`** трем. В этом примере массив используется с одним, двумя и тремя индексами. Хотя чаще всего указывается все индексы, как в `cout` инструкции, иногда бывает полезно выбрать конкретное подмножество элементов массива, как показано в следующих инструкциях `cout` .

## <a name="overloading-subscript-operator"></a>Перегрузка оператора индекса

Как и другие операторы, оператор индекса ( `[]` ) может быть переопределен пользователем. Поведение оператора индекса по умолчанию, если он не перегружен, — совмещать имя массива и индекс с помощью следующего метода.

`*((array_name) + (subscript))`

Как и во всех дополнениех, включающих типы указателей, масштабирование выполняется автоматически для корректировки размера типа. Результирующее значение не *n* байт из источника `array_name` ; вместо этого это *n*-й элемент массива. Дополнительные сведения об этом преобразовании см. в разделе [аддитивные операторы](additive-operators-plus-and.md).

Аналогично, для многомерных массивов адрес извлекается с использованием следующего метода.

`((array_name) + (subscript1 * max2 * max3 * ... * maxn) + (subscript2 * max3 * ... * maxn) + ... + subscriptn))`

## <a name="arrays-in-expressions"></a>Массивы в выражениях

Если идентификатор типа массива встречается в выражении, отличном от **`sizeof`** , адрес ( `&` ) или инициализации ссылки, он преобразуется в указатель на первый элемент массива. Пример:

```cpp
char szError1[] = "Error: Disk drive not ready.";
char *psz = szError1;
```

Указатель `psz` указывает на первый элемент массива `szError1`. Массивы, в отличие от указателей, не являются изменяемыми l-значениями. Вот почему следующее назначение недопустимо:

```cpp
szError1 = psz;
```

## <a name="see-also"></a>См. также раздел

[std:: Array](../standard-library/array-class-stl.md)
