---
title: Класс ctype
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype
- xlocale/std::ctype::char_type
- xlocale/std::ctype::do_is
- xlocale/std::ctype::do_narrow
- xlocale/std::ctype::do_scan_is
- xlocale/std::ctype::do_scan_not
- xlocale/std::ctype::do_tolower
- xlocale/std::ctype::do_toupper
- xlocale/std::ctype::do_widen
- xlocale/std::ctype::is
- xlocale/std::ctype::narrow
- xlocale/std::ctype::scan_is
- xlocale/std::ctype::scan_not
- xlocale/std::ctype::tolower
- xlocale/std::ctype::toupper
- xlocale/std::ctype::widen
helpviewer_keywords:
- std::ctype [C++]
- std::ctype [C++], char_type
- std::ctype [C++], do_is
- std::ctype [C++], do_narrow
- std::ctype [C++], do_scan_is
- std::ctype [C++], do_scan_not
- std::ctype [C++], do_tolower
- std::ctype [C++], do_toupper
- std::ctype [C++], do_widen
- std::ctype [C++], is
- std::ctype [C++], narrow
- std::ctype [C++], scan_is
- std::ctype [C++], scan_not
- std::ctype [C++], tolower
- std::ctype [C++], toupper
- std::ctype [C++], widen
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
ms.openlocfilehash: a0e3aad99c335f1a907189ee84e55a38e41b62e1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222515"
---
# <a name="ctype-class"></a>Класс ctype

Класс, предоставляющий аспект, используемый для классификации символов, преобразования из верхнего и нижнего регистра, а также преобразования между собственной кодировкой и кодировкой, используемой языковым стандартом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType>
class ctype : public ctype_base;
```

### <a name="parameters"></a>Параметры

*CharType*\
Тип, используемый внутри программы для кодирования символов.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в `id`. Критерии классификации получают вложенный тип битовой маски в базовом классе ctype_base.

Стандартная библиотека C++ определяет две явные специализации этого шаблона класса:

- `ctype<char>`, явная специализация, различия которой описаны отдельно. Дополнительные сведения см. в [статье &lt; &gt; класс CType char](../standard-library/ctype-char-class.md).

- `ctype<wchar_t>`, который обрабатывает элементы как широкие символы.

Другие специализации шаблона класса `ctype<CharType>` :

- Преобразование значения *CH* типа *CharType* в значение типа **`char`** с выражением `(char)ch` .

- Преобразование значения *Byte* типа **`char`** в значение типа *CharType* с помощью выражения `CharType(byte)` .

Все остальные операции выполняются по **`char`** значениям так же, как и для явной специализации `ctype<char>` .

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[CType](#ctype)|Конструктор для объектов класса `ctype`, которые служат в качестве аспектов языкового стандарта для символов.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, который описывает символ, используемый языковым стандартом.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[do_is](#do_is)|Виртуальная функция, вызываемая для проверки того, есть ли у отдельного символа определенный атрибут, или для классификации атрибутов каждого символа в диапазоне и сохранения их в массиве.|
|[do_narrow](#do_narrow)|Виртуальная функция, вызываемая для преобразования символа типа `CharType` , используемого локальным языком, в соответствующий символ типа **`char`** в собственной кодировке.|
|[do_scan_is](#do_scan_is)|Виртуальная функция, вызываемая для обнаружения первого символа, соответствующего указанной маске, в диапазоне.|
|[do_scan_not](#do_scan_not)|Виртуальная функция, вызываемая для обнаружения первого символа, не соответствующего указанной маске, в диапазоне.|
|[do_tolower](#do_tolower)|Виртуальная функция, вызываемая для преобразования символа или диапазона символов в нижний регистр.|
|[do_toupper](#do_toupper)|Виртуальная функция, вызываемая для преобразования символа или диапазона символов в верхний регистр.|
|[do_widen](#do_widen)|Виртуальная функция, вызываемая для преобразования символа типа **`char`** в собственной кодировке в соответствующий символ типа `CharType` , используемый языковым стандартом.|
|[is](#is)|Проверяет, есть ли у отдельного символа определенный атрибут, или классифицирует атрибуты каждого символа в диапазоне и сохраняет их в массиве.|
|[narrow](#narrow)|Преобразовывает символ типа `CharType`, используемый языковым стандартом, в соответствующий символ типа char в исходной кодировке.|
|[scan_is](#scan_is)|Обнаруживает первый символ, соответствующий указанной маске, в диапазоне.|
|[scan_not](#scan_not)|Обнаруживает первый символ, несоответствующий указанной маске, в диапазоне.|
|[ToLower](#tolower)|Преобразует символ или диапазон символов в нижний регистр.|
|[ToUpper](#toupper)|Преобразует символ или диапазон символов в верхний регистр.|
|[widen](#widen)|Преобразует символ типа **`char`** в собственной кодировке в соответствующий символ типа `CharType` , используемый языковым стандартом.|

## <a name="requirements"></a>Требования

**Заголовок:**\<locale>

**Пространство имен:** std

## <a name="ctypechar_type"></a><a name="char_type"></a>CType:: char_type

Тип, который описывает символ, используемый языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона *Chartype*.

### <a name="example"></a>Пример

Пример, в котором `char_type` используется в качестве возвращаемого значения, см. в описании функции-члена [widen](#widen).

## <a name="ctypectype"></a><a name="ctype"></a>CType:: CType

Конструктор для объектов класса ctype, которые служат в качестве аспектов языкового стандарта для символов.

```cpp
explicit ctype(size_t _Refs = 0);
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

