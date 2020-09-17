---
title: Класс locale
ms.date: 07/20/2020
f1_keywords:
- xlocale/std::locale
- xlocale/std::locale::category
- xlocale/std::locale::combine
- xlocale/std::locale::name
- xlocale/std::locale::classic
- xlocale/std::locale::global
- xlocale/std::locale::operator( )
- xlocale/std::locale::facet
- xlocale/std::locale::id
helpviewer_keywords:
- std::locale [C++]
- std::locale [C++], category
- std::locale [C++], combine
- std::locale [C++], name
- std::locale [C++], classic
- std::locale [C++], global
- std::locale [C++], facet
- std::locale [C++], id
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
ms.openlocfilehash: 55aeaf27b1c31ef0dba68d0ead3633590777cbdf
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040605"
---
# <a name="locale-class"></a>Класс locale

Класс, описывающий объект языкового стандарта, инкапсулирующий данные по соответствующей культуре в качестве набора аспектов, которые собирательно определяют ту или иную локализованную среду.

## <a name="syntax"></a>Синтаксис

```cpp
class locale;
```

## <a name="remarks"></a>Примечания

Аспект — это указатель на объект класса, выведенного производным от класса [facet](#facet_class), который обладает общим объектом в формате:

```cpp
static locale::id id;
```

Можно задать открытый набор данных аспектов. Можно также создать объект языкового стандарта, назначающий произвольное количество аспектов.

Предопределенные группы этих аспектов представляют [категории языкового стандарта](#category), которыми в стандартной библиотеке C традиционно управляет функция `setlocale`.

Категория `collate` (LC_COLLATE) включает аспекты:

```cpp
collate<char>
collate<wchar_t>
```

Категория `ctype` (LC_CTYPE) включает аспекты:

```cpp
ctype<char>
ctype<wchar_t>
codecvt<char, char, mbstate_t>
codecvt<wchar_t, char, mbstate_t>
codecvt<char16_t, char, mbstate_t>
codecvt<char32_t, char, mbstate_t>
```

Категория `monetary` (LC_MONETARY) включает аспекты:

```cpp
moneypunct<char, false>
moneypunct<wchar_t, false>
moneypunct<char, true>
moneypunct<wchar_t, true>
money_get<char, istreambuf_iterator<char>>
money_get<wchar_t, istreambuf_iterator<wchar_t>>
money_put<char, ostreambuf_iterator<char>>
money_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Категория `numeric` (LC_NUMERIC) включает аспекты:

```cpp
num_get<char, istreambuf_iterator<char>>
num_get<wchar_t, istreambuf_iterator<wchar_t>>
num_put<char, ostreambuf_iterator<char>>
num_put<wchar_t, ostreambuf_iterator<wchar_t>>
numpunct<char>
numpunct<wchar_t>
```

Категория `time` (LC_TIME) включает аспекты:

```cpp
time_get<char, istreambuf_iterator<char>>
time_get<wchar_t, istreambuf_iterator<wchar_t>>
time_put<char, ostreambuf_iterator<char>>
time_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Категория `messages` (LC_MESSAGES) включает аспекты:

```cpp
messages<char>
messages<wchar_t>
```

(Последняя категория необходима для POSIX, но не для стандарта C.)

Некоторые из этих предопределенных аспектов используются `iostream` классами для управления преобразованием числовых значений в текстовые последовательности и из них.

Объект класса locale также сохраняет имя языкового стандарта в качестве объекта класса [string](../standard-library/string-typedefs.md#string). Использование недопустимого имени языкового стандарта для создания аспекта языкового стандарта или объекта языкового стандарта создает объект класса [runtime_error](../standard-library/runtime-error-class.md). Имя сохраненного языкового стандарта имеет значение, `"*"` Если объект языкового стандарта не может быть уверен в том, что язык C в стиле с точно соответствует тому, который представлен объектом. В противном случае можно установить соответствующий языковой стандарт в стандартной библиотеке C для некоторого объекта языкового стандарта `locale_object` , вызвав `setlocale(LC_ALL , locale_object.` [имя](#name) `().c_str())` .

В данном случае можно также вызвать статическую функцию-член:

```cpp
static locale empty();
```

создать объект языкового стандарта без аспектов. Это также прозрачный языковой стандарт. Если функции шаблона [has_facet](../standard-library/locale-functions.md#has_facet) и [use_facet](../standard-library/locale-functions.md#use_facet) не могут найти требуемый аспект в прозрачном языковом стандарте, они обращаются к первому глобальному языковому стандарту, а затем, если они прозрачны, классический языковой стандарт. Таким образом, можно написать:

```cpp
cout.imbue(locale::empty());
```

Последующие операции вставки [`cout`](../standard-library/iostream.md#cout) исправляются текущим состоянием глобального языкового стандарта. Можно даже написать:

```cpp
locale loc(locale::empty(),
    locale::classic(),
    locale::numeric);

cout.imbue(loc);
```

Числовые правила форматирования для последующих вставок в `cout` остаются такими же, как в языковом стандарте C, даже если глобальный языковой стандарт предоставляет другие правила вставки дат и денежных сумм.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[locale](#locale)|Создает языковой стандарт, копию языкового стандарта или копию языкового стандарта, в которой аспект или категория заменены аспектом или категорией из другого языкового стандарта.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[category](#category)|Целочисленный тип, который содержит значения битовой маски для обозначения стандартных семейств аспектов.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[состоят](#combine)|Вставляет аспект из определенного языкового стандарта в целевой языковой стандарт.|
|[name](#name)|Возвращает имя сохраненного языкового стандарта.|

### <a name="static-functions"></a>Статические функции

|Имя|Описание|
|-|-|
|[Классические](#classic)|Данная статическая функция-член возвращает объект языкового стандарта, представляющий классический языковой стандарт C.|
|[global](#global)|Сброс языкового стандарта программы по умолчанию.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator=](#op_eq)|Назначает языковой стандарт.|
|[operator!=](#op_neq)|Проверка двух языковых стандартов на неравенство.|
|[operator()](#op_call)|Сравнивает два объекта `basic_string`.|
|[operator==](#op_eq_eq)|Проверка двух языковых стандартов на равенство.|

### <a name="classes"></a>Классы

|Class|Описание|
|-|-|
|[устанавливают](#facet_class)|Класс, используемый как базовый класс для всех аспектов языкового стандарта.|
|[`id`](#id_class)|Класс члена содержит уникальный идентификатор аспекта, применяемый в качестве индекса для поиска аспектов в языковом стандарте.|

## <a name="requirements"></a>Требования

**Заголовок:**\<locale>

**Пространство имен:** std

## <a name="localecategory"></a><a name="category"></a> языковой стандарт:: Category

Целочисленный тип, который содержит значения битовой маски для обозначения стандартных семейств аспектов.

```cpp
typedef int category;
static const int collate = LC_COLLATE;
static const int ctype = LC_CTYPE;
static const int monetary = LC_MONETARY;
static const int numeric = LC_NUMERIC;
static const int time = LC_TIME;
static const int messages = LC_MESSAGES;
static const int all = LC_ALL;
static const int none = 0;
```

### <a name="remarks"></a>Комментарии

Тип является синонимом для **`int`** типа, который может представлять группу различных элементов типа битовой маски Local для класса locale или может использоваться для представления любой из соответствующих категорий языкового стандарта C. Элементы:

- `collate`, соответствующий категории C LC_COLLATE

- `ctype`, соответствующий категории C LC_CTYPE

- `monetary`, соответствующий категории C LC_MONETARY

- `numeric`, соответствующий категории C LC_NUMERIC

- `time`, соответствующий категории C LC_TIME

- `messages`, соответствующее категории POSIX LC_MESSAGES

Два более полезных значения:

- `none`, соответствующий ни одной из категорий C

- `all`, соответствующий объединению C всех категорий LC_ALL

Можно представить произвольную группу категорий с помощью `OR` с этими константами, как в `monetary` &#124; `time` .

## <a name="localeclassic"></a><a name="classic"></a> locale:: классический

Данная статическая функция-член возвращает объект языкового стандарта, представляющий классический языковой стандарт C.

```cpp
static const locale& classic();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на языковой стандарт C.

### <a name="remarks"></a>Комментарии

Классический язык C — это языковой стандарт ASCII американского английского языка в стандартной библиотеке C. Это языковой стандарт, который неявно используется в программах, которые не являются международными.

### <a name="example"></a>Пример

```cpp
// locale_classic.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: " << loc2.name( )
        << "." << endl;
   cout << "The name of the current locale is: " << loc1.name( )
        << "." << endl;

   if (loc2 == locale::classic( ) )
      cout << "The previous locale was classic." << endl;
   else
      cout << "The previous locale was not classic." << endl;

   if (loc1 == locale::classic( ) )
      cout << "The current locale is classic." << endl;
   else
      cout << "The current locale is not classic." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
The previous locale was classic.
The current locale is not classic.
```

## <a name="localecombine"></a><a name="combine"></a> языковой стандарт:: Combine

Вставляет аспект из определенного языкового стандарта в целевой языковой стандарт.

```cpp
template <class Facet>
locale combine(const locale& source_locale) const;
```

### <a name="parameters"></a>Параметры

*source_locale*\
Языковой стандарт, содержащий аспект для вставки в целевой языковой стандарт.

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает объект языкового стандарта, который заменяет или добавляет к ** \* этому** аспекту, `Facet` указанному в *source_locale*.

### <a name="example"></a>Пример

```cpp
// locale_combine.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main() {
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   locale loc2 ( "C" );
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;
}
```

## <a name="facet-class"></a><a name="facet_class"></a> Класс аспекта

Класс, используемый как базовый класс для всех аспектов языкового стандарта.

```cpp
class facet {
protected:
    explicit facet(size_t references = 0);
    virtual ~facet();
private:
    facet(const facet&) // not defined
    void operator=(const facet&) // not defined
};
```

### <a name="remarks"></a>Комментарии

Нельзя скопировать или назначить объект класса `facet` . Можно создавать и удалять объекты, производные от класса `locale::facet`, но не объекты правильного базового класса. Как правило, создается объект `_Myfac` , производный от `facet` , при создании `locale` , как в `locale loc(locale::classic(), new _Myfac);`

В таких случаях конструктор базового класса `facet` должен иметь аргумент с нулевым числом *ссылок* . Если объект больше не нужен, он удаляется, поэтому аргумент ненулевых *ссылок* указывается только в редких случаях, когда ответственность за время существования объекта несется.

## <a name="localeglobal"></a><a name="global"></a> locale:: Global

Сброс языкового стандарта по умолчанию для программы. Этот вызов влияет на глобальный языковой стандарт для C и C++.

```cpp
static locale global(const locale& new_default_locale);
```

### <a name="parameters"></a>Параметры

*new_default_locale*\
Языковой стандарт, который будет использоваться программой по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Языковой стандарт до сброса языкового стандарта по умолчанию.

### <a name="remarks"></a>Комментарии

При запуске программы глобальный языковой стандарт совпадает в классическим языковым стандартом. Функция `global()` вызывает `setlocale( LC_ALL, loc.name. c_str())` для установки соответствующего языкового стандарта в стандартной библиотеке C.

### <a name="example"></a>Пример

```cpp
// locale_global.cpp
// compile by using: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_germany" );
   locale loc1;
   cout << "The initial locale is: " << loc1.name( ) << endl;
   locale loc2 = locale::global ( loc );
   locale loc3;
   cout << "The current locale is: " << loc3.name( ) << endl;
   cout << "The previous locale was: " << loc2.name( ) << endl;
}
```

```Output
The initial locale is: C
The current locale is: German_Germany.1252
The previous locale was: C
```

## <a name="id-class"></a><a name="id_class"></a> Класс ID

Класс члена содержит уникальный идентификатор аспекта, применяемый в качестве индекса для поиска аспектов в языковом стандарте.

```cpp
class id
{
   protected:    id();
   private:      id(const id&)
   void operator=(const id&)  // not defined
};
```

### <a name="remarks"></a>Комментарии

Класс-член описывает статический объект-член, необходимый для каждого уникального аспекта языкового стандарта. Нельзя скопировать или назначить объект класса `id` .

## <a name="localelocale"></a><a name="locale"></a> языковой стандарт:: locale

Создает языковой стандарт, копию языкового стандарта или копию языкового стандарта, в которой аспект или категория заменены аспектом или категорией из другого языкового стандарта. Также включает деструктор.

```cpp
locale();

explicit locale(const char* locale_name, category new_category = all);
explicit locale(const string& locale_name);
locale(const locale& from_locale);
locale(const locale& from_locale, const locale& Other, category new_category);
locale(const locale& from_locale, const char* locale_name, category new_category);

template <class Facet>
locale(const locale& from_locale, const Facet* new_facet);

~locale();
```

### <a name="parameters"></a>Параметры

*locale_name*\
Имя языкового стандарта.

*from_locale*\
Языковой стандарт, который будет копироваться при создании нового языкового стандарта.

*Other*\
Языковой стандарт, из которого будет выбираться категория.

*new_category*\
Категория для замены в созданном языковом стандарте.

*new_facet*\
Аспект для замены в созданном языковом стандарте.

### <a name="remarks"></a>Комментарии

Первый конструктор инициализирует объект для соответствия глобальному языковому стандарту. Второй и третий конструкторы инициализируют все категории языкового стандарта, чтобы их поведение соответствовало имени локали *locale_name*. Остальные конструкторы копируют *from_locale*, за исключением указанных ниже.

`locale(const locale& from_locale, const locale& Other, category new_category);`

заменяет *другие* аспекты, соответствующие категории c, для которой c & *new_category* не равно нулю.

`locale(const locale& from_locale, const char* locale_name, category new_category);`

`locale(const locale& from_locale, const string& locale_name, category new_category);`

заменяет `locale(locale_name, all)` эти аспекты, соответствующие категории *replace_category* , для которых `replace_category & new_category` ненулевое значение.

`template<class Facet> locale(const locale& from_locale, Facet* new_facet);`

заменяет в (или добавляет к) *from_locale* аспект *new_facet*, если *new_facet* не является пустым указателем.

Если имя локали *locale_name* является пустым указателем или недопустимым, функция создает исключение [runtime_error](../standard-library/runtime-error-class.md).

### <a name="example"></a>Пример

```cpp
// locale_locale.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( ) {

   // Second constructor
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   // The first (default) constructor
   locale loc2;
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   // Third constructor
   locale loc3 (loc2,loc, _M_COLLATE );
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;

   // Fourth constructor
   locale loc4 (loc2, "German_Germany", _M_COLLATE );
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;
}
```

## <a name="localename"></a><a name="name"></a> locale:: Name

Возвращает имя сохраненного языкового стандарта.

```cpp
string name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, задающая имя языкового стандарта.

### <a name="example"></a>Пример

```cpp
// locale_name.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: "
        << loc2.name( ) << "." << endl;
   cout << "The name of the current locale is: "
        << loc1.name( ) << "." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
```

## <a name="localeoperator"></a><a name="op_eq"></a> языковой стандарт::operator=

Назначает языковой стандарт.

```cpp
const locale& operator=(const locale& other) noexcept;
```

## <a name="localeoperator"></a><a name="op_neq"></a> языковой стандарт::operator!=

Проверка двух языковых стандартов на неравенство.

```cpp
bool operator!=(const locale& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Один из языковых стандартов для проверки на неравенство.

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, равное, **`true`** Если языковые стандарты не являются копиями одного и того же языкового стандарта. **`false`** Если языковые стандарты являются копиями одного и того же языкового стандарта.

### <a name="remarks"></a>Комментарии

Два языковых стандарта равны, если они совпадают, если одна из них является копией другого или если они имеют одинаковые имена.

### <a name="example"></a>Пример

```cpp
// locale_op_ne.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 != loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;

   if ( loc1 != loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;
}
```

```Output
locales loc1 (German_Germany.1252) and
loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252) and
loc3 (English_United States.1252) are not equal.
```

## <a name="localeoperator"></a><a name="op_call"></a> языковой стандарт::operator ()

Сравнивает два `basic_string` объекта в соответствии с правилами сравнения лексикографическим порядком, определенными `std::collate<charT>` аспектом локали.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right) const;
```

### <a name="parameters"></a>Параметры

*left*\
Первая сравниваемая строка.

*right*\
Вторая сравниваемая строка.

### <a name="return-value"></a>Возвращаемое значение

- **`true`** Если *Left* имеет значение лексикографически меньше *право*, в противном случае — значение **`false`** .

### <a name="remarks"></a>Комментарии

Функция-член фактически выполняет:

```cpp
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```

Это означает, что объект языкового стандарта можно использовать в качестве объекта функции.

### <a name="example"></a>Пример

```cpp
// locale_op_compare.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

int main( )
{
   using namespace std;
   const wchar_t *sa = L"ztesting";
   const wchar_t *sb = L"\0x00DFtesting";
   basic_string<wchar_t> a( sa );
   basic_string<wchar_t> b( sb );

   locale loc( "German_Germany" );
   cout << loc( a,b ) << endl;

   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );
   cout << ( fac.compare( sa, sa + a.length( ),
       sb, sb + b.length( ) ) < 0) << endl;
}
```

```Output
0
0
```

## <a name="localeoperator"></a><a name="op_eq_eq"></a> языковой стандарт::operator==

Проверка двух языковых стандартов на равенство.

```cpp
bool operator==(const locale& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Один из языковых стандартов для проверки на равенство.

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, равное, **`true`** Если языковые стандарты являются копиями одного и того же языкового стандарта. **`false`** Если языковые стандарты не являются копиями одного и того же языкового стандарта.

### <a name="remarks"></a>Комментарии

Два языковых стандарта равны, если они совпадают, если одна из них является копией другого или если они имеют одинаковые имена.

### <a name="example"></a>Пример

```cpp
// locale_op_eq.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 == loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."
      << endl;

   if ( loc1 == loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."
      << endl;
}
```

```Output
locales loc1 (German_Germany.1252)
and loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252)
and loc3 (English_United States.1252) are not equal.
```

## <a name="see-also"></a>См. также раздел

[\<locale>](../standard-library/locale.md)\
[Кодовые страницы](../c-runtime-library/code-pages.md)\
[Имена языковых стандартов, языки и строки страны или региона](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
