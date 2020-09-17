---
title: Класс Platform::Collections::VectorIterator
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
ms.openlocfilehash: bade67a104774c3ab6187e250c6faf6969002c0c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218420"
---
# <a name="platformcollectionsvectoriterator-class"></a>Класс Platform::Collections::VectorIterator

Предоставляет итератор стандартной библиотеки шаблонов для объектов, производных от интерфейса среда выполнения Windows IVector.

VectorIterator — это итератор прокси-сервера, в котором хранятся элементы типа VectorProxy \<T> . Однако объект прокси-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections (C++/CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class VectorIterator;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Имя типа класса шаблона VectorIterator.

### <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`difference_type`|Различие указателя (ptrdiff_t).|
|`iterator_category`|Категория итератора произвольного доступа (::std::random_access_iterator_tag).|
|`pointer`|Указатель на внутренний тип, Platform:: Collections::D состояния:: VectorProxy \<T> , необходимый для реализации VectorIterator.|
|`reference`|Ссылка на внутренний тип, Platform:: Collections::D состояния:: VectorProxy \<T> , которая требуется для реализации VectorIterator.|
|`value_type`|Имя типа `T` .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[VectorIterator:: VectorIterator](#ctor)|Инициализирует новый экземпляр класса VectorIterator.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор VectorIterator::operator-](#operator-minus)|Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.|
|[Оператор VectorIterator::operator--](#operator-decrement)|Выполняет уменьшение текущего итератора VectorIterator.|
|[Оператор VectorIterator::operator!=](#operator-inequality)|Указывает, отличен ли текущий объект VectorIterator от указанного объекта VectorIterator.|
|[Оператор VectorIterator::operator*](#operator-dereference)|Извлекает ссылку на элемент, указанный текущим итератором VectorIterator.|
|[Оператор VectorIterator::operator\[\]](#operator-at)|Извлекает ссылку на элемент, отстоящий от текущего итератора VectorIterator на указанную величину смещения.|
|[Оператор VectorIterator::operator+](#operator-plus)|Возвращает объект VectorIterator, указывающий на элемент с заданным смещением от указанного объекта VectorIterator.|
|[Оператор VectorIterator::operator++](#operator-increment)|Выполняет увеличение текущего итератора VectorIterator.|
|[Оператор VectorIterator::operator+=](#operator-plus-assign)|Увеличивает текущий итератор VectorIterator на указанную величину смещения.|
|[Оператор VectorIterator::operator<](#operator-less-than)|Указывает, является ли текущий объект VectorIterator меньшим, чем указанный объект VectorIterator.|
|[Оператор VectorIterator::operator\< =](#operator-less-than-or-equals)|Указывает, является ли текущий объект VectorIterator меньшим или равным указанному объекту VectorIterator.|
|[Оператор VectorIterator::operator-=](#operator-minus-equals)|Уменьшает текущий итератор VectorIterator на указанную величину смещения.|
|[Оператор VectorIterator::operator==](#operator-equality)|Указывает, равен ли текущий объект VectorIterator указанному объекту VectorIterator.|
|[Оператор VectorIterator::operator>](#operator-greater-than)|Указывает, действительно ли текущий объект VectorIterator больше, чем указанный объект VectorIterator.|
|[Оператор VectorIterator::operator->](#operator-arrow)|Извлекает адрес элемента, на который ссылается текущий итератор VectorIterator.|
|[Оператор VectorIterator::operator>=](#operator-greater-than-or-equals)|Указывает, действительно ли текущий объект VectorIterator больше указанного объекта VectorIterator или равен ему.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VectorIterator`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="vectoriteratoroperator-gt-operator"></a><a name="operator-arrow"></a>Оператор VectorIterator::operator-&gt;

Извлекает адрес элемента, на который ссылается текущий итератор VectorIterator.

### <a name="syntax"></a>Синтаксис

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение элемента, на который ссылается текущий итератор VectorIterator.

Тип возвращаемого значения является неуказанным внутренним типом, необходимым для реализации этого оператора.

## <a name="vectoriteratoroperator---operator"></a><a name="operator-decrement"></a>Оператор VectorIterator::operator--

Выполняет уменьшение текущего итератора VectorIterator.

### <a name="syntax"></a>Синтаксис

```

VectorIterator& operator--();
VectorIterator operator--(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый синтаксис выполняет уменьшение текущего итератора VectorIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorIterator, а затем выполняет уменьшение текущего итератора VectorIterator.

### <a name="remarks"></a>Примечания

Первый синтаксис выполняет уменьшение текущего итератора VectorIterator перед его использованием.

Второй синтаксис выполняет уменьшение текущего итератора VectorIterator после его использования. **`int`** Тип во втором синтаксисе указывает на операцию после декремента, а не на фактический целочисленный операнд.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-dereference"></a>Оператор VectorIterator::operator\*

Извлекает адрес элемента, указанного текущим итератором VectorIterator.

### <a name="syntax"></a>Синтаксис

```
reference operator*() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент, указанный текущим итератором VectorIterator.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-equality"></a>Оператор VectorIterator::operator==

Указывает, равен ли текущий объект VectorIterator указанному объекту VectorIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator==(const VectorIterator& other) const;
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если текущий VectorIterator равен *другому*; в противном случае — **`false`** .

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than"></a>Оператор VectorIterator::operator&gt;

Указывает, действительно ли текущий объект VectorIterator больше, чем указанный объект VectorIterator.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator>(const VectorIterator& other) const
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если текущий VectorIterator больше *другого*; в противном случае — **`false`** .

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a>Оператор VectorIterator::operator&gt;=

Указывает, является ли текущий объект VectorIterator большим или равным указанному объекту VectorIterator.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator>=(const VectorIterator& other) const
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если текущий VectorIterator больше или равен *другому*; в противном случае — **`false`** .

## <a name="vectoriteratoroperator-operator"></a><a name="operator-increment"></a>Оператор VectorIterator::operator++

Выполняет увеличение текущего итератора VectorIterator.

### <a name="syntax"></a>Синтаксис

```
VectorIterator& operator++();
VectorIterator operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый синтаксис выполняет увеличение текущего итератора VectorIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorIterator, а затем выполняет увеличение текущего итератора VectorIterator.

### <a name="remarks"></a>Примечания

Первый синтаксис выполняет увеличение текущего итератора VectorIterator перед его использованием.

Второй синтаксис выполняет увеличение текущего итератора VectorIterator после его использования. **`int`** Тип во втором синтаксисе указывает на операцию после приращения, а не на фактический целочисленный операнд.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-inequality"></a>Оператор VectorIterator::operator!=

Указывает, отличен ли текущий объект VectorIterator от указанного объекта VectorIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator!=(const VectorIterator& other) const;
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если текущий VectorIterator не равен *другому*; в противном случае — **`false`** .

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than"></a>Оператор VectorIterator::operator&lt;

Указывает, является ли текущий объект VectorIterator меньшим, чем указанный объект VectorIterator.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator<(const VectorIterator& other) const
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если текущий VectorIterator меньше *другого*; в противном случае — **`false`** .

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a>Оператор VectorIterator::operator&lt;=

Указывает, является ли текущий объект VectorIterator меньшим или равным указанному объекту VectorIterator.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator<=(const VectorIterator& other) const
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если текущий VectorIterator меньше или равен *другому*; в противном случае — **`false`** .

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus"></a>Оператор VectorIterator::operator-

Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.

### <a name="syntax"></a>Синтаксис

```

VectorIterator operator-(difference_type n) const;

difference_type operator-(const VectorIterator& other) const;
```

### <a name="parameters"></a>Параметры

*n*<br/>
Количество элементов.

*иной*<br/>
Другой объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

Синтаксис первого оператора возвращает объект VectorIterator, количество элементов которого меньше, чем у текущего объекта VectorIterator, на `n`. Синтаксис второго оператора возвращает количество элементов между текущим объектом VectorIterator и другим объектом VectorIterator, заданным параметром `other`.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus-assign"></a>Оператор VectorIterator::operator+=

Увеличивает текущий итератор VectorIterator на указанную величину смещения.

### <a name="syntax"></a>Синтаксис

```
VectorIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целочисленная величина смещения.

### <a name="return-value"></a>Возвращаемое значение

Обновленный VectorIterator.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus"></a>Оператор VectorIterator::operator+

Возвращает объект VectorIterator, указывающий на элемент с заданным смещением от указанного объекта VectorIterator.

### <a name="syntax"></a>Синтаксис

```

VectorIterator operator+(difference_type n);

template <typename T>
inline VectorIterator<T> operator+(
  ptrdiff_t n,
  const VectorIterator<T>& i);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Во втором синтаксисе — имя типа объекта VectorIterator.

*n*<br/>
Целочисленная величина смещения.

*i*<br/>
Во втором синтаксисе — объект VectorIterator.

### <a name="return-value"></a>Возвращаемое значение

В первом синтаксисе — объект VectorIterator, указывающий на элемент с заданным смещением от текущего объекта VectorIterator.

Во втором синтаксисе — объект VectorIterator, указывающий на элемент с заданным смещением от начала параметра `i`.

### <a name="remarks"></a>Примечания

Первый пример синтаксиса

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus-equals"></a>Оператор VectorIterator::operator-=

Уменьшает текущий итератор VectorIterator на указанную величину смещения.

### <a name="syntax"></a>Синтаксис

```
VectorIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целочисленная величина смещения.

### <a name="return-value"></a>Возвращаемое значение

Обновленный VectorIterator.

## <a name="vectoriteratoroperator"></a><a name="operator-at"></a>Оператор VectorIterator::operator\[\]

Извлекает ссылку на элемент, отстоящий от текущего итератора VectorIterator на указанную величину смещения.

### <a name="syntax"></a>Синтаксис

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Параметры

*n*<br/>
Целочисленная величина смещения.

### <a name="return-value"></a>Возвращаемое значение

Элемент, отстоящий от текущего итератора VectorIterator на `n` элементов.

## <a name="vectoriteratorvectoriterator-constructor"></a><a name="ctor"></a>Конструктор VectorIterator::VectorIterator

Инициализирует новый экземпляр класса VectorIterator.

### <a name="syntax"></a>Синтаксис

```
VectorIterator();

explicit VectorIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

### <a name="parameters"></a>Параметры

*3,3*<br/>
Объект IVector \<T> .

### <a name="remarks"></a>Примечания

Первый пример синтаксиса является конструктором по умолчанию. Вторым примером синтаксиса является явный конструктор, который используется для создания VectorIterator из \<T> объекта IVector.

## <a name="see-also"></a>См. также раздел

[Пространство имен платформы](platform-namespace-c-cx.md)
