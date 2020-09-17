---
title: Класс Platform::Collections::Vector
ms.date: 12/04/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Vector::Vector
- COLLECTION/Platform::Collections::Vector::Append
- COLLECTION/Platform::Collections::Vector::Clear
- COLLECTION/Platform::Collections::Vector::First
- COLLECTION/Platform::Collections::Vector::GetAt
- COLLECTION/Platform::Collections::Vector::GetMany
- COLLECTION/Platform::Collections::Vector::GetView
- COLLECTION/Platform::Collections::Vector::IndexOf
- COLLECTION/Platform::Collections::Vector::InsertAt
- COLLECTION/Platform::Collections::Vector::ReplaceAll
- COLLECTION/Platform::Collections::Vector::RemoveAt
- COLLECTION/Platform::Collections::Vector::RemoveAtEnd
- COLLECTION/Platform::Collections::Vector::SetAt
- COLLECTION/Platform::Collections::Vector::Size
- COLLECTION/Platform::Collections::Vector::VectorChanged
helpviewer_keywords:
- Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
ms.openlocfilehash: dc467b8db3cd6ec88395554eef7f109877f10d41
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839092"
---
# <a name="platformcollectionsvector-class"></a>Класс Platform::Collections::Vector

Представляет упорядоченную коллекцию объектов с индивидуальным доступом, осуществляемым при помощи индекса. Реализует [Windows:: Foundation:: Collections:: иобсерваблевектор](/uwp/api/windows.foundation.collections.iobservablevector-1) для помощи с [привязкой данных](/windows/uwp/data-binding/data-binding-in-depth)XAML.

## <a name="syntax"></a>Синтаксис

```
template <typename T, typename E>
   ref class Vector sealed;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип элементов, содержащихся в объекте Vector.

*&*<br/>
Задает бинарный предикат для проверки равенства со значениями типа *T*. Значение по умолчанию — `std::equal_to<T>` .

### <a name="remarks"></a>Примечания

Допустимые типы:

1. integers

1. класс интерфейса ^

1. открытый ссылочный класс ^

1. структура значений

1. открытый класс перечисления

Класс **vector** — конкретная реализация интерфейса [Windows:: Foundation:: Collections:: IVector](/uwp/api/windows.foundation.collections.ivector-1) в C++.

При попытке использовать тип **vector** в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Вы можете исправить ошибку, изменив тип параметра или возвращаемого значения на [Windows::Foundation::Collections::IVector](/uwp/api/windows.foundation.collections.ivector-1). Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Vector:: Vector](#ctor)|Инициализирует новый экземпляр класса Vector.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Vector::Append](#append)|Вставляет указанный элемент после последнего элемента текущего объекта Vector.|
|[Вектор:: Clear](#clear)|Удаляет все элементы текущего объекта Vector.|
|[Вектор:: First](#first)|Возвращает итератор, указывающий первый элемент объекта Vector.|
|[Vector:: GetAt](#getat)|Извлекает элемент текущего объекта Vector, указанный заданным индексом.|
|[Vector:: множество](#getmany)|Извлекает последовательность элементов из текущего объекта Vector, начиная с указанного индекса.|
|[Vector::/View](#getview)|Возвращает доступное только для чтения представление объекта Vector, то есть [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md).|
|[Vector:: IndexOf](#indexof)|Выполняет поиск указанного элемента в текущем объекте Vector и возвращает его индекс, если он найден.|
|[Vector::InsertAt](#insertat)|Вставляет указанный элемент в текущий вектор элемента, идентифицируемого по указанному индексу.|
|[Vector::ReplaceAll](#replaceall)|Удаляет элементы из текущего объекта Vector, а затем вставляет элементы из указанного массива.|
|[Vector::RemoveAt](#removeat)|Удаляет элемент, определенный заданным индексом из текущего объекта Vector.|
|[Vector::RemoveAtEnd](#removeatend)|Удаляет элемент в конце текущего объекта Vector.|
|[Vector::SetAt](#setat)|Присваивает указанное значение к элементу текущего объекта Vector, определяемому заданным индексом.|
|[Вектор:: size](#size)|Возвращает количество элементов в текущем объекте Vector.|

### <a name="events"></a>События

| Имя | Описание |
|--|--|
| [окна событий:: Foundation:: Collection:: VectorChangedEventHandler \<T> ^ векторчанжед](/uwp/api/windows.foundation.collections.vectorchangedeventhandler-1) | Происходит при изменении объекта Vector. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Vector`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="vectorappend-method"></a><a name="append"></a> Метод Vector:: Append

