---
title: Класс complex
ms.date: 03/27/2019
f1_keywords:
- complex/std::complex::value_type
- complex/std::complex::imag
- complex/std::complex::real
helpviewer_keywords:
- std::complex [C++], value_type
- std::complex [C++], imag
- std::complex [C++], real
ms.assetid: d6492e1c-5eba-4bc5-835b-2a88001a5868
ms.openlocfilehash: c7e2ca2c14ed0ac5f561fab446f6cd2dcc19649d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836548"
---
# <a name="complex-class"></a>Класс complex

Шаблон класса описывает объект, в котором хранятся два объекта типа `Type` , один из которых представляет реальную часть комплексного числа, а другой — мнимую часть.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type>
class complex
```

## <a name="remarks"></a>Примечания

Объект класса `Type` :

- Имеет открытый конструктор по умолчанию, деструктор, конструктор копии и оператор присваивания, работающие обычным образом.

- Могут быть присвоены целочисленные значения или значения с плавающей запятой, или приведение типов к таким значениям с обычным поведением.

- При необходимости определяет арифметические операторы и математические функции, определенные для типов с плавающей запятой и работающие обычным образом.

В частности, между конструкцией копирования и конструкцией по умолчанию, за которыми следует присваивание, не может существовать даже малейших отличий. Ни одна из операций с объектами класса `Type` не может вызывать исключения.

Явные специализации шаблона класса Complex существуют для трех типов с плавающей запятой. В этой реализации значение любого другого типа `Type` является приведением к **`double`** фактическим вычислениям с **`double`** возвратом результата в сохраненный объект типа `Type` .

## <a name="members"></a>Элементы

### <a name="constructors"></a>Конструкторы

|Имя|Описание|
|-|-|
|[сложной](#complex)|Строит комплексное число с указанными вещественной и мнимой частями или как копию некоторого другого комплексного числа.|

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|-|-|
|[value_type](#value_type)|Тип, представляющий тип данных, который используется для представления действительной и мнимой частей комплексного числа.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[imag](#imag)|Извлекает мнимую часть комплексного числа.|
|[real](#real)|Извлекает вещественную часть комплексного числа.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator*=](#op_star_eq)|Умножает целевое комплексное число на множитель, который может быть комплексным или иметь тот же тип, что и действительная и мнимая части комплексного числа.|
|[operator+=](#op_add_eq)|Добавляет число к целевому комплексному числу, где добавляемое число может быть комплексным или того же типа, что и действительная и мнимая части комплексного числа, к которому выполняется добавление.|
|[operator-=](#operator-_eq)|Вычитает число из целевого комплексного числа, где вычитаемое число может быть комплексным или того же типа, что и действительная и мнимая части комплексного числа, из которого выполняется вычитание.|
|[operator/=](#op_div_eq)|Делит целевое комплексное число на делитель, который может быть комплексным или иметь тот же тип, что и действительная и мнимая части комплексного числа.|
|[operator=](#op_eq)|Присваивает число целевому комплексному числу, где присваиваемое число может быть комплексным или того же типа, что и действительная и мнимая части комплексного числа, которому выполняется присвоение.|

## <a name="complex"></a><a name="complex"></a> сложной

Строит комплексное число с указанными вещественной и мнимой частями или как копию некоторого другого комплексного числа.

```cpp
constexpr complex(
    const T& _RealVal = 0,
    const T& _ImagVal = 0);

template <class Other>
constexpr complex(
    const complex<Other>& complexNum);
