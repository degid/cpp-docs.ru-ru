---
title: Класс istream_iterator
ms.date: 11/04/2016
f1_keywords:
- iterator/std::istream_iterator
- iterator/std::istream_iterator::char_type
- iterator/std::istream_iterator::istream_type
- iterator/std::istream_iterator::traits_type
helpviewer_keywords:
- std::istream_iterator [C++]
- std::istream_iterator [C++], char_type
- std::istream_iterator [C++], istream_type
- std::istream_iterator [C++], traits_type
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
ms.openlocfilehash: 4ab1c6188a076b46f08b9ea171a8a945cbe1fc70
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215677"
---
# <a name="istream_iterator-class"></a>Класс istream_iterator

Описывает объект итератора ввода. Извлекает объекты класса `Type` из входного потока, доступ к которому получает через сохраненный объект типа `pointer`, на `basic_istream`< `CharType`, `Traits`>.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type, class CharType = char, class Traits = char_traits<CharType>, class Distance = ptrdiff_t,>
class istream_iterator
: public iterator<
    input_iterator_tag, Type, Distance,
    const Type *,
    const Type&>;
```

### <a name="parameters"></a>Параметры

*Type*\
Тип объекта, который необходимо извлечь из потока ввода.

*CharType*\
Тип, представляющий шрифт символа для `istream_iterator`. Этот аргумент является необязательным, и значение по умолчанию — **`char`** .

*Traits*\
Тип, представляющий шрифт символа для `istream_iterator`. Этот аргумент является необязательным, и в качестве значения по умолчанию используется `char_traits`< `CharType`>.

*Друг*\
Тип целого числа со знаком, представляющий тип отличия для `istream_iterator`. Этот аргумент является необязательным, и значением по умолчанию является `ptrdiff_t`.

После создания или увеличения объекта класса istream_iterator с помощью сохраненного указателя, не содержащего null, объект фактически пытается извлечь и сохранить объект типа `Type` из соответствующего входного потока. Если извлечение завершается ошибкой, этот объект фактически заменяет сохраненный указатель указателем null, тем самым создавая индикатор конца последовательности.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[istream_iterator](#istream_iterator)|Создает итератор конца потока в качестве итератора `istream_iterator` по умолчанию или итератор `istream_iterator`, инициализированный в тип потока итератора, из которого он считывается.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип, обеспечивающий тип символа для `istream_iterator`.|
|[istream_type](#istream_type)|Тип, обеспечивающий тип потока для `istream_iterator`.|
|[traits_type](#traits_type)|Тип, обеспечивающий тип признаков символа для `istream_iterator`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator*](#op_star)|Оператор удаления ссылки возвращает сохраненный объект типа `Type`, к которому обращается `istream_iterator`.|
|[operator->](#op_arrow)|Возвращает значение члена при наличии.|
|[operator++](#op_add_add)|Либо извлекает увеличенный объект из входного потока, либо копирует объект перед его увеличением и возвращает копию.|

## <a name="requirements"></a>Требования

**Заголовок:**\<iterator>

**Пространство имен:** std

## <a name="istream_iteratorchar_type"></a><a name="char_type"></a>istream_iterator:: char_type

Тип, обеспечивающий тип символа для `istream_iterator`.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `Chartype`.

### <a name="example"></a>Пример

```cpp
// istream_iterator_char_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef istream_iterator<int>::char_type CHT1;
   typedef istream_iterator<int>::traits_type CHTR1;

   // Standard iterator interface for reading
   // elements from the input stream:
   cout << "Enter integers separated by spaces & then\n"
        << " any character ( try example: '2 4 f' ): ";

   // istream_iterator for reading int stream
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );

   // End-of-stream iterator
   istream_iterator<int, CHT1, CHTR1> EOFintRead;

   while ( intRead != EOFintRead )
   {
      cout << "Reading:  " << *intRead << endl;
      ++intRead;
   }
   cout << endl;
}
```

## <a name="istream_iteratoristream_iterator"></a><a name="istream_iterator"></a>istream_iterator:: istream_iterator

Создает итератор конца потока в качестве итератора `istream_iterator` по умолчанию или итератор `istream_iterator`, инициализированный в тип потока итератора, из которого он считывается.

```cpp
istream_iterator();

istream_iterator(istream_type& _Istr);
```

### <a name="parameters"></a>Параметры

*_Istr*\
Входной поток для чтения, используется для инициализации `istream_iterator`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует указатель входного потока значением null и создает итератор конца потока. Второй конструктор инициализирует указатель входного потока с *&_Istr*, а затем пытается извлечь и сохранить объект типа `Type` .

Итератор конца потока можно использовать для проверки, достигнут ли конец потока `istream_iterator`.

### <a name="example"></a>Пример

```cpp
// istream_iterator_istream_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <algorithm>
#include <iostream>

