---
title: Класс Platform::Collections::UnorderedMap
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
ms.openlocfilehash: ec458f5d4a47b6eced939c4fe346d5d0414ea7c2
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839131"
---
# <a name="platformcollectionsunorderedmap-class"></a>Класс Platform::Collections::UnorderedMap

Представляет неупорядоченное *сопоставление*, являющееся коллекцией пар "ключ-значение".

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename K,
   typename V,
   typename C = std::equal_to<K>
>
ref class Map sealed;
```

#### <a name="parameters"></a>Параметры

*Занят*<br/>
Тип ключа в паре "ключ-значение".

*3,3*<br/>
Тип значения в паре "ключ-значение".

*В*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию [std:: equal_to \<K> ](../standard-library/equal-to-struct.md).

### <a name="remarks"></a>Примечания

Допустимые типы:

- integers

- класс интерфейса ^

- открытый ссылочный класс ^

- структура значений

- открытый класс перечисления

**UnorderedMap** по сути является оболочкой для [std:: unordered_map](../standard-library/unordered-map-class.md) , которая поддерживает хранение типов Среда выполнения Windows. Это конкретная реализация типов [Windows:: Foundation:: Collections:: IMAP](/uwp/api/windows.foundation.collections.imap-2) и [IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) , которые передаются через общедоступные интерфейсы Среда выполнения Windows. При попытке использования типа `Platform::Collections::UnorderedMap` в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Вы можете исправить ошибку, изменив тип параметра или возвращаемого значения на [Windows::Foundation::Collections::IMap](/uwp/api/windows.foundation.collections.imap-2).

Дополнительные сведения см. в разделе [коллекции](../cppcx/collections-c-cx.md).

### <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[UnorderedMap:: UnorderedMap](#ctor)|Инициализирует новый экземпляр класса Map.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[UnorderedMap:: Clear](#clear)|Удаляет все пары "ключ-значение" из текущего объекта Map.|
|[UnorderedMap:: First](#first)|Возвращает итератор, указывающий первый элемент в сопоставлении.|
|[UnorderedMap:: View](#getview)|Возвращает доступное только для чтения представление текущего сопоставления, то есть класс Platform::Collections::UnorderedMapView.|
|[UnorderedMap:: HasKey](#haskey)|Определяет, содержит ли текущий объект Map указанный ключ.|
|[UnorderedMap:: INSERT](#insert)|Добавляет в текущий объект Map указанную пару "ключ-значение".|
|[UnorderedMap:: Lookup](#lookup)|Извлекает элемент по указанному ключу в текущем объекте Map.|
|[UnorderedMap:: Remove](#remove)|Удаляет указанную пару "ключ-значение" из текущего объекта Map.|
|[UnorderedMap:: size](#size)|Возвращает количество элементов в текущем объекте Map.|

### <a name="events"></a>События

| Имя | Описание |
|--|--|
| Событие [Map:: мапчанжед](#mapchanged) | Происходит при изменении объекта Map. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`UnorderedMap`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="unorderedmapclear-method"></a><a name="clear"></a> Метод UnorderedMap:: Clear

Удаляет все пары "ключ-значение" из текущего объекта UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="unorderedmapfirst-method"></a><a name="first"></a> Метод UnorderedMap:: First

Возвращает итератор, указывающий первый элемент [Windows:: Foundation:: Collections:: \<K,V> IKeyValuePair](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) в неупорядоченной карте.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
   First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент на карте.

### <a name="remarks"></a>Примечания

Удобным способом удержания итератора, возвращенного первым (), является присвоение возвращаемого значения переменной, объявленной с **`auto`** ключевым словом выведения типа. Например, `auto x = myUnorderedMap->First();`.

## <a name="unorderedmapgetview-method"></a><a name="getview"></a> Метод UnorderedMap:: onview

Возвращает доступное только для чтения представление текущего UnorderedMap; то есть [класс Platform:: Collections:: UnorderedMapView](../cppcx/platform-collections-unorderedmapview-class.md) , реализующий интерфейс [Windows:: Foundation:: Collections:: IMapView:: IMapView](/uwp/api/windows.foundation.collections.imapview-2) .

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `UnorderedMapView`.

## <a name="unorderedmaphaskey-method"></a><a name="haskey"></a> Метод UnorderedMap:: HasKey

Определяет, содержит ли текущий объект UnorderedMap указанный ключ.

### <a name="syntax"></a>Синтаксис

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента UnorderedMap. Тип *ключа* — TypeName *K*.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ключ найден; в противном случае — **`false`** .

## <a name="unorderedmapinsert-method"></a><a name="insert"></a> Метод UnorderedMap:: INSERT

Добавляет в текущий объект UnorderedMap указанную пару "ключ-значение".

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключа* — TypeName *K*.

*value*<br/>
Значение из пары "ключ-значение". Тип *значения* — TypeName *V*.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ключ существующего элемента в текущей карте соответствует *ключу* , а значение этого элемента равно *значению*. **`false`** Если в текущем *ключе* сопоставления нет существующего элемента, а параметры *ключа* и *значения* вносятся в пару "ключ-значение", а затем добавляются в текущий UnorderedMap.

## <a name="unorderedmaplookup-method"></a><a name="lookup"></a> Метод UnorderedMap:: Lookup

Возвращает значение типа V, связанное с указанным ключом типа K.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента в объекте UnorderedMap. Тип *ключа* — TypeName *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с *ключом*. Тип возвращаемого значения — TypeName *V*.

## <a name="unorderedmapmapchanged"></a><a name="mapchanged"></a> UnorderedMap:: Мапчанжед

Возникает, когда элемент вставляется в сопоставление или удаляется из него.

### <a name="syntax"></a>Синтаксис

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение

Объект [мапчанжедевенсандлер \<K,V> ](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) , содержащий сведения об объекте, вызвавшем событие, и типе произошедшего изменения. См. также [перечисление](/uwp/api/windows.foundation.collections.collectionchange) [ \<K> имапчанжедевентаргс](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) и коллектиончанже.

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

Среда выполнения Windows приложения, которые C# или Visual Basic Project IMap \<K,V> как IDictionary \<K,V> .

## <a name="unorderedmapremove-method"></a><a name="remove"></a> Метод UnorderedMap:: Remove

Удаляет указанную пару "ключ-значение" из текущего объекта UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключа* — TypeName *K*.

## <a name="unorderedmapsize-method"></a><a name="size"></a> Метод UnorderedMap:: size

Возвращает число элементов [Windows:: Foundation:: Collections:: IKeyValuePair \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) в UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в объекте UnorderedMap.

## <a name="unorderedmapunorderedmap-constructor"></a><a name="ctor"></a> Конструктор UnorderedMap:: UnorderedMap

Инициализирует новый экземпляр класса UnorderedMap.

### <a name="syntax"></a>Синтаксис

```cpp
UnorderedMap();

