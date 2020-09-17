---
title: InvokeHelper - структура
ms.date: 10/18/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper
- event/Microsoft::WRL::Details::InvokeHelper::callback_
- event/Microsoft::WRL::Details::InvokeHelper::Invoke
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
helpviewer_keywords:
- Microsoft::WRL::Details::InvokeHelper structure
- Microsoft::WRL::Details::callback_ data member
- Microsoft::WRL::Details::Invoke method
- Microsoft::WRL::Details::InvokeHelper, constructor
ms.assetid: 555ad2bc-4dd6-4e65-a2e2-1242c395f0e5
ms.openlocfilehash: 9cb4e166628a6b5e7671494446d467e73c9f8cc3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371384"
---
# <a name="invokehelper-structure"></a>InvokeHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename TDelegateInterface, typename TCallback, unsigned int argCount>
struct InvokeHelper;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 0> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 1> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 2> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 3> :
    public Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 4> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 5> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 6> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 7> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 8> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;

template<typename TDelegateInterface, typename TCallback>
struct InvokeHelper<TDelegateInterface, TCallback, 9> :
    Microsoft::WRL::RuntimeClass<
        RuntimeClassFlags<Delegate>,
        TDelegateInterface
    >;
```

### <a name="parameters"></a>Параметры

*TDelegateИнтерфейс*<br/>
Тип интерфейса делегата.

*TCallback*<br/>
Тип функции обработчика событий.

*argCount*<br/>
Количество аргументов в `InvokeHelper` специализации.

## <a name="remarks"></a>Примечания

Обеспечивает реализацию метода `Invoke()` на основе указанного числа и типа аргументов.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя     | Описание
-------- | -----------------------------------------------------------------------------
`Traits` | Синоним для класса, определяющий тип каждого аргумента обработчика событий.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                        | Описание
------------------------------------------- | -------------------------------------------------------
[InvokeHelper::InvokeHelper](#invokehelper) | Инициализирует новый экземпляр класса `InvokeHelper`.

### <a name="public-methods"></a>Открытые методы

Имя                            | Описание
------------------------------- | -----------------------------------------------------------------------------------
[InvokeHelper::Invoke](#invoke) | Вызывает обработчик анонса, подпись которого содержит указанное количество аргументов.

### <a name="public-data-members"></a>Открытые члены данных

Имя                                 | Описание
------------------------------------ | ----------------------------------------------------------
[InvokeHelper::callback_](#callback) | Представляет обработчик событий для вызова при возникновении события.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InvokeHelper`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="invokehelpercallback_"></a><a name="callback"></a>InvokeHelper::callback_

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
TCallback callback_;
```

### <a name="remarks"></a>Примечания

Представляет обработчик событий для вызова при возникновении события.

Параметр `TCallback` шаблона определяет тип обработчика событий.

## <a name="invokehelperinvoke"></a><a name="invoke"></a>InvokeHelper::Invoke

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
STDMETHOD(
   Invoke
)();
STDMETHOD(
   Invoke
)(typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
STDMETHOD(
   Invoke
)( typename Traits;
```

### <a name="parameters"></a>Параметры

*arg1*<br/>
Аргумент 1.

*arg2*<br/>
Аргумент 2.

*arg3*<br/>
Аргумент 3.

*arg4*<br/>
Аргумент 4.

*arg5*<br/>
Аргумент 5.

*arg6*<br/>
Аргумент 6.

*arg7*<br/>
Аргумент 7.

*arg8*<br/>
Аргумент 8.

*arg9*<br/>
Аргумент 9.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, HRESULT, который описывает ошибку.

### <a name="remarks"></a>Примечания

Вызывает обработчик анонса, подпись которого содержит указанное количество аргументов.

## <a name="invokehelperinvokehelper"></a><a name="invokehelper"></a>InvokeHelper::InvokeHelper

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>Параметры

*обратный вызов*<br/>
Обработчик событий.

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `InvokeHelper`.

Параметр `TCallback` шаблона определяет тип обработчика событий.
