---
title: Класс codecvt
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
ms.openlocfilehash: 77af6b627847dbb16523c247f03f58e30aeef236
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230134"
---
# <a name="codecvt-class"></a>Класс codecvt

Шаблон класса, описывающий объект, который может служить в качестве аспекта языкового стандарта. Он может управлять преобразованиями между последовательностями значений, используемых для кодирования символов внутри программы, и последовательностями значений, используемых для кодирования символы вне программы.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, class Byte, class StateType>
class codecvt : public locale::facet, codecvt_base;
```

### <a name="parameters"></a>Параметры

*CharType*\
Тип, используемый внутри программы для кодирования символов.

*Двухбайтовых*\
Тип, используемый для кодирования символов вне программы.

*StateType*\
Тип, который можно использовать для представления промежуточных состояний преобразования между внутренними и внешними типами представлений символов.

## <a name="remarks"></a>Примечания

Шаблон класса описывает объект, который может служить в качестве [аспекта языкового стандарта](../standard-library/locale-class.md#facet_class), для управления преобразованиями последовательности значений типа *CharType* и последовательности значений типа *Byte*. Класс *StateType* характеризует преобразование, а объект класса *StateType* сохраняет все необходимые сведения о состоянии во время преобразования.

В внутренней кодировке используется представление с фиксированным числом байтов на символ, обычно либо тип **`char`** , либо тип **`wchar_t`** .

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического `id` объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в `id`.

Шаблонные версии [do_in](#do_in) и [do_out](#do_out) всегда возвращают `codecvt_base::noconv`.

Стандартная библиотека C++ определяет несколько явных специализаций:

```cpp
template<>
codecvt<wchar_t, char, mbstate_t>
```

выполняет преобразование **`wchar_t`** между **`char`** последовательностями и.

```cpp
template<>
codecvt<char16_t, char, mbstate_t>
```

Преобразование между **`char16_t`** последовательностями в кодировке UTF-16 и **`char`** последовательностями в кодировке UTF-8.

```cpp
template<>
codecvt<char32_t, char, mbstate_t>
```

Преобразует **`char32_t`** последовательности в кодировке UTF-32 (UCS-4) и **`char`** последовательности в кодировке UTF-8.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[codecvt](#codecvt)|Конструктор для объектов класса `codecvt`, который служит в качестве аспекта языкового стандарта для обработки преобразований.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[extern_type](#extern_type)|Тип символа, используемый для внешних представлений.|
|[intern_type](#intern_type)|Тип символа, используемый для внутренних представлений.|
|[state_type](#state_type)|Тип символа, который используется для представления промежуточных состояний во время преобразований между внутренними и внешними представлениями.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[always_noconv](#always_noconv)|Проверяет, не требуется ли выполнит преобразования.|
|[do_always_noconv](#do_always_noconv)|Виртуальная функция, вызываемая проверки того, не требуется ли выполнить преобразования.|
|[do_encoding](#do_encoding)|Виртуальная функция, которая проверяет, зависит ли кодировка потока от состояния, независимо от того, что `Byte` соотношение между `Byte` используемыми значениями и `CharType` получаемыми значениями является константой, и, если это так, определяет значение этого соотношения.|
|[do_in](#do_in)|Виртуальная функция, вызываемая для преобразования последовательности внутренних `Byte` значений в последовательность внешних `CharType` значений.|
|[do_length](#do_length)|Виртуальная функция, определяющая `Byte` , сколько значений заданной последовательности внешних `Byte` значений создает не больше заданного количества внутренних `CharType` значений и возвращает это количество `Byte` значений.|
|[do_max_length](#do_max_length)|Виртуальная функция, возвращающая максимальное число внешних байтов, необходимых для создания одного внутреннего `CharType`.|
|[do_out](#do_out)|Виртуальная функция, вызываемая для преобразования последовательности внутренних `CharType` значений в последовательность внешних байтов.|
|[do_unshift](#do_unshift)|Виртуальная функция, вызываемая для предоставления `Byte` значений, необходимых в преобразовании, зависящем от состояния, для завершения последнего символа в последовательности `Byte` значений.|
|[encoding](#encoding)|Проверяет, зависит ли кодировка `Byte` потока от состояния, независимо от того, какое отношение между `Byte` используемыми значениями и `CharType` какие значения являются константами, и, если это так, определяет значение этого отношения.|
|[in](#in)|Преобразует внешнее представление последовательности `Byte` значений во внутреннее представление последовательности `CharType` значений.|
|[length](#length)|Определяет, сколько `Byte` значений из заданной последовательности внешних `Byte` значений создает не больше заданного числа внутренних `CharType` значений и возвращает это количество `Byte` значений.|
|[max_length](#max_length)|Возвращает максимальное количество внешних `Byte` значений, необходимых для создания одного внутреннего объекта `CharType` .|
|[out](#out)|Преобразует последовательность внутренних `CharType` значений в последовательность внешних `Byte` значений.|
|[unshift](#unshift)|Предоставляет внешние `Byte` значения, необходимые для преобразования, зависящего от состояния, для завершения последнего символа в последовательности `Byte` значений.|

## <a name="requirements"></a>Требования

**Заголовок:**\<locale>

**Пространство имен:** std

## <a name="codecvtalways_noconv"></a><a name="always_noconv"></a>codecvt:: always_noconv

Проверяет, нужно ли выполнять преобразования.

```cpp
bool always_noconv() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, равное, **`true`** если не требуется выполнять преобразования; **`false`** Если необходимо выполнить хотя бы одну операцию.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_always_noconv](#do_always_noconv).

### <a name="example"></a>Пример

```cpp
// codecvt_always_noconv.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result1 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;

   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).always_noconv( );

   if ( result2 )
      cout << "No conversion is needed." << endl;
   else
      cout << "At least one conversion is required." << endl;
}
```

```Output
No conversion is needed.
At least one conversion is required.
```

## <a name="codecvtcodecvt"></a><a name="codecvt"></a>codecvt:: codecvt

Конструктор для объектов класса codecvt, который служит в качестве аспекта языкового стандарта для обработки преобразований.

```cpp
explicit codecvt(size_t refs = 0);
```

### <a name="parameters"></a>Параметры

*ReFS*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Примечания

Возможные значения для параметра *ReFS* и их значимости:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- 2: эти значения не определены.

Конструктор инициализирует свой `locale::facet` базовый объект с [языковым стандартом:: Facet](../standard-library/locale-class.md#facet_class) `(refs)` .

## <a name="codecvtdo_always_noconv"></a><a name="do_always_noconv"></a>codecvt::d o_always_noconv

Виртуальная функция, вызываемая для проверки того, нужно ли выполнять преобразования.

```cpp
virtual bool do_always_noconv() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Защищенная виртуальная функция – член возвращает, **`true`** только если при каждом вызове метода [do_in](#do_in) или [do_out](#do_out) возвращается значение `noconv` .

Версия шаблона всегда возвращает значение **`true`** .

### <a name="example"></a>Пример

См. пример для [always_noconv](#always_noconv), в котором вызывается `do_always_noconv`.

## <a name="codecvtdo_encoding"></a><a name="do_encoding"></a>codecvt::d o_encoding

Виртуальная функция, которая проверяет, зависит ли кодировка потока от состояния, независимо от того, что `Byte` соотношение между `Byte` используемыми значениями и `CharType` получаемыми значениями является константой и, если это так, определяет значение этого соотношения.

```cpp
virtual int do_encoding() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Защищенная функция-член возвращает:

- -1, если кодировка последовательностей типа `extern_type` зависит от состояния.

- 0, если кодировка включает последовательности переменной длины;

- *N*, если кодировка включает только последовательности длиной *N*

### <a name="example"></a>Пример

См. пример для [encoding](#encoding), в котором вызывается `do_encoding`.

## <a name="codecvtdo_in"></a><a name="do_in"></a>codecvt::d o_in

Виртуальная функция, вызываемая для преобразования последовательности внешних `Byte` значений в последовательность внутренних `CharType` значений.

```cpp
virtual result do_in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Параметры

*с*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало последовательности для преобразования.

*last1*\
Указатель на конец последовательности для преобразования.

*next1*\
Указатель за пределами преобразованной последовательности для первого непреобразованного символа.

*first2*\
Указатель на начало преобразованной последовательности.

*last2*\
Указатель на конец преобразованной последовательности.

*next2*\
Указатель на объект `CharType` , который поступает после последнего преобразования `CharType` , к первому неизмененному символу в последовательности назначения.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение, которое указывает успех, частичный успех или сбой операции. Функция возвращает:

- `codecvt_base::error`значение, если исходная последовательность сформирована неправильно.

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`значение, если преобразование выполнено.

- `codecvt_base::partial`значение, если источник недостаточен или если место назначения недостаточно велико для успешности преобразования.

### <a name="remarks"></a>Примечания

*состояние* должно представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. В противном случае сохраненное значение будет незаданным.

### <a name="example"></a>Пример

См. пример для [in](#in), в котором вызывается `do_in`.

## <a name="codecvtdo_length"></a><a name="do_length"></a>codecvt::d o_length

Виртуальная функция, определяющая `Byte` , сколько значений заданной последовательности внешних `Byte` значений создает не больше заданного количества внутренних `CharType` значений и возвращает это количество `Byte` значений.

```cpp
virtual int do_length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Параметры

*с*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало внешней последовательности.

*last1*\
Указатель на конец внешней последовательности.

*len2*\
Максимальное число `Byte` значений, которое может быть возвращено функцией члена.

### <a name="return-value"></a>Возвращаемое значение

Целое число, представляющее число преобразований, не превышающих значение *len2*, определяемое внешней исходной последовательностью в [ `first1` , `last1` ).

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член фактически вызывает `do_in( state, first1, last1, next1, buf, buf + len2, next2)` *состояние* (копию состояния), некоторый буфер `buf` , указатели `next1` и `next2` .

Затем он возвращает `next2`  -  `buf` . Таким же результатом считается максимальное число преобразований, не превышающих *len2*, определяемое исходной последовательностью в [ `first1` , `last1` ).

Версия шаблона всегда возвращает меньшее значение *last1*  -  *first1* и *len2*.

### <a name="example"></a>Пример

См. пример для [length](#length), который вызывает `do_length` .

## <a name="codecvtdo_max_length"></a><a name="do_max_length"></a>codecvt::d o_max_length

Виртуальная функция, возвращающая максимальное количество внешних `Byte` значений, необходимых для получения одного внутреннего объекта `CharType` .

```cpp
virtual int do_max_length() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное количество значений, `Byte` необходимое для его создания `CharType` .

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция с членом возвращает максимальное допустимое значение, которое может быть возвращено [do_length](#do_length) `( first1, last1, 1)` для произвольных допустимых значений *first1* и *last1*.

### <a name="example"></a>Пример

См. пример для [max_length](#max_length), в котором вызывается `do_max_length`.

## <a name="codecvtdo_out"></a><a name="do_out"></a>codecvt::d o_out

Виртуальная функция, вызываемая для преобразования последовательности внутренних `CharType` значений в последовательность внешних `Byte` значений.

```cpp
virtual result do_out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Параметры

*с*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало последовательности для преобразования.

*last1*\
Указатель на конец последовательности для преобразования.

*next1*\
Ссылка на указатель на первый непреобразованный объект `CharType` после последнего `CharType` преобразования.

*first2*\
Указатель на начало преобразованной последовательности.

*last2*\
Указатель на конец преобразованной последовательности.

*next2*\
Ссылка на указатель на первый непреобразованный объект `Byte` после последнего `Byte` преобразования.

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает:

- `codecvt_base::error`значение, если исходная последовательность сформирована неправильно.

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`значение, если преобразование выполнено.

- `codecvt_base::partial`Если источник недостаточен или место назначения недостаточно велико для успешности преобразования.

### <a name="remarks"></a>Примечания

*состояние* должно представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. В противном случае сохраненное значение будет незаданным.

### <a name="example"></a>Пример

См. пример для [out](#out), в котором вызывается `do_out`.

## <a name="codecvtdo_unshift"></a><a name="do_unshift"></a>codecvt::d o_unshift

Виртуальная функция, вызываемая для предоставления `Byte` значений, необходимых в преобразовании, зависящем от состояния, для завершения последнего символа в последовательности `Byte` значений.

```cpp
virtual result do_unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Параметры

*с*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first2*\
Указатель первой позиции в целевом диапазоне.

*last2*\
Указатель последней позиции в целевом диапазоне.

*next2*\
Указатель на первый неизмененный элемент в целевой последовательности.

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает:

- `codecvt_base::error`Если *State* представляет недопустимое состояние

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`Если преобразование выполнено

- `codecvt_base::partial`Если назначение недостаточно велико для успешности преобразования

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается преобразовать исходный элемент `CharType` (0) в конечную последовательность, которая хранится в [ `first2` , `last2` ), за исключением завершающего элемента `Byte` (0). Он всегда сохраняет в *Next2* указатель на первый неизмененный элемент в конечной последовательности.

Объект _ *State* должен представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. Как правило, преобразование исходного элемента `CharType` (0) оставляет текущее состояние в исходном состоянии преобразования.

### <a name="example"></a>Пример

См. пример для [unshift](#unshift), в котором вызывается `do_unshift`.

## <a name="codecvtencoding"></a><a name="encoding"></a>codecvt:: Encoding

Проверяет, зависит ли кодировка `Byte` потока от состояния, независимо от того, какое отношение между `Byte` используемыми значениями и `CharType` какие значения являются константами, и, если это так, определяет значение этого отношения.

```cpp
int encoding() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Если возвращаемое значение положительное, это значение является константным числом `Byte` символов, необходимых для создания `CharType` символа.

Защищенная функция-член возвращает:

- -1, если кодировка последовательностей типа `extern_type` зависит от состояния.

- 0, если кодировка включает последовательности переменной длины;

- *N*, если кодировка включает только последовательности длиной *N*.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_encoding](#do_encoding).

### <a name="example"></a>Пример

```cpp
// codecvt_encoding.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc ( "German_Germany" );
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );
   cout << result1 << endl;
}
```

```Output
1
1
1
```

## <a name="codecvtextern_type"></a><a name="extern_type"></a>codecvt:: extern_type

Тип символа, используемый для внешних представлений.

```cpp
typedef Byte extern_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Byte`.

## <a name="codecvtin"></a><a name="in"></a>codecvt:: in

Преобразует внешнее представление последовательности `Byte` значений во внутреннее представление последовательности `CharType` значений.

```cpp
result in(
    StateType& state,
    const Byte* first1,
    const Byte* last1,
    const Byte*& next1,
    CharType* first2,
    CharType* last2,
    CharType*& next2,) const;
```

### <a name="parameters"></a>Параметры

*с*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало последовательности для преобразования.

*last1*\
Указатель на конец последовательности для преобразования.

*next1*\
Указатель за пределами преобразованной последовательности для первого непреобразованного символа.

*first2*\
Указатель на начало преобразованной последовательности.

*last2*\
Указатель на конец преобразованной последовательности.

*next2*\
Указатель на объект `CharType` , который поступает после последнего преобразования в `Chartype` первый неизмененный символ в конечной последовательности.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение, которое указывает успех, частичный успех или сбой операции. Функция возвращает:

- `codecvt_base::error`значение, если исходная последовательность сформирована неправильно.

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`значение, если преобразование выполнено.

- `codecvt_base::partial`Если источник недостаточен или место назначения недостаточно велико для успешности преобразования.

### <a name="remarks"></a>Примечания

*состояние* должно представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. После частичного преобразования должно быть задано *состояние* , чтобы разрешить возобновление преобразования при поступлении новых символов.

Функция члена возвращает [do_in](#do_in) `( state, first1,  last1,  next1, first2, last2,  next2)` .

### <a name="example"></a>Пример

```cpp
// codecvt_in.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string to be converted!";
   wchar_t pwszInt [LEN+1];
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));
   const char* pszNext;
   wchar_t* pwszNext;
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).in( state,
          pszExt, &pszExt[strlen(pszExt)], pszNext,
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );
   pwszInt[strlen(pszExt)] = 0;
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )
   << L"The converted string is:\n ["
   << &pwszInt[0]
   << L"]" << endl;
   exit(-1);
}
```

```Output
It worked! The converted string is:
[This is the string to be converted!]
```

## <a name="codecvtintern_type"></a><a name="intern_type"></a>codecvt:: intern_type

Тип символа, используемый для внутренних представлений.

```cpp
typedef CharType intern_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `CharType`.

## <a name="codecvtlength"></a><a name="length"></a>codecvt:: Length

Определяет, сколько `Byte` значений из заданной последовательности внешних `Byte` значений создает не больше заданного числа внутренних `CharType` значений и возвращает это количество `Byte` значений.

```cpp
int length(
    const StateType& state,
    const Byte* first1,
    const Byte* last1,
    size_t len2) const;
```

### <a name="parameters"></a>Параметры

*с*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало внешней последовательности.

*last1*\
Указатель на конец внешней последовательности.

*len2*\
Максимальное число объектов Byte, которое может возвратить функция-член.

### <a name="return-value"></a>Возвращаемое значение

Целое число, представляющее число преобразований, не превышающих значение *len2*, определяемое внешней исходной последовательностью в [ `first1` , `last1` ).

### <a name="remarks"></a>Примечания

Функция члена возвращает [do_length](#do_length) `( state, first1, last1, len2)` .

### <a name="example"></a>Пример

```cpp
// codecvt_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;
#define LEN 90
int main( )
{
   char* pszExt = "This is the string whose length is to be measured!";
   mbstate_t state = {0};
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
     ( loc ).length( state,
          pszExt, &pszExt[strlen(pszExt)], LEN );
   cout << "The length of the string is: ";
   wcout << res;
   cout << "." << endl;
   exit(-1);
}
```

```Output
The length of the string is: 50.
```

## <a name="codecvtmax_length"></a><a name="max_length"></a>codecvt:: max_length

Возвращает максимальное количество внешних `Byte` значений, необходимых для создания одного внутреннего объекта `CharType` .

```cpp
int max_length() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное количество значений, `Byte` необходимое для его создания `CharType` .

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_max_length](#do_max_length).

### <a name="example"></a>Пример

```cpp
// codecvt_max_length.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc( "C");//English_Britain" );//German_Germany
   int res = use_facet<codecvt<char, char, mbstate_t> >
     ( loc ).max_length( );
   wcout << res << endl;
}
```

```Output
1
```

## <a name="codecvtout"></a><a name="out"></a>codecvt:: out

Преобразует последовательность внутренних `CharType` значений в последовательность внешних `Byte` значений.

```cpp
result out(
    StateType& state,
    const CharType* first1,
    const CharType* last1,
    const CharType*& next1,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Параметры

*с*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first1*\
Указатель на начало последовательности для преобразования.

*last1*\
Указатель на конец последовательности для преобразования.

*next1*\
Ссылка на указатель на первый непреобразованный объект `CharType` после последнего `CharType` преобразования.

*first2*\
Указатель на начало преобразованной последовательности.

*last2*\
Указатель на конец преобразованной последовательности.

*next2*\
Ссылка на указатель на первый непреобразованный объект `Byte` после последнего преобразования `Byte` .

### <a name="return-value"></a>Возвращаемое значение

Функция члена возвращает [do_out](#do_out) `( state, first1, last1, next1, first2, last2, next2)` .

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в описании [codecvt::do_out](#do_out).

### <a name="example"></a>Пример

```cpp
// codecvt_out.cpp
// compile with: /EHsc
#define _INTL
#include <locale>
#include <iostream>
#include <wchar.h>
using namespace std;
#define LEN 90
int main( )
{
   char pszExt[LEN+1];
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );
   char* pszNext;
   const wchar_t* pwszNext;
   mbstate_t state;
   locale loc("C");//English_Britain");//German_Germany
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >
      ( loc ).out( state,
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );
   pszExt[wcslen( pwszInt )] = 0;
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )
   << "The converted string is:\n ["
   << &pszExt[0]
   << "]" << endl;
}
```

```Output
It worked: The converted string is:
[This is the wchar_t string to be converted.]
```

## <a name="codecvtstate_type"></a><a name="state_type"></a>codecvt:: state_type

Тип символа, который используется для представления промежуточных состояний во время преобразований между внутренними и внешними представлениями.

```cpp
typedef StateType state_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `StateType`.

## <a name="codecvtunshift"></a><a name="unshift"></a>codecvt:: unshift

Предоставляет `Byte` значения, необходимые для преобразования, зависящего от состояния, для завершения последнего символа в последовательности `Byte` значений.

```cpp
result unshift(
    StateType& state,
    Byte* first2,
    Byte* last2,
    Byte*& next2) const;
```

### <a name="parameters"></a>Параметры

*с*\
Состояние преобразования, которое поддерживается между вызовами функции-члена.

*first2*\
Указатель первой позиции в целевом диапазоне.

*last2*\
Указатель последней позиции в целевом диапазоне.

*next2*\
Указатель на первый неизмененный элемент в целевой последовательности.

### <a name="return-value"></a>Возвращаемое значение

Функция возвращает:

- `codecvt_base::error`Если State представляет недопустимое состояние.

- `codecvt_base::noconv`, если функция не выполняет преобразование;

- `codecvt_base::ok`значение, если преобразование выполнено.

- `codecvt_base::partial`значение, если назначение недостаточно велико для успешности преобразования.

### <a name="remarks"></a>Примечания

Защищенная виртуальная функция-член пытается преобразовать исходный элемент `CharType` (0) в конечную последовательность, которая хранится в [ `first2` , `last2` ), за исключением завершающего элемента `Byte` (0). Он всегда сохраняет в *Next2* указатель на первый неизмененный элемент в конечной последовательности.

*состояние* должно представлять начальное состояние преобразования в начале новой исходной последовательности. Функция изменяет это сохраненное значение так, чтобы отразить текущее состояние успешного преобразования. Как правило, преобразование исходного элемента `CharType` (0) оставляет текущее состояние в исходном состоянии преобразования.

Функция члена возвращает [do_unshift](#do_unshift) `( state, first2, last2, next2 )` .

## <a name="see-also"></a>См. также раздел

[\<locale>](../standard-library/locale.md)\
[Кодовые страницы](../c-runtime-library/code-pages.md)\
[Имена языковых стандартов, языки и строки страны или региона](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
