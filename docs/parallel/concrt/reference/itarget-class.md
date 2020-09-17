---
title: Класс ITarget
ms.date: 11/04/2016
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
ms.openlocfilehash: 39aebd9d82f098225c1275ac6f43d64fc1ce3ba8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231719"
---
# <a name="itarget-class"></a>Класс ITarget

Класс `ITarget` является интерфейсом для всех целевых блоков. Целевые блоки потребляют сообщения, предлагаемые ими блоками `ISource`.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class ITarget;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных полезной нагрузки в сообщениях, принимаемых целевым блоком.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`filter_method`|Сигнатура любого метода, используемого блоком, который возвращает **`bool`** значение, чтобы определить, должно ли быть принято предложенное сообщение.|
|`type`|Псевдоним типа для `T` .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Деструктор ~ ITarget](#dtor)|Уничтожает `ITarget` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[распространения](#propagate)|При переопределении в производном классе асинхронно передает сообщение из исходного блока в этот целевой блок.|
|[send](#send)|При переопределении в производном классе синхронно передает сообщение в целевой блок.|
|[supports_anonymous_source](#supports_anonymous_source)|При переопределении в производном классе возвращает значение true или false в зависимости от того, принимает ли блок сообщений сообщения, предоставляемые не связанным с ним источником. Если переопределенный метод возвращает **`true`** , целевой объект не может отложить предлагаемое сообщение, так как в дальнейшем для использования отложенного сообщения в реестре ссылок на него необходимо определить источник.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[link_source](#link_source)|При переопределении в производном классе связывает указанный блок источника с этим `ITarget` блоком.|
|[unlink_source](#unlink_source)|При переопределении в производном классе отменяет связь указанного исходного блока с этим `ITarget` блоком.|
|[unlink_sources](#unlink_sources)|При переопределении в производном классе отменяет связь всех исходных блоков с этим `ITarget` блоком.|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ITarget`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="itarget"></a><a name="dtor"></a>~ ITarget

Уничтожает `ITarget` объект.

```cpp
virtual ~ITarget();
```

## <a name="link_source"></a><a name="link_source"></a>link_source

При переопределении в производном классе связывает указанный блок источника с этим `ITarget` блоком.

```cpp
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Параметры

*_PSource*<br/>
`ISource`Блок, связанный с этим `ITarget` блоком.

### <a name="remarks"></a>Примечания

Эта функция не должна вызываться напрямую в `ITarget` блоке. Блоки должны быть соединены вместе с помощью `link_target` метода для `ISource` блоков, которые будут вызывать `link_source` метод для соответствующего целевого объекта.

## <a name="propagate"></a><a name="propagate"></a>распространения

При переопределении в производном классе асинхронно передает сообщение из исходного блока в этот целевой блок.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если `_PMessage` параметр или имеет значение `_PSource` `NULL` .

## <a name="send"></a><a name="send"></a>Отправить

При переопределении в производном классе синхронно передает сообщение в целевой блок.

```cpp
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Параметры

*_PMessage*<br/>
Указатель на объект `message`.

*_PSource*<br/>
Указатель на исходный блок, предлагающий сообщение.

### <a name="return-value"></a>Возвращаемое значение

[Message_status](concurrency-namespace-enums.md) указывает, что цель решила делать с сообщением.

### <a name="remarks"></a>Примечания

Метод вызывает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) , если `_PMessage` параметр или имеет значение `_PSource` `NULL` .

Использование `send` метода за пределами инициации сообщений и распространения сообщений в сети опасно и может привести к взаимоблокировке.

Когда `send` метод возвращает значение, сообщение уже было принято и передано в целевой блок или было отклонено целевым объектом.

## <a name="supports_anonymous_source"></a><a name="supports_anonymous_source"></a>supports_anonymous_source

При переопределении в производном классе возвращает значение true или false в зависимости от того, принимает ли блок сообщений сообщения, предоставляемые не связанным с ним источником. Если переопределенный метод возвращает **`true`** , целевой объект не может отложить предлагаемое сообщение, так как в дальнейшем для использования отложенного сообщения в реестре ссылок саурсе необходимо определить источник.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если блок может принимать сообщение из источника, который не связан с ним **`false`** .

## <a name="unlink_source"></a><a name="unlink_source"></a>unlink_source

При переопределении в производном классе отменяет связь указанного исходного блока с этим `ITarget` блоком.

```cpp
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Параметры

*_PSource*<br/>
`ISource`Несвязанный с этим `ITarget` блоком блок.

### <a name="remarks"></a>Примечания

Эта функция не должна вызываться напрямую в `ITarget` блоке. Блоки должны быть отключены с `unlink_target` помощью `unlink_targets` методов или для `ISource` блоков, которые будут вызывать `unlink_source` метод для соответствующего целевого объекта.

## <a name="unlink_sources"></a><a name="unlink_sources"></a>unlink_sources

При переопределении в производном классе отменяет связь всех исходных блоков с этим `ITarget` блоком.

```cpp
virtual void unlink_sources() = 0;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс ISource](isource-class.md)