```

### <a name="parameters"></a>Параметры

*_RealVal*\
Значение вещественной части, используемое для инициализации конструируемого комплексного числа.

*_ImagVal*\
Значение мнимой части, используемое для инициализации конструируемого комплексного числа.

*комплекснум*\
Комплексное число, вещественная и мнимая части которого используются для инициализации конструируемого комплексного числа.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует хранимую реальную часть * \_ реалвал* , а хранимую мнимую часть — * \_ имагвал*. Второй конструктор инициализирует хранимую реальную часть `complexNum.real()` , а хранимую мнимую часть — на `complexNum.imag()` .

Если в этой реализации транслятор не поддерживает функции шаблона члена, то шаблон

```cpp
template <class Other>
complex(const complex<Other>& right);
```

заменяется на

```cpp
complex(const complex& right);
```

который является конструктором копии.

### <a name="example"></a>Пример

```cpp
// complex_complex.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    double pi = 3.14159265359;

    // The first constructor specifies real & imaginary parts
    complex<double> c1( 4.0 , 5.0 );
    cout << "Specifying initial real & imaginary parts,"
        << "c1 = " << c1 << endl;

    // The second constructor initializes values of the real &
    // imaginary parts using those of another complex number
    complex<double> c2( c1 );
    cout << "Initializing with the real and imaginary parts of c1,"
        << " c2 = " << c2 << endl;

    // Complex numbers can be initialized in polar form
    // but will be stored in Cartesian form
    complex<double> c3( polar( sqrt( (double)8 ) , pi / 4 ) );
    cout << "c3 = polar( sqrt( 8 ) , pi / 4 ) = " << c3 << endl;

    // The modulus and argument of a complex number can be recovered
    double absc3 = abs( c3 );
    double argc3 = arg( c3 );
    cout << "The modulus of c3 is recovered from c3 using: abs( c3 ) = "
        << absc3 << endl;
    cout << "Argument of c3 is recovered from c3 using:\n arg( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
```

## <a name="imag"></a><a name="imag"></a> ин

Извлекает мнимую часть комплексного числа.

```cpp
T imag() const;

T imag(const T& right);
```

### <a name="parameters"></a>Параметры

*right*\
Комплексное число, мнимая часть которого извлекается.

### <a name="return-value"></a>Возвращаемое значение

Мнимая часть комплексного числа.

### <a name="remarks"></a>Примечания

Для комплексного числа *a + bi*мнимая часть или компонент — это *IM (a + BI) = b*.

### <a name="example"></a>Пример

```cpp
// complex_imag.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;

    complex<double> c1( 4.0 , 3.0 );
    cout << "The complex number c1 = " << c1 << endl;

    double dr1 = c1.real();
    cout << "The real part of c1 is c1.real() = "
        << dr1 << "." << endl;

    double di1 = c1.imag();
    cout << "The imaginary part of c1 is c1.imag() = "
        << di1 << "." << endl;
}
```

```Output
The complex number c1 = (4,3)
The real part of c1 is c1.real() = 4.
The imaginary part of c1 is c1.imag() = 3.
```

## <a name="operator"></a><a name="op_star_eq"></a> operator*=

Умножает целевое комплексное число на множитель, который может быть комплексным или иметь тот же тип, что и действительная и мнимая части комплексного числа.

```cpp
template <class Other>
complex& operator*=(const complex<Other>& right);

complex<Type>& operator*=(const Type& right);

