---
title: Класс EventTargetArray
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
- event/Microsoft::WRL::Details::EventTargetArray::Begin
- event/Microsoft::WRL::Details::EventTargetArray::End
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
- event/Microsoft::WRL::Details::EventTargetArray::Length
- event/Microsoft::WRL::Details::EventTargetArray::~EventTargetArray
helpviewer_keywords:
- Microsoft::WRL::Details::EventTargetArray class
- Microsoft::WRL::Details::EventTargetArray::AddTail method
- Microsoft::WRL::Details::EventTargetArray::Begin method
- Microsoft::WRL::Details::EventTargetArray::End method
- Microsoft::WRL::Details::EventTargetArray::EventTargetArray, constructor
- Microsoft::WRL::Details::EventTargetArray::Length method
- Microsoft::WRL::Details::EventTargetArray::~EventTargetArray, destructor
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
ms.openlocfilehash: 9ea8800aa22a6b5cae0b3342cf337786fb53fc76
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371505"
---
# <a name="eventtargetarray-class"></a>Класс EventTargetArray

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
class EventTargetArray :
    public Microsoft::WRL::RuntimeClass<
        Microsoft::WRL::RuntimeClassFlags<ClassicCom>,
        IUnknown
    >;
```

## <a name="remarks"></a>Примечания

Представляет массив обработчиков событий.

Обработчики событий, связанные с объектом [EventSource,](eventsource-class.md) хранятся в защищенном `EventTargetArray` элементе данных.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                           | Описание
-------------------------------------------------------------- | -----------------------------------------------------------
[EventTargetArray:EventTargetArray](#eventtargetarray)        | Инициализирует новый экземпляр класса `EventTargetArray`.
[EventTargetArray:::EventTargetArray](#tilde-eventtargetarray) | Деприниализирует `EventTargetArray` текущий класс.

### <a name="public-methods"></a>Открытые методы

Имя                                  | Описание
------------------------------------- | ---------------------------------------------------------------------------------------
[EventTargetArray::AddTail](#addtail) | Приспособите указанный обработчик событий к концу внутреннего массива обработчиков событий.
[EventTargetArray:Начало](#begin)     | Получает адрес первого элемента во внутреннем массиве обработчиков событий.
[EventTargetArray::Конец](#end)         | Получает адрес последнего элемента во внутреннем массиве обработчиков событий.
[EventTargetArray::Длина](#length)   | Получает текущее количество элементов во внутреннем массиве обработчиков событий.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EventTargetArray`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="eventtargetarrayeventtargetarray"></a><a name="tilde-eventtargetarray"></a>EventTargetArray:::EventTargetArray

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
~EventTargetArray();
```

### <a name="remarks"></a>Примечания

Деприниализирует `EventTargetArray` текущий класс.

## <a name="eventtargetarrayaddtail"></a><a name="addtail"></a>EventTargetArray::AddTail

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Указатель на обработчик событий для приложения.

### <a name="remarks"></a>Примечания

Приспособите указанный обработчик событий к концу внутреннего массива обработчиков событий.

`AddTail()`предназначен для внутреннего использования только `EventSource` классом.

## <a name="eventtargetarraybegin"></a><a name="begin"></a>EventTargetArray:Начало

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
ComPtr<IUnknown>* Begin();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес первого элемента во внутреннем массиве обработчиков событий.

### <a name="remarks"></a>Примечания

Получает адрес первого элемента во внутреннем массиве обработчиков событий.

## <a name="eventtargetarrayend"></a><a name="end"></a>EventTargetArray::Конец

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
ComPtr<IUnknown>* End();
```

### <a name="return-value"></a>Возвращаемое значение

Адрес последнего элемента во внутреннем массиве обработчиков событий.

### <a name="remarks"></a>Примечания

Получает адрес последнего элемента во внутреннем массиве обработчиков событий.

## <a name="eventtargetarrayeventtargetarray"></a><a name="eventtargetarray"></a>EventTargetArray:EventTargetArray

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
EventTargetArray(
   _Out_ HRESULT* hr,
   size_t items
);
```

### <a name="parameters"></a>Параметры

*Hr*<br/>
После этого *конструктора,* параметр hr указывает, удалось ли выделение массива или не удалось. В следующем списке показаны возможные значения для *hr*.

- S_OK<br/>
  Операция успешно выполнена.

- E_OUTOFMEMORY<br/>
  Память не может быть выделена для массива.

- S_FALSE<br/>
  *Параметры элементов* меньше или равны нулю.

*Элементы*<br/>
Количество элементов массива для выделения.

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `EventTargetArray`.

`EventTargetArray`используется для сохранения массива обработчиков событий в объекте. `EventSource`

## <a name="eventtargetarraylength"></a><a name="length"></a>EventTargetArray::Длина

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
size_t Length();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее количество элементов во внутреннем массиве обработчиков событий.

### <a name="remarks"></a>Примечания

Получает текущее количество элементов во внутреннем массиве обработчиков событий.
