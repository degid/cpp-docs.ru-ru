---
title: Класс RuntimeClass
ms.date: 09/11/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::AddRef
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
- implements/Microsoft::WRL::RuntimeClass::GetIids
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
- implements/Microsoft::WRL::RuntimeClass::QueryInterface
- implements/Microsoft::WRL::RuntimeClass::Release
- implements/Microsoft::WRL::RuntimeClass::RuntimeClass
- implements/Microsoft::WRL::RuntimeClass::~RuntimeClass
helpviewer_keywords:
- Microsoft::WRL::RuntimeClass class
- Microsoft::WRL::RuntimeClass::AddRef method
- Microsoft::WRL::RuntimeClass::DecrementReference method
- Microsoft::WRL::RuntimeClass::GetIids method
- Microsoft::WRL::RuntimeClass::GetRuntimeClassName method
- Microsoft::WRL::RuntimeClass::GetTrustLevel method
- Microsoft::WRL::RuntimeClass::GetWeakReference method
- Microsoft::WRL::RuntimeClass::InternalAddRef method
- Microsoft::WRL::RuntimeClass::QueryInterface method
- Microsoft::WRL::RuntimeClass::Release method
- Microsoft::WRL::RuntimeClass::RuntimeClass, constructor
- Microsoft::WRL::RuntimeClass::~RuntimeClass, destructor
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
ms.openlocfilehash: 64b4124ba3c60fdcb53fc29c7b791c0f73a49579
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376236"
---
# <a name="runtimeclass-class"></a>Класс RuntimeClass

Представляет класс WinRT или COM, который наследует указанные интерфейсы и предоставляет указанное время выполнения Windows, классическую COM и слабую справочную поддержку.

Этот класс обеспечивает шаблонную реализацию классов WinRT и `QueryInterface`COM, обеспечивая реализацию `AddRef`и `Release` т.д., управляет эталонным подсчетом модуля и имеет поддержку для обеспечения фабрики класса для активируемых объектов.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename ...TInterfaces> class RuntimeClass
template <unsigned int classFlags, typename ...TInterfaces> class RuntimeClass;
```

### <a name="parameters"></a>Параметры

*классФлаги*<br/>
Необязательный параметр. Комбинация одного или нескольких значений перечисления [RuntimeClassType.](runtimeclasstype-enumeration.md) Макрос `__WRL_CONFIGURATION_LEGACY__` можно определить для изменения значения класса ClassFlags по умолчанию для всех классов выполнения проекта. Если это определено, экземпляры RuntimeClass по умолчанию не проворны. Если не определено, экземпляры RuntimeClass проворны по умолчанию. Чтобы избежать двусмысленности всегда `Microsoft::WRL::FtmBase` `TInterfaces` укажите в или `RuntimeClassType::InhibitFtmBase`. Обратите внимание, что если используются InhibitFtmBase и FtmBase, объект будет гибким.

*TИнтерфейсы*<br/>
Список интерфейсов, которые объект `IUnknown` `IInspectable` реализует за пределами, или других интерфейсов, контролируемых [RuntimeClassType.](runtimeclasstype-enumeration.md) Он также может перечислить другие классы, которые будут выведены из, в частности, `Microsoft::WRL::FtmBase` чтобы сделать объект гибким и заставить его реализовать. `IMarshal`

## <a name="members"></a>Участники

`RuntimeClassInitialize`<br/>
Функция, которая инициализирует `MakeAndInitialize` объект, если функция шаблона используется для построения объекта. Он возвращает S_OK если объект был успешно инициализирован, или код ошибки COM, если не удалось инициализации. Код ошибки COM распространяется как значение `MakeAndInitialize`возврата. Обратите внимание, что `RuntimeClassInitialize` метод `Make` не вызывается, если функция шаблона используется для построения объекта.

### <a name="public-constructors"></a>Открытые конструкторы

| Имя                                               | Описание                                                     |
| -------------------------------------------------- | --------------------------------------------------------------- |
| [RuntimeClass::RuntimeClass](#runtimeclass)        | Инициализирует текущий экземпляр `RuntimeClass` класса.   |
| [RuntimeClass:::'RuntimeClass](#tilde-runtimeclass) | Деприиратизирует текущий `RuntimeClass` экземпляр класса. |

### <a name="public-methods"></a>Открытые методы

| Имя                                                      | Описание                                                                                        |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| [RuntimeClass::AddRef](#addref)                           | Приращения отсчета ссылок на текущий `RuntimeClass` объект.                              |
| [RuntimeClass::DecrementСправка](#decrementreference)   | Декретирует значение отсчета `RuntimeClass` ссылок для текущего объекта.                              |
| [RuntimeClass::GetIids](#getiids)                         | Получает массив, который может содержать иные иксы интерфейса, реализованные текущим `RuntimeClass` объектом. |
| [RuntimeClass::GetRuntimeClassName](#getruntimeclassname) | Получает имя класса времени выполнения `RuntimeClass` текущего объекта.                                  |
| [RuntimeClass::GetTrustLevel](#gettrustlevel)             | Получает уровень доверия `RuntimeClass` к текущему объекту.                                         |
| [RuntimeClass::GetWeakСправка](#getweakreference)       | Получает указатель на слабый эталонный `RuntimeClass` объект для текущего объекта.                 |
| [RuntimeClass::InternalAddRef](#internaladdref)           | Приращения отсчета ссылок на текущий `RuntimeClass` объект.                               |
| [RuntimeClass::Квитип](#queryinterface)           | Извлекает указатель на указанный идентификатор интерфейса.                                                 |
| [RuntimeClass::Release](#release)                         | Выполняет операцию COM Release `RuntimeClass` на текущем объекте.                             |

## <a name="inheritance-hierarchy"></a>Иерархия наследования

Это сведения о реализации примера.

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="runtimeclassruntimeclass"></a><a name="tilde-runtimeclass"></a>RuntimeClass:::'RuntimeClass

Деприиратизирует текущий `RuntimeClass` экземпляр класса.

```cpp
virtual ~RuntimeClass();
```

## <a name="runtimeclassaddref"></a><a name="addref"></a>RuntimeClass::AddRef

Приращения отсчета ссылок на текущий `RuntimeClass` объект.

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="runtimeclassdecrementreference"></a><a name="decrementreference"></a>RuntimeClass::DecrementСправка

Декретирует значение отсчета `RuntimeClass` ссылок для текущего объекта.

```cpp
ULONG DecrementReference();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="runtimeclassgetiids"></a><a name="getiids"></a>RuntimeClass::GetIids

