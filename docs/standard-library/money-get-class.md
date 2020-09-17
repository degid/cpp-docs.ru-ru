---
title: Класс money_get
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_get
- xlocmon/std::money_get::char_type
- xlocmon/std::money_get::iter_type
- xlocmon/std::money_get::string_type
- xlocmon/std::money_get::do_get
- xlocmon/std::money_get::get
helpviewer_keywords:
- std::money_get [C++]
- std::money_get [C++], char_type
- std::money_get [C++], iter_type
- std::money_get [C++], string_type
- std::money_get [C++], do_get
- std::money_get [C++], get
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
ms.openlocfilehash: ab49dad1a24e57eb33834cc651d9ccdb50abe68c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224764"
---
# <a name="money_get-class"></a>Класс money_get

Шаблон класса описывает объект, который может служить в качестве аспекта языкового стандарта для управления преобразованием последовательностей типа `CharType` в денежные значения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class money_get : public locale::facet;
```

### <a name="parameters"></a>Параметры

*CharType*\
Тип, используемый внутри программы для кодирования символов в языковом стандарте.

*InputIterator*\
Тип итератора, из которого функции получения считывают своих входные данные.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[money_get](#money_get)|Конструктор для объектов типа `money_get`, используемых для извлечения числовых значений из последовательностей, представляющих денежные значения.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[iter_type](#iter_type)|Тип, который описывает итератор ввода.|
|[string_type](#string_type)|Тип, описывающий строку, содержащую символы типа `CharType`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[do_get](#do_get)|Виртуальная функция, вызываемая для извлечения числового значения из последовательности символов, представляющей денежное значение.|
|[get](#get)|Извлекает числовое значение из последовательности символов, представляющей денежное значение.|

## <a name="requirements"></a>Требования

**Заголовок:**\<locale>

**Пространство имен:** std

## <a name="money_getchar_type"></a><a name="char_type"></a>money_get:: char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона *Chartype*.

## <a name="money_getdo_get"></a><a name="do_get"></a>money_get::d o_get

Виртуальная функция, которая вызывается для извлечения числового значения из последовательности символов, которая представляет денежное значение.

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*Intl*\
Логическое значение, указывающее тип символа валюты, ожидаемого в последовательности: **`true`** Если международная, то **`false`** если он является внутренним.

*Iosbase*\
Флаг формата, который, будучи установленным, указывает, что символ валюты не обязателен; в противном случае он обязателен.

*С*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*val*\
Строка, хранящая преобразованную последовательность.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после денежного поля ввода.

### <a name="remarks"></a>Примечания

Первая защищенная виртуальная функция-член пытается сопоставить последовательные элементы, начиная с первого в последовательности [ `first`, `last`), пока не распознает полное, непустое денежное поле ввода. В случае успеха оно преобразует это поле в последовательность из одной или нескольких десятичных цифр, при необходимости перед знаком минуса ( `-` ), чтобы представить сумму и сохранить результат в [string_type](#string_type) объект *Val*. Она возвращает итератор, обозначающий первый элемент после денежного поля ввода. В противном случае функция сохраняет пустую последовательность в *Val* и задает `ios_base::failbit` в *состоянии*. Она возвращает итератор, обозначающий первый элемент после любого префикса допустимого денежного поля ввода. В любом случае, если возвращаемое значение равно `last`, функция устанавливает `ios_base::eofbit` в `State`.

Вторая виртуальная Защищенная функция-член ведет себя так же, как и первая, за исключением того, что при успешном выполнении она преобразует последовательность цифр со знаком подписывания в значение типа **`long double`** и сохраняет это значение в аргументе *Val*.

Формат поля денежного ввода определяется с помощью [аспекта locale](../standard-library/locale-class.md#facet_class)**fac** , возвращаемого эффективным вызовом [use_facet](../standard-library/locale-functions.md#use_facet)  <  [moneypunct](../standard-library/moneypunct-class.md) \< **CharType**, **intl**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)).

В частности, внесены следующие изменения.

- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) определяет порядок, в котором будут расположены компоненты поля.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) определяет последовательность элементов, составляющую символ валюты.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) определяет последовательность элементов, составляющую положительный знак.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#negative_sign) определяет последовательность элементов, составляющую отрицательный знак.

- **fac**. [grouping](../standard-library/moneypunct-class.md#grouping) определяет, как группируются цифры слева от любого десятичного разделителя.

- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) определяет элемент, разделяющий группы цифр слева от любого десятичного разделителя.

- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) определяет элемент, который отделяет цифры целой части от цифр дробной части.

- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) определяет количество значимых цифр дробной части справа от любого десятичного разделителя. При разборе денежной суммы, в которой больше цифр после запятой, чем требуется `frac_digits`, `do_get` прекращает разбор после как максимум `frac_digits` символов.

Если строка знака (**fac**. `negative_sign` или **fac**. `positive_sign`) имеет более одного элемента, сопоставляется только первый элемент, если элемент, равный **money_base::sign** появляется в шаблоне формата ( **fac**. `neg_format`). Любые остающиеся элементы сопоставляются в конце денежного поля ввода. Если ни одна из строк не имеет первого элемента, который соответствует следующему элементу в денежном поле ввода, строка знака считается пустой, а знак — положительным.

Если **iosbase**. [Флаги](../standard-library/ios-base-class.md#flags)  &  [showbase](../standard-library/ios-functions.md#showbase) имеет ненулевое значение, строка **fac**. `curr_symbol` должна соответствовать в том месте, где в шаблоне формата возникает элемент, равный **money_base::symbol**. В противном случае, если **money_base::symbol** возникает в конце шаблона формате и если не осталось элементов строки знака для сопоставления, символ валюты не сопоставляется. В противном случае символ валюты при необходимости сопоставляется.

Если в части значения числового поля ввода не появляется экземпляров **fac**. `thousands_sep` (если в шаблоне формата есть элемент, равный **money_base::value**), ограничения группировки не применяются. В противном случае применяются любые ограничения группировки, определяемые в **fac**. **grouping**. Обратите внимание, что результирующая последовательность цифр представляет собой целое число, чьи младшие десятичные цифры **fac**. `frac_digits` считаются находящимися справа от десятичного разделителя.

Произвольный пробел считается соответствующим, если в шаблоне формата появляется элемент, равный **money_base::space**, если он находится не в конце шаблона формата. В противном случае внутренние пробелы не сопоставляются. Элемент *CH* считается пробелом, если [use_facet](../standard-library/locale-functions.md#use_facet)  <  [CType](../standard-library/ctype-class.md) \< **CharType**> > ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). [имеет](../standard-library/ctype-class.md#is) **Размер (ctype_base:: Space**, *CH*) **`true`** .

### <a name="example"></a>Пример

См. пример для [get](#get), в котором вызывается `do_get`.

## <a name="money_getget"></a><a name="get"></a>money_get:: Get

Извлекает числовое значение из последовательности символов, представляющей денежное значение.

```cpp
iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*Intl*\
Логическое значение, указывающее тип символа валюты, ожидаемого в последовательности: **`true`** Если международная, то **`false`** если он является внутренним.