complex<Type>& operator*=(const complex<Type>& right);
```

### <a name="parameters"></a>Параметры

*right*\
Комплексное число или число того же типа, что и параметр целевого комплексного числа.

### <a name="return-value"></a>Возвращаемое значение

Комплексное число, умноженное на число, указанное в качестве параметра.

### <a name="remarks"></a>Примечания

Эта операция является перегруженной, так что простые арифметические операции могут выполняться без преобразования данных в определенный формат.

### <a name="example"></a>Пример

```cpp
// complex_op_me.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main()
{
    using namespace std;
    double pi = 3.14159265359;

    // Example of the first member function
    // type complex<double> multiplied by type complex<double>
    complex<double> cl1( polar ( 3.0 , pi / 6 ) );
    complex<double> cr1( polar ( 2.0 , pi / 3 ) );
    cout << "The left-side complex number is cl1 = " << cl1 << endl;
    cout << "The right-side complex number is cr1 = " << cr1 << endl;

    complex<double> cs1 = cl1 * cr1;
    cout << "Quotient of two complex numbers is: cs1 = cl1 * cr1 = "
        << cs1 << endl;

    // This is equivalent to the following operation
    cl1 *= cr1;
    cout << "Quotient of two complex numbers is also: cl1 *= cr1 = "
        << cl1 << endl;

    double abscl1 = abs ( cl1 );
    double argcl1 = arg ( cl1 );
    cout << "The modulus of cl1 is: " << abscl1 << endl;
    cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "
        << argcl1 * 180 / pi << " degrees." << endl << endl;

    // Example of the second member function
    // type complex<double> multiplied by type double
    complex<double> cl2 ( polar ( 3.0 , pi / 6 ) );
    double cr2 = 5.0;
    cout << "The left-side complex number is cl2 = " << cl2 << endl;
    cout << "The right-side complex number is cr2 = " << cr2 << endl;

    complex<double> cs2 = cl2 * cr2;
    cout << "Quotient of two complex numbers is: cs2 = cl2 * cr2 = "
        << cs2 << endl;

    // This is equivalent to the following operation
    cl2 *= cr2;
    cout << "Quotient of two complex numbers is also: cl2 *= cr2 = "
        << cl2 << endl;

    double abscl2 = abs ( cl2 );
    double argcl2 = arg ( cl2 );
    cout << "The modulus of cl2 is: " << abscl2 << endl;
    cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "
        << argcl2 * 180 / pi << " degrees." << endl;
}
```

## <a name="operator"></a><a name="op_add_eq"></a> operator+=

Добавляет число к целевому комплексному числу, где добавляемое число может быть комплексным или того же типа, что и действительная и мнимая части комплексного числа, к которому выполняется добавление.

```cpp
template <class Other>
complex<Type>& operator+=(const complex<Other>& right);

complex<Type>& operator+=(const Type& right);

complex<Type>& operator+=(const complex<Type>& right);
```

### <a name="parameters"></a>Параметры

*right*\
Комплексное число или число того же типа, что и параметр целевого комплексного числа.

### <a name="return-value"></a>Возвращаемое значение

Комплексное число, к которому добавлено число, указанное в качестве параметра.

### <a name="remarks"></a>Примечания

Эта операция является перегруженной, так что простые арифметические операции могут выполняться без преобразования данных в определенный формат.

### <a name="example"></a>Пример

```cpp
// complex_op_pe.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // Example of the first member function
   // type complex<double> added to type complex<double>
   complex<double> cl1( 3.0 , 4.0 );
   complex<double> cr1( 2.0 , -1.0 );
   cout << "The left-side complex number is cl1 = " << cl1 << endl;
   cout << "The right-side complex number is cr1 = " << cr1 << endl;

   complex<double> cs1 = cl1 + cr1;
   cout << "The sum of the two complex numbers is: cs1 = cl1 + cr1 = "
        << cs1 << endl;

   // This is equivalent to the following operation
   cl1 += cr1;
   cout << "The complex number cr1 added to the complex number cl1 is:"
        << "\n cl1 += cr1 = " << cl1 << endl;

   double abscl1 = abs( cl1 );
   double argcl1 = arg( cl1 );
   cout << "The modulus of cl1 is: " << abscl1 << endl;
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "
        << argcl1 * 180 / pi << " degrees." << endl << endl;

   // Example of the second member function
   // type double added to type complex<double>
   complex<double> cl2( -2 , 4 );
   double cr2 =5.0;
   cout << "The left-side complex number is cl2 = " << cl2 << endl;
   cout << "The right-side complex number is cr2 = " << cr2 << endl;

   complex<double> cs2 = cl2 + cr2;
   cout << "The sum of the two complex numbers is: cs2 = cl2 + cr2 = "
        << cs2 << endl;

   // This is equivalent to the following operation
   cl2 += cr2;
   cout << "The complex number cr2 added to the complex number cl2 is:"
        << "\n cl2 += cr2 = " << cl2 << endl;

   double abscl2 = abs( cl2 );
   double argcl2 = arg( cl2 );
   cout << "The modulus of cl2 is: " << abscl2 << endl;
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "
        << argcl2 * 180 / pi << " degrees." << endl << endl;
}
```

```Output
The left-side complex number is cl1 = (3,4)
The right-side complex number is cr1 = (2,-1)
The sum of the two complex numbers is: cs1 = cl1 + cr1 = (5,3)
The complex number cr1 added to the complex number cl1 is:
cl1 += cr1 = (5,3)
The modulus of cl1 is: 5.83095
The argument of cl1 is: 0.54042 radians, which is 30.9638 degrees.