Получает массив, который может содержать иные иксы интерфейса, реализованные текущим `RuntimeClass` объектом.

```cpp
STDMETHOD(
   GetIids
)
   (_Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Параметры

*iidCount*<br/>
Когда эта операция завершается, общее количество элементов в массиве *iids.*

*iids*<br/>
После завершения операции представляет указатель на массив идентификаторов интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение E_OUTOFMEMORY.

## <a name="runtimeclassgetruntimeclassname"></a><a name="getruntimeclassname"></a>RuntimeClass::GetRuntimeClassName

Получает имя класса времени выполнения `RuntimeClass` текущего объекта.

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Параметры

*время выполненияИмя*<br/>
После завершения операции представляет имя класса среды выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Ошибка утверждения испускается, `__WRL_STRICT__` `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` если или не определена.

## <a name="runtimeclassgettrustlevel"></a><a name="gettrustlevel"></a>RuntimeClass::GetTrustLevel

Получает уровень доверия `RuntimeClass` к текущему объекту.

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Параметры

*trustLvl*<br/>
Когда эта операция завершается, уровень `RuntimeClass` доверия текущего объекта.

### <a name="return-value"></a>Возвращаемое значение

Всегда S_OK.

### <a name="remarks"></a>Примечания

Ошибка утверждения испускается, `__WRL_STRICT__` `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` если или не определена.

## <a name="runtimeclassgetweakreference"></a><a name="getweakreference"></a>RuntimeClass::GetWeakСправка

Получает указатель на слабый эталонный `RuntimeClass` объект для текущего объекта.

```cpp
STDMETHOD(
   GetWeakReference
)(_Deref_out_ IWeakReference **weakReference);
```

### <a name="parameters"></a>Параметры

*Weakreference*<br/>
После завершения операции представляет указатель на объект слабой ссылки.

### <a name="return-value"></a>Возвращаемое значение

Всегда S_OK.

## <a name="runtimeclassinternaladdref"></a><a name="internaladdref"></a>RuntimeClass::InternalAddRef

Приращения отсчета ссылок на текущий `RuntimeClass` объект.

```cpp
ULONG InternalAddRef();
```

### <a name="return-value"></a>Возвращаемое значение

В результате отсчет ссылок.

## <a name="runtimeclassqueryinterface"></a><a name="queryinterface"></a>RuntimeClass::Квитип

Извлекает указатель на указанный идентификатор интерфейса.

```cpp
STDMETHOD(
   QueryInterface
)
   (REFIID riid,
   _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ppvObject*<br/>
Когда эта оперезания завершается, указатель на интерфейс, указанный параметром *riid.*

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="runtimeclassrelease"></a><a name="release"></a>RuntimeClass::Release

Выполняет операцию COM Release `RuntimeClass` на текущем объекте.

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Если количество ссылок становится `RuntimeClass` нулевым, объект удаляется.

## <a name="runtimeclassruntimeclass"></a><a name="runtimeclass"></a>RuntimeClass::RuntimeClass

Инициализирует текущий экземпляр `RuntimeClass` класса.

```cpp
RuntimeClass();
```
