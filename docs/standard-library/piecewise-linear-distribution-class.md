---
title: Класс piecewise_linear_distribution
ms.date: 11/04/2016
f1_keywords:
- random/std::piecewise_linear_distribution
- random/std::piecewise_linear_distribution::reset
- random/std::piecewise_linear_distribution::intervals
- random/std::piecewise_linear_distribution::densities
- random/std::piecewise_linear_distribution::param
- random/std::piecewise_linear_distribution::min
- random/std::piecewise_linear_distribution::max
- random/std::piecewise_linear_distribution::operator()
- random/std::piecewise_linear_distribution::param_type
- random/std::piecewise_linear_distribution::param_type::intervals
- random/std::piecewise_linear_distribution::param_type::densities
- random/std::piecewise_linear_distribution::param_type::operator==
- random/std::piecewise_linear_distribution::param_type::operator!=
helpviewer_keywords:
- std::piecewise_linear_distribution [C++]
- std::piecewise_linear_distribution [C++], reset
- std::piecewise_linear_distribution [C++], intervals
- std::piecewise_linear_distribution [C++], densities
- std::piecewise_linear_distribution [C++], param
- std::piecewise_linear_distribution [C++], min
- std::piecewise_linear_distribution [C++], max
- std::piecewise_linear_distribution [C++], param_type
- std::piecewise_linear_distribution [C++], param_type
ms.assetid: cd141152-7163-4754-8f98-c6d6500005e0
ms.openlocfilehash: 57c6e19bc56068c98f6c85978c7af68e56cb4f2a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832689"
---
# <a name="piecewise_linear_distribution-class"></a>Класс piecewise_linear_distribution

Формирует кусочно-линейное распределение с меняющимися интервалами ширины и линейно меняющейся вероятностью в каждом интервале.

## <a name="syntax"></a>Синтаксис

```cpp
template<class RealType = double>
class piecewise_linear_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;

   // constructor and reset functions
   piecewise_linear_distribution();
   template <class InputIteratorI, class InputIteratorW>
   piecewise_linear_distribution(
      InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);
   template <class UnaryOperation>
   piecewise_linear_distribution(
      initializer_list<result_type> intervals, UnaryOperation weightfunc);
   template <class UnaryOperation>
   piecewise_linear_distribution(
      size_t count, result_type xmin, result_type xmax, UnaryOperation weightfunc);
   explicit piecewise_linear_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   vector<result_type> intervals() const;
   vector<result_type> densities() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Параметры

*реалтипе*\
Тип результата с плавающей запятой, по умолчанию — **`double`** . Возможные типы см. в разделе [\<random>](../standard-library/random.md) .

## <a name="remarks"></a>Примечания

Выборочное распределение использует меняющиеся интервалы ширины с линейно меняющейся вероятностью в каждом интервале. Сведения о других выборочных распределениях см. в разделах [piecewise_linear_distribution](../standard-library/piecewise-constant-distribution-class.md) и [discrete_distribution](../standard-library/discrete-distribution-class.md).

В следующей таблице представлены ссылки на статьи об отдельных членах.

[piecewise_linear_distribution](#piecewise_linear_distribution)\
[param_type](#param_type)

Функция свойства `intervals()` возвращает значение типа `vector<result_type>` с набором хранимых интервалов распределения.

Функция свойства `densities()` возвращает значение типа `vector<result_type>` с хранимыми плотностями для каждого набора интервалов, которые вычисляются в соответствии с весами, заданными в параметрах конструктора.

Член свойства `param()` устанавливает или возвращает хранимый пакет параметров распределения `param_type`.

Функции-члены `min()` и `max()` возвращают наименьший и наибольший из возможных результатов соответственно.

Функция-член `reset()` удаляет любые кэшированные значения, чтобы результат следующего вызова `operator()` не зависел от любых значений, полученных от механизма перед вызовом.

Функции-члены `operator()` возвращают следующее значение, созданное механизмом РГСЧ, из текущего или указанного пакета параметров.

Дополнительные сведения о классах распределения и их членах см [\<random>](../standard-library/random.md) . в разделе.

## <a name="example"></a>Пример

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

using namespace std;

void test(const int s) {

    // uncomment to use a non-deterministic generator
    // random_device rd;
    // mt19937 gen(rd());
    mt19937 gen(1701);

    // Three intervals, non-uniform: 0 to 1, 1 to 6, and 6 to 15
    vector<double> intervals{ 0, 1, 6, 15 };
    // weights determine the densities used by the distribution
    vector<double> weights{ 1, 5, 5, 10 };

    piecewise_linear_distribution<double> distr(intervals.begin(), intervals.end(), weights.begin());

    cout << endl;
    cout << "min() == " << distr.min() << endl;
    cout << "max() == " << distr.max() << endl;
    cout << "intervals (index: interval):" << endl;
    vector<double> i = distr.intervals();
    int counter = 0;
    for (const auto& n : i) {
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;
        ++counter;
    }
    cout << endl;
    cout << "densities (index: density):" << endl;
    vector<double> d = distr.densities();
    counter = 0;
    for (const auto& n : d) {
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;
        ++counter;
    }
    cout << endl;

    // generate the distribution as a histogram
    map<int, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    cout << "Distribution for " << s << " samples:" << endl;
    for (const auto& elem : histogram) {
        cout << setw(5) << elem.first << '-' << elem.first + 1 << ' ' << string(elem.second, ':') << endl;
    }
    cout << endl;
}

int main()
{
    int samples = 100;

    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;
    cout << "Enter an integer value for the sample count: ";
    cin >> samples;

    test(samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for the sample count: 100
min() == 0
max() == 15
intervals (index: interval):
          0:   0.0000000000
          1:   1.0000000000
          2:   6.0000000000
          3:  15.0000000000
densities (index: density):
          0:   0.0645161290
          1:   0.3225806452
          2:   0.3225806452
          3:   0.6451612903
Distribution for 100 samples:
    0-1 :::::::::::::::::::::
    1-2 ::::::
    2-3 :::
    3-4 :::::::
    4-5 ::::::
    5-6 ::::::
    6-7 :::::
    7-8 ::::::::::
    8-9 ::::::::::
    9-10 ::::::
   10-11 ::::
   11-12 :::
   12-13 :::
   13-14 :::::
   14-15 :::::
```