The left-side complex number is cl2 = (-2,4)
The right-side complex number is cr2 = 5
The sum of the two complex numbers is: cs2 = cl2 + cr2 = (3,4)
The complex number cr2 added to the complex number cl2 is:
cl2 += cr2 = (3,4)
The modulus of cl2 is: 5
The argument of cl2 is: 0.927295 radians, which is 53.1301 degrees.
```

## <a name="operator-"></a><a name="operator-_eq"></a> operator-=

Вычитает число из целевого комплексного числа, где вычитаемое число может быть комплексным или того же типа, что и действительная и мнимая части комплексного числа, из которого выполняется вычитание.

```cpp
template <class Other>
complex<Type>& operator-=(const complex<Other>& complexNum);

complex<Type>& operator-=(const Type& _RealPart);

complex<Type>& operator-=(const complex<Type>& complexNum);
```

### <a name="parameters"></a>Параметры

*комплекснум*\
Комплексное число для вычитания из целевого комплексного числа.

*_RealPart*\
Действительное число для вычитания из целевого комплексного числа.

### <a name="return-value"></a>Возвращаемое значение

Комплексное число, из которого вычтено число, указанное в качестве параметра.

### <a name="remarks"></a>Примечания

Эта операция является перегруженной, так что простые арифметические операции могут выполняться без преобразования данных в определенный формат.

### <a name="example"></a>Пример

```cpp
// complex_op_se.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // Example of the first member function
   // type complex<double> subtracted from type complex<double>
   complex<double> cl1( 3.0 , 4.0 );
   complex<double> cr1( 2.0 , -1.0 );
   cout << "The left-side complex number is cl1 = " << cl1 << endl;
   cout << "The right-side complex number is cr1 = " << cr1 << endl;

   complex<double> cs1 = cl1 - cr1;
   cout << "The difference between the two complex numbers is:"
        << "\n cs1 = cl1 - cr1 = " << cs1 << endl;

   // This is equivalent to the following operation
   cl1 -= cr1;
   cout << "Complex number cr1 subtracted from complex number cl1 is:"
        << "\n cl1 -= cr1 = " << cl1 << endl;

   double abscl1 = abs( cl1 );
   double argcl1 = arg( cl1 );
   cout << "The modulus of cl1 is: " << abscl1 << endl;
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "
        << argcl1 * 180 / pi << " degrees." << endl << endl;

   // Example of the second member function
   // type double subtracted from type complex<double>
   complex<double> cl2( 2.0 , 4.0 );
   double cr2 = 5.0;
   cout << "The left-side complex number is cl2 = " << cl2 << endl;
   cout << "The right-side complex number is cr2 = " << cr2 << endl;

   complex<double> cs2 = cl2 - cr2;
   cout << "The difference between the two complex numbers is:"
        << "\n cs2 = cl2 - cr2 = " << cs2 << endl;

   // This is equivalent to the following operation
   cl2  -= cr2;
   cout << "Complex number cr2 subtracted from complex number cl2 is:"
        << "\n cl2 -= cr2 = " << cl2 << endl;

   double abscl2 = abs( cl2 );
   double argcl2 = arg( cl2 );
   cout << "The modulus of cl2 is: " << abscl2 << endl;
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "
        << argcl2 * 180 / pi << " degrees." << endl << endl;
}
```

```Output
The left-side complex number is cl1 = (3,4)
The right-side complex number is cr1 = (2,-1)
The difference between the two complex numbers is:
cs1 = cl1 - cr1 = (1,5)
Complex number cr1 subtracted from complex number cl1 is:
cl1 -= cr1 = (1,5)
The modulus of cl1 is: 5.09902
The argument of cl1 is: 1.3734 radians, which is 78.6901 degrees.