*Iosbase*\
Флаг формата, который при установке указывает, что символ валюты является необязательным. В противном случае он обязателен.

*С*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*val*\
Строка, хранящая преобразованную последовательность.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после денежного поля ввода.

### <a name="remarks"></a>Примечания

Обе функции элементов возвращают [do_get](#do_get) `(first, last, Intl, Iosbase, State, val)` .

### <a name="example"></a>Пример

```cpp
// money_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;

int main( )
{
   locale loc( "german_germany" );

   basic_stringstream< char > psz;
   psz << use_facet<moneypunct<char, 1> >(loc).curr_symbol() << "-1.000,56";
   basic_stringstream< char > psz2;
   psz2 << "-100056" << use_facet<moneypunct<char, 1> >(loc).curr_symbol();

   ios_base::iostate st = 0;
   long double fVal;

   psz.flags( psz.flags( )|ios_base::showbase );
   // Which forced the READING the currency symbol
   psz.imbue(loc);
   use_facet < money_get < char > >( loc ).
      get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter( 0 ), true, psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz.str( ) << ", intl = 1) FAILED"
           << endl;
   else
      cout << "money_get(" << psz.str( ) << ", intl = 1) = "
           << fVal/100.0 << endl;

   use_facet < money_get < char > >( loc ).
      get(basic_istream<char>::_Iter(psz2.rdbuf( )),
          basic_istream<char>::_Iter(0), false, psz2, st, fVal);

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz2.str( ) << ", intl = 0) FAILED"
           << endl;
   else
      cout << "money_get(" << psz2.str( ) << ", intl = 0) = "
           << fVal/100.0 << endl;
};
```

## <a name="money_getiter_type"></a><a name="iter_type"></a>money_get:: iter_type

Тип, который описывает итератор ввода.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра-шаблона **InputIterator**.

## <a name="money_getmoney_get"></a><a name="money_get"></a>money_get:: money_get

Конструктор для объектов типа `money_get`, используемых для извлечения числовых значений из последовательностей, представляющих денежные значения.

```cpp
explicit money_get(size_t _Refs = 0);
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

Конструктор инициализирует свой базовый объект с **языковым стандартом::**[Facet](../standard-library/locale-class.md#facet_class)(*_Refs*).

## <a name="money_getstring_type"></a><a name="string_type"></a>money_get:: string_type

Тип, который описывает строку символов типа **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Примечания

Тип описывает специализацию шаблона класса [basic_string](../standard-library/basic-string-class.md).

## <a name="see-also"></a>См. также статью

[\<locale>](../standard-library/locale.md)\
[Класс аспекта](../standard-library/locale-class.md#facet_class)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
