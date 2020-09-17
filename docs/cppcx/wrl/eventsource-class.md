---
title: EventSource - класс
ms.date: 09/12/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
- event/Microsoft::WRL::EventSource::Add
- event/Microsoft::WRL::EventSource::addRemoveLock_
- event/Microsoft::WRL::EventSource::EventSource
- event/Microsoft::WRL::EventSource::GetSize
- event/Microsoft::WRL::EventSource::InvokeAll
- event/Microsoft::WRL::EventSource::Remove
- event/Microsoft::WRL::EventSource::targets_
- event/Microsoft::WRL::EventSource::targetsPointerLock_
helpviewer_keywords:
- Microsoft::WRL::EventSource class
- Microsoft::WRL::EventSource::Add method
- Microsoft::WRL::EventSource::addRemoveLock_ data member
- Microsoft::WRL::EventSource::EventSource, constructor
- Microsoft::WRL::EventSource::GetSize method
- Microsoft::WRL::EventSource::InvokeAll method
- Microsoft::WRL::EventSource::Remove method
- Microsoft::WRL::EventSource::targets_ data member
- Microsoft::WRL::EventSource::targetsPointerLock_ data member
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
ms.openlocfilehash: bb9151e55d133e3e5d8bf10baeb8448101ad6ce0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371542"
---
# <a name="eventsource-class"></a>EventSource - класс

Представляет негибкое событие. Функции-члены `EventSource` добавляют, удаляют и вызывают обработчики событий. Для гибких событий используйте [AgileEventSource.](agileeventsource-class.md)

## <a name="syntax"></a>Синтаксис

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>Параметры

*TDelegateИнтерфейс*<br/>
Интерфейс для делегата, представляющий обработчик событий.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

