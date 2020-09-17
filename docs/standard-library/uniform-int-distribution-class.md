---
title: Класс uniform_int_distribution
ms.date: 11/04/2016
f1_keywords:
- random/std::uniform_int_distribution
- random/std::uniform_int_distribution::reset
- random/std::uniform_int_distribution::a
- random/std::uniform_int_distribution::b
- random/std::uniform_int_distribution::param
- random/std::uniform_int_distribution::min
- random/std::uniform_int_distribution::max
- random/std::uniform_int_distribution::operator()
- random/std::uniform_int_distribution::param_type
- random/std::uniform_int_distribution::param_type::a
- random/std::uniform_int_distribution::param_type::b
- random/std::uniform_int_distribution::param_type::operator==
- random/std::uniform_int_distribution::param_type::operator!=
helpviewer_keywords:
- std::uniform_int_distribution [C++]
- std::uniform_int_distribution [C++], reset
- std::uniform_int_distribution [C++], a
- std::uniform_int_distribution [C++], b
- std::uniform_int_distribution [C++], param
- std::uniform_int_distribution [C++], min
- std::uniform_int_distribution [C++], max
- std::uniform_int_distribution [C++], param_type
- std::uniform_int_distribution [C++], param_type
ms.assetid: a1867dcd-3bd9-4787-afe3-4b62692c1d04
ms.openlocfilehash: 3d9bb3cf9c4e34916dad3e435c7f4040dcc5f373
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831415"
---
# <a name="uniform_int_distribution-class"></a>Класс uniform_int_distribution

Формирует равномерное (каждое значение одинаково вероятно) распределение целых чисел в выходном инклюзивно-эксклюзивном диапазоне.

## <a name="syntax"></a>Синтаксис

```cpp
template<class IntType = int>
   class uniform_int_distribution {
public:
   // types
   typedef IntType result_type;
   struct param_type;

   // constructors and reset functions
   explicit uniform_int_distribution(
      result_type a = 0, result_type b = numeric_limits<result_type>::max());
   explicit uniform_int_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
      result_type operator()(URNG& gen);
   template <class URNG>
      result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type a() const;
   result_type b() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
};
```

### <a name="parameters"></a>Параметры

*инттипе*\
Целочисленный тип результата, по умолчанию — **`int`** . Возможные типы см. в разделе [\<random>](../standard-library/random.md) .

## <a name="remarks"></a>Примечания

Шаблон класса описывает инклюзивное инклюзивное распределение, которое создает значения указанного пользователем целочисленного типа с распределением, так что каждое значение одинаково возможно. В следующей таблице представлены ссылки на статьи об отдельных членах.

[uniform_int_distribution](#uniform_int_distribution)\
[param_type](#param_type)

Член свойства `a()` возвращает текущее хранимое минимальное значение распределения, а `b()` возвращает текущее хранимое максимальное значение. Для класса распределения эти минимальные и максимальные значения совпадают со значениями, которые возвращаются функциями свойств `min()` и `max()`.

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

void test(const int a, const int b, const int s) {

    // uncomment to use a non-deterministic seed
    //    std::random_device rd;
    //    std::mt19937 gen(rd());
    std::mt19937 gen(1729);

    std::uniform_int_distribution<> distr(a, b);

    std::cout << "lower bound == " << distr.a() << std::endl;
    std::cout << "upper bound == " << distr.b() << std::endl;

    // generate the distribution as a histogram
    std::map<int, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Distribution for " << s << " samples:" << std::endl;
    for (const auto& elem : histogram) {
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    int a_dist = 1;
    int b_dist = 10;

    int samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter an integer value for the lower bound of the distribution: ";
    std::cin >> a_dist;
    std::cout << "Enter an integer value for the upper bound of the distribution: ";
    std::cin >> b_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(a_dist, b_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for the lower bound of the distribution: 0
Enter an integer value for the upper bound of the distribution: 12
Enter an integer value for the sample count: 200
lower bound == 0
upper bound == 12
Distribution for 200 samples:
    0 :::::::::::::::
    1 :::::::::::::::::::::
    2 ::::::::::::::::::
    3 :::::::::::::::
    4 :::::::
    5 :::::::::::::::::::::
    6 :::::::::::::
    7 ::::::::::
    8 :::::::::::::::
    9 :::::::::::::
   10 ::::::::::::::::::::::
   11 :::::::::::::
   12 :::::::::::::::::
```

## <a name="requirements"></a>Требования

**Заголовок:**\<random>

**Пространство имен:** std

## <a name="uniform_int_distributionuniform_int_distribution"></a><a name="uniform_int_distribution"></a> uniform_int_distribution:: uniform_int_distribution

Формирует распределение.

```cpp
explicit uniform_int_distribution(
   result_type a = 0, result_type b = std::numeric_limits<result_type>::max());
explicit uniform_int_distribution(const param_type& parm);
```

### <a name="parameters"></a>Параметры

*конкретного*\
Нижняя граница случайных значений (инклюзивно).

*&*\
Верхняя граница случайных значений (инклюзивно).

*ParM*\
Структура `param_type`, используемая для формирования распределения.

### <a name="remarks"></a>Примечания

**Предварительное условие:**`a ≤ b`

Первый конструктор конструирует объект, хранимое значение которого *содержит значение* *a* , а хранимое значение *b* содержит значение *b*.

Второй конструктор создает объект, хранимые параметры которого инициализируются из *parm*. Вы можете получить и задать текущие параметры существующего распределения, вызвав функцию-член `param()`.

## <a name="uniform_int_distributionparam_type"></a><a name="param_type"></a> uniform_int_distribution::p aram_type

Сохраняет параметры распределения.

```cpp
struct param_type {
   typedef uniform_int_distribution<result_type> distribution_type;
   param_type(
      result_type a = 0, result_type b = std::numeric_limits<result_type>::max());
   result_type a() const;
   result_type b() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Параметры

*конкретного*\
Нижняя граница случайных значений (инклюзивно).

*&*\
Верхняя граница случайных значений (инклюзивно).

*right*\
Объект `param_type`, который требуется сравнить с данным объектом.

### <a name="remarks"></a>Примечания

**Предварительное условие:**`a ≤ b`

Эту структуру можно передать конструктору класса распределения во время создания экземпляра, функции-члену `param()` для установки хранимых параметров существующего распределения и `operator()` для использования вместо хранимых параметров.

## <a name="see-also"></a>См. также раздел

[\<random>](../standard-library/random.md)
