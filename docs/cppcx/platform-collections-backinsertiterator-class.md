---
title: Класс Platform::Collections::BackInsertIterator
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
ms.openlocfilehash: 56393fd522ecd0e2f161dfa5b9fe8230563c0f65
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223490"
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Класс Platform::Collections::BackInsertIterator

Представляет итератор, который вставляет, а не перезаписывает элементы в конец упорядоченной коллекции.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class BackInsertIterator :
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип элемента в текущей коллекции.

### <a name="remarks"></a>Примечания

Класс BackInsertIterator реализует правила, необходимые для [back_insert_iterator Class](../standard-library/back-insert-iterator-class.md).

### <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[BackInsertIterator:: BackInsertIterator](#ctor)|Инициализирует новый экземпляр класса BackInsertIterator.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор BackInsertIterator::operator*](#operator-dereference)|Получает ссылку на текущий объект BackInsertIterator.|
|[Оператор BackInsertIterator::operator++](#operator-increment)|Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.|
|[Оператор BackInsertIterator::operator=](#operator-assign)|Добавляет указанный объект в конец текущей упорядоченной коллекции.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BackInsertIterator`

### <a name="requirements"></a>Требования

**Заголовок:** collection.h

**Пространство имен:** Platform::Collections

## <a name="backinsertiteratorbackinsertiterator-constructor"></a><a name="ctor"></a>Конструктор BackInsertIterator:: BackInsertIterator

Инициализирует новый экземпляр класса `BackInsertIterator`.

## <a name="syntax"></a>Синтаксис

```
explicit BackInsertIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

#### <a name="parameters"></a>Параметры

*3,3*<br/>
Объект IVector \<T> .

### <a name="remarks"></a>Примечания

`BackInsertIterator` вставляет элементы после последнего элемента объекта, указанного параметром `v`.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-assign"></a>Оператор BackInsertIterator::operator=

Добавляет указанный объект в конец текущей упорядоченной коллекции.

## <a name="syntax"></a>Синтаксис

```
BackInsertIterator& operator=( const T& t);
```

#### <a name="parameters"></a>Параметры

*t*<br/>
Объект, добавляемый к текущей коллекции.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект BackInsertIterator.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-dereference"></a>Оператор BackInsertIterator::operator*

Получает ссылку на текущий объект BackInsertIterator.

## <a name="syntax"></a>Синтаксис

```
BackInsertIterator& operator*();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект BackInsertIterator.

### <a name="remarks"></a>Примечания

Этот оператор возвращает ссылку на текущий BackInsertIterator, а не на любой элемент в текущей коллекции.

## <a name="backinsertiteratoroperator-operator"></a><a name="operator-increment"></a>Оператор BackInsertIterator::operator++

Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.

## <a name="syntax"></a>Синтаксис

```
BackInsertIterator& operator++();

BackInsertIterator operator++(int);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на текущий объект BackInsertIterator.

### <a name="remarks"></a>Примечания

Выражение в первом примере синтаксиса увеличивает значение текущего элемента BackInsertIterator перед его использованием, а во втором — после его использования. **`int`** Тип во втором синтаксисе указывает на операцию после приращения, а не на фактический целочисленный операнд.

Впрочем, этот оператор не изменяет объект BackInsertIterator. Вместо этого он возвращает ссылку на текущий итератор, остающийся неизменным. Это то же поведение, что и [оператор *](#operator-dereference).

## <a name="see-also"></a>См. также статью

[Пространство имен платформы](platform-namespace-c-cx.md)
