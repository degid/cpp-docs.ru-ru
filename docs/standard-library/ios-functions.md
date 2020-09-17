---
title: Функции &lt;ios&gt;
ms.date: 11/04/2016
f1_keywords:
- xiosbase/std::defaultfloat
- xiosbase/std::boolalpha
- xiosbase/std::dec
- ios/std::fixed
- ios/std::hex
- ios/std::internal
- ios/std::left
- ios/std::noboolalpha
- ios/std::noshowbase
- ios/std::noshowpoint
- ios/std::noshowpos
- ios/std::noskipws
- ios/std::nounitbuf
- ios/std::nouppercase
- ios/std::oct
- ios/std::right
- ios/std::scientific
- ios/std::showbase
- ios/std::showpoint
- ios/std::showpos
- ios/std::skipws
- ios/std::unitbuf
- ios/std::uppercase
ms.assetid: 1382d53f-e531-4b41-adf6-6a1543512e51
helpviewer_keywords:
- std::defaultfloat [C++]
- std::boolalpha [C++]
- std::dec [C++]
- std::fixed [C++]
- std::hex [C++]
- std::hexfloat [C++]
- std::io_errc [C++]
- std::internal [C++]
- std::iostream_category [C++]
- std::is_error_code_enum [C++]
- std::left [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::noboolalpha [C++]
- std::noshowbase [C++]
- std::noshowpoint [C++]
- std::noshowpos [C++]
- std::noskipws [C++]
- std::nounitbuf [C++]
- std::nouppercase [C++]
- std::oct [C++]
- std::right [C++]
- std::scientific [C++]
- std::showbase [C++]
- std::showpoint [C++]
- std::showpos [C++]
- std::skipws [C++]
- std::unitbuf [C++]
- std::uppercase [C++]
ms.openlocfilehash: a750f17ba8eba40dd01a2fb4a89e47a0927e4b61
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212297"
---
# <a name="ltiosgt-functions"></a>Функции &lt;ios&gt;

## <a name="boolalpha"></a><a name="boolalpha"></a>boolalpha

Указывает, что переменные типа [bool](../cpp/bool-cpp.md) отображаются как **`true`** или **`false`** в потоке.

```cpp
ios_base& boolalpha(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию переменные типа **`bool`** отображаются как 1 или 0.

`boolalpha`фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf)( `ios_base::boolalpha` ), а затем возвращает *str*.

[noboolalpha](../standard-library/ios-functions.md#noboolalpha) отменяет результат `boolalpha`.

### <a name="example"></a>Пример

```cpp
// ios_boolalpha.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   bool b = true;
   cout << b << endl;
   boolalpha( cout );
   cout << b << endl;
   noboolalpha( cout );
   cout << b << endl;
   cout << boolalpha << b << endl;
}
```

```Output
1
true
1
true
```

## <a name="dec"></a><a name="dec"></a>уменьшение

Устанавливает режим отображения целочисленных переменных в нотации с основанием 10.

```cpp
ios_base& dec(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию целочисленные переменные отображаются в десятичной записи.

`dec`фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf)( `ios_base::dec` , `ios_base::basefield` ), а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_dec.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 100;

   cout << i << endl;   // Default is base 10
   cout << hex << i << endl;
   dec( cout );
   cout << i << endl;
   oct( cout );
   cout << i << endl;
   cout << dec << i << endl;
}
```

```Output
100
64
100
144
100
```

## <a name="ltiosgt-defaultfloat"></a><a name="ios_defaultfloat"></a> &lt;ios&gt; defaultfloat

Устанавливает флаги объекта `ios_base` в соответствии с форматом отображения значений с плавающей запятой, принятым по умолчанию.

```cpp
ios_base& defaultfloat(ios_base& iosbase);
```

### <a name="parameters"></a>Параметры

*_Iosbase*\
Объект `ios_base`.

### <a name="remarks"></a>Примечания

Манипулятор фактически вызывает `iosbase.` [ios_base:: unsetf](../standard-library/ios-base-class.md#unsetf) `(ios_base::floatfield)` , а затем возвращает *iosbase*.

## <a name="fixed"></a><a name="fixed"></a>префикс

Устанавливает режим отображения чисел с плавающей запятой в нотации фиксированного десятичного формата.

```cpp
ios_base& fixed(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

`fixed`— это отображаемая по умолчанию нотация для чисел с плавающей запятой. [scientific](../standard-library/ios-functions.md#scientific) вызывает отображение чисел с плавающей запятой в экспоненциальном представлении.

Манипулятор фактически вызывает *str*. [setf](../standard-library/ios-base-class.md#setf)( `ios_base::fixed` , `ios_base::floatfield` ), а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_fixed.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 1.1F;

   cout << i << endl;   // fixed is the default
   cout << scientific << i << endl;
   cout.precision( 1 );
   cout << fixed << i << endl;
}
```

```Output
1.1
1.100000e+000
1.1
```

## <a name="hex"></a><a name="hex"></a>Hex

Устанавливает режим отображения целочисленных переменных в шестнадцатеричной записи.

```cpp
ios_base& hex(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию целочисленные переменные отображаются в десятичной записи. [dec](../standard-library/ios-functions.md#dec) и [oct](../standard-library/ios-functions.md#oct) также изменяют способ показа целочисленных переменных.

Манипулятор эффективно вызывает `str` **.** [setf](../standard-library/ios-base-class.md#setf)( `ios_base::hex` , `ios_base::basefield` ), а затем возвращает *str*.

### <a name="example"></a>Пример

Пример использования см. в [Dec](../standard-library/ios-functions.md#dec) `hex` .

## <a name="hexfloat"></a><a name="hexfloat"></a>свертывания

```cpp
ios_base& hexfloat (ios_base& str);
```

## <a name="io_errc"></a><a name="io_errc"></a>io_errc

```cpp
enum class io_errc {
    stream = 1
};
```

## <a name="internal"></a><a name="internal"></a>внутрикластерных

Устанавливает режим выравнивания знака числа по левому краю, а самого числа — по правому краю.

```cpp
ios_base& internal(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

[showpos](../standard-library/ios-functions.md#showpos) вызывает показ знака для отображения положительных чисел.

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(` [ios_base:: Internal](../standard-library/ios-base-class.md#fmtflags) `,` [ios_base:: adjustfield](../standard-library/ios-base-class.md#fmtflags) `)` , а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_internal.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>

int main( void )
{
   using namespace std;
   float i = -123.456F;
   cout.fill( '.' );
   cout << setw( 10 ) << i << endl;
   cout << setw( 10 ) << internal << i << endl;
}
```

```Output
..-123.456
-..123.456
```

## <a name="is_error_code_enum"></a><a name="is_error_code_enum"></a>is_error_code_enum

```cpp
template <> struct is_error_code_enum<io_errc> : public true_type { };
```

## <a name="iostream_category"></a><a name="iostream_category"></a>iostream_category

```cpp
const error_category& iostream_category() noexcept;
```

## <a name="left"></a><a name="left"></a>слева

Устанавливает режим добавления левого поля для текста, ширина которого меньше, чем ширина выходных данных, при представлении его в потоке.

```cpp
ios_base& left(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(ios_base::left, ios_base::adjustfield)` , а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_left.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout.width( 20 );
   cout << f1 << endl;
   cout << left << f1 << endl;
}
```

```Output
5
        5
```

## <a name="make_error_code"></a><a name="make_error_code"></a>make_error_code

```cpp
error_code make_error_code(io_errc e) noexcept;
```

## <a name="make_error_condition"></a><a name="make_error_condition"></a>make_error_condition

```cpp
error_condition make_error_condition(io_errc e) noexcept;
```

## <a name="noboolalpha"></a><a name="noboolalpha"></a>нобулалфа

Устанавливает режим отображения переменных типа [bool](../cpp/bool-cpp.md) в потоке в виде 1 или 0.

```cpp
ios_base& noboolalpha(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию действует `noboolalpha`.

`noboolalpha`фактически вызывает `str.` [unsetf](../standard-library/ios-base-class.md#unsetf) `(ios_base::boolalpha)` , а затем возвращает *str*.

[noboolalpha](../standard-library/ios-functions.md#boolalpha) отменяет результат `noboolalpha`.

### <a name="example"></a>Пример

См. [boolalpha](../standard-library/ios-functions.md#boolalpha) с примером использования `noboolalpha`.

## <a name="noshowbase"></a><a name="noshowbase"></a>ношовбасе

Отключает отображение основания нотации, в которой отображается число.

```cpp
ios_base& noshowbase(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

`noshowbase` включен по умолчанию. Используйте [showbase](../standard-library/ios-functions.md#showbase) для указания основания чисел.

Манипулятор фактически вызывает `str.` [unsetf](../standard-library/ios-base-class.md#unsetf) `(ios_base::showbase)` , а затем возвращает *str*.

### <a name="example"></a>Пример

См. [showbase](../standard-library/ios-functions.md#showbase) с примером использования `noshowbase`.

## <a name="noshowpoint"></a><a name="noshowpoint"></a>ношовпоинт

Отображает только целую часть числа с плавающей запятой, дробная часть которого равна нулю.

```cpp
ios_base& noshowpoint(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию `noshowpoint` включен. Используйте [showpoint](../standard-library/ios-functions.md#showpoint) и [precision](../standard-library/ios-base-class.md#precision) для показа нулей после десятичной запятой.

Манипулятор фактически вызывает `str.` [unsetf](../standard-library/ios-base-class.md#unsetf) `(ios_base::showpoint)` , а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_noshowpoint.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.000;
   cout << f1 << endl;   // noshowpoint is default
   cout.precision( 4 );
   cout << showpoint << f1 << endl;
   cout << noshowpoint << f1 << endl;
}
```

```Output
5
5.000
5
```

## <a name="noshowpos"></a><a name="noshowpos"></a>ношовпос

Устанавливает режим отображения положительных чисел без обязательного знака.

```cpp
ios_base& noshowpos(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

`noshowpos` включен по умолчанию.

Манипулятор фактически вызывает `str.` [unsetf](../standard-library/ios-base-class.md#unsetf) `(ios_base::showps)` , а затем возвращает *str*.

### <a name="example"></a>Пример

См. [showpos](../standard-library/ios-functions.md#showpos) с примером использования `noshowpos`.

## <a name="noskipws"></a><a name="noskipws"></a>noskipws

Устанавливает режим чтения пробелов потоком ввода.

```cpp
ios_base& noskipws(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию используется [skipws](../standard-library/ios-functions.md#skipws). При чтении пробела из входного потока он сообщает о конце буфера.

Манипулятор фактически вызывает `str.` [unsetf](../standard-library/ios-base-class.md#unsetf) `(ios_base::skipws)` , а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_noskipws.cpp
// compile with: /EHsc
#include <iostream>
#include <string>

int main() {
   using namespace std;
   string s1, s2, s3;
   cout << "Enter three strings: ";
   cin >> noskipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

## <a name="nounitbuf"></a><a name="nounitbuf"></a>наунитбуф

Устанавливает буферизацию выходных данных и их обработку при заполнении буфера.

```cpp
ios_base& nounitbuf(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

[unitbuf](../standard-library/ios-functions.md#unitbuf) вызывает обработку буфера, когда он не пустой.

Манипулятор фактически вызывает `str.` [unsetf](../standard-library/ios-base-class.md#unsetf) `(ios_base::unitbuf)` , а затем возвращает *str*.

## <a name="nouppercase"></a><a name="nouppercase"></a>прописные буквы

Устанавливает режим отображения шестнадцатеричных цифр и показателя степени в экспоненциальном представлении в нижнем регистре.

```cpp
ios_base& nouppercase(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

Манипулятор фактически вызывает `str.` [unsetf](../standard-library/ios-base-class.md#unsetf) `(ios_base::uppercase)` , а затем возвращает *str*.

### <a name="example"></a>Пример

См. [uppercase](../standard-library/ios-functions.md#uppercase) с примером использования `nouppercase`.

## <a name="oct"></a><a name="oct"></a>октября

Устанавливает режим отображения целочисленных переменных в нотации с основанием 8.

```cpp
ios_base& oct(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию целочисленные переменные отображаются в десятичной записи. [dec](../standard-library/ios-functions.md#dec) и [hex](../standard-library/ios-functions.md#hex) также изменяют способ показа целочисленных переменных.

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(ios_base::oct, ios_base::basefield)` , а затем возвращает *str*.

### <a name="example"></a>Пример

Пример использования см. в [Dec](../standard-library/ios-functions.md#dec) `oct` .

## <a name="right"></a><a name="right"></a>Правильно

Устанавливает режим добавления правого поля для текста, ширина которого меньше, чем ширина выходных данных, при представлении его в потоке.

```cpp
ios_base& right(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

[left](../standard-library/ios-functions.md#left) также изменяет выравнивание текста.

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(ios_base::right, ios_base::adjustfield)` , а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_right.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << left << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << right << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
}
```

```Output
5
                   5
5
5
                   5
                   5
```

## <a name="scientific"></a><a name="scientific"></a>экспоненциаль

Устанавливает режим отображения чисел с плавающей запятой с использованием экспоненциального представления.

```cpp
ios_base& scientific(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию числа с плавающей запятой показываются в нотации [fixed](../standard-library/ios-functions.md#fixed).

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(ios_base::scientific, ios_base::floatfield)` , а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_scientific.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 100.23F;

   cout << i << endl;
   cout << scientific << i << endl;
}
```

```Output
100.23
1.002300e+002
```

## <a name="showbase"></a><a name="showbase"></a>showbase

Включает отображение основания нотации, в которой отображается число.

```cpp
ios_base& showbase(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

Запись числа можно изменить при помощи [dec](../standard-library/ios-functions.md#dec), [oct](../standard-library/ios-functions.md#oct) или [hex](../standard-library/ios-functions.md#hex).

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(ios_base::showbase)` , а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_showbase.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int j = 100;

   cout << showbase << j << endl;   // dec is default
   cout << hex << j << showbase << endl;
   cout << oct << j << showbase << endl;

   cout << dec << j << noshowbase << endl;
   cout << hex << j << noshowbase << endl;
   cout << oct << j << noshowbase << endl;
}
```

```Output
100
0x64
0144
100
64
144
```

## <a name="showpoint"></a><a name="showpoint"></a>showpoint

Отображает целую часть числа с плавающей запятой и цифры справа от десятичной запятой даже в том случае, если дробная часть равна нулю.

```cpp
ios_base& showpoint(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию действует [noshowpoint](../standard-library/ios-functions.md#noshowpoint).

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(ios_base::showpoint)` , а затем возвращает *str*.

### <a name="example"></a>Пример

См. [noshowpoint](../standard-library/ios-functions.md#noshowpoint) с примером использования `showpoint`.

## <a name="showpos"></a><a name="showpos"></a>showpos

Устанавливает режим отображения положительных чисел с обязательным знаком.

```cpp
ios_base& showpos(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию используется [noshowpos](../standard-library/ios-functions.md#noshowpos).

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(ios_base::showpos)` , а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_showpos.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 1;

   cout << noshowpos << i << endl;   // noshowpos is default
   cout << showpos << i << endl;
}
```

```Output
1
+1
```

## <a name="skipws"></a><a name="skipws"></a>skipws

Устанавливает режим игнорирования пробелов потоком ввода.

```cpp
ios_base& skipws(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию действует `skipws`. [noskipws](../standard-library/ios-functions.md#noskipws) устанавливает режим чтения пробелов из входного потока.

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(ios_base::skipws)` , а затем возвращает *str*.

### <a name="example"></a>Пример

```cpp
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   char s1, s2, s3;
   cout << "Enter three characters: ";
   cin >> skipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

```Input
1 2 3
```

```Output
Enter three characters: 1 2 3
.1.
.2.
.3.
```

## <a name="unitbuf"></a><a name="unitbuf"></a>unitbuf

Устанавливает режим обработки выходных данных при наличии данных в буфере.

```cpp
ios_base& unitbuf(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

Обратите внимание, что `endl` также очищает буфер.

По умолчанию действует [nounitbuf](../standard-library/ios-functions.md#nounitbuf).

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(` [ios_base:: unitbuf](../standard-library/ios-base-class.md#fmtflags) `)` , а затем возвращает *str*.

## <a name="uppercase"></a><a name="uppercase"></a>верхний регистр

Устанавливает режим отображения шестнадцатеричных цифр и показателя степени в экспоненциальном представлении в верхнем регистре.

```cpp
ios_base& uppercase(ios_base& str);
```

### <a name="parameters"></a>Параметры

*str*\
Ссылка на объект типа [ios_base](../standard-library/ios-base-class.md), или на тип, который наследует от `ios_base`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект, из которого является производным *str* .

### <a name="remarks"></a>Примечания

По умолчанию действует [nouppercase](../standard-library/ios-functions.md#nouppercase).

Манипулятор фактически вызывает `str.` [setf](../standard-library/ios-base-class.md#setf) `(` [ios_base:: прописные](../standard-library/ios-base-class.md#fmtflags) `)` и возвращает *str*.

### <a name="example"></a>Пример

```cpp
// ios_uppercase.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
   using namespace std;

   double i = 1.23e100;
   cout << i << endl;
   cout << uppercase << i << endl;

   int j = 10;
   cout << hex << nouppercase << j << endl;
   cout << hex << uppercase << j << endl;
}
```

```Output
1.23e+100
1.23E+100
a
A
```
