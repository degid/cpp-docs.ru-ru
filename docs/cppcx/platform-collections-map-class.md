---
title: Класс Platform::Collections::Map
ms.date: 10/01/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
helpviewer_keywords:
- Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
ms.openlocfilehash: 40b7d653b21cdc2b0fab4c852c9809ab1db46a12
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839144"
---
# <a name="platformcollectionsmap-class"></a>Класс Platform::Collections::Map

Представляет *сопоставление*, являющееся коллекцией пар "ключ-значение". Реализует [Windows:: Foundation:: Collections:: IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) для помощи с [привязкой данных](/windows/uwp/data-binding/data-binding-in-depth)XAML.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>Параметры

*Занят*<br/>
Тип ключа в паре "ключ-значение".

*3,3*<br/>
Тип значения в паре "ключ-значение".

*В*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию [std:: less \<K> ](../standard-library/less-struct.md).

*__is_valid_winrt_type ()* Созданная компилятором функция, которая проверяет тип *K* и *V* и предоставляет понятное сообщение об ошибке, если тип не может быть сохранен на карте.

### <a name="remarks"></a>Примечания

Допустимые типы:

- integers

- класс интерфейса ^

- открытый ссылочный класс ^

- структура значений

- открытый класс перечисления

Карта — это, по сути, программа-оболочка для [std::map](../standard-library/map-class.md). Это конкретная реализация C++ типов [Windows:: Foundation:: Collections:: IMAP \<Windows::Foundation::Collections::IKeyValuePair\<K,V> > ](/uwp/api/windows.foundation.collections.imap-2) и [IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) , которая передается через общедоступные интерфейсы Среда выполнения Windows. При попытке использования типа `Platform::Collections::Map` в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Эту ошибку можно исправить, изменив тип параметра или возвращаемого значения на [Windows:: Foundation:: Collections:: IMAP \<K,V> ](/uwp/api/windows.foundation.collections.imap-2).

Дополнительные сведения см. в разделе [коллекции](../cppcx/collections-c-cx.md).

