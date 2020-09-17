---
title: Класс cancellation_token_registration
ms.date: 11/04/2016
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
ms.openlocfilehash: 9342841e207c93b66521c2fc742c1b1114682f78
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142240"
---
# <a name="cancellation_token_registration-class"></a>Класс cancellation_token_registration

Класс `cancellation_token_registration` представляет уведомление обратного вызова из `cancellation_token`. При использовании метода `register` на `cancellation_token` для получения уведомления о времени выполнения отмены объект `cancellation_token_registration` возвращается как дескриптор для обратного вызова, чтобы вызывающий код мог запросить, чтобы определенный обратный вызов больше не выполнялся с помощью метода `deregister`.

## <a name="syntax"></a>Синтаксис

```cpp
class cancellation_token_registration;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[cancellation_token_registration](#ctor)||
|[Деструктор ~ cancellation_token_registration](#dtor)||

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[оператор=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`cancellation_token_registration`

## <a name="requirements"></a>Требования

**Заголовок:** pplcancellation_token.h

**Пространство имен:** concurrency

## <a name="dtor"></a>~ cancellation_token_registration

```cpp
~cancellation_token_registration();
```

## <a name="ctor"></a>cancellation_token_registration

```cpp
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
`cancellation_token_registration` для копирования или перемещения.

## <a name="operator_neq"></a>operator!=

```cpp
bool operator!= (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Объект `cancellation_token_registration` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

## <a name="operator_eq"></a>Оператор =

```cpp
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
`cancellation_token_registration` для назначения.

### <a name="return-value"></a>Возвращаемое значение

## <a name="operator_eq_eq"></a>Оператор = =

```cpp
bool operator== (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Объект `cancellation_token_registration` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
