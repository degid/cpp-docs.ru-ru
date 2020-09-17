---
title: Операторы &lt;istream&gt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: 3b9521fde1b5a03389bfc1ad3e35fa407d9d6ac0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363037"
---
# <a name="ltistreamgt-operators"></a>Операторы &lt;istream&gt;

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a>Оператор&gt;&gt;

Извлекает символы и строки из потока.

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>Параметры

*Ch*\
Символ.

*Истр*\
Поток.

*str*\
Строка.

*Валь*\
Тип.

### <a name="return-value"></a>Возвращаемое значение

Поток.

### <a name="remarks"></a>Примечания

Класс `basic_istream` также определяет несколько операторов извлечения. Дополнительные сведения см. в разделе [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt).

Шаблон функции:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

извлекает до `N - 1` элементов и хранит их в массиве, начиная с *str.* Если `Istr.` [ширина](../standard-library/ios-base-class.md#width) больше нуля, `Istr.width` *N* ; в противном случае, это размер `Elem` самого большого массива, который может быть объявлен. Функция всегда хранит `Elem()` значение после любых извлеченных элементов, которые она хранит. Извлечение останавливается рано в конце `Elem(0)` файла, на символе со значением (который не извлечен), или на любом элементе (который не извлечен), который будет отброшен [ws.](../standard-library/istream-functions.md#ws) Если функция не извлекает элементов, она вызывает `Istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`. В любом случае, `Istr.width(0)` он вызывает и возвращает *Istr*.

**Примечание безопасности** Нулевая строка, извлеченная из входного потока, не должна превышать размер *строки*буфера назначения. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

Шаблон функции:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

извлекает элемент, если это возможно, и хранит его в *Ch*. В противном `is.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`случае, он вызывает . В любом случае, он возвращает *Istr*.

Шаблон функции:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

Возвращает `Istr >> ( char * ) str`.

Шаблон функции:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

Возвращает `Istr >> ( char& ) Ch`.

Шаблон функции:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

Возвращает `Istr >> ( char * ) str`.

Шаблон функции:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

Возвращает `Istr >> ( char& ) Ch`.

Шаблон функции:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

возвращает `Istr >> val` (и преобразует ссылку `Istr` на rvalue к lvalue в процессе).

### <a name="example"></a>Пример

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>См. также раздел

[\<istream>](../standard-library/istream.md)
