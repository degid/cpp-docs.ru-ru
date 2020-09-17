---
title: Класс money_put
ms.date: 11/01/2018
f1_keywords:
- xlocmon/std::money_put
- xlocmon/std::money_put::char_type
- xlocmon/std::money_put::iter_type
- xlocmon/std::money_put::string_type
- xlocmon/std::money_put::do_put
- xlocmon/std::money_put::put
helpviewer_keywords:
- std::money_put [C++]
- std::money_put [C++], char_type
- std::money_put [C++], iter_type
- std::money_put [C++], string_type
- std::money_put [C++], do_put
- std::money_put [C++], put
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
ms.openlocfilehash: d15667f4e30561dbba024f877530c4ff0f824f64
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224751"
---
# <a name="money_put-class"></a>Класс money_put

Шаблон класса описывает объект, который может служить в качестве аспекта языкового стандарта для управления преобразованием денежных значений в последовательности типа `CharType` .

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class money_put : public locale::facet;
```

### <a name="parameters"></a>Параметры

*CharType*\
Тип, используемый внутри программы для кодирования символов в языковом стандарте.

*OutputIterator*\
Тип итератора, куда функции записи денежных значений записывают свои выходные данные.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[money_put](#money_put)|Конструктор для объектов типа `money_put`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[iter_type](#iter_type)|Тип, который описывает итератор вывода.|
|[string_type](#string_type)|Тип, описывающий строку, содержащую символы типа `CharType`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[do_put](#do_put)|Виртуальная функция, вызываемая для преобразования числа или строки в последовательность символов, представляющую денежное значение.|
|[PUT](#put)|Преобразует число или строку в последовательность символов, представляющую денежное значение.|

## <a name="requirements"></a>Требования

**Заголовок:**\<locale>

**Пространство имен:** std

## <a name="money_putchar_type"></a><a name="char_type"></a>money_put:: char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона **Chartype**.

## <a name="money_putdo_put"></a><a name="do_put"></a>money_put::d o_put

Виртуальная функция, вызываемая для преобразования числа или строки в последовательность символов, представляющую денежное значение.

```cpp
virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;

virtual iter_type do_put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>Параметры

*очеред*\
Итератор, адресующий первый элемент во вставляемой строке.

*_Intl*\
Логическое значение, указывающее тип символа валюты, ожидаемого в последовательности: **`true`** Если международная, то **`false`** если он является внутренним.

*_Iosbase*\
Флаг формата, который при установке указывает, что символ валюты является необязательным. В противном случае он обязателен.

*_Fill*\
Символ, используемый для пробелов.

*val*\
Строковый объект для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Итератор вывода, который адресует позицию после последнего сформированного элемента.

### <a name="remarks"></a>Примечания

Первая виртуальная Защищенная функция-член создает последовательные элементы, начиная с *следующего* , чтобы получить поле денежного вывода из [string_type](#string_type) объекта *Val*. Последовательность, управляемая аргументом *Val* , должна начинаться с одной или нескольких десятичных цифр, при необходимости предшествует знаку минус (-), представляющему сумму. Функция возвращает итератор, обозначающий первый элемент за пределами созданного выходного денежного поля.

Вторая виртуальная Защищенная функция-член ведет себя так же, как первая, за исключением того, что она фактически сначала преобразует значение *Val* в последовательность десятичных цифр, при необходимости перед знаком минус, а затем преобразует эту последовательность выше.

Формат поля денежного вывода определяется [аспектом locale](../standard-library/locale-class.md#facet_class) fac, возвращаемым (эффективным) вызовом [use_facet](../standard-library/locale-functions.md#use_facet)  <  [moneypunct](../standard-library/moneypunct-class.md) \< **CharType**, **intl**> > ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)).

В частности, внесены следующие изменения.

- **fac**. [pos_format](../standard-library/moneypunct-class.md#pos_format) определяет порядок, в котором компоненты поля создаются для неотрицательного значения.

- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) определяет порядок, в котором компоненты поля создаются для отрицательного значения.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) определяет последовательность элементов для создания символа валюты.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) определяет последовательность элементов для создания положительного знака.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#negative_sign) определяет последовательность элементов для создания отрицательного знака.

- **fac**. [grouping](../standard-library/moneypunct-class.md#grouping) определяет, как группируются цифры слева от любого десятичного разделителя.

- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) определяет элемент, разделяющий группы цифр слева от любого десятичного разделителя.

- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) определяет элемент, который отделяет целочисленное значение от любых цифр дробного значения.

- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) определяет количество значимых цифр дробной части справа от любого десятичного разделителя.