## <a name="requirements"></a>Требования

**Заголовок:**\<random>

**Пространство имен:** std

## <a name="piecewise_linear_distributionpiecewise_linear_distribution"></a><a name="piecewise_linear_distribution"></a> piecewise_linear_distribution::p iecewise_linear_distribution

Формирует распределение.

```cpp
// default constructor
piecewise_linear_distribution();

// constructs using a range of intervals, [firstI, lastI), with
// matching weights starting at firstW
template <class InputIteratorI, class InputIteratorW>
piecewise_linear_distribution(InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);

// constructs using an initializer list for range of intervals,
// with weights generated by function weightfunc
template <class UnaryOperation>
piecewise_linear_distribution(initializer_list<RealType>
intervals, UnaryOperation weightfunc);

// constructs using an initializer list for range of count intervals,
// distributed uniformly over [xmin,xmax] with weights generated by function weightfunc
template <class UnaryOperation>
piecewise_linear_distribution(size_t count, RealType xmin, RealType xmax, UnaryOperation weightfunc);

// constructs from an existing param_type structure
explicit piecewise_linear_distribution(const param_type& parm);
```

### <a name="parameters"></a>Параметры

*фирсти*\
Итератор ввода первого элемента в диапазоне распределения.

*ласти*\
Итератор ввода последнего элемента в диапазоне распределения.

*firstW*\
Итератор ввода первого элемента в диапазоне весов.

*диапазона*\
Объект [initializer_list](../cpp/initializers.md) с интервалами распределения.

*count*\
Количество элементов в диапазоне распределения.

*xmin*\
Минимальное значение в диапазоне распределения.

*xmax*\
Максимальное значение в диапазоне распределения. Должно быть больше, чем *xmin*.

*веигхтфунк*\
Объект, представляющий функцию вероятности распределения. Параметр и возвращаемое значение должны быть преобразованы в **`double`** .

*ParM*\
Структура параметров, используемая для формирования распределения.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию задает хранимые параметры таким образом, чтобы существовал один интервал от 0 до 1 с плотностью вероятности 1.

Конструктор диапазона итератора

```cpp
template <class InputIteratorI, class InputIteratorW>
piecewise_linear_distribution(
    InputIteratorI firstI,
    InputIteratorI lastI,
    InputIteratorW firstW);
```

конструирует объект распределения с интервалами от итераторов по последовательности [ `firstI` , `lastI` ) и соответствующей последовательности весов, начиная с *firstW*.

Конструктор списка инициализаторов

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    initializer_list<result_type> intervals,
    UnaryOperation weightfunc);
```

Создает объект распределения с интервалами между *интервалами* списка инициализаторов и весовыми коэффициентами, созданными из функции *веигхтфунк*.

Конструктор, определенный как

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    size_t count,
    result_type xmin,
    result_type xmax,
    UnaryOperation weightfunc);
```

конструирует объект *распределения с равномерно* распределенными интервалами по [ `xmin,xmax` ], присваивая вес каждого интервала в соответствии с функцией *веигхтфунк*, а *веигхтфунк* должен принимать один параметр и иметь возвращаемое значение, которое можно преобразовать в **`double`** . **Предусловие:** `xmin < xmax` .

Конструктор, определенный как

```cpp
explicit piecewise_linear_distribution(const param_type& parm);
```

конструирует объект распределения, используя *ParM* в качестве структуры хранимого параметра.

## <a name="piecewise_linear_distributionparam_type"></a><a name="param_type"></a> piecewise_linear_distribution::p aram_type

Сохраняет все параметры распределения.

```cpp
struct param_type {
   typedef piecewise_linear_distribution<result_type> distribution_type;
   param_type();
   template <class IterI, class IterW>
   param_type(
      IterI firstI, IterI lastI, IterW firstW);
   template <class UnaryOperation>
   param_type(
      size_t count, result_type xmin, result_type xmax, UnaryOperation weightfunc);
   std::vector<result_type> densities() const;
   std::vector<result_type> intervals() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Параметры

См. параметры конструктора [piecewise_linear_distribution](#piecewise_linear_distribution).

### <a name="remarks"></a>Примечания

**Предварительное условие:**`xmin < xmax`

Эту структуру можно передать конструктору класса распределения во время создания экземпляра, функции-члену `param()` для установки хранимых параметров существующего распределения и `operator()` для использования вместо хранимых параметров.

## <a name="see-also"></a>См. также раздел

[\<random>](../standard-library/random.md)