Вставляет указанный элемент после последнего элемента текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Append(T item);
```

### <a name="parameters"></a>Параметры

*index*<br/>
Элемент, который требуется вставить в объект Vector. Тип *элемента* определяется свойством *T* TypeName.

## <a name="vectorclear-method"></a><a name="clear"></a> Метод Vector:: Clear

Удаляет все элементы текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="vectorfirst-method"></a><a name="first"></a> Метод Vector:: First

Возвращает итератор, указывающий первый элемент объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator <T>^ First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент объекта Vector.

### <a name="remarks"></a>Примечания

Удобным способом удержания итератора, возвращенного первым (), является присвоение возвращаемого значения переменной, объявленной с **`auto`** ключевым словом выведения типа. Например, `auto x = myVector->First();`. Этому итератору известна длина коллекции.

Если для передачи функции STL требуется пара итераторов, используйте функции Free [Windows:: Foundation:: Collections:: Begin](../cppcx/begin-function.md) и [Windows:: Foundation:: Collections:: end](../cppcx/end-function.md)

## <a name="vectorgetat-method"></a><a name="getat"></a> Метод Vector:: GetAt

Извлекает элемент текущего объекта Vector, указанный заданным индексом.

### <a name="syntax"></a>Синтаксис

```cpp
virtual T GetAt(unsigned int index);
```

### <a name="parameters"></a>Параметры

*index*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

### <a name="return-value"></a>Возвращаемое значение

Элемент, заданный параметром *index* . Тип элемента определяется с помощью имени *T* TypeName.

## <a name="vectorgetmany-method"></a><a name="getmany"></a> Метод Vector:: множеством

Извлекает последовательность элементов из текущего объекта Vector, начиная с определенного индекса, и копирует их в выделенный вызывающим объектом массив.

### <a name="syntax"></a>Синтаксис

```cpp
virtual unsigned int GetMany(
    unsigned int startIndex,
    Platform::WriteOnlyArray<T>^ dest);
```

### <a name="parameters"></a>Параметры

*startIndex*<br/>
Отсчитываемый от нуля индекс начала элементов для извлечения.

*dest*<br/>
Выделенный вызывающим объектом массив элементов, начинающихся с элемента, указанного *startIndex* , и заканчивая последним элементом в векторе.

### <a name="return-value"></a>Возвращаемое значение

Количество извлеченных элементов.

### <a name="remarks"></a>Примечания

Эта функция не предназначена для прямого использования в клиентском коде. Он используется внутренне в [функции to_vector](../cppcx/to-vector-function.md) , чтобы обеспечить эффективное преобразование платформы:: Vector принимаемые экземпляры в экземпляры std:: Vector.

## <a name="vectorgetview-method"></a><a name="getview"></a> Метод Vector::/View

Возвращает доступное только для чтения представление объекта Vector, то есть интерфейс IVectorView.

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IVectorView<T>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект IVectorView.

## <a name="vectorindexof-method"></a><a name="indexof"></a> Метод Vector:: IndexOf

Выполняет поиск указанного элемента в текущем объекте Vector и возвращает его индекс, если он найден.

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool IndexOf(T value, unsigned int* index);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Элемент, который нужно найти.

*index*<br/>
Отсчитываемый от нуля индекс элемента, если *значение* параметра найдено. в противном случае — значение 0.

Параметр *индекса* равен 0, если элемент является первым элементом вектора или элемент не найден. Если возвращаемое значение равно **`true`** , элемент был найден и является первым элементом; в противном случае элемент не был найден.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если указанный элемент найден; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

IndexOf использует std::find_if для поиска элемента. Таким образом, типы настраиваемых элементов должны перегрузить оператор == и != для включения сравнений на равенство, которое требуется для find_if.

## <a name="vectorinsertat-method"></a><a name="insertat"></a> Метод Vector:: Инсертат

Вставляет указанный элемент в текущий вектор элемента, идентифицируемого по указанному индексу.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void InsertAt(unsigned int index, T item)
```

