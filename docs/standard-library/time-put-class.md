---
title: Класс time_put
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put
- locale/std::time_put::char_type
- locale/std::time_put::iter_type
- locale/std::time_put::do_put
- locale/std::time_put::put
helpviewer_keywords:
- std::time_put [C++]
- std::time_put [C++], char_type
- std::time_put [C++], iter_type
- std::time_put [C++], do_put
- std::time_put [C++], put
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
ms.openlocfilehash: 4f7b609493e16d3d1c0a9ab6274ed6f5bfd7b033
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212115"
---
# <a name="time_put-class"></a>Класс time_put

Шаблон класса описывает объект, который может служить в качестве аспекта языкового стандарта для управления преобразованием значений времени в последовательности типа `CharType` .

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType,
    class OutputIterator = ostreambuf_iterator<CharType>>
class time_put : public locale::facet;
```

### <a name="parameters"></a>Параметры

*CharType*\
Тип, используемый внутри программы для кодирования символов.

*OutputIterator*\
Тип итератора, в который функции записи времени записывают свои выходные данные.

## <a name="remarks"></a>Примечания

Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[time_put](#time_put)|Конструктор для объектов типа `time_put`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|
|[iter_type](#iter_type)|Тип, который описывает итератор вывода.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[do_put](#do_put)|Виртуальная функция, выводящая информацию о времени и дате в виде последовательности `CharType`.|
|[PUT](#put)|Выводит информацию о времени и дате в виде последовательности `CharType`.|

## <a name="requirements"></a>Требования

**Заголовок:**\<locale>

**Пространство имен:** std

## <a name="time_putchar_type"></a><a name="char_type"></a>time_put:: char_type

Тип, используемый для описания символа, используемого языковым стандартом.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `CharType`.

## <a name="time_putdo_put"></a><a name="do_put"></a>time_put::d o_put

Виртуальная функция, выводящая информацию о времени и дате в виде последовательности `CharType`.

```cpp
virtual iter_type do_put(
    iter_type next,
    ios_base& _Iosbase,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;
```

### <a name="parameters"></a>Параметры

*очеред*\
Итератор вывода, куда необходимо вставить последовательность символов, представляющих дату и время.

*_Iosbase*\
Не используется.

*_Pt*\
Выводимые сведения о дате и времени.

*_Fmt*\
Формат вывода См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

*_Mod*\
Модификатор для формата. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

### <a name="return-value"></a>Возвращаемое значение

Итератор для первой позиции после последнего вставленного элемента.

### <a name="remarks"></a>Примечания

Виртуальная Защищенная функция Member создает последовательные элементы `next` , начиная с значений времени, хранящихся в объекте \* `_Pt` , типа `tm` . Функция возвращает итератор, обозначающий следующую позицию для вставки элемента после сформированного вывода.

Выходные данные создаются теми же правилами, которые используются с `strftime` последним аргументом *_Pt*для создания последовательности **`char`** элементов в массиве. **`char`** Предполагается, что каждый такой элемент сопоставлен с эквивалентным элементом типа `CharType` с помощью простого сопоставления «один к одному». Если *_Mod* равно нулю, эффективный формат — "% F", где F заменяется *_Fmt*. В противном случае эффективный формат — "% MF", где M заменяется *_Mod*.

### <a name="example"></a>Пример

См. пример для [put](#put), который вызывает `do_put`.

## <a name="time_putiter_type"></a><a name="iter_type"></a>time_put:: iter_type

Тип, который описывает итератор вывода.

```cpp
typedef OutputIterator iter_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `OutputIterator`.

## <a name="time_putput"></a><a name="put"></a>time_put::p UT

Выводит информацию о времени и дате в виде последовательности `CharType`.

```cpp
iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;

iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Параметры

*очеред*\
Итератор вывода, куда необходимо вставить последовательность символов, представляющих дату и время.

*_Iosbase*\
Не используется.

*_Fill*\
Символ типа, `CharType` используемый для интервала.

*_Pt*\
Выводимые сведения о дате и времени.

*_Fmt*\
Формат вывода См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

*_Mod*\
Модификатор для формата. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

*first*\
Начало строки форматирования для выходных данных. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

*last*\
Конец строки форматирования для выходных данных. См. допустимые значения в разделе [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md).

### <a name="return-value"></a>Возвращаемое значение

Итератор для первой позиции после последнего вставленного элемента.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [do_put](#do_put)( `next` , `_Iosbase` , `_Fill` , `_Pt` , `_Fmt` , `_Mod` ). Вторая функция-член копирует в \* `next` + + любой элемент в интервале [ `first` , `last` ), отличный от процента (%). Для процента, за которым следует символ *C* в интервале [ `first` , `last` ), функция вместо этого вычисляет `next`  =  `do_put` ( `next` , `_Iosbase` ,, `_Fill` `_Pt` , *C*, 0) и пропускается за знаком *c*. Однако, если *C* является символом-квалификатором из набора EOQ #, за которым следует символ `C2` в интервале [ `first` , `last` ), то функция вместо этого вычисляет `next`  =  `do_put` ( `next` , `_Iosbase` ,,, `_Fill` `_Pt` `C2` , *C*) и пропускается назад `C2` .

### <a name="example"></a>Пример

```cpp
// time_put_put.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
#include <time.h>
using namespace std;
int main( )
{
   locale loc;
   basic_stringstream<char> pszPutI;
   ios_base::iostate st = 0;
   struct tm t;
   memset( &t, 0, sizeof( struct tm ) );

   t.tm_hour = 5;
   t.tm_min = 30;
   t.tm_sec = 40;
   t.tm_year = 00;
   t.tm_mday = 4;
   t.tm_mon = 6;

   pszPutI.imbue( loc );
   char *pattern = "x: %X %x";
   use_facet <time_put <char> >
   (loc).put(basic_ostream<char>::_Iter(pszPutI.rdbuf( )),
          pszPutI, ' ', &t, pattern, pattern+strlen(pattern));

      cout << "num_put( ) = " << pszPutI.rdbuf( )->str( ) << endl;

      char strftimebuf[255];
      strftime(&strftimebuf[0], 255, pattern, &t);
      cout << "strftime( ) = " << &strftimebuf[0] << endl;
}
```

```Output
num_put( ) = x: 05:30:40 07/04/00
strftime( ) = x: 05:30:40 07/04/00
```

## <a name="time_puttime_put"></a><a name="time_put"></a>time_put:: time_put

Конструктор для объектов типа `time_put`.

```cpp
explicit time_put(size_t _Refs = 0);
```

### <a name="parameters"></a>Параметры

*_Refs*\
Целочисленное значение, используемое для указания типа управления памятью для объекта.

### <a name="remarks"></a>Примечания

Возможные значения параметра *_Refs* и их значимость:

- 0: время существования объекта управляется языковыми стандартами, которые его содержат.

- 1: время существования объекта должно управляться вручную.

- \>1: эти значения не определены.

Конструктор инициализирует свой базовый объект с [языковым стандартом:: Facet](../standard-library/locale-class.md#facet_class)(*_Refs*).

## <a name="see-also"></a>См. также раздел

[\<locale>](../standard-library/locale.md)\
[Класс time_base](../standard-library/time-base-class.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
