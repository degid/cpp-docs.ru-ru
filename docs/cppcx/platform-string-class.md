---
title: Класс Platform::String
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::String::String
- VCCORLIB/Platform::String::Begin
- VCCORLIB/Platform::String::CompareOrdinal
- VCCORLIB/Platform::String::Concat
- VCCORLIB/Platform::String::Data
- VCCORLIB/Platform::String::Dispose
- VCCORLIB/Platform::String::End
- VCCORLIB/Platform::String::Equals
- VCCORLIB/Platform::String::GetHashCode
- VCCORLIB/Platform::String::IsEmpty
- VCCORLIB/Platform::String::IsFastPass
- VCCORLIB/Platform::String::Length
- VCCORLIB/Platform::String::ToString
helpviewer_keywords:
- Platform::String
ms.assetid: 72dd04a4-a694-40d3-b899-eaa0b503eab8
ms.openlocfilehash: f8b5888ee2d28a3d870b5f0eeab143b189c88180
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87185259"
---
# <a name="platformstring-class"></a>Класс Platform::String

Представляет упорядоченную коллекцию символов Юникода, используемую для представления текста. Дополнительные сведения и примеры см. в разделе [строки](../cppcx/strings-c-cx.md).

## <a name="syntax"></a>Синтаксис

```cpp
public ref class String sealed : Object,
    IDisposable,
    IEquatable,
    IPrintable
```

## <a name="iterators"></a>Iterators

Две функции итераторов, не являющиеся членами класса String, можно использовать с функциями шаблона `std::for_each` для перечисления символов в объекте String.

|Член|Описание|
|------------|-----------------|
|`const char16* begin(String^ s)`|Возвращает указатель на начало указанного объекта String.|
|`const char16* end(String^ s)`|Возвращает указатель на позицию после окончания указанного объекта String.|

## <a name="members"></a>Элементы

Класс String наследует от класса Object и интерфейсов IDisposable, IEquatable и IPrintable.

Класс String имеет также следующие типы членов.

### <a name="constructors"></a>Конструкторы

