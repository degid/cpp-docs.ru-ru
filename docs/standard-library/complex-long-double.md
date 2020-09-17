---
title: complex&lt;long double&gt;
ms.date: 11/04/2016
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
ms.openlocfilehash: 73027ba76d608424b1a6da346e861b10c66989fe
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228392"
---
# <a name="complexltlong-doublegt"></a>complex&lt;long double&gt;

Этот явно специализированный шаблон класса описывает объект, в котором хранится упорядоченная пара объектов типа **`long double`** , первая из которых представляет реальную часть комплексного числа, а вторая — мнимую часть.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);

// rest same as class template complex
};
```

### <a name="parameters"></a>Параметры

*_RealVal*\
Значение типа **`long double`** для реальной части создаваемого комплексного числа.

*_ImagVal*\
Значение типа **`long double`** для мнимой части создаваемого комплексного числа.

*комплекснум*\
Комплексное число типа **`double`** или типа **`float`** , реальные и мнимые части которого используются для инициализации комплексного числа создаваемого типа **`long double`** .

## <a name="return-value"></a>Возвращаемое значение

Комплексное число типа **`long double`** .

## <a name="remarks"></a>Примечания

Явная специализация шаблона класса `complex` на сложный класс типа **`long double`** отличается от шаблона класса только в конструкторах, которые он определяет. Преобразование из **`long double`** в **`float`** не может быть неявным, но преобразование из в **`double`** **`long double`** **`explicit`** должно иметь значение. Использование **`explicit`** правил инициации при преобразовании типов с помощью синтаксиса назначения.

Дополнительные сведения о шаблоне класса `complex` и его членах см. в разделе [сложный класс](../standard-library/complex-class.md).

**Только для Microsoft**: **`long double`** типы и **`double`** имеют одно и то же представление, но являются отдельными типами. Дополнительные сведения см. [в разделе Встроенные типы](../cpp/fundamental-types-cpp.md).

## <a name="example"></a>Пример

```cpp
// complex_comp_ld.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    double pi = 3.14159265359;

    // The first constructor specifies real & imaginary parts
    complex<long double> c1( 4.0 , 5.0 );
    cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

    // The second constructor initializes values of the real &
    // imaginary parts using those of complex number of type float
    complex<float> c2float( 1.0 , 3.0 );
    complex<long double> c2longdouble ( c2float );
    cout << "Implicit conversion from type float to type long double,"
        << "\n gives c2longdouble = " << c2longdouble << endl;

    // The third constructor initializes values of the real &
    // imaginary parts using those of a complex number
    // of type double
    complex<double> c3double( 3.0 , 4.0 );
    complex<long double> c3longdouble( c3double );
    cout << "Implicit conversion from type long double to type float,"
        << "\n gives c3longdouble = " << c3longdouble << endl;

    // The modulus and argument of a complex number can be recovered
    double absc3 = abs( c3longdouble );
    double argc3 = arg( c3longdouble );
    cout << "The modulus of c3 is recovered from c3 using: abs( c3 ) = "
        << absc3 << endl;
    cout << "Argument of c3 is recovered from c3 using:\n arg( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
```

```Output
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type float to type long double,
gives c2longdouble = (1,3)
Implicit conversion from type long double to type float,
gives c3longdouble = (3,4)
The modulus of c3 is recovered from c3 using: abs( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg( c3 ) = 0.927295 radians, which is 53.1301 degrees.
```

## <a name="requirements"></a>Требования

**Заголовок**:\<complex>

**Пространство имен:** std

## <a name="see-also"></a>См. также статью

[сложный класс](../standard-library/complex-class.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