### <a name="parameters"></a>Параметры

*index*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

*Item*<br/>
Элемент, вставляемый в Vector в элементе, указанном параметром *index*. Тип *элемента* определяется свойством *T* TypeName.

## <a name="vectorremoveat-method"></a><a name="removeat"></a> Метод Vector:: RemoveAt

Удаляет элемент, определенный заданным индексом из текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void RemoveAt(unsigned int index);
```

### <a name="parameters"></a>Параметры

*index*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

## <a name="vectorremoveatend-method"></a><a name="removeatend"></a> Метод Vector:: Ремовеатенд

Удаляет элемент в конце текущего объекта Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void RemoveAtEnd();
```

## <a name="vectorreplaceall-method"></a><a name="replaceall"></a> Метод Vector:: ReplaceAll

Удаляет элементы из текущего объекта Vector, а затем вставляет элементы из указанного массива.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);
```

### <a name="parameters"></a>Параметры

*маленькая*<br/>
Массив объектов, тип которых определяется свойством *T* TypeName.

## <a name="vectorsetat-method"></a><a name="setat"></a> Метод Vector:: SetAt

Присваивает указанное значение к элементу текущего объекта Vector, определяемому заданным индексом.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void SetAt(unsigned int index, T item);
```

### <a name="parameters"></a>Параметры

*index*<br/>
Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.

*Item*<br/>
Значение, присваиваемое указанному элементу. Тип *элемента* определяется свойством *T* TypeName.

## <a name="vectorsize-method"></a><a name="size"></a> Метод Vector:: size

Возвращает количество элементов в текущем объекте Vector.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в текущем объекте Vector.

## <a name="vectorvector-constructor"></a><a name="ctor"></a> Конструктор Vector:: Vector

Инициализирует новый экземпляр класса Vector.

### <a name="syntax"></a>Синтаксис

```cpp
Vector();

explicit Vector(unsigned int size);
Vector( unsigned int size, T value);
template <typename U> explicit Vector( const ::std::vector<U>& v);
template <typename U> explicit Vector( std::vector<U>&& v);

Vector( const T * ptr, unsigned int size);
template <size_t N> explicit Vector(const T(&arr)[N]);
template <size_t N> explicit Vector(const std::array<T, N>& a);
explicit Vector(const Array<T>^ arr);

template <typename InIt> Vector(InIt first, InIt last);
Vector(std::initializer_list<T> il);
```

### <a name="parameters"></a>Параметры

*конкретного*<br/>
[Массив std:: Array](../standard-library/array-class-stl.md) , который будет использоваться для инициализации вектора.

*маленькая*<br/>
Объект [Platform:: Array](../cppcx/platform-array-class.md) , который будет использоваться для инициализации вектора.

*Ini*<br/>
Тип коллекции объектов, используемой для инициализации текущего объекта Vector.

*компонента*<br/>
Объект [std:: initializer_list](../standard-library/initializer-list-class.md) объектов типа *T* , которые будут использоваться для инициализации вектора.

*N*<br/>
Количество элементов в коллекции объектов, используемой для инициализации текущего объекта Vector.

*size*<br/>
Количество элементов в объекте Vector.

*value*<br/>
Значение, используемое для инициализации каждого элемента в текущем объекте Vector.

*3,3*<br/>
[Значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для [std:: Vector](../standard-library/vector-class.md) , который используется для инициализации текущего вектора.

*ptr*<br/>
Указатель на объект `std::vector`, используемый для инициализации текущего объекта Vector.

*first*<br/>
Первый элемент в последовательности объектов, используемых для инициализации текущего объекта Vector. Тип *первого* передается средствами *идеальной пересылки*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

*last*<br/>
Последний элемент в последовательности объектов, используемых для инициализации текущего объекта Vector. Тип *Last* передается средствами *идеальной пересылки*. Дополнительные сведения см. в статье [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>См. также раздел

[Коллекции (C++/CX)](collections-c-cx.md)<br/>
[Пространство имен платформы](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