explicit UnorderedMap(
    size_t n
    );

UnorderedMap(
    size_t n,
    const H& h
    );

UnorderedMap(
    size_t n,
    const H& h,
    const P& p
    );

explicit UnorderedMap(
    const std::unordered_map<K, V, H, P>& m
    );

explicit UnorderedMap(
    std::unordered_map<K, V, H, P>&& m
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p
    );
```

### <a name="parameters"></a>Параметры

*Ini*<br/>
Имя типа текущего объекта UnorderedMap.

*P*<br/>
Объект функции, который может сравнивать два ключа с целью определения их равенства. По умолчанию этот параметр имеет значение [std: \<K> : equal_to](../standard-library/equal-to-struct.md).

*H*<br/>
Объект функции, создающий хэш-значения для ключей. Этот параметр по умолчанию имеет [хэш-класс 1](../standard-library/hash-class.md) для типов ключей, поддерживаемых классом.

*m*<br/>
Ссылка или [значения lvalue и rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для [std:: unordered_map](../standard-library/unordered-map-class.md) , которая используется для инициализации текущего UnorderedMap.

*компонента*<br/>
Объект " [std:: initializer_list](../standard-library/initializer-list-class.md) " [стандартного::p объектов Air](../standard-library/pair-structure.md) , который используется для инициализации схемы.

*first*<br/>
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта UnorderedMap.

*last*<br/>
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта UnorderedMap.

## <a name="see-also"></a>См. также раздел

[Пространство имен платформы](platform-namespace-c-cx.md)<br/>
[Пространство имен Platform:: Collections](../cppcx/platform-collections-namespace.md)<br/>
[Класс Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md)<br/>
[Класс Platform:: Collections:: UnorderedMapView](../cppcx/platform-collections-unorderedmapview-class.md)<br/>
[Коллекции](../cppcx/collections-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
