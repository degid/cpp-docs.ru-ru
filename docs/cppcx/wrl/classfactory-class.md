---
title: ClassFactory - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
- module/Microsoft::WRL::ClassFactory::AddRef
- module/Microsoft::WRL::ClassFactory::ClassFactory
- module/Microsoft::WRL::ClassFactory::LockServer
- module/Microsoft::WRL::ClassFactory::QueryInterface
- module/Microsoft::WRL::ClassFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ClassFactory class
- Microsoft::WRL::ClassFactory::AddRef method
- Microsoft::WRL::ClassFactory::ClassFactory, constructor
- Microsoft::WRL::ClassFactory::LockServer method
- Microsoft::WRL::ClassFactory::QueryInterface method
- Microsoft::WRL::ClassFactory::Release method
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
ms.openlocfilehash: bbf20e2269e6d62206e06e748174d7b88898cd68
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87198103"
---
# <a name="classfactory-class"></a>ClassFactory - класс

Реализует базовую функциональность интерфейса `IClassFactory`.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ClassFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IClassFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<ClassicCom | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Интерфейс начальном.

*I1*<br/>
Первый интерфейс.

*I2*<br/>
Второй интерфейс.

## <a name="remarks"></a>Примечания

Используется `ClassFactory` для предоставления определяемой пользователем фабрики.

В следующем шаблоне программирования показано, как использовать структуру [Implements](implements-structure.md) , чтобы указать более трех интерфейсов в фабрике класса.

`struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                        | Описание
------------------------------------------- | -----------
[ClassFactory:: ClassFactory](#classfactory) |

### <a name="public-methods"></a>Открытые методы

name                                            | Описание
----------------------------------------------- | ----------------------------------------------------------------------------------------------------------------
[ClassFactory:: AddRef](#addref)                 | Увеличивает значение счетчика ссылок для текущего `ClassFactory` объекта.
[ClassFactory:: Локксервер](#lockserver)         | Увеличивает или уменьшает количество базовых объектов, которые отправляются текущим `ClassFactory` объектом.
[ClassFactory:: QueryInterface](#queryinterface) | Извлекает указатель на интерфейс, указанный параметром.
[ClassFactory:: Release](#release)               | Уменьшает значение счетчика ссылок для текущего `ClassFactory` объекта.

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

`ClassFactory`

## <a name="requirements"></a>Требования

**Заголовок:** Module.h

**Пространство имен:** Microsoft::WRL

## <a name="classfactoryaddref"></a><a name="addref"></a>ClassFactory:: AddRef

Увеличивает значение счетчика ссылок для текущего `ClassFactory` объекта.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="classfactoryclassfactory"></a><a name="classfactory"></a>ClassFactory:: ClassFactory

```cpp
WRL_NOTHROW ClassFactory();
```

## <a name="classfactorylockserver"></a><a name="lockserver"></a>ClassFactory:: Локксервер

Увеличивает или уменьшает количество базовых объектов, которые отправляются текущим `ClassFactory` объектом.

```cpp
STDMETHOD(
   LockServer
)(BOOL fLock);
```

### <a name="parameters"></a>Параметры

*флокк*<br/>
**`true`** значение для увеличения количества объектов, на которые отсчитывается объект. **`false`** для уменьшения числа объектов, на которые отписываются объекты.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение E_FAIL.

### <a name="remarks"></a>Примечания

`ClassFactory`отслеживает объекты в базовом экземпляре класса [module](module-class.md) .

## <a name="classfactoryqueryinterface"></a><a name="queryinterface"></a>ClassFactory:: QueryInterface

Извлекает указатель на интерфейс, указанный параметром.

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ппвобжект*<br/>
По завершении этой операции указатель на интерфейс, указанный параметром *riid*.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.

## <a name="classfactoryrelease"></a><a name="release"></a>ClassFactory:: Release

Уменьшает значение счетчика ссылок для текущего `ClassFactory` объекта.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.
