---
title: Класс Platform::Collections::UnorderedMapView
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
ms.openlocfilehash: acfc168959deb83244c98c5d361cf9e73c1388f2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213064"
---
# <a name="platformcollectionsunorderedmapview-class"></a>Класс Platform::Collections::UnorderedMapView

Представляет доступное только для чтения представление на *карте*, которое является коллекцией пар "ключ-значение".

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename K,
   typename V,
   typename C = ::std::equal_to<K>>
ref class UnorderedMapView sealed;
```

#### <a name="parameters"></a>Параметры

*Занят*<br/>
Тип ключа в паре "ключ-значение".

*3,3*<br/>
Тип значения в паре "ключ-значение".

*В*<br/>
Тип, предоставляющий объект функции, который может сравнивать два ключевых значения для определения равенства. По умолчанию [std:: equal_to \<K> ](../standard-library/equal-to-struct.md)

### <a name="remarks"></a>Примечания

UnorderedMapView является конкретной реализацией C++ интерфейса [Windows:: Foundation:: Collections:: IMapView \<K,V> ](/uwp/api/windows.foundation.collections.imapview-2) , который передается через двоичный интерфейс приложения (ABI). Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[UnorderedMapView:: UnorderedMapView](#ctor)|Инициализирует новый экземпляр класса UnorderedMapView.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[UnorderedMapView:: First](#first)|Возвращает итератор, который инициализируется первым элементом в представлении карты.|
|[UnorderedMapView:: HasKey](#haskey)|Определяет, содержит ли текущий объект UnorderedMapView указанный ключ.|
|[UnorderedMapView:: Lookup](#lookup)|Извлекает элемент по указанному ключу в текущем объекте UnorderedMapView.|
|[UnorderedMapView:: size](#size)|Возвращает количество элементов в текущем объекте UnorderedMapView.|
|[UnorderedMapView:: Split](#split)|Разделяет исходный объект UnorderedMapView на два объекта UnorderedMapView.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`UnorderedMapView`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="unorderedmapviewfirst-method"></a><a name="first"></a>Метод UnorderedMapView:: First

Возвращает итератор, указывающий первый элемент [Windows:: Foundation:: Collections:: \<K,V> IKeyValuePair](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) в неупорядоченной карте.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator<
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
    First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент в представлении сопоставления.

### <a name="remarks"></a>Примечания

Удобным способом удержания итератора, возвращенного первым (), является присвоение возвращаемого значения переменной, объявленной с **`auto`** ключевым словом выведения типа. Например, `auto x = myMapView->First();`.

## <a name="unorderedmapviewhaskey-method"></a><a name="haskey"></a>Метод UnorderedMapView:: HasKey

Определяет, содержит ли текущий объект UnorderedMap указанный ключ.

### <a name="syntax"></a>Синтаксис

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента. Тип `key` — TypeName *K*.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ключ найден; в противном случае — **`false`** .

## <a name="unorderedmapviewlookup-method"></a><a name="lookup"></a>Метод UnorderedMapView:: Lookup

Возвращает значение типа V, связанное с указанным ключом типа K.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента в объекте UnorderedMapView. Тип `key` — TypeName *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с ключом `key`. Тип возвращаемого значения — TypeName *V*.

## <a name="unorderedmapviewsize-method"></a><a name="size"></a>Метод UnorderedMapView:: size

Возвращает число элементов [Windows:: Foundation:: Collections:: IKeyValuePair \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) в UnorderedMapView.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в Unordered MapView.

## <a name="unorderedmapviewsplit-method"></a><a name="split"></a>Метод UnorderedMapView:: Split

Разделяет текущий объект UnorderedMapView на два объекта UnorderedMapView. Этот метод не выполняет никаких действий.

### <a name="syntax"></a>Синтаксис

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * secondPartition);
```

### <a name="parameters"></a>Параметры

*фирстпартитион*<br/>
Первая часть исходного объекта UnorderedMapView.

*секондпартитион*<br/>
Вторая часть исходного объекта UnorderedMapView.

### <a name="remarks"></a>Примечания

Этот метод не выполняет никаких действий.

## <a name="unorderedmapviewunorderedmapview-constructor"></a><a name="ctor"></a>Конструктор UnorderedMapView:: UnorderedMapView

Инициализирует новый экземпляр класса UnorderedMapView.

### <a name="syntax"></a>Синтаксис

```cpp
UnorderedMapView();
explicit UnorderedMapView(size_t n);
UnorderedMapView(size_t n, const H& h);
UnorderedMapView(size_t n, const H& h, const P& p);

explicit UnorderedMapView(
    const std::unordered_map<K, V, H, P>& m);
explicit UnorderedMapView(
    std::unordered_map<K, V, H, P>&& m);

template <typename InIt> UnorderedMapView(InIt first, InIt last );
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p );

UnorderedMapView(std::initializer_list<std::pair<const K, V>);

UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h);

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p );
```

### <a name="parameters"></a>Параметры

*n*<br/>
Число элементов, для которых необходимо заранее выделить пространство.

*Ini*<br/>
Имя типа UnorderedMapView.

*H*<br/>
Объект функции, который может создать хэш-значение для ключа. По умолчанию используется [std:: \<K> hash](../standard-library/hash-class.md) для типов, которые `std::hash` поддерживают.

*P*<br/>
Тип, предоставляющий объект функции, который может сравнивать два ключа с целью установления их равенства. По умолчанию используется [std:: \<K> equal_to](../standard-library/equal-to-struct.md).

*m*<br/>
Ссылка или [значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для [std:: unordered_map](../standard-library/unordered-map-class.md) , которая используется для инициализации UnorderedMapView.

*first*<br/>
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации UnorderedMapView.

*last*<br/>
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации UnorderedMapView.

## <a name="see-also"></a>См. также раздел

[Пространство имен Platform:: Collections](../cppcx/platform-collections-namespace.md)<br/>
[Windows::Foundation::IMapView](/uwp/api/windows.foundation.collections.imapview-2)
