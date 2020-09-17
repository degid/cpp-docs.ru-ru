---
title: Класс message_processor
ms.date: 11/04/2016
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
ms.openlocfilehash: 88944b2d935eebd0e031be1431c2a0f4efa3d760
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139471"
---
# <a name="message_processor-class"></a>Класс message_processor

Класс `message_processor` — это абстрактный базовый класс для обработки объектов `message`. Упорядочивание сообщений не гарантируется.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class message_processor;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных полезной нагрузки в сообщениях, обрабатываемых данным объектом `message_processor`.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`type`|Псевдоним типа для `T`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[async_send](#async_send)|При переопределении в производном классе помещает сообщения в блок асинхронно.|
|[sync_send](#sync_send)|При переопределении в производном классе помещает сообщения в блок синхронно.|
|[ожидания](#wait)|При переопределении в производном классе ожидает завершения всех асинхронных операций.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|При переопределении в производном классе выполняет прямую обработку сообщений в блок. Вызывается каждый раз при добавлении нового сообщения, если очередь пуста.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`message_processor`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="async_send"></a>async_send

При переопределении в производном классе помещает сообщения в блок асинхронно.

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Объект `message` для асинхронной отправки.

### <a name="remarks"></a>Примечания

Реализация процессора должна переопределять этот метод.

## <a name="process_incoming_message"></a>process_incoming_message

При переопределении в производном классе выполняет прямую обработку сообщений в блок. Вызывается каждый раз при добавлении нового сообщения, если очередь пуста.

```cpp
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Примечания

Реализации блоков сообщений должны переопределять этот метод.

## <a name="sync_send"></a>sync_send

При переопределении в производном классе помещает сообщения в блок синхронно.

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Параметры

*_Msg*<br/>
Объект `message` для синхронной отправки.

### <a name="remarks"></a>Примечания

Реализация процессора должна переопределять этот метод.

## <a name="wait"></a>ожидания

При переопределении в производном классе ожидает завершения всех асинхронных операций.

```cpp
virtual void wait() = 0;
```

### <a name="remarks"></a>Примечания

Реализация процессора должна переопределять этот метод.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс ordered_message_processor](ordered-message-processor-class.md)