|Член|Описание|
|------------|-----------------|
|[Строка:: строка](#ctor)|Инициализирует новый экземпляр класса String.|

### <a name="methods"></a>Методы

Класс String наследует методы Equals(), Finalize(), GetHashCode(), GetType(), MemberwiseClose() и ToString() от класса [Platform::Object Class](../cppcx/platform-object-class.md). Класс String содержит также следующие методы.

|Метод|Описание|
|------------|-----------------|
|[Строка:: начало](#begin)|Возвращает указатель на начало текущей строки.|
|[String:: CompareOrdinal](#compareordinal)|Сравнивает два объекта `String` , оценивая числовые значения соответствующих символов в двух строковых значениях, представленных объектами.|
|[String:: Concat](#concat)|Объединяет значения двух объектов String.|
|[Строка::D ATA](#data)|Возвращает указатель на начало текущей строки.|
|[Строка::D "Dispose"](#dispose)|Высвобождает ресурсы.|
|[Строка:: конец](#end)|Возвращает указатель на позицию после конца текущей строки.|
|[Строка:: Equals](#equals)|Указывает, равен ли указанный объект текущему объекту.|
|[String:: GetHashCode](#gethashcode)|Возвращает хэш-код данного экземпляра.|
|[String:: IsEmpty](#isempty)|Указывает, является ли объект String пустым.|
|[String:: IsFastPass](#isfastpass)|Указывает, участвует ли текущий объект строки в операции *быстрой передачи* . В операции быстрой передачи подсчет ссылок приостанавливается.|
|[Строка:: длина](#length)|Получает длину текущего объекта String.|
|[String:: ToString](#tostring)|Возвращает объект String, значение которого совпадает со значением текущей строки.|

### <a name="operators"></a>Операторы

Класс String имеет следующие операторы.

|Член|Описание|
|------------|-----------------|
|[Оператор string::operator==](#operator-equality)|Указывает, совпадают ли значения двух указанных строковых объектов.|
|[Оператор operator+](#operator-plus)|Сцепляет два объекта String в новый объект String.|
|[Оператор string::operator>](#operator-greater-than)|Указывает, является ли значение одного объекта String большим, чем значение второго объекта String.|
|[Оператор string::operator>=](#operator-greater-than-or-equals)|Указывает, является ли значение одного объекта String больше или равным значению второго объекта String.|
|[Оператор string::operator!=](#operator-inequality)|Указывает, различаются ли значения двух указанных строковых объектов.|
|[Оператор string::operator<](#operator-less-than)|Указывает, является ли значение одного объекта String меньшим, чем значение второго объекта String.|

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Заголовок** vccorlib.h (включается по умолчанию)

## <a name="stringbegin-method"></a><a name="begin"></a>Метод String:: Begin

Возвращает указатель на начало текущей строки.

### <a name="syntax"></a>Синтаксис

```cpp
char16* Begin();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало текущей строки.

## <a name="stringcompareordinal-method"></a><a name="compareordinal"></a>Метод String:: CompareOrdinal

Статический метод, сравнивающий два `String` объекта, оценивая числовые значения соответствующих символов в двух строковых значениях, представленных объектами.

### <a name="syntax"></a>Синтаксис

```cpp
static int CompareOrdinal( String^ str1, String^ str2 );
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект String.

*str2*<br/>
Второй объект String.

### <a name="return-value"></a>Возвращаемое значение

Целое число, выражающее лексическое соотношение двух сравниваемых значений. В следующей таблице перечислены возможные возвращаемые значения.

|Значение|Условие|
|-----------|---------------|
|-1|Значение `str1` меньше `str2`.|
|0|Значение `str1` равно значению `str2`.|
|1|Значение `str1` больше значения `str2`.|

## <a name="stringconcat-method"></a><a name="concat"></a>Метод String:: Concat

Объединяет значения двух объектов String.

### <a name="syntax"></a>Синтаксис

```cpp
String^ Concat( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект String или значение `null`.

*str2*<br/>
Второй объект String или значение `null`.

### <a name="return-value"></a>Возвращаемое значение

Новый объект String^, значение которого является объединением значений `str1` и `str2`.

Если `str1` имеет значение `null`, а `str2` — значение, отличное от null, возвращается значение `str1`. Если `str2` имеет значение `null`, а `str1` — значение, отличное от null, возвращается значение `str2`. Если оба параметра `str1` и `str2` имеют значение `null`, возвращается пустая строка (L"").

## <a name="stringdata-method"></a><a name="data"></a>Строка::D метод ATA

Возвращает указатель на начало буфера данных объекта в виде массива `char16` элементов () в стиле C **`wchar_t`** .

### <a name="syntax"></a>Синтаксис

```cpp
const char16* Data();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на начало `const char16` массива символов Юникода ( `char16` является typedef для **`wchar_t`** ).

### <a name="remarks"></a>Примечания

Используйте этот метод для преобразования из `Platform::String^` в `wchar_t*`. Когда объект `String` выходит за пределы области, указатель Data больше не является гарантированно допустимым. Чтобы сохранить данные за пределами времени существования исходного `String` объекта, используйте [wcscpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) , чтобы скопировать массив в память, выделенную самому себе.

## <a name="stringdispose-method"></a><a name="dispose"></a>String::D метод Dispose

Высвобождает ресурсы.

### <a name="syntax"></a>Синтаксис

```cpp
virtual override void Dispose();
```

## <a name="stringend-method"></a><a name="end"></a>Метод String:: end

Возвращает указатель на позицию после конца текущей строки.

### <a name="syntax"></a>Синтаксис

```cpp
char16* End();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на позицию после конца текущей строки.

### <a name="remarks"></a>Примечания

End () возвращает значение начала () + length.

## <a name="stringequals-method"></a><a name="equals"></a>Метод String:: Equals

Указывает, совпадает ли значение заданного объекта String со значением текущего объекта.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::Equals(Object^ str);
bool String::Equals(String^ str);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**`true`**`str`значение, если значение равно текущему объекту; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Этот метод эквивалентен статической строке: [: CompareOrdinal](#compareordinal). В первой перегрузке предполагается, что параметр `str` может быть приведен к объекту String^.

## <a name="stringgethashcode-method"></a><a name="gethashcode"></a>Метод String:: GetHashCode

Возвращает хэш-код данного экземпляра.

### <a name="syntax"></a>Синтаксис

```cpp
virtual override int GetHashCode();
```

### <a name="return-value"></a>Возвращаемое значение

Хэш-код данного экземпляра.

## <a name="stringisempty-method"></a><a name="isempty"></a>Метод String:: IsEmpty

Указывает, является ли объект String пустым.

### <a name="syntax"></a>Синтаксис

```cpp
bool IsEmpty();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`**`String`значение, если текущий объект равен **null** или является пустой строкой (L ""); в противном случае — значение **`false`** .

## <a name="stringisfastpass-method"></a><a name="isfastpass"></a>Метод String:: IsFastPass

Указывает, участвует ли текущий объект строки в операции *быстрой передачи* . В операции быстрой передачи подсчет ссылок приостанавливается.

### <a name="syntax"></a>Синтаксис

```cpp
bool IsFastPass();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`**`String`значение, если текущий объект является быстрым, в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

При вызове функции, где в качестве параметра используется объект с подсчетом ссылок и вызываемая функция обращается к этому объекту только для чтения, компилятор может безопасно приостановить подсчет ссылок, чтобы повысить производительность вызова. Это свойство не дает никакой дополнительной пользы для вашего кода. Система обрабатывает все сведения.

## <a name="stringlength-method"></a><a name="length"></a>Метод String:: Length

Извлекает количество символов в текущем `String` объекте.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned int Length();
```

### <a name="return-value"></a>Возвращаемое значение

Количество символов в текущем `String` объекте.

### <a name="remarks"></a>Примечания

Длина объекта String без символов равна нулю. Длина следующего объекта String равна 5.

```cpp
String^ str = "Hello";
int len = str->Length(); //len = 5
```

Массив символов, возвращаемый [строкой::D ATA](#data) имеет один дополнительный символ, который является завершающим нулем или "\ 0". Этот символ также имеет длину 2 байта.

## <a name="stringoperator-operator"></a><a name="operator-plus"></a>Оператор string::operator+

Сцепляет два [строковых](../cppcx/platform-string-class.md) объекта в новый [строковый](../cppcx/platform-string-class.md) объект.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator+( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект `String`.

*str2*<br/>
Второй объект `String`, содержимое которого будет добавлено в `str1`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если *str1* равен *str2*; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Этот оператор создает объект `String^`, содержащий данные из двух операндов. Используйте его для удобства, если производительность не играет решающей роли. Несколько вызовов "`+`" в функции, скорее всего, не будут иметь последствий, но если вы имеете дело с большими объектами или текстовыми данными в сложном цикле, используйте стандартные механизмы и типы C++.

## <a name="stringoperator-operator"></a><a name="operator-equality"></a>Оператор string::operator==

Указывает, равны ли текстовые значения двух указанных объектов String.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator==( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый сравниваемый объект `String`.

*str2*<br/>
Второй сравниваемый объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если содержимое `str1` равно `str2` ; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Этот оператор эквивалентен [String:: CompareOrdinal](#compareordinal).

## <a name="stringoperatorgt"></a><a name="operator-greater-than"></a>String:: оператор&gt;

Указывает, превышает ли значение одного `String` объекта значение второго `String` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator>( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект `String`.

*str2*<br/>
Второй объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**`true`**, если значение `str1` больше значения `str2` ; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Этот оператор эквивалентен явному вызову [String:: CompareOrdinal](#compareordinal) и получению результата больше нуля.

## <a name="stringoperatorgt"></a><a name="operator-greater-than-or-equals"></a>String:: оператор&gt;=

Указывает, является ли значение одного `String` объекта большим или равным значению второго `String` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator>=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект `String`.

*str2*<br/>
Второй объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**`true`**, если значение `str1` больше или равно значению `str2` ; в противном случае — **`false`** .

## <a name="stringoperator"></a><a name="operator-inequality"></a>String::operator!=

Указывает, имеют ли два указанных `String` объекта разные значения.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator!=( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый сравниваемый объект `String`.

*str2*<br/>
Второй сравниваемый объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**`true`**`str1`, если не равно `str2` ; в противном **`false`** случае —.

## <a name="stringoperatorlt"></a><a name="operator-less-than"></a>String:: оператор&lt;

Указывает, меньше ли значение одного `String` объекта, чем значение второго `String` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
bool String::operator<( String^ str1, String^ str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый объект `String`.

*str2*<br/>
Второй объект `String`.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если значение *str1* меньше значения *str2*; в противном случае — **`false`** .

## <a name="stringstring-constructor"></a><a name="ctor"></a>Конструктор строк:: String

Инициализирует новый экземпляр `String` класса с копией входных строковых данных.

### <a name="syntax"></a>Синтаксис

```cpp
String();
String(char16* s);
String(char16* s, unsigned int n);
```

### <a name="parameters"></a>Параметры

*#d0*<br/>
Серия расширенных символов, инициализирующих строку.  char16

*n*<br/>
Число, указывающее длину строки.

### <a name="remarks"></a>Примечания

Если важна производительность и вы управляете временем существования исходной строки, можно использовать [Platform:: StringReference](../cppcx/platform-stringreference-class.md) вместо String.

### <a name="example"></a>Пример

```cpp
String^ s = L"Hello!";
```

## <a name="stringtostring"></a><a name="tostring"></a>String:: ToString

Возвращает объект, значение которого совпадает с `String` текущей строкой.

### <a name="syntax"></a>Синтаксис

```cpp
String^ String::ToString();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, значение которого совпадает с `String` текущей строкой.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