The left-side complex number is cl2 = (2,4)
The right-side complex number is cr2 = 5
The difference between the two complex numbers is:
cs2 = cl2 - cr2 = (-3,4)
Complex number cr2 subtracted from complex number cl2 is:
cl2 -= cr2 = (-3,4)
The modulus of cl2 is: 5
The argument of cl2 is: 2.2143 radians, which is 126.87 degrees.
```

## <a name="operator"></a><a name="op_div_eq"></a> operator/=

Делит целевое комплексное число на делитель, который может быть комплексным или иметь тот же тип, что и действительная и мнимая части комплексного числа.

```cpp
template <class Other>
complex<Type>& operator/=(const complex<Other>& complexNum);

complex<Type>& operator/=(const Type& _RealPart);

complex<Type>& operator/=(const complex<Type>& complexNum);
```

### <a name="parameters"></a>Параметры

*комплекснум*\
Комплексное число для вычитания из целевого комплексного числа.

*_RealPart*\
Действительное число для вычитания из целевого комплексного числа.

### <a name="return-value"></a>Возвращаемое значение

Комплексное число, деленное на число, указанное в качестве параметра.

### <a name="remarks"></a>Примечания

Эта операция является перегруженной, так что простые арифметические операции могут выполняться без преобразования данных в определенный формат.

### <a name="example"></a>Пример

```cpp
// complex_op_de.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // Example of the first member function
   // type complex<double> divided by type complex<double>
   complex<double> cl1( polar (3.0 , pi / 6 ) );
   complex<double> cr1( polar (2.0 , pi / 3 ) );
   cout << "The left-side complex number is cl1 = " << cl1 << endl;
   cout << "The right-side complex number is cr1 = " << cr1 << endl;

   complex<double> cs1 = cl1 / cr1;
   cout << "The quotient of the two complex numbers is: cs1 = cl1 /cr1 = "
        << cs1 << endl;

   // This is equivalent to the following operation
   cl1 /= cr1;
   cout << "Quotient of two complex numbers is also: cl1 /= cr1 = "
        << cl1 << endl;

   double abscl1 = abs( cl1 );
   double argcl1 = arg( cl1 );
   cout << "The modulus of cl1 is: " << abscl1 << endl;
   cout << "The argument of cl1 is: "<< argcl1 << " radians, which is "
        << argcl1 * 180 / pi << " degrees." << endl << endl;

   // Example of the second member function
   // type complex<double> divided by type double
   complex<double> cl2( polar(3.0 , pi / 6 ) );
   double cr2 =5;
   cout << "The left-side complex number is cl2 = " << cl2 << endl;
   cout << "The right-side complex number is cr2 = " << cr2 << endl;

   complex<double> cs2 = cl2 / cr2;
   cout << "The quotient of the two complex numbers is: cs2 /= cl2 cr2 = "
        << cs2 << endl;

   // This is equivalent to the following operation
   cl2 /= cr2;
   cout << "Quotient of two complex numbers is also: cl2 = /cr2 = "
        << cl2 << endl;

   double abscl2 = abs( cl2 );
   double argcl2 = arg( cl2 );
   cout << "The modulus of cl2 is: " << abscl2 << endl;
   cout << "The argument of cl2 is: "<< argcl2 << " radians, which is "
        << argcl2 * 180 / pi << " degrees." << endl << endl;
}
```

```Output
The left-side complex number is cl1 = (2.59808,1.5)
The right-side complex number is cr1 = (1,1.73205)
The quotient of the two complex numbers is: cs1 = cl1 /cr1 = (1.29904,-0.75)
Quotient of two complex numbers is also: cl1 /= cr1 = (1.29904,-0.75)
The modulus of cl1 is: 1.5
The argument of cl1 is: -0.523599 radians, which is -30 degrees.

The left-side complex number is cl2 = (2.59808,1.5)
The right-side complex number is cr2 = 5
The quotient of the two complex numbers is: cs2 /= cl2 cr2 = (0.519615,0.3)
Quotient of two complex numbers is also: cl2 = /cr2 = (0.519615,0.3)
The modulus of cl2 is: 0.6
The argument of cl2 is: 0.523599 radians, which is 30 degrees.
```

## <a name="operator"></a><a name="op_eq"></a> operator=

Присваивает число целевому комплексному числу, где присваиваемое число может быть комплексным или того же типа, что и действительная и мнимая части комплексного числа, которому выполняется присвоение.

```cpp
template <class Other>
complex<Type>& operator=(const complex<Other>& right);

