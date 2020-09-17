---
title: ActivationFactory - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::AddRef
- module/Microsoft::WRL::ActivationFactory::GetIids
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
- module/Microsoft::WRL::ActivationFactory::QueryInterface
- module/Microsoft::WRL::ActivationFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ActivationFactory class
- Microsoft::WRL::ActivationFactory::ActivationFactory, constructor
- Microsoft::WRL::ActivationFactory::AddRef method
- Microsoft::WRL::ActivationFactory::GetIids method
- Microsoft::WRL::ActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::ActivationFactory::GetTrustLevel method
- Microsoft::WRL::ActivationFactory::QueryInterface method
- Microsoft::WRL::ActivationFactory::Release method
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
ms.openlocfilehash: 0655caeb3f49a18e9c57c78f0008901aaaedda4a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368708"
---
# <a name="activationfactory-class"></a>ActivationFactory - класс

Позволяет одному или нескольким классам быть активированными средой выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ActivationFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IActivationFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<WinRt | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Интерфейс нулевой.

*I1*<br/>
Первый интерфейс.

*I2*<br/>
Второй интерфейс.

## <a name="remarks"></a>Примечания

`ActivationFactory`обеспечивает методы регистрации и `IActivationFactory` основные функциональные возможности для интерфейса. `ActivationFactory`также позволяет обеспечить пользовательскую реализацию завода.

Следующий фрагмент кода символически иллюстрирует, как использовать ActivationFactory.

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

Следующий фрагмент кода показывает, как использовать структуру [реализации](implements-structure.md) для указания более трех идонов интерфейса.

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                       | Описание
---------------------------------------------------------- | ------------------------------------------
[АктивацияFactory::АктивацияFactory](#activationfactory) | Инициализирует класс `ActivationFactory`.

### <a name="public-methods"></a>Открытые методы

Имя                                                           | Описание
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[АктивацияFactory::AddRef](#addref)                           | Приращения эталонного количества `ActivationFactory` текущего объекта.
[АктивацияFactory::GetIids](#getiids)                         | Извлекает массив идентификаторов реализованного интерфейса.
[АктивацияFactory::GetRuntimeClassName](#getruntimeclassname) | Получает название класса времени выполнения объекта, `ActivationFactory` которое происходит в текущем моменте.
[АктивацияFactory::GetTrustLevel](#gettrustlevel)             | Получает уровень доверия объекта, `ActivationFactory` который моментирует текущий.
[АктивацияFactory::Квиинтерфейс](#queryinterface)           | Извлекает указатель на указанный интерфейс.
[АктивацияFactory::Release](#release)                         | Декретирует количество ссылок `ActivationFactory` текущего объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="activationfactoryactivationfactory"></a><a name="activationfactory"></a>АктивацияFactory::АктивацияFactory

Инициализирует класс `ActivationFactory`.

```cpp
ActivationFactory();
```

## <a name="activationfactoryaddref"></a><a name="addref"></a>АктивацияFactory::AddRef

Приращения эталонного количества `ActivationFactory` текущего объекта.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="activationfactorygetiids"></a><a name="getiids"></a>АктивацияFactory::GetIids

Извлекает массив идентификаторов реализованного интерфейса.

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Параметры

*iidCount*<br/>
Когда эта операция завершается, количество идентификаторов взаимосвязей в массиве *iids.*

*iids*<br/>
После завершения операции представляет массив идентификаторов реализованного интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. E_OUTOFMEMORY является возможной ошибкой HRESULT.

## <a name="activationfactorygetruntimeclassname"></a><a name="getruntimeclassname"></a>АктивацияFactory::GetRuntimeClassName

Получает название класса времени выполнения объекта, `ActivationFactory` которое происходит в текущем моменте.

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>Параметры

*время выполненияИмя*<br/>
Когда эта операция завершается, ручка строки, содержащей имя класса `ActivationFactory` времени выполнения объекта, который моментирует текущий.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="activationfactorygettrustlevel"></a><a name="gettrustlevel"></a>АктивацияFactory::GetTrustLevel

Получает уровень доверия объекта, `ActivationFactory` который моментирует текущий.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>Параметры

*trustLvl*<br/>
Когда эта операция завершается, уровень доверия класса `ActivationFactory` времени выполнения, который мгновенно.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, ошибка утверждения излучается `FullTrust`и *trustLvl* установлен на .

## <a name="activationfactoryqueryinterface"></a><a name="queryinterface"></a>АктивацияFactory::Квиинтерфейс

Извлекает указатель на указанный интерфейс.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ppvObject*<br/>
Когда эта операция завершена, указатель на интерфейс, указанный *паралимбером riid.*

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="activationfactoryrelease"></a><a name="release"></a>АктивацияFactory::Release

Декретирует количество ссылок `ActivationFactory` текущего объекта.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.
