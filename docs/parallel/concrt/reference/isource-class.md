---
title: Класс ISource
ms.date: 11/04/2016
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
ms.openlocfilehash: df592e965b436ed5a1d60702f9e57088887d5a94
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222710"
---
# <a name="isource-class"></a>Класс ISource

Класс `ISource` является интерфейсом для всех блоков источников. Блоки источников распространяют сообщения в блоки `ITarget`.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class ISource;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных полезной нагрузки в сообщениях, создаваемых исходным блоком.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`source_type`|Псевдоним типа для `T` .|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Деструктор "~ ISource"](#dtor)|Уничтожает `ISource` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[гласит](#accept)|При переопределении в производном классе принимает сообщение, которое было предложено этим `ISource` блоком, передавая владение вызывающему объекту.|
|[acquire_ref](#acquire_ref)|При переопределении в производном классе получает счетчик ссылок `ISource` для этого блока, чтобы предотвратить удаление.|
|[потребляющие](#consume)|При переопределении в производном классе использует сообщение, которое было ранее предложено этим `ISource` блоком и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.|
|[link_target](#link_target)|При переопределении в производном классе связывает целевой блок с этим `ISource` блоком.|
|[отпускании](#release)|При переопределении в производном классе освобождает предыдущее успешное резервирование сообщения.|
|[release_ref](#release_ref)|При переопределении в производном классе освобождает счетчик ссылок на этот `ISource` блок.|
|[reserve](#reserve)|При переопределении в производном классе резервирует сообщение, которое было ранее предложено этим `ISource` блоком.|
|[unlink_target](#unlink_target)|При переопределении в производном классе отменяет связь целевого блока с этим `ISource` блоком, если он ранее был связан.|
|[unlink_targets](#unlink_targets)|При переопределении в производном классе отменяет связь всех целевых блоков с этим `ISource` блоком.|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISource`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="accept"></a><a name="accept"></a>гласит

При переопределении в производном классе принимает сообщение, которое было предложено этим `ISource` блоком, передавая владение вызывающему объекту.

```cpp
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `accept` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на сообщение о том, что вызывающий объект теперь является владельцем.

### <a name="remarks"></a>Примечания

`accept`Метод вызывается целевым объектом, в то время как сообщение предлагается этим `ISource` блоком. Возвращаемый указатель на сообщение может отличаться от переданного в `propagate` метод `ITarget` блока, если этот источник решит создать копию сообщения.

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

При переопределении в производном классе получает счетчик ссылок `ISource` для этого блока, чтобы предотвратить удаление.

```cpp
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объектом, который связан с этим источником во время выполнения `link_target` метода.

## <a name="consume"></a><a name="consume"></a>потребляющие

При переопределении в производном классе использует сообщение, которое было ранее предложено этим `ISource` блоком и успешно зарезервировано целевым объектом, передавая владение вызывающему объекту.

```cpp
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект зарезервированного `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `consume` метод.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `message` объект, владельцем которого стал вызывающий объект.

### <a name="remarks"></a>Примечания

`consume`Метод аналогичен `accept` , но ему всегда должен предшествовать вызов `reserve` , который возвращает **`true`** .

## <a name="isource"></a><a name="dtor"></a>~ ISource

Уничтожает `ISource` объект.

```cpp
virtual ~ISource();
```

## <a name="link_target"></a><a name="link_target"></a>link_target

При переопределении в производном классе связывает целевой блок с этим `ISource` блоком.

```cpp
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, связываемый с этим `ISource` блоком.

## <a name="release"></a><a name="release"></a>отпускании

При переопределении в производном классе освобождает предыдущее успешное резервирование сообщения.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект зарезервированного `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `release` метод.

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

При переопределении в производном классе освобождает счетчик ссылок на этот `ISource` блок.

```cpp
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, вызывающий этот метод.

### <a name="remarks"></a>Примечания

Этот метод вызывается `ITarget` объектом, для которого удаляется связь из этого источника. Блоку источника разрешено освобождать все ресурсы, зарезервированные для целевого блока.

## <a name="reserve"></a><a name="reserve"></a>предназначен

При переопределении в производном классе резервирует сообщение, которое было ранее предложено этим `ISource` блоком.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_MsgId*<br/>
`runtime_object_identity`Объект предлагаемого `message` объекта.

*_PTarget*<br/>
Указатель на целевой блок, вызывающий `reserve` метод.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если сообщение было успешно зарезервировано, **`false`** в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.

### <a name="remarks"></a>Примечания

После вызова метода `reserve` , если он выполняется, необходимо вызвать метод `consume` или `release` , чтобы получить или предоставить владение сообщениями соответственно.

## <a name="unlink_target"></a><a name="unlink_target"></a>unlink_target

При переопределении в производном классе отменяет связь целевого блока с этим `ISource` блоком, если он ранее был связан.

```cpp
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>Параметры

*_PTarget*<br/>
Указатель на целевой блок, связь с которым выполняется из этого `ISource` блока.

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

При переопределении в производном классе отменяет связь всех целевых блоков с этим `ISource` блоком.

```cpp
virtual void unlink_targets() = 0;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)<br/>
[Класс ITarget](itarget-class.md)