### <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Map:: Map](#ctor)|Инициализирует новый экземпляр класса Map.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Map:: Clear](#clear)|Удаляет все пары "ключ-значение" из текущего объекта Map.|
|[Map:: First](#first)|Возвращает итератор, указывающий первый элемент в сопоставлении.|
|[Map:: onview](#getview)|Возвращает представление текущего объекта Map, доступное только для чтения (т. е. [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md)).|
|[Map:: HasKey](#haskey)|Определяет, содержит ли текущий объект Map указанный ключ.|
|[Map:: INSERT](#insert)|Добавляет в текущий объект Map указанную пару "ключ-значение".|
|[Map:: Lookup](#lookup)|Извлекает элемент по указанному ключу в текущем объекте Map.|
|[Map::Remove](#remove)|Удаляет указанную пару "ключ-значение" из текущего объекта Map.|
|[Map:: size](#size)|Возвращает количество элементов в текущем объекте Map.|

### <a name="events"></a>События

| Имя | Описание |
|--|--|
| Событие [Map:: мапчанжед](#mapchanged) | Происходит при изменении объекта Map. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Map`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="mapclear-method"></a><a name="clear"></a> Метод Map:: Clear

Удаляет все пары "ключ-значение" из текущего объекта Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Clear();
```

## <a name="mapfirst-method"></a><a name="first"></a> Метод Map:: First

Возвращает итератор, указывающий первый элемент в сопоставлении или **`nullptr`** значение, если схема пуста.

### <a name="syntax"></a>Синтаксис

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий первый элемент на карте.

### <a name="remarks"></a>Примечания

Удобным способом удержания итератора, возвращенного первым (), является присвоение возвращаемого значения переменной, объявленной с **`auto`** ключевым словом выведения типа. Например, `auto x = myMap->First();`.

## <a name="mapgetview-method"></a><a name="getview"></a> Метод Map:: onview

Возвращает доступное только для чтения представление текущей схемы. то есть [класс Platform:: Collections:: MapView](../cppcx/platform-collections-mapview-class.md), реализующий интерфейс [Windows:: Foundation:: Collections:: IMapView \<K,V> ](/uwp/api/windows.foundation.collections.imapview-2) .

### <a name="syntax"></a>Синтаксис

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `MapView`.

## <a name="maphaskey-method"></a><a name="haskey"></a> Метод Map:: HasKey

Определяет, содержит ли текущий объект Map указанный ключ.

### <a name="syntax"></a>Синтаксис

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента Map. Тип *ключа* — TypeName *K*.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ключ найден; в противном случае — **`false`** .

## <a name="mapinsert-method"></a><a name="insert"></a> Метод Map:: INSERT

Добавляет в текущий объект Map указанную пару "ключ-значение".

### <a name="syntax"></a>Синтаксис

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключа* — TypeName *K*.

*value*<br/>
Значение из пары "ключ-значение". Тип *значения* — TypeName *V*.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если ключ существующего элемента в текущей карте соответствует *ключу* , а значение этого элемента равно *значению*. **`false`** значение, если существующий элемент в текущем *ключе* сопоставления не совпадает с параметрами *ключа* и *значения* , а затем добавляется в текущую карту.

## <a name="maplookup-method"></a><a name="lookup"></a> Метод Map:: Lookup

Возвращает значение типа V, связанное с указанным ключом типа K, если ключ существует.

### <a name="syntax"></a>Синтаксис

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, используемый для поиска элемента на карте. Тип *ключа* — TypeName *K*.

### <a name="return-value"></a>Возвращаемое значение

Значение, связанное с *ключом*. Тип возвращаемого значения — TypeName *V*.

### <a name="remarks"></a>Примечания

Если ключ не существует, создается исключение [Platform:: OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) .

## <a name="mapmap-constructor"></a><a name="ctor"></a> Конструктор Map:: Map

Инициализирует новый экземпляр класса Map.

### <a name="syntax"></a>Синтаксис

```cpp
explicit Map(const C& comp = C());
explicit Map(const StdMap& m);
explicit Map(StdMap&& m ;
template <typename InIt>
Map(
   InItfirst,
   InItlast,
   const C& comp = C());
```

### <a name="parameters"></a>Параметры

*Ini*<br/>
Имя типа текущего объекта Map.

*comp*<br/>
Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map.

*m*<br/>
Ссылка или [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) для `map Class` , который используется для инициализации текущей схемы.

*first*<br/>
Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта Map.

*last*<br/>
Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта Map.

## <a name="mapmapchanged-event"></a><a name="mapchanged"></a> Событие Map:: Мапчанжед

Возникает, когда элемент вставляется в сопоставление или удаляется из него.

### <a name="syntax"></a>Синтаксис

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение

Объект [мапчанжедевенсандлер \<K,V> ](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) , содержащий сведения об объекте, вызвавшем событие, и типе произошедшего изменения. См. также [перечисление](/uwp/api/windows.foundation.collections.collectionchange) [ \<K> имапчанжедевентаргс](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) и коллектиончанже.

## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework

Среда выполнения Windows приложений, использующих C# или Visual Basic Project IMap \<K,V> как IDictionary \<K,V> .

## <a name="mapremove-method"></a><a name="remove"></a> Метод Map:: Remove

Удаляет указанную пару "ключ-значение" из текущего объекта Map.

### <a name="syntax"></a>Синтаксис

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ из пары "ключ-значение". Тип *ключа* — TypeName *K*.

## <a name="mapsize-method"></a><a name="size"></a> Метод Map:: size

Возвращает число элементов [Windows:: Foundation:: Collections:: IKeyValuePair \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) в сопоставлении.

### <a name="syntax"></a>Синтаксис

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в объекте Map.

## <a name="see-also"></a>См. также раздел

[Коллекции (C++/CX)](collections-c-cx.md)<br/>
[Пространство имен платформы](platform-namespace-c-cx.md)<br/>
[Создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