Конструктор инициализирует свой базовый объект `locale::facet` с **locale::**[facet](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="ctypedo_is"></a><a name="do_is"></a>CType::d o_is

Виртуальная функция, вызываемая для проверки того, есть ли у отдельного символа определенный атрибут, или для классификации атрибутов каждого символа в диапазоне и сохранения их в массиве.

```cpp
virtual bool do_is(
    mask maskVal,
    CharType ch) const;

virtual const CharType *do_is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>Параметры

*масквал*\
Значение маски, для которого должен тестироваться символ.

*канал*\
Символ, атрибуты которого должны тестироваться.

*first*\
Указатель на первый символ в диапазоне, атрибуты которого должны классифицироваться.

*last*\
Указатель на символ, следующий сразу за последним символом в диапазоне, атрибуты которого должны классифицироваться.

*dest*\
Указатель на начало массива, где должны храниться значения маски, характеризующие атрибуты каждого из символов.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает логическое значение, равное, **`true`** Если проверяемый символ имеет атрибут, описанный в значении маски. значение, **`false`** если не удается получить атрибут.

Вторая функция-член возвращает массив, содержащий значения маски, характеризующие атрибуты каждого символа в диапазоне.

### <a name="remarks"></a>Примечания

Значения маски, классифицирующие атрибуты символов, предоставляются классом [ctype_base](../standard-library/ctype-base-class.md), от которого производится класс ctype. Первая функция-член может принимать для своего первого параметра выражения, которые называются битовыми масками и формируются из сочетания значений маски логическими побитовыми операторами (&#124;, &, ^, ~).

### <a name="example"></a>Пример

См. пример для [is](#is), в котором вызывается `do_is`.

## <a name="ctypedo_narrow"></a><a name="do_narrow"></a>CType::d o_narrow

Виртуальная функция, вызываемая для преобразования символа типа `CharType` , используемого локальным языком, в соответствующий символ типа **`char`** в собственной кодировке.

```cpp
virtual char do_narrow(
    CharType ch,
    char default = '\0') const;

virtual const CharType* do_narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>Параметры

*канал*\
Символ типа `Chartype`, используемого языковым стандартом, который требуется преобразовать.

*параметры*\
Значение по умолчанию, присваиваемое функцией члена символам типа `CharType` , у которых нет аналоговых символов типа **`char`** .

*first*\
Указатель на первый символ в диапазоне символов для преобразования.

*last*\
Указатель на символ, следующий сразу за последним символом в преобразуемом диапазоне символов.

*dest*\
Указатель const на первый символ типа **`char`** в диапазоне назначения, в котором хранится преобразованный диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая Защищенная функция-член возвращает собственный символ типа char, соответствующий символу параметра типа `CharType` или *Default* , если не определен аналог.

Вторая защищенная функция-член возвращает указатель на целевой диапазон собственных символов, преобразованных из символов типа `CharType`.

### <a name="remarks"></a>Примечания

Вторая Защищенная функция шаблона элемента сохраняет в `dest` [ `I` ] значение `do_narrow` ( `first` [ `I` ], `default` ) для `I` в интервале [0, `last`  -  `first` ).

### <a name="example"></a>Пример

См. пример для [narrow](#narrow), в котором вызывается `do_narrow`.

## <a name="ctypedo_scan_is"></a><a name="do_scan_is"></a>CType::d o_scan_is

Виртуальная функция, вызываемая для обнаружения первого символа, соответствующего указанной маске, в диапазоне.

```cpp
virtual const CharType *do_scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*масквал*\
Значение маски для сопоставления с символом.

*first*\
Указатель на первый символ в просматриваемом диапазоне символов.

*last*\
Указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, соответствующий указанной маске. Если такого значения не существует, функция возвращает *last*.

### <a name="remarks"></a>Примечания

Защищенная функция-член возвращает наименьший указатель `ptr` в диапазоне [ `first` , `last` ), для которого [do_is](#do_is)( `maskVal` , \* `ptr` ) имеет значение true.

### <a name="example"></a>Пример

См. пример для [scan_is](#scan_is), в котором вызывается `do_scan_is`.

## <a name="ctypedo_scan_not"></a><a name="do_scan_not"></a>CType::d o_scan_not

Виртуальная функция, вызываемая для обнаружения первого символа, не соответствующего указанной маске, в диапазоне.

```cpp
virtual const CharType *do_scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*масквал*\
Значение маски, которому не должен соответствовать символ.

*first*\
Указатель на первый символ в просматриваемом диапазоне символов.

*last*\
Указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, не соответствующий указанной маске. Если такого значения не существует, функция возвращает *last*.

### <a name="remarks"></a>Примечания

Защищенная функция-член возвращает наименьший указатель `ptr` в диапазоне [ `first` , `last` ), для которого [do_is](#do_is)( `maskVal` , \* `ptr` ) имеет значение false.

### <a name="example"></a>Пример

См. пример для [scan_not](#scan_not), в котором вызывается `do_scan_not`.

## <a name="ctypedo_tolower"></a><a name="do_tolower"></a>CType::d o_tolower

Виртуальная функция, вызываемая для преобразования символа или диапазона символов в нижний регистр.

```cpp
virtual CharType do_tolower(CharType ch) const;

virtual const CharType *do_tolower(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*канал*\
Символ для преобразования в нижний регистр.

*first*\
Указатель на первый символ в диапазоне символов, регистр которых нужно преобразовать.

*last*\
Указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого нужно преобразовать.

### <a name="return-value"></a>Возвращаемое значение

Первая Защищенная функция Member возвращает строчную форму параметра *CH*. Если форма нижнего регистра не существует, она возвращает *CH*. Вторая Защищенная функция Member возвращает *last*.

### <a name="remarks"></a>Примечания

Вторая Защищенная функция-шаблон элемента заменяет каждый элемент `first` [ `I` ] для `I` в интервале [0, `last`  -  `first` ) на `do_tolower` ( `first` [ `I` ]).

### <a name="example"></a>Пример

См. пример для [tolower](#tolower), в котором вызывается `do_tolower`.

## <a name="ctypedo_toupper"></a><a name="do_toupper"></a>CType::d o_toupper

Виртуальная функция, вызываемая для преобразования символа или диапазона символов в верхний регистр.

```cpp
virtual CharType do_toupper(CharType ch) const;

virtual const CharType *do_toupper(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*канал*\
Символ для преобразования в верхний регистр.

*first*\
Указатель на первый символ в диапазоне символов, регистр которых нужно преобразовать.

*last*\
Указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого нужно преобразовать.

### <a name="return-value"></a>Возвращаемое значение

Первая Защищенная функция Member возвращает прописную форму параметра *CH*. Если форма в верхнем регистре не существует, она возвращает *CH*. Вторая Защищенная функция Member возвращает *last*.

### <a name="remarks"></a>Примечания

Вторая Защищенная функция-шаблон элемента заменяет каждый элемент `first` [ `I` ] для `I` в интервале [0, `last`  -  `first` ) на `do_toupper` ( `first` [ `I` ]).

### <a name="example"></a>Пример

См. пример для [toupper](#toupper), в котором вызывается `do_toupper`.

## <a name="ctypedo_widen"></a><a name="do_widen"></a>CType::d o_widen

Виртуальная функция, вызываемая для преобразования символа типа **`char`** в собственной кодировке в соответствующий символ типа `CharType` , используемый языковым стандартом.

```cpp
virtual CharType do_widen(char byte) const;

virtual const char *do_widen(
    const char* first,
    const char* last,
    CharType* dest) const;
```

### <a name="parameters"></a>Параметры

*двухбайтовых*\
Символ типа **`char`** в собственной кодировке для преобразования.

*first*\
Указатель на первый символ в диапазоне символов для преобразования.

*last*\
Указатель на символ, следующий сразу за последним символом в преобразуемом диапазоне символов.

*dest*\
Указатель на первый символ типа `CharType` в целевом диапазоне, который хранит преобразуемый диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая Защищенная функция Member возвращает символ типа `CharType` , соответствующий символу параметра собственного типа **`char`** .

Вторая Защищенная функция-член возвращает указатель на целевой диапазон символов типа `CharType` , используемого языковым стандартом, преобразованных из машинных символов типа **`char`** .

### <a name="remarks"></a>Примечания

Вторая защищенная функция-член шаблона сохраняет в `dest`[`I`] значение `do_widen`(`first`[`I`]) для `I` в диапазоне [0, `last` - `first`).

### <a name="example"></a>Пример

См. пример для [widen](#widen), в котором вызывается `do_widen`.

## <a name="ctypeis"></a><a name="is"></a>CType:: является

Проверяет, есть ли у отдельного символа определенный атрибут, или классифицирует атрибуты каждого символа в диапазоне и сохраняет их в массиве.

```cpp
bool is(mask maskVal, CharType ch) const;

const CharType *is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>Параметры

*масквал*\
Значение маски, для которого должен тестироваться символ.

*канал*\
Символ, атрибуты которого должны тестироваться.

*first*\
Указатель на первый символ в диапазоне, атрибуты которого должны классифицироваться.

*last*\
Указатель на символ, следующий сразу за последним символом в диапазоне, атрибуты которого должны классифицироваться.

*dest*\
Указатель на начало массива, где должны храниться значения маски, характеризующие атрибуты каждого из символов.

### <a name="return-value"></a>Возвращаемое значение

Первая функция – член возвращает, **`true`** Если проверяемый символ имеет атрибут, описанный в значении маски. значение, **`false`** если не удается получить атрибут.

Вторая функция-член возвращает указатель на последний символ в диапазоне, атрибуты которого должны классифицироваться.

### <a name="remarks"></a>Примечания

Значения маски, классифицирующие атрибуты символов, предоставляются классом [ctype_base](../standard-library/ctype-base-class.md), от которого производится класс ctype. Первая функция-член может принимать для своего первого параметра выражения, которые называются битовыми масками и формируются из сочетания значений маски логическими побитовыми операторами (&#124;, &, ^, ~).

### <a name="example"></a>Пример

```cpp
// ctype_is.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main() {
   locale loc1 ( "German_Germany" ), loc2 ( "English_Australia" );

   if (use_facet<ctype<char> > ( loc1 ).is( ctype_base::alpha, 'a' ))
      cout << "The character 'a' in locale loc1 is alphabetic."
           << endl;
   else
      cout << "The character 'a' in locale loc1 is not alphabetic."
           << endl;

   if (use_facet<ctype<char> > ( loc2 ).is( ctype_base::alpha, '!' ))
      cout << "The character '!' in locale loc2 is alphabetic."
           << endl;
   else
      cout << "The character '!' in locale loc2 is not alphabetic."
           << endl;

   char *string = "Hello, my name is John!";
   ctype<char>::mask maskarray[30];
   use_facet<ctype<char> > ( loc2 ).is(
      string, string + strlen(string), maskarray );
   for (unsigned int i = 0; i < strlen(string); i++) {
      cout << string[i] << ": "
           << (maskarray[i] & ctype_base::alpha  "alpha"
                                                : "not alpha")
           << endl;;
   };
}
```

## <a name="ctypenarrow"></a><a name="narrow"></a>CType:: Narrow

Преобразует символы типа `CharType` , используемые локальными языками, в соответствующие символы типа **`char`** в собственной кодировке.

```cpp
char narrow(CharType ch, char default = '\0') const;

const CharType* narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>Параметры

*канал*\
Символ типа `Chartype`, используемого языковым стандартом, который требуется преобразовать.

*параметры*\
Значение по умолчанию, присваиваемое функцией члена символам типа `CharType` , у которых нет аналоговых символов типа **`char`** .

*first*\
Указатель на первый символ в диапазоне символов для преобразования.

*last*\
Указатель на символ, следующий сразу за последним символом в преобразуемом диапазоне символов.

*dest*\
Указатель const на первый символ типа **`char`** в диапазоне назначения, в котором хранится преобразованный диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает собственный символ типа **`char`** , соответствующий символу параметра типа, `CharType default` Если определено не аналог.

Вторая функция-член возвращает указатель на целевой диапазон собственных символов, преобразованных из символов типа `CharType`.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [do_narrow](#do_narrow)( `ch` , `default` ). Вторая функция-член возвращает [do_narrow](#do_narrow) ( `first` , `last` , `default` , `dest` ). Только основные исходные символы всегда имеют уникальный прообраз `CharType` в `narrow`. Для этих базовых исходных символов хранится следующий инвариант: `narrow` ([widen](#widen) (**c**), 0) == **c**.

### <a name="example"></a>Пример

```cpp
// ctype_narrow.cpp
// compile with: /EHsc /W3
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "english" );
   wchar_t *str1 = L"\x0392fhello everyone";
   char str2 [16];
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).narrow
      ( str1, str1 + wcslen(str1), 'X', &str2[0] ) != 0);  // C4996
   str2[wcslen(str1)] = '\0';
   wcout << str1 << endl;
   cout << &str2[0] << endl;
}
```

```Output
Xhello everyone
```

## <a name="ctypescan_is"></a><a name="scan_is"></a>CType:: scan_is

Обнаруживает первый символ, соответствующий указанной маске, в диапазоне.

```cpp
const CharType *scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*масквал*\
Значение маски для сопоставления с символом.

*first*\
Указатель на первый символ в просматриваемом диапазоне символов.

*last*\
Указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, соответствующий указанной маске. Если такого значения не существует, функция возвращает *last*.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_scan_is](#do_scan_is)( `maskVal` , `first` , `last` ).

### <a name="example"></a>Пример

```cpp
// ctype_scan_is.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char *string = "Hello, my name is John!";

   const char* i = use_facet<ctype<char> > ( loc1 ).scan_is
      ( ctype_base::punct, string, string + strlen(string) );
   cout << "The first punctuation is \"" << *i << "\" at position: "
      << i - string << endl;
}
```

```Output
The first punctuation is "," at position: 5
```

## <a name="ctypescan_not"></a><a name="scan_not"></a>CType:: scan_not

Обнаруживает первый символ, несоответствующий указанной маске, в диапазоне.

```cpp
const CharType *scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*масквал*\
Значение маски, которому не должен соответствовать символ.

*first*\
Указатель на первый символ в просматриваемом диапазоне символов.

*last*\
Указатель на символ, следующий сразу за последним символом в просматриваемом диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первый символ в диапазоне, не соответствующий указанной маске. Если такого значения не существует, функция возвращает *last*.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_scan_not](#do_scan_not)( `maskVal` , `first` , `last` ).

### <a name="example"></a>Пример

```cpp
// ctype_scan_not.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char *string = "Hello, my name is John!";

   const char* i = use_facet<ctype<char> > ( loc1 ).scan_not
      ( ctype_base::alpha, string, string + strlen(string) );
   cout << "First nonalpha character is \"" << *i << "\" at position: "
      << i - string << endl;
}
```

```Output
First nonalpha character is "," at position: 5
```

## <a name="ctypetolower"></a><a name="tolower"></a>CType:: ToLower

Преобразует символ или диапазон символов в нижний регистр.

```cpp
CharType tolower(CharType ch) const;

const CharType *tolower(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*канал*\
Символ для преобразования в нижний регистр.

*first*\
Указатель на первый символ в диапазоне символов, регистр которых нужно преобразовать.

*last*\
Указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого нужно преобразовать.

### <a name="return-value"></a>Возвращаемое значение

Первая функция – член возвращает строчную форму параметра *CH*. Если форма нижнего регистра не существует, она возвращает *CH*.

Вторая функция – член возвращает *last*.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [do_tolower](#do_tolower)( `ch` ). Вторая функция-член возвращает [do_tolower](#do_tolower)( `first` , `last` ).

### <a name="example"></a>Пример

```cpp
// ctype_tolower.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char string[] = "HELLO, MY NAME IS JOHN";

   use_facet<ctype<char> > ( loc1 ).tolower
      ( string, string + strlen(string) );
   cout << "The lowercase string is: " << string << endl;
}
```

```Output
The lowercase string is: hello, my name is john
```

## <a name="ctypetoupper"></a><a name="toupper"></a>CType:: ToUpper

Преобразует символ или диапазон символов в верхний регистр.

```cpp
CharType toupper(CharType ch) const;
const CharType *toupper(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*канал*\
Символ для преобразования в верхний регистр.

*first*\
Указатель на первый символ в диапазоне символов, регистр которых нужно преобразовать.

*last*\
Указатель на символ, следующий сразу за последним символом в диапазоне, регистр символов которого нужно преобразовать.

### <a name="return-value"></a>Возвращаемое значение

Первая функция – член возвращает прописную форму параметра *CH*. Если форма в верхнем регистре не существует, она возвращает *CH*.

Вторая функция – член возвращает *last*.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [do_toupper](#do_toupper)( `ch` ). Вторая функция-член возвращает [do_toupper](#do_toupper)( `first` , `last` ).

### <a name="example"></a>Пример

```cpp
// ctype_toupper.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char string[] = "Hello, my name is John";

   use_facet<ctype<char> > ( loc1 ).toupper
      ( string, string + strlen(string) );
   cout << "The uppercase string is: " << string << endl;
}
```

```Output
The uppercase string is: HELLO, MY NAME IS JOHN
```

## <a name="ctypewiden"></a><a name="widen"></a>CType:: Widening

Преобразует символ типа **`char`** в собственной кодировке в соответствующий символ типа `CharType` , используемый языковым стандартом.

```cpp
CharType widen(char byte) const;
const char *widen(const char* first, const char* last, CharType* dest) const;
```

### <a name="parameters"></a>Параметры

*двухбайтовых*\
Символ типа char в исходной кодировке для преобразования.

*first*\
Указатель на первый символ в диапазоне символов для преобразования.

*last*\
Указатель на символ, следующий сразу за последним символом в преобразуемом диапазоне символов.

*dest*\
Указатель на первый символ типа `CharType` в целевом диапазоне, который хранит преобразуемый диапазон символов.

### <a name="return-value"></a>Возвращаемое значение

Первая функция – член возвращает символ типа `CharType` , соответствующий символу параметра собственного типа **`char`** .

Вторая функция-член возвращает указатель на целевой диапазон символов типа `CharType` , используемого языковым стандартом, преобразованных из машинных символов типа **`char`** .

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [do_widen](#do_widen)( `byte` ). Вторая функция-член возвращает [do_widen](#do_widen)( `first` , `last` , `dest` ).

### <a name="example"></a>Пример

```cpp
// ctype_widen.cpp
// compile with: /EHsc /W3
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "English" );
   char *str1 = "Hello everyone!";
   wchar_t str2 [16];
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).widen
      ( str1, str1 + strlen(str1), &str2[0] ) != 0);  // C4996
   str2[strlen(str1)] = '\0';
   cout << str1 << endl;
   wcout << &str2[0] << endl;

   ctype<wchar_t>::char_type charT;
   charT = use_facet<ctype<char> > ( loc1 ).widen( 'a' );
}
```

```Output
Hello everyone!
Hello everyone!
```

## <a name="see-also"></a>См. также раздел

[\<locale>](../standard-library/locale.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
