---
title: Класс time_get
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_get
- locale/std::time_get::char_type
- locale/std::time_get::iter_type
- locale/std::time_get::date_order
- locale/std::time_get::do_date_order
- locale/std::time_get::do_get
- locale/std::time_get::do_get_date
- locale/std::time_get::do_get_monthname
- locale/std::time_get::do_get_time
- locale/std::time_get::do_get_weekday
- locale/std::time_get::do_get_year
- locale/std::time_get::get
- locale/std::time_get::get_date
- locale/std::time_get::get_monthname
- locale/std::time_get::get_time
- locale/std::time_get::get_weekday
- locale/std::time_get::get_year
helpviewer_keywords:
- std::time_get [C++]
- std::time_get [C++], char_type
- std::time_get [C++], iter_type
- std::time_get [C++], date_order
- std::time_get [C++], do_date_order
- std::time_get [C++], do_get
- std::time_get [C++], do_get_date
- std::time_get [C++], do_get_monthname
- std::time_get [C++], do_get_time
- std::time_get [C++], do_get_weekday
- std::time_get [C++], do_get_year
- std::time_get [C++], get
- std::time_get [C++], get_date
- std::time_get [C++], get_monthname
- std::time_get [C++], get_time
- std::time_get [C++], get_weekday
- std::time_get [C++], get_year
ms.assetid: 869d5f5b-dbab-4628-8333-bdea7e272023
ms.openlocfilehash: 9aebdaffc8bf3754bdbda08247f72ae08475711f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368037"
---
# <a name="time_get-class"></a>Класс time_get

Шаблон класса описывает объект, который может служить в качестве аспекта локализации для управления преобразованиями последовательностей типа `CharType` к значениям времени.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType,
    class InputIterator = istreambuf_iterator<CharType>>
class time_get : public time_base;
```

### <a name="parameters"></a>Параметры

*Chartype*\
Тип, используемый внутри программы для кодирования символов.

*Inputiterator*\
Итератор, из которого считываются значения времени.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[time_get](#time_get)|Конструктор для объектов типа `time_get`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[iter_type](#iter_type)|Тип, который описывает итератор ввода.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[date_order](#date_order)|Возвращает порядок даты, используемый аспектом.|
|[do_date_order](#do_date_order)|Защищенная виртуальная функция-член, вызываемая для возврата порядка даты использовала аспектом.|
|[do_get](#do_get)|Считывает и преобразует символьные данные в значение времени.|
|[do_get_date](#do_get_date)|Защищенная виртуальная функция-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве даты, созданной спецификатором `x` для `strftime`.|
|[do_get_monthname](#do_get_monthname)|Защищенная виртуальная функция-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве названия месяца.|
|[do_get_time](#do_get_time)|Защищенная виртуальная функция-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве даты, созданной спецификатором `X` для `strftime`.|
|[do_get_weekday](#do_get_weekday)|Защищенная виртуальная функция-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве названия дня недели.|
|[do_get_year](#do_get_year)|Защищенная виртуальная функция-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве названия года.|
|[get](#get)|Считывает данные из источника символьных данных и преобразует их в значение времени, сохраняемое в структуре времени.|
|[get_date](#get_date)|Анализирует строку как дату, созданную спецификатором `x` для `strftime`.|
|[get_monthname](#get_monthname)|Анализирует строку как название месяца.|
|[get_time](#get_time)|Анализирует строку как дату, созданную спецификатором `X` для `strftime`.|
|[get_weekday](#get_weekday)|Анализирует строку как название дня недели.|
|[get_year](#get_year)|Анализирует строку как название года.|

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="time_getchar_type"></a><a name="char_type"></a>time_get::char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом для параметра-шаблона **Chartype**.

## <a name="time_getdate_order"></a><a name="date_order"></a>time_get::dат-заказ

Возвращает порядок даты, используемый аспектом.

```cpp
dateorder date_order() const;
```

### <a name="return-value"></a>Возвращаемое значение

Порядок даты, используемый аспектом.

### <a name="remarks"></a>Примечания

Функция-член возвращает [do_date_order](#do_date_order).

### <a name="example"></a>Пример

```cpp
// time_get_date_order.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
void po( char *p )
{
   locale loc( p );

   time_get <char>::dateorder order = use_facet <time_get <char> >( loc ).date_order ( );
   cout << loc.name( );
   switch (order){
      case time_base::dmy: cout << "(day, month, year)" << endl;
      break;
      case time_base::mdy: cout << "(month, day, year)" << endl;
      break;
      case time_base::ydm: cout << "(year, day, month)" << endl;
      break;
      case time_base::ymd: cout << "(year, month, day)"<< endl;
      break;
      case time_base::no_order: cout << "(no_order)"<< endl;
      break;
   }
}