| Имя                                     | Описание                                            |
| ---------------------------------------- | ------------------------------------------------------ |
| [СобытиеИсточник::EventИсточник](#eventsource) | Инициализирует новый экземпляр класса `EventSource`. |

### <a name="public-methods"></a>Открытые методы

| Имя                                 | Описание                                                                                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [EventSource:Add](#add)             | Придатит обработчик событий, представленный указанным интерфейсом делегата, к набору обработчиков событий для текущего `EventSource` объекта.                     |
| [СобытиеИсточник::GetSize](#getsize)     | Извлекает количество обработчиков событий, `EventSource` связанных с текущим объектом.                                                                         |
| [СобытиеИсточник::InvokeAll](#invokeall) | Вызовы каждого обработчика событий, связанного с текущим `EventSource` объектом, с помощью указанных типов аргументов и аргументов.                                      |
| [EventИсточник::Удалить](#remove)       | Удаляет обработчик событий, представленный определенным маркером регистрации событий, из `EventSource` набора обработчиков событий, связанных с текущим объектом. |

### <a name="protected-data-members"></a>Защищенные члены данных

| Имя                                                    | Описание                                                                                                                       |
| ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| [СобытиеИсточник::addRemoveLock_](#addremovelock)           | Синхронизирует доступ к [targets_](#targets) массиву при добавлении, удалении или вызываении обработчиков событий.                          |
| [СобытиеИсточник::targets_](#targets)                       | Массив одного или нескольких обработчиков событий.                                                                                           |
| [СобытиеИсточник::targetsPointerLock_](#targetspointerlock) | Синхронизирует доступ к внутренним членам данных даже при добавлении, удалении или вызове обработчиков событий для этого EventSource. |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EventSource`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL

## <a name="eventsourceadd"></a><a name="add"></a>EventSource:Add

Придатит обработчик событий, представленный указанным интерфейсом делегата, к набору обработчиков событий для текущего `EventSource` объекта.

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Параметры

*делегатИнтерфейс*<br/>
Интерфейс для объекта делегата, который представляет обработчик событий.

*Маркер*<br/>
После завершения операции представляет дескриптор события. Используйте этот маркер в качестве параметра для метода [Удаления()](#remove) для удаления обработчика событий.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="eventsourceaddremovelock_"></a><a name="addremovelock"></a>СобытиеИсточник::addRemoveLock_

Синхронизирует доступ к [targets_](#targets) массиву при добавлении, удалении или вызываении обработчиков событий.

```cpp
Wrappers::SRWLock addRemoveLock_;
```

## <a name="eventsourceeventsource"></a><a name="eventsource"></a>СобытиеИсточник::EventИсточник

Инициализирует новый экземпляр класса `EventSource`.

```cpp
EventSource();
```

## <a name="eventsourcegetsize"></a><a name="getsize"></a>СобытиеИсточник::GetSize

Извлекает количество обработчиков событий, `EventSource` связанных с текущим объектом.

```cpp
size_t GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество обработчиков событий в [targets_](#targets).

## <a name="eventsourceinvokeall"></a><a name="invokeall"></a>СобытиеИсточник::InvokeAll

Вызовы каждого обработчика событий, связанного с текущим `EventSource` объектом, с помощью указанных типов аргументов и аргументов.

```cpp
void InvokeAll();
template <
   typename T0
>
void InvokeAll(
   T0arg0
);
template <
   typename T0,
   typename T1
>
void InvokeAll(
   T0arg0,
   T1arg1
);
template <
   typename T0,
   typename T1,
   typename T2
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8
);
template <
   typename T0,
   typename T1,
   typename T2,
   typename T3,
   typename T4,
   typename T5,
   typename T6,
   typename T7,
   typename T8,
   typename T9
>
void InvokeAll(
   T0arg0,
   T1arg1,
   T2arg2,
   T3arg3,
   T4arg4,
   T5arg5,
   T6arg6,
   T7arg7,
   T8arg8,
   T9arg9
);
```

### <a name="parameters"></a>Параметры

*T0*<br/>
Тип нулевого аргумента обработчика событий.

*T1*<br/>
Тип первого аргумента обработчика событий.

*T2*<br/>
Тип второго аргумента обработчика событий.

*T3*<br/>
Тип третьего аргумента обработчика событий.

*T4*<br/>
Тип четвертого аргумента обработчика событий.

*T5*<br/>
Тип пятого аргумента обработчика событий.

*T6*<br/>
Тип шестого аргумента обработчика событий.

*T7*<br/>
Тип седьмого аргумента обработчика событий.

*T8*<br/>
Тип восьмого аргумента обработчика событий.

*T9*<br/>
Тип девятого аргумента обработчика событий.

*arg0*<br/>
Нулевой аргумент обработчика событий.

*arg1*<br/>
Первый аргумент обработчика событий.

*arg2*<br/>
Второй аргумент обработчика событий.

*arg3*<br/>
Третий аргумент обработчика событий.

*arg4*<br/>
Четвертый аргумент обработчика событий.

*arg5*<br/>
Пятый аргумент обработчика событий.

*arg6*<br/>
Шестой аргумент обработчика событий.

*arg7*<br/>
Седьмой аргумент обработчика событий.

*arg8*<br/>
Восьмой аргумент обработчик события.

*arg9*<br/>
Девятый аргумент обработчика событий.

## <a name="eventsourceremove"></a><a name="remove"></a>EventИсточник::Удалить

Удаляет обработчик событий, представленный определенным маркером регистрации событий, из `EventSource` набора обработчиков событий, связанных с текущим объектом.

```cpp
HRESULT Remove(
   EventRegistrationToken token
);
```

### <a name="parameters"></a>Параметры

*Маркер*<br/>
Ручка, представляющая обработчик событий. Этот маркер был возвращен, когда обработчик событий был зарегистрирован методом [Add()](#add)

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Для получения дополнительной `EventRegistrationToken` информации о структуре, см. **Windows::Основа::EventRegistrationToken Структура** тема в **Windows Runtime** справочной документации.

## <a name="eventsourcetargets_"></a><a name="targets"></a>СобытиеИсточник::targets_

Массив одного или нескольких обработчиков событий.

```cpp
ComPtr<Details::EventTargetArray> targets_;
```

### <a name="remarks"></a>Примечания

При возникновении события, представленного `EventSource` текущим объектом, вызовуются обработчики событий.

## <a name="eventsourcetargetspointerlock_"></a><a name="targetspointerlock"></a>СобытиеИсточник::targetsPointerLock_

Синхронизирует доступ к внутренним членам данных даже при `EventSource` добавлении, удалении или вызове обработчиков событий.

```cpp
Wrappers::SRWLock targetsPointerLock_;
```
