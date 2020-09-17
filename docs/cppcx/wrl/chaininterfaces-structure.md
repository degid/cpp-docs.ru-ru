---
title: ChainInterfaces - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
- implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
- implements/Microsoft::WRL::ChainInterfaces::IidCount
- implements/Microsoft::WRL::ChainInterfaces::Verify
helpviewer_keywords:
- Microsoft::WRL::ChainInterfaces structure
- Microsoft::WRL::ChainInterfaces::CanCastTo method
- Microsoft::WRL::ChainInterfaces::CastToUnknown method
- Microsoft::WRL::ChainInterfaces::FillArrayWithIid method
- Microsoft::WRL::ChainInterfaces::IidCount constant
- Microsoft::WRL::ChainInterfaces::Verify method
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
ms.openlocfilehash: 48b663f2042ff0095466d83fe872ef6196112f76
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211545"
---
# <a name="chaininterfaces-structure"></a>ChainInterfaces - структура

Указывает функции проверки и инициализации, которые могут применяться к набору идентификаторов интерфейсов.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename I0,
    typename I1,
    typename I2 = Details::Nil,
    typename I3 = Details::Nil,
    typename I4 = Details::Nil,
    typename I5 = Details::Nil,
    typename I6 = Details::Nil,
    typename I7 = Details::Nil,
    typename I8 = Details::Nil,
    typename I9 = Details::Nil
>
struct ChainInterfaces : I0;

template <
    typename DerivedType,
    typename BaseType,
    bool hasImplements,
    typename I1,
    typename I2,
    typename I3,
    typename I4,
    typename I5,
    typename I6,
    typename I7,
    typename I8,
    typename I9
>
struct ChainInterfaces<
    MixIn<
        DerivedType,
        BaseType,
        hasImplements
    >, I1, I2, I3, I4, I5, I6, I7, I8, I9
>;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Необходимости Идентификатор интерфейса 0.

*I1*<br/>
Необходимости Идентификатор интерфейса 1.

*I2*<br/>
Используемых Идентификатор интерфейса 2.

*I3*<br/>
Используемых Идентификатор интерфейса 3.

*I4*<br/>
Используемых Идентификатор интерфейса 4.

*I5*<br/>
Используемых Идентификатор интерфейса 5.

*I6*<br/>
Используемых Идентификатор интерфейса 6.

*I7*<br/>
Используемых Идентификатор интерфейса 7.

*I8*<br/>
Используемых Идентификатор интерфейса 8.

*I9*<br/>
Используемых Идентификатор интерфейса 9.

*дериведтипе*<br/>
Производный тип.

*BaseType*<br/>
Базовый тип производного типа.

*хасимплементс*<br/>
Логическое значение, которое **`true`** , если, означает, что нельзя использовать структуру [примеси](mixin-structure.md) с классом, который не является производным [от Implements](implements-structure.md) структуру.

## <a name="members"></a>Элементы

### <a name="protected-methods"></a>Защищенные методы

Имя                                                   | Описание
------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[Метод ChainInterfaces:: CanCastTo](#cancastto)               | Указывает, можно ли привести указанный идентификатор интерфейса к каждой специализации, определенной `ChainInterface` параметрами шаблона.
[Метод ChainInterfaces:: CastToUnknown](#casttounknown)       | Приводит указатель интерфейса к типу, определенному параметром шаблона *I0* , в указатель на `IUnknown` .
[Метод ChainInterfaces:: FillArrayWithIid](#fillarraywithiid) | Хранит идентификатор интерфейса, определенный параметром шаблона *I0* , в указанное расположение в указанном массиве идентификаторов интерфейсов.
[Метод ChainInterfaces:: Verify](#verify)                     | Проверяет, что каждый интерфейс, определенный параметрами шаблона *I0* через *i9* , наследует от класса `IUnknown` и/или `IInspectable` и что *I0* наследует от *I1* до *i9*.

### <a name="protected-constants"></a>Защищенные константы

Имя                                   | Описание
-------------------------------------- | -----------------------------------------------------------------------------------------------------------------
[Метод ChainInterfaces:: IidCount](#iidcount) | Общее число идентификаторов интерфейсов, содержащихся в интерфейсах, указанных в параметрах шаблона *I0* через *i9*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`I0`

`ChainInterfaces`

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft::WRL

## <a name="chaininterfacescancastto"></a><a name="cancastto"></a>Метод ChainInterfaces:: CanCastTo

Указывает, можно ли привести указанный идентификатор интерфейса к каждой специализации, определенной параметрами шаблона, отличными от параметров по умолчанию.

```cpp
__forceinline bool CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Идентификатор интерфейса.

*ппв*<br/>
Указатель на последний идентификатор интерфейса, который был успешно приведен.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если все операции приведения выполняются удачно. в противном случае — **`false`** .

## <a name="chaininterfacescasttounknown"></a><a name="casttounknown"></a>Метод ChainInterfaces:: CastToUnknown

Приводит указатель интерфейса к типу, определенному параметром шаблона *I0* , в указатель на `IUnknown` .

```cpp
__forceinline IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `IUnknown`.

## <a name="chaininterfacesfillarraywithiid"></a><a name="fillarraywithiid"></a>Метод ChainInterfaces:: FillArrayWithIid

Хранит идентификатор интерфейса, определенный параметром шаблона *I0* , в указанное расположение в указанном массиве идентификаторов интерфейсов.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*номер*<br/>
Указатель на значение индекса в массиве *идентификаторов IID* .

*идентификаторов IID*<br/>
Массив идентификаторов интерфейсов.

## <a name="chaininterfacesiidcount"></a><a name="iidcount"></a>Метод ChainInterfaces:: IidCount

Общее число идентификаторов интерфейсов, содержащихся в интерфейсах, указанных в параметрах шаблона *I0* через *i9*.

```cpp
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;
```

### <a name="return-value"></a>Возвращаемое значение

Общее число идентификаторов интерфейсов.

### <a name="remarks"></a>Примечания

Параметры шаблона *I0* и *I1* являются обязательными, а параметры *I2* – *i9* являются необязательными. Число IID каждого интерфейса обычно равно 1.

## <a name="chaininterfacesverify"></a><a name="verify"></a>Метод ChainInterfaces:: Verify

Проверяет, что каждый интерфейс, определенный параметрами шаблона *I0* через *i9* , наследует от класса `IUnknown` и/или `IInspectable` и что *I0* наследует от *I1* до *i9*.

```cpp
WRL_NOTHROW __forceinline static void Verify();
```

### <a name="remarks"></a>Примечания

Если операция проверки завершается неудачно, **`static_assert`** выдает сообщение об ошибке с описанием сбоя.

Параметры шаблона *I0* и *I1* являются обязательными, а параметры *I2* – *i9* являются необязательными.
