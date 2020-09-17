---
title: Класс cancellation_token
ms.date: 11/04/2016
f1_keywords:
- cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::cancellation_token
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::deregister_callback
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_cancelable
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::is_canceled
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::none
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token::register_callback
helpviewer_keywords:
- cancellation_token class
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
ms.openlocfilehash: 6f1e204c87a6bc940227416696e3cee233271e64
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213870"
---
# <a name="cancellation_token-class"></a>Класс cancellation_token

Класс `cancellation_token` представляет возможность определить, получала ли некоторая операция запрос на отмену. Заданный токен можно связать с `task_group`, `structured_task_group` или `task` для предоставления неявной отмены. Его также можно опрашивать на предмет отмены или зарегистрировать обратный вызов для той ситуации, когда отменяется связанный `cancellation_token_source`.

## <a name="syntax"></a>Синтаксис

```cpp
class cancellation_token;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[cancellation_token](#ctor)||
|[Деструктор ~ cancellation_token](#dtor)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[deregister_callback](#deregister_callback)|Удаляет обратный вызов, ранее зарегистрированный с помощью метода `register` на основании объекта `cancellation_token_registration`, возвращенного во время регистрации.|
|[is_cancelable](#is_cancelable)|Возвращает значение, указывающее, может ли этот токен быть отменен или нет.|
|[is_canceled](#is_canceled)|Возвращает значение **`true`** , если токен был отменен.|
|[Нет](#none)|Возвращает токен отмены, который никогда не может подвергаться отмене.|
|[register_callback](#register_callback)|Регистрирует функцию обратного вызова в токене. Если и когда токен отменяется, выполняется обратный вызов. Обратите внимание, что если токен уже отменен в той точке, где вызывается этот метод, обратный вызов будет выполнен немедленно и синхронно.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[operator=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`cancellation_token`

## <a name="requirements"></a>Требования

**Заголовок:** pplcancellation_token.h

**Пространство имен:** concurrency

## <a name="cancellation_token"></a><a name="dtor"></a>~ cancellation_token

```cpp
~cancellation_token();
```

## <a name="cancellation_token"></a><a name="ctor"></a>cancellation_token

```cpp
cancellation_token(const cancellation_token& _Src);

cancellation_token(cancellation_token&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Копируемый или перемещаемый cancellation_token.

## <a name="deregister_callback"></a><a name="deregister_callback"></a>deregister_callback

Удаляет обратный вызов, ранее зарегистрированный с помощью метода `register` на основании объекта `cancellation_token_registration`, возвращенного во время регистрации.

```cpp
void deregister_callback(const cancellation_token_registration& _Registration) const;
```

### <a name="parameters"></a>Параметры

*_Registration*<br/>
Объект `cancellation_token_registration`, соответствующий обратному вызову, регистрацию которого требуется отменить. Этот токен должен быть предварительно возвращен из вызова метода `register`.

## <a name="is_cancelable"></a><a name="is_cancelable"></a>is_cancelable

Возвращает значение, указывающее, может ли этот токен быть отменен или нет.

```cpp
bool is_cancelable() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индикация того, может ли этот токен быть отменен.

## <a name="is_canceled"></a><a name="is_canceled"></a>is_canceled

Возвращает значение **`true`** , если токен был отменен.

```cpp
bool is_canceled() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение **`true`** , если токен был отменен; в противном случае — значение **`false`** .

## <a name="none"></a><a name="none"></a>None

Возвращает токен отмены, который никогда не может подвергаться отмене.

```cpp
static cancellation_token none();
```

### <a name="return-value"></a>Возвращаемое значение

Токен отмены, который невозможно отменить.

## <a name="operator"></a><a name="operator_neq"></a>operator!=

```cpp
bool operator!= (const cancellation_token& _Src) const;
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Объект `cancellation_token` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

## <a name="operator"></a><a name="operator_eq"></a>Оператор =

```cpp
cancellation_token& operator= (const cancellation_token& _Src);

cancellation_token& operator= (cancellation_token&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Объект `cancellation_token` для назначения.

### <a name="return-value"></a>Возвращаемое значение

## <a name="operator"></a><a name="operator_eq_eq"></a>Оператор = =

```cpp
bool operator== (const cancellation_token& _Src) const;
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Объект `cancellation_token` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

## <a name="register_callback"></a><a name="register_callback"></a>register_callback

Регистрирует функцию обратного вызова в токене. Если и когда токен отменяется, выполняется обратный вызов. Обратите внимание, что если токен уже отменен в той точке, где вызывается этот метод, обратный вызов будет выполнен немедленно и синхронно.

```cpp
template<typename _Function>
::Concurrency::cancellation_token_registration register_callback(const _Function& _Func) const;
```

### <a name="parameters"></a>Параметры

*_Function*<br/>
Тип объекта функции, вызываемого при отмене этого `cancellation_token`.

*_Func*<br/>
Объект функции, вызываемый при отмене этого `cancellation_token`.

### <a name="return-value"></a>Возвращаемое значение

Объект `cancellation_token_registration`, который можно использовать в методе `deregister` для отмены регистрации ранее зарегистрированного обратного вызова и предотвращения его выполнения. Метод вызовет исключение [invalid_operation](invalid-operation-class.md) , если оно вызывается для `cancellation_token` объекта, созданного с помощью метода [cancellation_token:: None](#none) .

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency](concurrency-namespace.md)
