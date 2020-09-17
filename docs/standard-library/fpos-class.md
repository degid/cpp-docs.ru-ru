---
title: Класс fpos
ms.date: 03/27/2019
f1_keywords:
- iosfwd/std::fpos
- iosfwd/std::fpos::seekpos
- iosfwd/std::fpos::state
- iosfwd/std::fpos::operator streamoff
helpviewer_keywords:
- std::fpos [C++]
- std::fpos [C++], seekpos
- std::fpos [C++], state
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
ms.openlocfilehash: 37536443455ca4ddc40568e15951b814982d4ad9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87193306"
---
# <a name="fpos-class"></a>Класс fpos

Шаблон класса описывает объект, который может хранить всю информацию, необходимую для восстановления произвольного индикатора положения файла в любом потоке. Объект класса fpos \< **St**> эффективно хранит по крайней мере два объекта члена:

- Смещение в байтах типа [streamoff](../standard-library/ios-typedefs.md#streamoff).

- Состояние преобразования, используемое объектом класса basic_filebuf типа `St` , обычно `mbstate_t` .

Также можно хранить произвольное положение в файле для использования объектом класса [basic_filebuf](../standard-library/basic-filebuf-class.md) типа `fpos_t`. В среде с ограниченным размером файлов `streamoff` и `fpos_t` могут быть взаимозаменяемыми. В среде без потоков с кодированием, зависящим от состояния, `mbstate_t` может фактически не использоваться. Таким образом, число хранимых объектов-членов может различаться.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Statetype>
class fpos
```

### <a name="parameters"></a>Параметры

*StateType*\
Сведения о состоянии.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[fpos](#fpos)|Создает объект, содержащий сведения о положении (смещении) в потоке.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[seekpos](#seekpos)|Используется только внутренними механизмами стандартной библиотеки C++. Не вызывайте этот метод в коде.|
|[state](#state)|Задает или возвращает состояние преобразования.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](#op_neq)|Проверяет индикаторы положений в файлах на неравенство.|
|[operator+](#op_add)|Увеличивает значение положения в файле.|
|[operator+=](#op_add_eq)|Увеличивает значение положения в файле.|
|[operator-](#operator-)|Уменьшает значение положения в файле.|
|[operator-=](#operator-_eq)|Уменьшает значение положения в файле.|
|[operator==](#op_eq_eq)|Проверяет индикаторы положений в файлах на равенство.|
|[operator streamoff](#op_streamoff)|Приводит объект типа `fpos` к объекту типа `streamoff`.|

## <a name="requirements"></a>Требования

**Заголовок:**\<ios>

**Пространство имен:** std

## <a name="fposfpos"></a><a name="fpos"></a>fpos:: fpos

Создает объект, содержащий сведения о положении (смещении) в потоке.

```cpp
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```

### <a name="parameters"></a>Параметры

*_Off*\
Смещение в поток.

*_State*\
Начальное состояние объекта `fpos`.

*_Filepos*\
Смещение в поток.

### <a name="remarks"></a>Примечания

Первый конструктор сохраняет *_Off*смещения относительно начала файла и в начальном состоянии преобразования (если это важно). Если *_Off* равен-1, результирующий объект представляет недопустимую точку в потоке.

Второй конструктор сохраняет нулевое смещение и объект *_State*.

## <a name="fposoperator"></a><a name="op_neq"></a>fpos::operator!=

Проверяет индикаторы положений в файлах на неравенство.

```cpp
bool operator!=(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Индикатор положения в файле, с которым нужно выполнять сравнение.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если индикаторы позиционирования файлов не равны; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Функция-член возвращает значение `!(*this == right)`.

### <a name="example"></a>Пример

```cpp
// fpos_op_neq.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;

   fpos<int> pos1, pos2;
   ifstream file;
   char c;

   // Compare two fpos object
   if ( pos1 != pos2 )
      cout << "File position pos1 and pos2 are not equal" << endl;
   else
      cout << "File position pos1 and pos2 are equal" << endl;

   file.open( "fpos_op_neq.txt" );
   file.seekg( 0 );   // Goes to a zero-based position in the file
   pos1 = file.tellg( );
   file.get( c);
   cout << c << endl;

   // Increment pos1
   pos1 += 1;
   file.get( c );
   cout << c << endl;

   pos1 = file.tellg( ) - fpos<int>( 2);
   file.seekg( pos1 );
   file.get( c );
   cout << c << endl;

   // Increment pos1
   pos1 = pos1 + fpos<int>( 1 );
   file.get(c);
   cout << c << endl;

   pos1 -= fpos<int>( 2 );
   file.seekg( pos1 );
   file.get( c );
   cout << c << endl;

   file.close( );
}
```

## <a name="fposoperator"></a><a name="op_add"></a>fpos::operator+

Увеличивает значение положения в файле.

```cpp
fpos<Statetype> operator+(streamoff _Off) const;
```

### <a name="parameters"></a>Параметры

*_Off*\
Смещение, на которое нужно увеличить индикатор положения в файле.

### <a name="return-value"></a>Возвращаемое значение

Позиция в файле.

### <a name="remarks"></a>Примечания

Функция-член возвращает **fpos(\*this) +=** `_Off`.

### <a name="example"></a>Пример

См. в [operator!=](#op_neq) пример применения `operator+`.

## <a name="fposoperator"></a><a name="op_add_eq"></a>fpos::operator+=

Увеличивает значение положения в файле.

```cpp
fpos<Statetype>& operator+=(streamoff _Off);
```

### <a name="parameters"></a>Параметры

*_Off*\
Смещение, на которое нужно увеличить индикатор положения в файле.

### <a name="return-value"></a>Возвращаемое значение

Позиция в файле.

### <a name="remarks"></a>Примечания

Функция члена добавляет *_Off* к сохраненному объекту смещения элемента, а затем возвращает ** \*this**. Для позиционирования в файле результат будет обычно действителен только для двоичных потоков, в которых не применяется зависящее от состояния кодирование.

### <a name="example"></a>Пример

См. в [operator!=](#op_neq) пример применения `operator+=`.

## <a name="fposoperator-"></a><a name="operator-"></a>fpos::operator-

Уменьшает значение положения в файле.

```cpp
streamoff operator-(const fpos<Statetype>& right) const;

fpos<Statetype> operator-(streamoff _Off) const;
```

### <a name="parameters"></a>Параметры

*right*\
Положение в файле.

*_Off*\
Смещение потока.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает значение `(streamoff)*this - (streamoff) right`. Вторая функция-член возвращает значение `fpos(*this) -= _Off`.

### <a name="example"></a>Пример

См. в [operator!=](#op_neq) пример применения `operator-`.

## <a name="fposoperator-"></a><a name="operator-_eq"></a>fpos::operator-=

Уменьшает значение положения в файле.

```cpp
fpos<Statetype>& operator-=(streamoff _Off);
```

### <a name="parameters"></a>Параметры

*_Off*\
Смещение потока.

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает значение `fpos(*this) -= _Off`.

### <a name="remarks"></a>Примечания

Для позиционирования в файле результат будет обычно действителен только для двоичных потоков, в которых не применяется зависящее от состояния кодирование.

### <a name="example"></a>Пример

См. в [operator!=](#op_neq) пример применения `operator-=`.

## <a name="fposoperator"></a><a name="op_eq_eq"></a>fpos::operator==

Проверяет индикаторы положений в файлах на равенство.

```cpp
bool operator==(const fpos<Statetype>& right) const;
```

### <a name="parameters"></a>Параметры

*right*\
Индикатор положения в файле, с которым нужно выполнять сравнение.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если индикаторы позиционирования файлов равны; в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Функция-член возвращает значение `(streamoff)*this == (streamoff)right`.

### <a name="example"></a>Пример

См. в [operator!=](#op_neq) пример применения `operator+=`.

## <a name="fposoperator-streamoff"></a><a name="op_streamoff"></a>fpos::operator streamoff

Приводит объект типа `fpos` к объекту типа `streamoff`.

```cpp
operator streamoff() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает хранимый объект-член смещения и любое дополнительное смещение, хранимое как часть объекта-члена `fpos_t`.

### <a name="example"></a>Пример

```cpp
// fpos_op_streampos.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main( )
{
   using namespace std;
   streamoff s;
   ofstream file( "rdbuf.txt");

   fpos<mbstate_t> f = file.tellp( );
   // Is equivalent to ..
   // streampos f = file.tellp( );
   s = f;
   cout << s << endl;
}
```

```Output
0
```

## <a name="fposseekpos"></a><a name="seekpos"></a>fpos:: seekpos

Этот метод используется только внутренними механизмами стандартной библиотеки C++. Не вызывайте этот метод в коде.

```cpp
fpos_t seekpos() const;
```

## <a name="fposstate"></a><a name="state"></a>fpos:: State

Задает или возвращает состояние преобразования.

```cpp
Statetype state() const;

void state(Statetype _State);
```

### <a name="parameters"></a>Параметры

*_State*\
Новое состояние преобразования.

### <a name="return-value"></a>Возвращаемое значение

Состояние преобразования.

### <a name="remarks"></a>Примечания

Первая функция – член возвращает значение, хранящееся в `St` объекте члена. Вторая функция – член сохраняет *_State* в `St` объекте Member.

### <a name="example"></a>Пример

```cpp
// fpos_state.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main() {
   using namespace std;
   streamoff s;
   ifstream file( "fpos_state.txt" );

   fpos<mbstate_t> f = file.tellg( );
   char ch;
   while ( !file.eof( ) )
      file.get( ch );
   s = f;
   cout << f.state( ) << endl;
   f.state( 9 );
   cout << f.state( ) << endl;
}
```

## <a name="see-also"></a>См. также раздел

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
