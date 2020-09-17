---
title: Класс cancellation_token_source
ms.date: 11/04/2016
f1_keywords:
- cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancel
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::create_linked_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::get_token
helpviewer_keywords:
- cancellation_token_source class
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
ms.openlocfilehash: 131c4155ad902221d14f90f750f89c31479e2067
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142234"
---
# <a name="cancellation_token_source-class"></a>Класс cancellation_token_source

Класс `cancellation_token_source` представляет возможность отмены некоторой отменяемой операции.

## <a name="syntax"></a>Синтаксис

```cpp
class cancellation_token_source;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[cancellation_token_source](#ctor)|Перегружен. Конструирует новый объект `cancellation_token_source`. Источник можно использовать, чтобы сигнализировать об отмене некоторой отменяемой операции.|
|[Деструктор ~ cancellation_token_source](#dtor)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[cancel](#cancel)|Отменяет токен. Любой элемент `task_group`, `structured_task_group` или `task`, который использует этот токен, будет отменен при этом вызове и создаст исключение в следующей точке прерывания.|
|[create_linked_source](#create_linked_source)|Перегружен. Создает `cancellation_token_source`, который отменяется при отмене предоставленного токена.|
|[get_token](#get_token)|Возвращает токен отмены, связанный с данным источником. Возвращенный токен можно опрашивать на предмет отмены или предоставить обратный вызов, если и когда произойдет отмена.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[оператор=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`cancellation_token_source`

## <a name="requirements"></a>Требования

**Заголовок:** pplcancellation_token.h

**Пространство имен:** concurrency

## <a name="dtor"></a>~ cancellation_token_source

```cpp
~cancellation_token_source();
```

## <a name="cancel"></a>Отмена

Отменяет токен. Любой элемент `task_group`, `structured_task_group` или `task`, который использует этот токен, будет отменен при этом вызове и создаст исключение в следующей точке прерывания.

```cpp
void cancel() const;
```

## <a name="ctor"></a>cancellation_token_source

Конструирует новый объект `cancellation_token_source`. Источник можно использовать, чтобы сигнализировать об отмене некоторой отменяемой операции.

```cpp
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Объект для копирования или перемещения.

## <a name="create_linked_source"></a>create_linked_source

Создает `cancellation_token_source`, который отменяется при отмене предоставленного токена.

```cpp
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```

### <a name="parameters"></a>Параметры

*_Iter*<br/>
Тип итератора.

*_Src*<br/>
Токен, отмена которого приведет к отмене возвращаемого источника токена. Обратите внимание, что возвращаемый источник токена также можно отменить независимо от источника, содержащегося в этом параметре.

*_Begin*<br/>
Итератор C++ стандартной библиотеки, соответствующий началу диапазона токенов для прослушивания отмены.

*_End*<br/>
Итератор C++ стандартной библиотеки, соответствующий концу диапазона токенов для прослушивания отмены.

### <a name="return-value"></a>Возвращаемое значение

`cancellation_token_source`, который отменяется при отмене токена, предоставляемого параметром `_Src`.

## <a name="get_token"></a>get_token

Возвращает токен отмены, связанный с данным источником. Возвращенный токен можно опрашивать на предмет отмены или предоставить обратный вызов, если и когда произойдет отмена.

```cpp
cancellation_token get_token() const;
```

### <a name="return-value"></a>Возвращаемое значение

Токен отмены, связанный с этим источником.

## <a name="operator_neq"></a>operator!=

```cpp
bool operator!= (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Операнд.

### <a name="return-value"></a>Возвращаемое значение

## <a name="operator_eq"></a>Оператор =

```cpp
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Операнд.

### <a name="return-value"></a>Возвращаемое значение

## <a name="operator_eq_eq"></a>Оператор = =

```cpp
bool operator== (const cancellation_token_source& _Src) const;
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
Операнд.

### <a name="return-value"></a>Возвращаемое значение

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
