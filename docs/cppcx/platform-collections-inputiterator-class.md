---
title: Класс Platform::Collections::InputIterator
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: 4aeef07a34c04bd1ab47acf808026024faada567
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218433"
---
# <a name="platformcollectionsinputiterator-class"></a>Класс Platform::Collections::InputIterator

Предоставляет библиотеку стандартных шаблонов InputIterator для коллекций, производных от среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <typename X>
class InputIterator;
```

#### <a name="parameters"></a>Параметры

*X*<br/>
Имя типа класса шаблона InputIterator.

### <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`difference_type`|Различие указателя (ptrdiff_t).|
|`iterator_category`|Категория итератора ввода (:: std::input_iterator_tag).|
|`pointer`|Указатель на `const X`|
|`reference`|Ссылка на объект `const X`|
|`value_type`|Имя типа `X` .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[InputIterator:: InputIterator](#ctor)|Инициализирует новый экземпляр класса InputIterator.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор InputIterator::operator!=](#operator-inequality)|Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.|
|[Оператор InputIterator::operator*](#operator-dereference)|Извлекает ссылку на элемент, указанный текущим итератором InputIterator.|
|[Оператор InputIterator::operator++](#operator-increment)|Выполняет приращение текущего итератора InputIterator.|
|[Оператор InputIterator::operator==](#operator-equality)|Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.|
|[Оператор InputIterator::operator->](#operator-arrow)|Извлекает адрес элемента, на который ссылается текущий итератор InputIterator.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InputIterator`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="inputiteratorinputiterator-constructor"></a><a name="ctor"></a>Конструктор InputIterator:: InputIterator

Инициализирует новый экземпляр класса InputIterator.

### <a name="syntax"></a>Синтаксис

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iterator);
```

### <a name="parameters"></a>Параметры

*итераци*<br/>
Объект итератора.

## <a name="inputiteratoroperator-gt-operator"></a><a name="operator-arrow"></a>Оператор InputIterator::operator- &gt;

Извлекает адрес элемента, указанного текущим итератором InputIterator.

### <a name="syntax"></a>Синтаксис

```
pointer operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес элемента, указанного текущим итератором InputIterator.

## <a name="inputiteratoroperator-operator"></a><a name="operator-dereference"></a>Оператор InputIterator::operator \*

Извлекает ссылку на элемент, указанный текущим итератором InputIterator.

### <a name="syntax"></a>Синтаксис

```
reference operator*() const;
```

### <a name="return-value"></a>Возвращаемое значение

Элемент, указанный текущим итератором InputIterator.

## <a name="inputiteratoroperator-operator"></a><a name="operator-equality"></a>Оператор InputIterator::operator==

Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Другой объект InputIterator.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если текущий InputIterator равен *другому*; в противном случае — **`false`** .

## <a name="inputiteratoroperator-operator"></a><a name="operator-increment"></a>Оператор InputIterator::operator++

Выполняет приращение текущего итератора InputIterator.

### <a name="syntax"></a>Синтаксис

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Первый синтаксис выполняет приращение текущего итератора InputIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора InputIterator, а затем выполняет приращение текущего итератора InputIterator.

### <a name="remarks"></a>Примечания

Первый синтаксис InputIterator выполняет приращение текущего итератора InputIterator перед его использованием.

Второй синтаксис выполняет приращение текущего итератора InputIterator после его использования. **`int`** Тип во втором синтаксисе указывает на операцию после приращения, а не на фактический целочисленный операнд.

## <a name="inputiteratoroperator-operator"></a><a name="operator-inequality"></a>Оператор InputIterator::operator!=

Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.

### <a name="syntax"></a>Синтаксис

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Другой объект InputIterator.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если текущий InputIterator не равен *другому*; в противном случае — **`false`** .

## <a name="see-also"></a>См. также раздел

[Пространство имен платформы](platform-namespace-c-cx.md)
