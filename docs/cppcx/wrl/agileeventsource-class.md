---
title: Класс Агиливентсаурце
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::AgileEventSource
helpviewer_keywords:
- AgileEventSource class
ms.openlocfilehash: 71a70f783d8f8967d755bb788f4aae4861340d64
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214192"
---
# <a name="agileeventsource-class"></a>Класс Агиливентсаурце

Представляет событие, которое вызывается компонентом Agile, который является компонентом, доступ к которому можно получить из любого потока. Наследует от [EventSource](eventsource-class.md) и переопределяет `Add` функцию члена с дополнительным параметром типа для указания параметров способа вызова гибкого события.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    typename TDelegateInterface,
    typename TEventSourceOptions = Microsoft::WRL::InvokeModeOptions<FireAll>
>
class AgileEventSource :
    public Microsoft::WRL::EventSource<
        TDelegateInterface, TEventSourceOptions>;
```

## <a name="parameters"></a>Параметры

*тделегатеинтерфаце*<br/>
Интерфейс к делегату, который представляет обработчик событий.

*тевентсаурцеоптионс*<br/>
Структура [инвокемодеоптионс](invokemodeoptions-structure.md) , для которой в поле инвокемоде задано значение `InvokeMode::StopOnFirstError` или `InvokeMode::FireAll`.

## <a name="remarks"></a>Примечания

Подавляющее большинство компонентов в среда выполнения Windows являются гибкими компонентами. Дополнительные сведения см. в разделе Работа [с потоками иC++маршалирование (/CX)](../../cppcx/threading-and-marshaling-c-cx.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`EventSource`

`AgileEventSource`

## <a name="requirements"></a>Требования

**Заголовок:** Event.h

**Пространство имен:** Microsoft::WRL

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод Агиливентсаурце:: Add](#add)|Добавляет в набор обработчиков событий для текущего объекта **агиливентсаурце** обработчик событий Agile, представленный указанным интерфейсом делегата.|

## <a name="agileeventsourceadd-method"></a><a name="add"></a>Метод Агиливентсаурце:: Add

Добавляет обработчик событий, представленный указанным интерфейсом делегата, к набору обработчиков событий для текущего объекта [EventSource](eventsource-class.md) .

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT Add(
   _In_ TDelegateInterface* delegateInterface,
   _Out_ EventRegistrationToken* token
);
```

### <a name="parameters"></a>Параметры

*делегатеинтерфаце*<br/>
Интерфейс для объекта делегата, который представляет обработчик событий.

*token*<br/>
После завершения операции представляет дескриптор события. Используйте этот маркер в качестве параметра метода `Remove()` для отмены обработчика событий.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