int main( )
{
   po( "C" );
   po( "german" );
   po( "English_Britain" );
}
```

```Output
C(month, day, year)
German_Germany.1252(day, month, year)
English_United Kingdom.1252(day, month, year)
```

## <a name="time_getdo_date_order"></a><a name="do_date_order"></a>time_get::do-дата

Защищенная виртуальная функция-член, вызываемая для возврата порядка даты использовала аспектом.

```cpp
virtual dateorder do_date_order() const;
```

### <a name="return-value"></a>Возвращаемое значение

Порядок даты, используемый аспектом.

### <a name="remarks"></a>Примечания

Виртуальная защищенная функция-член возвращает значение типа **time_base::dateorder**, которое описывает порядок сопоставления компонентов данных типом [do_get_date](#do_get_date). В этой реализации используется значение **time_base::mdy**, соответствующее датам в форме 2 декабря 1979.

### <a name="example"></a>Пример

См. тип [date_order](#date_order), вызывающий `do_date_order`, в примере.

## <a name="time_getdo_get"></a><a name="do_get"></a>time_get::do-get

Считывает и преобразует символьные данные в значение времени. Принимает один описатель преобразования и модификатор.

```cpp
virtual iter_type
    do_get(
iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm,
    char fmt,
    char mod) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, который указывает на начало преобразуемой последовательности.

*last*\
Входной итератор, который указывает на конец последовательности.

*iosbase*\
Объект потока.

*Государства*\
Поле в iosbase, где соответствующие элементы битмаски установлены для указания ошибок.

*Ptm*\
Указатель на структуру времени, где будет храниться время.

*Fmt*\
Символ описателя преобразования.

*Мод*\
Необязательный символ модификатора.

### <a name="return-value"></a>Возвращаемое значение

Возвращает итератор, назначающий первый непреобразованный элемент. Сбой преобразования `ios_base::failbit` `state` устанавливает сявки в и возвращает *сперва.*

### <a name="remarks"></a>Примечания

Функция виртуального члена преобразует и пропускает один или несколько `last`входных элементов в диапазоне , `*pt``first`для определения значений, хранящихся в одном или нескольких членах . Сбой преобразования `ios_base::failbit` `state` устанавливает сявки в и возвращает *сперва.* В противном случае функция возвращает итератор, назначающий первый непреобразованный элемент.

Описатели преобразования:

