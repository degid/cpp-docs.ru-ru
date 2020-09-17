---
title: SimpleActivationFactory - класс
ms.date: 09/07/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
ms.openlocfilehash: 39e539c63e91b508f51656114ee8fbd68150991f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370936"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory - класс

Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>Параметры

*Базы*<br/>
Базовый класс.

## <a name="remarks"></a>Примечания

Базовый класс должен предоставить конструктор по умолчанию.

Следующий пример кода демонстрирует, как использовать SimpleActivationFactory с помощью макроса [ActivatableWithFactoryEx.](activatableclass-macros.md)

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод SimpleActivationFactory::ActivateInstance](#activateinstance)|Создает экземпляр указанного интерфейса.|
|[Метод SimpleActivationFactory::GetRuntimeClassName](#getruntimeclassname)|Получается название класса времени выполнения экземпляра класса, указанного параметром *шаблона* базового класса.|
|[Метод SimpleActivationFactory::GetTrustLevel](#gettrustlevel)|Получает уровень доверия экземпляра класса, указанный параметром *шаблона* базового класса.|

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

`SimpleActivationFactory`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::WRL

## <a name="simpleactivationfactoryactivateinstance-method"></a><a name="activateinstance"></a>ПростаяактивацияФабрика::Метод активацииInstance

Создает экземпляр указанного интерфейса.

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>Параметры

*ppvObject*<br/>
Когда эта операция завершается, указатель на экземпляр `Base` объекта, указанный параметром шаблона класса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Если `__WRL_STRICT__` определено, ошибка утверждения испускается, если базовый класс, указанный в параметре шаблона класса, не получен из [RuntimeClass](runtimeclass-class.md)или не настроен со значением перечисления WinRt или WinRtClassicComMix [RuntimeClassTypeType.](runtimeclasstype-enumeration.md)

## <a name="simpleactivationfactorygetruntimeclassname-method"></a><a name="getruntimeclassname"></a>SimpleActivationFactory::GetRuntimeClassName Метод

Получает имя класса среды выполнения экземпляра класса, указанного в параметре шаблона класса `Base`.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>Параметры

*время выполненияИмя*<br/>
После завершения операции представляет имя класса среды выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Если `__WRL_STRICT__` определено, ошибка утверждения испускается, если `Base` класс, указанный параметром шаблона класса, не получен из [RuntimeClass](runtimeclass-class.md)или не настроен со значением winRt или WinRtClassicComMix [RuntimeClassTypeType.](runtimeclasstype-enumeration.md)

## <a name="simpleactivationfactorygettrustlevel-method"></a><a name="gettrustlevel"></a>ПростаяактивацияФабрика::GetTrustLevel Метод

Получает уровень доверия экземпляра класса, `Base` указанный параметром шаблона класса.

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>Параметры

*trustLvl*<br/>
Когда эта операция завершается, уровень доверия объекта текущего класса.

### <a name="return-value"></a>Возвращаемое значение

Всегда S_OK.