Если строка знака (**fac**. `negative_sign` или **fac**. `positive_sign`) имеет более одного элемента, только первый элемент создается, если элемент, равный **money_base::sign**, отображается в шаблоне формата (**fac**. `neg_format` или **fac**. `pos_format`). Все оставшиеся элементы создаются в конце поля вывода денежных значений.

Если **iosbase**. [Флаги](../standard-library/ios-base-class.md#flags)  &  [showbase](../standard-library/ios-functions.md#showbase) имеет ненулевое значение, строка **fac**. `curr_symbol`создается, когда в шаблоне формата появляется элемент, равный **money_base::symbol**. В противном символ валюты не создается.

Если не накладываются ограничения по группированию со стороны **fac**. **grouping** (первый элемент имеет значение CHAR_MAX), то никакие экземпляры **fac**. `thousands_sep` не создаются в разделе значения денежных полей (если в шаблоне формата появляется элемент, равный **money_base::value**). Если **fac**. `frac_digits` — нуль, то после десятичных цифр не создаются никакие экземпляры **fac**. `decimal_point`. В противном случае результат поля вывода денежных значений будет иметь младшие десятичные цифры **fac**. `frac_digits` справа от десятичного разделителя.

Заполнение происходит как для любого числового поля вывода, за исключением того, что, если значение **iosbase**. **Флаги**  &  **iosbase**. [internal](../standard-library/ios-functions.md#internal) не нулевое, любое внутреннее заполнение создается там, где в шаблоне формата появляется элемент, равный **money_base::space**, если он есть. В противном случае внутреннее заполнение предшествует создаваемой последовательности. Символ заполнения — **fill**.

Функция вызывает **iosbase**. **width**(0) для сброса ширины поля в нуль.

### <a name="example"></a>Пример

См. пример для [put](#put), где виртуальная функция-член вызывается из **put**.

## <a name="money_putiter_type"></a><a name="iter_type"></a>money_put:: iter_type

Тип, который описывает итератор вывода.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом параметра-шаблона **OutputIterator.**

## <a name="money_putmoney_put"></a><a name="money_put"></a>money_put:: money_put

Конструктор для объектов типа `money_put`.

```cpp
explicit money_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_Refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Примечания

Возможные значения параметра *_Refs* и их значимость:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \>1: эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой базовый объект с **локальным::**[Facet](../standard-library/locale-class.md#facet_class)( `_Refs` ).

## <a name="money_putput"></a><a name="put"></a>money_put::p UT

Преобразует число или строку в последовательность символов, представляющую денежное значение.

```cpp
iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    const string_type& val) const;

iter_type put(
    iter_type next,
    bool _Intl,
    ios_base& _Iosbase,
    CharType _Fill,
    long double val) const;
```

### <a name="parameters"></a>Параметры

*очеред*\
Итератор, адресующий первый элемент во вставляемой строке.

*_Intl*\
Логическое значение, указывающее тип символа валюты, ожидаемого в последовательности: **`true`** Если международная, то **`false`** если он является внутренним.

*_Iosbase*\
Флаг формата, который при установке указывает, что символ валюты является необязательным. В противном случае он обязателен.

*_Fill*\
Символ, используемый для пробелов.

*val*\
Строковый объект для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Итератор вывода, который адресует позицию после последнего сформированного элемента.

### <a name="remarks"></a>Примечания

Обе функции-члены возвращают [do_put](#do_put)( `next` , `_Intl` , `_Iosbase` , `_Fill` , `val` ).

### <a name="example"></a>Пример

```cpp
// money_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

int main()
{
    std::locale loc( "german_germany" );
    std::basic_stringstream<char> psz;

    psz.imbue(loc);
    psz.flags(psz.flags() | std::ios_base::showbase); // force the printing of the currency symbol
    std::use_facet<std::money_put<char> >(loc).put(std::basic_ostream<char>::_Iter(psz.rdbuf()), true, psz, ' ', 100012);
    if (psz.fail())
        std::cout << "money_put() FAILED" << std::endl;
    else
        std::cout << "money_put() = \"" << psz.rdbuf()->str() << "\"" << std::endl;
}
```

```Output
money_put() = "EUR1.000,12"
```

## <a name="money_putstring_type"></a><a name="string_type"></a>money_put:: string_type

Тип, описывающий строку, содержащую символы типа `CharType`.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [basic_string](../standard-library/basic-string-class.md) , объекты которой могут хранить последовательности элементов из исходной последовательности.

## <a name="see-also"></a>См. также статью

[\<locale>](../standard-library/locale.md)\
[Класс аспекта](../standard-library/locale-class.md#facet_class)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