`'a'` или `'A'` — ведет себя так же, как [time_get::get_weekday](#get_weekday).

`'b'`, `'B'` или `'h'` — ведет себя так же, как [time_get::get_monthname](#get_monthname).

`'c'` — аналогичен `"%b %d %H : %M : %S %Y"`.

`'C'` — преобразует десятичное поле ввода в диапазоне [0, 99] в значение `val` и сохраняет `val * 100 - 1900` в `pt-&tm_year`.

`'d'` или `'e'` — преобразует десятичное поле ввода в диапазоне [1, 31] и сохраняет его значение в `pt-&tm_mday`.

`'D'` — аналогичен `"%m / %d / %y"`.

`'H'` — преобразует десятичное поле ввода в диапазоне [0, 23] и сохраняет его значение в `pt-&tm_hour`.

`'I'` — преобразует десятичное поле ввода в диапазоне [0, 11] и сохраняет его значение в `pt-&tm_hour`.

`'j'` — преобразует десятичное поле ввода в диапазоне [1, 366] и сохраняет его значение в `pt-&tm_yday`.

`'m'` — преобразует десятичное поле ввода в диапазоне [1, 12] в значение `val` и сохраняет `val - 1` в `pt-&tm_mon`.

`'M'` — преобразует десятичное поле ввода в диапазоне [0, 59] и сохраняет его значение в `pt-&tm_min`.

`'n'` или `'t'` — аналогичен `" "`.

`'p'` — преобразует AM или am в ноль, а PM или pm — в 12 и добавляет это значение к `pt-&tm_hour`.

`'r'` — аналогичен `"%I : %M : %S %p"`.

`'R'` — аналогичен `"%H %M"`.

`'S'` — преобразует десятичное поле ввода в диапазоне [0, 59] и сохраняет его значение в `pt-&tm_sec`.

`'T'` или `'X'` — аналогичен `"%H : %M : S"`.

`'U'` — преобразует десятичное поле ввода в диапазоне [0, 53] и сохраняет его значение в `pt-&tm_yday`.

`'w'` — преобразует десятичное поле ввода в диапазоне [0, 6] и сохраняет его значение в `pt-&tm_wday`.

`'W'` — преобразует десятичное поле ввода в диапазоне [0, 53] и сохраняет его значение в `pt-&tm_yday`.

`'x'` — аналогичен `"%d / %m / %y"`.

`'y'` — преобразует десятичное поле ввода в диапазоне [0, 99] в значение `val` и сохраняет `val < 69  val + 100 : val` в `pt-&tm_year`.

`'Y'` — ведет себя так же, как [time_get::get_year](#get_year).

Все другие описатели преобразования устанавливают `ios_base::failbit` в `state` и возвращают значение. В этой реализации любой модификатор не оказывает влияния.

## <a name="time_getdo_get_date"></a><a name="do_get_date"></a>time_get::do-get

Защищенная виртуальная функция-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве даты, созданной спецификатором * x * для `strftime`.

```cpp
virtual iter_type do_get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Флаг формата, который, будучи установленным, указывает, что символ валюты не обязателен; в противном случае он обязателен.

*Государства*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о дате.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Виртуальная защищенная функция-член пытается сопоставить последовательные элементы, начиная с первого в последовательности [`first`, `last`), пока не распознает полное, непустое целочисленное поле ввода даты. В случае успеха, он преобразует это поле в эквивалентное значение, как компоненты **\_tm::tm mon**, **tm::tm\_день,** и **tm::tm\_год**, и сохраняет результаты в `ptm->tm_mon`, `ptm->tm_day`и `ptm->tm_year`, соответственно. Она возвращает итератор, обозначающий первый элемент после поля ввода даты. В противном `iosbase::failbit` случае функция устанавливается в *состоянии.* Она возвращает итератор, обозначающий первый элемент после любого префикса допустимого поля ввода даты. В любом случае, если значение возврата равно `ios_base::eofbit` *последнему,* функция устанавливается в *состоянии.*

Формат для поля ввода даты зависит от языкового стандарта. Для языкового стандарта по умолчанию поле ввода даты имеет вид МММ ДД, ГГГГ, где:

- MMM сопоставляется вызовом метода [get_monthname](#get_monthname), это месяц.

- ДД — это последовательность десятичных цифр, соответствующее числовое значение которой должно находиться в диапазоне [1, 31], это день месяца.

- ГГГГ сопоставляется вызовом метода [get_year](#get_year), это год.

Литеральные пробелы и запятые должны соответствовать соответствующим элементам во входной последовательности.

### <a name="example"></a>Пример

См. пример для [get_date](#get_date), который вызывает `do_get_date`.

## <a name="time_getdo_get_monthname"></a><a name="do_get_monthname"></a>time_get::do-get

Защищенная виртуальная функция-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве названия месяца.

```cpp
virtual iter_type do_get_monthname(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Не используется.

*Государства*\
Выходной параметр, задающий нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о месяце.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Виртуальная защищенная функция-член пытается сопоставить последовательные элементы, начиная с первого в последовательности [`first`, `last`), пока не распознает полное, непустое целочисленное поле ввода месяца. В случае успеха, он преобразует это поле в эквивалентное значение в качестве `ptm->tm_mon`компонента **\_tm::tm mon,** и хранит результат в . Она возвращает итератор, обозначающий первый элемент после поля ввода месяца. В противном `ios_base::failbit` случае функция устанавливается в *состоянии.* Она возвращает итератор, обозначающий первый элемент после любого префикса допустимого поля ввода месяца. В любом случае, если значение возврата равно `ios_base::eofbit` *последнему,* функция устанавливается в *состоянии.*

Поле ввода месяца это последовательность, соответствующая самому длинному множеству последовательностей с учетом языковых стандартов, таких как "янв.", "январь", "фев.", "февраль" и т. д. Преобразованное значение — количество месяцев с января.

### <a name="example"></a>Пример

См. пример для [get_monthname](#get_monthname), который вызывает `do_get_monthname`.

## <a name="time_getdo_get_time"></a><a name="do_get_time"></a>time_get::do-get

Защищенная функция виртуального члена, которая называется для разбора строки как `strftime`дата, произведенная *спецификацией X* для .

```cpp
virtual iter_type do_get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Не используется.

*Государства*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о дате.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Виртуальная защищенная функция-член пытается сопоставить последовательные элементы, начиная с первого в последовательности [`first`, `last`), пока не распознает полное, непустое целочисленное поле ввода времени. В случае успеха, он преобразует это поле `tm::tm_hour`в `tm::tm_min`эквивалентное значение в качестве компонентов, и , `tm::tm_sec`и хранит результаты в `ptm->tm_hour`, `ptm->tm_min`и `ptm->tm_sec`, соответственно. Она возвращает итератор, обозначающий первый элемент после поля ввода даты. В противном `ios_base::failbit` случае функция устанавливается в *состоянии.* Она возвращает итератор, обозначающий первый элемент после любого префикса допустимого поля ввода времени. В любом случае, если значение возврата равно `ios_base::eofbit` *последнему,* функция устанавливается в *состоянии.*

В этой реализации поле ввода времени имеет вид ЧЧ:ММ:СС, где:

- ЧЧ — это последовательность десятичных цифр, соответствующее числовое значение которой должно находиться в диапазоне [0, 24), это час дня;

- ММ — это последовательность десятичных цифр, соответствующее числовое значение которой должно находиться в диапазоне [0, 60), это минуты часа;

- СС — это последовательность десятичных цифр, соответствующее числовое значение которой должно находиться в диапазоне [0, 60), это секунды минуты.

Литеральные двоеточия должны соответствовать соответствующим элементам во входной последовательности.

### <a name="example"></a>Пример

См. пример для [get_time](#get_time), который вызывает `do_get_time`.

## <a name="time_getdo_get_weekday"></a><a name="do_get_weekday"></a>time_get::do-get'weekday

Защищенная виртуальная функция-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве названия дня недели.

```cpp
virtual iter_type do_get_weekday(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Флаг формата, который, будучи установленным, указывает, что символ валюты не обязателен; в противном случае он обязателен.

*Государства*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о дне недели.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Функция виртуального защищенного члена пытается сопоставить последовательные элементы, `first` `last`начинающиеся *сначала* в последовательности , ) до тех пор, пока она не распознает полное, непустое поле ввода буднего дня. В случае успеха, он преобразует это поле в эквивалентное значение в качестве `ptm->tm_wday`компонента **tm::tm\_wday,** и хранит результат в . Она возвращает итератор, обозначающий первый элемент после поля ввода дня недели. В противном `ios_base::failbit` случае функция устанавливается в *состоянии.* Она возвращает итератор, обозначающий первый элемент после любого префикса допустимого поля ввода дня недели. В любом случае, если значение возврата равно `ios_base::eofbit` *последнему,* функция устанавливается в *состоянии.*

Поле ввода дня недели — это последовательность, соответствующая самому длинному множеству последовательностей с учетом языковых стандартов, таких как "пнд", "понедельник", "втр", "вторник" и т. д. Преобразованное значение — количество дней с понедельника.

### <a name="example"></a>Пример

См. пример для [get_weekday](#get_weekday), который вызывает `do_get_weekday`.

## <a name="time_getdo_get_year"></a><a name="do_get_year"></a>time_get::do-get

Защищенная виртуальная функция-член, вызываемая для того, чтобы выполнить синтаксический анализ строки в качестве названия года.

```cpp
virtual iter_type do_get_year(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Флаг формата, который, будучи установленным, указывает, что символ валюты не обязателен; в противном случае он обязателен.

*Государства*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о годе.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Функция виртуального защищенного члена пытается сопоставить последовательные элементы, `first` `last`начинающиеся *сначала* в последовательности , ) до тех пор, пока она не распознает полное, непустое поле ввода года. В случае успеха, он преобразует это поле в эквивалентное значение в качестве `ptm->tm_year`компонента **\_tm::tm год,** и хранит результат в . Она возвращает итератор, обозначающий первый элемент после поля ввода года. В противном `ios_base::failbit` случае функция устанавливается в *состоянии.* Она возвращает итератор, обозначающий первый элемент после любого префикса допустимого поля ввода года. В любом случае, если значение возврата равно `ios_base::eofbit` *последнему,* функция устанавливается в *состоянии.*

Поле ввода года — это последовательность десятичных цифр, соответствующее числовое значение которой должно находиться в диапазоне [1900, 2036). Сохраненное значение — это значение минус 1900. В этой реализации значения в диапазоне [69, 136) представляют диапазон лет [1969, 2036). Значения в диапазоне [0, 69) также допустимы, но они могут представлять либо диапазон лет [1900, 1969), либо [2000, 2069) в зависимости от конкретной среды перевода.

### <a name="example"></a>Пример

См. пример для [get_year](#get_year), который вызывает `do_get_year`.

## <a name="time_getget"></a><a name="get"></a>time_get::get

Считывает данные из источника символьных данных и преобразует их в значение времени, сохраняемое в структуре времени. Первая функция принимает один описатель и модификатор преобразования, а вторая — несколько.

```cpp
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm,
    char fmt,
    char mod) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm,
    char_type* fmt_first,
    char_type* fmt_last) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, который указывает начало преобразуемой последовательности.

*last*\
Входной итератор, который указывает конец преобразуемой последовательности.

*iosbase*\
Поток.

*Государства*\
Для состояния потока задаются соответствующие элементы битовой маски для указания ошибок.

*Ptm*\
Указатель на структуру времени, где будет храниться время.

*Fmt*\
Символ описателя преобразования.

*Мод*\
Необязательный символ модификатора.

*fmt_first*\
Указывает на начало директив формата.

*fmt_last*\
Указывает на конец директив формата.

### <a name="return-value"></a>Возвращаемое значение

Возвращает итератор первому символу после данных, которые были использованы для присвоения структуры `*ptm`времени.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает значение `do_get(first, last, iosbase, state, ptm, fmt, mod)`.

Вторая функция-член вызывает `do_get` в формате с разделением `[fmt_first, fmt_last)`. Она воспринимает формат как последовательность полей, каждое из которых определяет преобразование нуля или большего числа входных элементов, разделенных `[first, last)`. Возвращает итератор, назначающий первый непреобразованный элемент. Существует три типа полей.

Процент (%) в формате, а затем дополнительный модификатор модификатор модификатор *аудирует* в наборе «EO» с последующим конверсионным спецификацией *fmt,* заменяет *сначала* значение, возвращенное `do_get(first, last, iosbase, state, ptm, fmt, mod)`. Сбой преобразования `ios_base::failbit` устанавливается в *состоянии* и возвращается.

Элемент пробела в формате пропускает ноль или более последних входных элементов пробелов.

Любой другой элемент в формате должен соответствовать следующему входному элементу, который пропускается. Сбой матча `ios_base::failbit` устанавливается в *состоянии* и возвращается.

## <a name="time_getget_date"></a><a name="get_date"></a>time_get::get_date

Анализирует строку как дату, созданную спецификатором * x * для `strftime`.

```cpp
iter_type get_date(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Флаг формата, который, будучи установленным, указывает, что символ валюты не обязателен; в противном случае он обязателен.

*Государства*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о дате.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Функция участника возвращает [сяра](#do_get_date) `state`do_get_date `ptm`(,`first` `last`, `iosbase`, ).

Обратите внимание, что месяцы отсчитываются от 0 до 11.

### <a name="example"></a>Пример

```cpp
// time_get_get_date.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream< char > pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset(&t, 0, sizeof(struct tm));

   pszGetF << "July 4, 2000";
   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet <time_get<char> >
   (loc).get_date(basic_istream<char>::_Iter(pszGetF.rdbuf( ) ),
            basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if ( st & ios_base::failbit )
      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_sec: " << t.tm_sec
      << "\ntm_min: " << t.tm_min
      << "\ntm_hour: " << t.tm_hour
      << "\ntm_mday: " << t.tm_mday
      << "\ntm_mon: " << t.tm_mon
      << "\ntm_year: " << t.tm_year
      << "\ntm_wday: " << t.tm_wday
      << "\ntm_yday: " << t.tm_yday
      << "\ntm_isdst: " << t.tm_isdst
      << endl;
}
```

```Output
time_get(July 4, 2000) =
tm_sec: 0
tm_min: 0
tm_hour: 0
tm_mday: 4
tm_mon: 6
tm_year: 100
tm_wday: 0
tm_yday: 0
tm_isdst: 0
```

## <a name="time_getget_monthname"></a><a name="get_monthname"></a>time_get::get_monthname

Анализирует строку как название месяца.

```cpp
iter_type get_monthname(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Не используется.

*Государства*\
Выходной параметр, задающий нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о месяце.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Функция участника [do_get_monthname](#do_get_monthname)возвращает`first`do_get_monthname `last` `iosbase`(, , , `state`. `ptm`. . . . . . . . . . . . . . . . . . . . . . . . . .

### <a name="example"></a>Пример

```cpp
// time_get_get_monthname.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc ( "French" );
   basic_stringstream<char> pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "juillet";
   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet <time_get <char> >
   (loc).get_monthname(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
              basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_sec: " << t.tm_sec
      << "\ntm_min: " << t.tm_min
      << "\ntm_hour: " << t.tm_hour
      << "\ntm_mday: " << t.tm_mday
      << "\ntm_mon: " << t.tm_mon
      << "\ntm_year: " << t.tm_year
      << "\ntm_wday: " << t.tm_wday
      << "\ntm_yday: " << t.tm_yday
      << "\ntm_isdst: " << t.tm_isdst
      << endl;
}
```

```Output
time_get(juillet) =
tm_sec: 0
tm_min: 0
tm_hour: 0
tm_mday: 0
tm_mon: 6
tm_year: 0
tm_wday: 0
tm_yday: 0
tm_isdst: 0
```

## <a name="time_getget_time"></a><a name="get_time"></a>time_get::get_time

Парс строки, как дата производства *X* спецификации `strftime`для .

```cpp
iter_type get_time(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Не используется.

*Государства*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о дате.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Функция участника [do_get_time](#do_get_time)возвращает`first`do_get_time `last` `iosbase`(, , , `state`. `ptm`. . . . . . . . . . . . . . . . . . . . . . . . . .

### <a name="example"></a>Пример

```cpp
// time_get_get_time.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "11:13:20";
   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet
      <time_get <char> >
      (loc).get_time(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
               basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_sec: " << t.tm_sec
      << "\ntm_min: " << t.tm_min
      << "\ntm_hour: " << t.tm_hour
      << endl;
}
```

```Output
time_get::get_time(11:13:20) =
tm_sec: 20
tm_min: 13
tm_hour: 11
```

## <a name="time_getget_weekday"></a><a name="get_weekday"></a>time_get::get_weekday

Анализирует строку как название дня недели.

```cpp
iter_type get_weekday(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Флаг формата, который, будучи установленным, указывает, что символ валюты не обязателен; в противном случае он обязателен.

*Государства*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о дне недели.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Функция участника [do_get_weekday](#do_get_weekday)возвращает`first`do_get_weekday `last` `iosbase`(, , , `state`. `ptm`. . . . . . . . . . . . . . . . . . . . . . . . . .

### <a name="example"></a>Пример

```cpp
// time_get_get_weekday.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc ( "French" );
   basic_stringstream< char > pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "mercredi";
   pszGetF.imbue(loc);
   basic_istream<char>::_Iter i = use_facet
      <time_get<char> >
      (loc).get_weekday(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
               basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get::get_time("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_wday: " << t.tm_wday
      << endl;
}
```

```Output
time_get::get_time(mercredi) =
tm_wday: 3
```

## <a name="time_getget_year"></a><a name="get_year"></a>time_get::get_year

Анализирует строку как название года.

```cpp
iter_type get_year(iter_type first,
    iter_type last,
    ios_base& iosbase,
    ios_base::iostate& state,
    tm* ptm) const;
```

### <a name="parameters"></a>Параметры

*first*\
Входной итератор, адресующий начало последовательности для преобразования.

*last*\
Входной итератор, адресующий конец последовательности для преобразования.

*iosbase*\
Флаг формата, который, будучи установленным, указывает, что символ валюты не обязателен; в противном случае он обязателен.

*Государства*\
Устанавливает нужные элементы битовой маски для состояния потока согласно тому, успешно ли выполнились операции.

*Ptm*\
Указатель на место, где будет храниться информация о годе.

### <a name="return-value"></a>Возвращаемое значение

Входной итератор, адресующий первый элемент после поля ввода.

### <a name="remarks"></a>Примечания

Функция участника [do_get_year](#do_get_year)возвращает`first`do_get_year `last` `iosbase`(, , , `state`. `ptm`. . . . . . . . . . . . . . . . . . . . . . . . . .

### <a name="example"></a>Пример

```cpp
// time_get_get_year.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszGetF, pszPutF, pszGetI, pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   pszGetF << "1928";

   pszGetF.imbue( loc );
   basic_istream<char>::_Iter i = use_facet
      <time_get<char> >
      (loc).get_year(basic_istream<char>::_Iter(pszGetF.rdbuf( )),
               basic_istream<char>::_Iter(0), pszGetF, st, &t);

   if (st & ios_base::failbit)
      cout << "time_get::get_year("<< pszGetF.rdbuf( )->str( )<< ") FAILED on char: " << *i << endl;
   else

      cout << "time_get::get_year("<< pszGetF.rdbuf( )->str( )<< ") ="
      << "\ntm_year: " << t.tm_year
      << endl;
}
```

```Output
time_get::get_year(1928) =
tm_year: 28
```

## <a name="time_getiter_type"></a><a name="iter_type"></a>time_get::iter_type

Тип, который описывает итератор ввода.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра-шаблона **InputIterator**.

## <a name="time_gettime_get"></a><a name="time_get"></a>time_get::time_get

Конструктор для объектов типа `time_get`.

```cpp
explicit time_get(size_t refs = 0);
```

### <a name="parameters"></a>Параметры

*Refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Примечания

Возможные значения параметра *рефери* и их значение:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \>1: Эти значения не определены.

Прямые примеры привести нельзя, так как деструктор защищен.

Конструктор инициализирует свой базовый объект с`refs` **помощью локализации::**[грань](../standard-library/locale-class.md#facet_class)( ).

## <a name="see-also"></a>См. также раздел

[\<локализовая>](../standard-library/locale.md)\
[класс time_base](../standard-library/time-base-class.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