complex<Type>& operator=(const Type& right);
```

### <a name="parameters"></a>Параметры

*right*\
Комплексное число или число того же типа, что и параметр целевого комплексного числа.

### <a name="return-value"></a>Возвращаемое значение

Комплексное число, которому присвоено число, указанное в качестве параметра.

### <a name="remarks"></a>Примечания

Эта операция является перегруженной, так что простые арифметические операции могут выполняться без преобразования данных в определенный формат.

### <a name="example"></a>Пример

```cpp
// complex_op_as.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // Example of the first member function
   // type complex<double> assigned to type complex<double>
   complex<double> cl1( 3.0 , 4.0 );
   complex<double> cr1( 2.0 , -1.0 );
   cout << "The left-side complex number is cl1 = " << cl1 << endl;
   cout << "The right-side complex number is cr1 = " << cr1 << endl;

   cl1  = cr1;
   cout << "The complex number cr1 assigned to the complex number cl1 is:"
        << "\ncl1 = cr1 = " << cl1 << endl;

   // Example of the second member function
   // type double assigned to type complex<double>
   complex<double> cl2( -2 , 4 );
   double cr2 =5.0;
   cout << "The left-side complex number is cl2 = " << cl2 << endl;
   cout << "The right-side complex number is cr2 = " << cr2 << endl;

   cl2 = cr2;
   cout << "The complex number cr2 assigned to the complex number cl2 is:"
        << "\ncl2 = cr2 = " << cl2 << endl;

   cl2 = complex<double>(3.0, 4.0);
   cout << "The complex number (3, 4) assigned to the complex number cl2 is:"
        << "\ncl2 = " << cl2 << endl;
}
```

```Output
The left-side complex number is cl1 = (3,4)
The right-side complex number is cr1 = (2,-1)
The complex number cr1 assigned to the complex number cl1 is:
cl1 = cr1 = (2,-1)
The left-side complex number is cl2 = (-2,4)
The right-side complex number is cr2 = 5
The complex number cr2 assigned to the complex number cl2 is:
cl2 = cr2 = (5,0)
The complex number (3, 4) assigned to the complex number cl2 is:
cl2 = (3,4)
```

## <a name="real"></a><a name="real"></a> Real

Возвращает или задает вещественную часть комплексного числа.

```cpp
constexpr T real() const;

T real(const T& right);
```

### <a name="parameters"></a>Параметры

*right*\
Комплексное число, вещественное значение которого извлекается.

### <a name="return-value"></a>Возвращаемое значение

Действительная часть комплексного числа.

### <a name="remarks"></a>Примечания

Для комплексного числа *a + bi*действительная часть или компонент перемещается *(а + BI) = a*.

### <a name="example"></a>Пример

```cpp
// complex_class_real.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;

   complex<double> c1( 4.0 , 3.0 );
   cout << "The complex number c1 = " << c1 << endl;

   double dr1 = c1.real();
   cout << "The real part of c1 is c1.real() = "
        << dr1 << "." << endl;

   double di1 = c1.imag();
   cout << "The imaginary part of c1 is c1.imag() = "
        << di1 << "." << endl;
}
```

```Output
The complex number c1 = (4,3)
The real part of c1 is c1.real() = 4.
The imaginary part of c1 is c1.imag() = 3.
```

## <a name="value_type"></a><a name="value_type"></a> value_type

Тип, представляющий тип данных, который используется для представления действительной и мнимой частей комплексного числа.

```cpp
typedef Type value_type;
```

### <a name="remarks"></a>Примечания

`value_type` является синонимом для параметра сложного `Type` шаблона класса.

### <a name="example"></a>Пример

```cpp
// complex_valuetype.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    complex<double>::value_type a = 3, b = 4;

    complex<double> c1 ( a , b );
    cout << "Specifying initial real & imaginary parts"
        << "\nof type value_type: "
        << "c1 = " << c1 << "." << endl;
}
```

```Output
Specifying initial real & imaginary parts
of type value_type: c1 = (3,4).
```

## <a name="see-also"></a>См. также раздел

[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