int main( )
{
   using namespace std;

   // Used in conjunction with copy algorithm
   // to put elements into a vector read from cin
   vector<int> vec ( 4 );
   vector <int>::iterator Iter;

   cout << "Enter 4 integers separated by spaces & then\n"
        << " a character ( try example: '2 4 6 8 a' ): ";
   istream_iterator<int> intvecRead ( cin );

   // Default constructor will test equal to end of stream
   // for delimiting source range of vecor
   copy ( intvecRead , istream_iterator<int>( ) , vec.begin ( ) );
   cin.clear ( );

   cout << "vec = ";
   for ( Iter = vec.begin( ) ; Iter != vec.end( ) ; Iter++ )
      cout << *Iter << " "; cout << endl;
}
```

## <a name="istream_iteratoristream_type"></a><a name="istream_type"></a>istream_iterator:: istream_type

Тип, обеспечивающий тип потока для `istream_iterator`.

```cpp
typedef basic_istream<CharType, Traits> istream_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `basic_istream` \< **CharType**, **Traits**> .

### <a name="example"></a>Пример

См. раздел [istream_iterator](#istream_iterator) с примером объявления и использования `istream_type`.

## <a name="istream_iteratoroperator"></a><a name="op_star"></a>istream_iterator::operator*

Оператор удаления ссылки возвращает сохраненный объект типа `Type`, к которому обращается `istream_iterator`.

```cpp
const Type& operator*() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект типа `Type` .

### <a name="example"></a>Пример

```cpp
// istream_iterator_operator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <algorithm>
#include <iostream>

int main( )
{
   using namespace std;

   cout << "Enter integers separated by spaces & then\n"
        << " a character ( try example: '2 4 6 8 a' ): ";

   // istream_iterator from stream cin
   istream_iterator<int> intRead ( cin );

   // End-of-stream iterator
   istream_iterator<int> EOFintRead;

   while ( intRead != EOFintRead )
   {
      cout << "Reading:  " << *intRead << endl;
      ++intRead;
   }
   cout << endl;
}
```

## <a name="istream_iteratoroperator-gt"></a><a name="op_arrow"></a>istream_iterator::operator-&gt;

Возвращает значение члена при наличии.

```cpp
const Type* operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение члена при его наличии.

### <a name="remarks"></a>Примечания

`i->m` — это эквивалент `(*i).m`

Оператор возвращает `&*this`.

### <a name="example"></a>Пример

```cpp
// istream_iterator_operator_vm.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>
#include <complex>

using namespace std;

int main( )
{
   cout << "Enter complex numbers separated by spaces & then\n"
        << " a character pair ( try example: '(1,2) (3,4) (a,b)' ): ";

   // istream_iterator from stream cin
   istream_iterator< complex<double> > intRead ( cin );

   // End-of-stream iterator
   istream_iterator<complex<double> > EOFintRead;

   while ( intRead != EOFintRead )
   {
      cout << "Reading the real part: " << intRead ->real( ) << endl;
      cout << "Reading the imaginary part: " << intRead ->imag( ) << endl;
      ++intRead;
   }
   cout << endl;
}
```

## <a name="istream_iteratoroperator"></a><a name="op_add_add"></a>istream_iterator::operator++

Либо извлекает увеличенный объект из входного потока, либо копирует объект перед его увеличением и возвращает копию.

```cpp
istream_iterator<Type, CharType, Traits, Distance>& operator++();

istream_iterator<Type, CharType, Traits, Distance> operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый оператор-член возвращает ссылку на увеличивающийся объект типа, `Type` извлеченного из входного потока, а вторая функция-член возвращает копию объекта.

### <a name="example"></a>Пример

```cpp
// istream_iterator_operator_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <algorithm>
#include <iostream>

int main( )
{
   using namespace std;

   cout << "Enter integers separated by spaces & then\n"
        << " a character ( try example: '2 4 6 8 a' ): ";

   // istream_iterator from stream cin
   istream_iterator<int> intRead ( cin );

   // End-of-stream iterator
   istream_iterator<int> EOFintRead;

   while ( intRead != EOFintRead )
   {
      cout << "Reading:  " << *intRead << endl;
      ++intRead;
   }
   cout << endl;
}
```

## <a name="istream_iteratortraits_type"></a><a name="traits_type"></a>istream_iterator:: traits_type

Тип, обеспечивающий тип признаков символа для `istream_iterator`.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра-шаблона *Traits*.

### <a name="example"></a>Пример

```cpp
// istream_iterator_traits_type.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

int main( )
{
   using namespace std;

   typedef istream_iterator<int>::char_type CHT1;
   typedef istream_iterator<int>::traits_type CHTR1;

   // Standard iterator interface for reading
   // elements from the input stream:
   cout << "Enter integers separated by spaces & then\n"
        << " any character ( try example: '10 20 a' ): ";

   // istream_iterator for reading int stream
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );

   // End-of-stream iterator
   istream_iterator<int, CHT1, CHTR1> EOFintRead;

   while ( intRead != EOFintRead )
   {
      cout << "Reading:  " << *intRead << endl;
      ++intRead;
   }
   cout << endl;
}
```

## <a name="see-also"></a>См. также раздел

[Структура input_iterator_tag](../standard-library/input-iterator-tag-struct.md)\
[Структура итератора](../standard-library/iterator-struct.md)\
[\<iterator>](../standard-library/iterator.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
