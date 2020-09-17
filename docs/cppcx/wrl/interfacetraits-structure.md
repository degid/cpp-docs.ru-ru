---
title: InterfaceTraits - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
- implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase
- implements/Microsoft::WRL::Details::InterfaceTraits::CastToUnknown
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
- implements/Microsoft::WRL::Details::InterfaceTraits::IidCount
- implements/Microsoft::WRL::Details::InterfaceTraits::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::InterfaceTraits structure
- Microsoft::WRL::Details::InterfaceTraits::CanCastTo method
- Microsoft::WRL::Details::InterfaceTraits::CastToBase method
- Microsoft::WRL::Details::InterfaceTraits::CastToUnknown method
- Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid method
- Microsoft::WRL::Details::InterfaceTraits::IidCount constant
- Microsoft::WRL::Details::InterfaceTraits::Verify method
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
ms.openlocfilehash: c08c6e8bbcc16120dd44da69a2933fc3ec42f387
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216574"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits - структура

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename I0>
struct __declspec(novtable) InterfaceTraits;

template<typename CloakedType>
struct __declspec(novtable) InterfaceTraits<
    CloakedIid<CloakedType>
>;

template<>
struct __declspec(novtable) InterfaceTraits<Nil>;
```

### <a name="parameters"></a>Параметры

*I0*<br/>
Имя интерфейса.

*клоакедтипе*<br/>
Для `RuntimeClass` `Implements` и `ChainInterfaces` интерфейс, который не будет входить в список поддерживаемых идентификаторов интерфейса.

## <a name="remarks"></a>Примечания

Реализует общие характеристики интерфейса.

Второй шаблон является специализацией для замаскированных интерфейсов. Третий шаблон — это специализация для пустых параметров.

## <a name="members"></a>Элементы

### <a name="public-typedefs"></a><a name="public-typedefs"></a>Открытые определения типов

Имя   | Описание
------ | ------------------------------------------
`Base` | Синоним для параметра шаблона *I0* .

### <a name="public-methods"></a>Открытые методы

name                                                   | Описание
------------------------------------------------------ | ----------------------------------------------------------------------------------------
[Метод InterfaceTraits:: CanCastTo](#cancastto)               | Указывает, может ли указанный указатель быть приведен к указателю на `Base` .
[Метод InterfaceTraits:: CastToBase](#casttobase)             | Приводит определенный указатель к указателю на `Base`.
[Метод InterfaceTraits:: CastToUnknown](#casttounknown)       | Приводит определенный указатель к указателю на `IUnknown`.
[Метод InterfaceTraits:: FillArrayWithIid](#fillarraywithiid) | Присваивает идентификатор интерфейса `Base` элементу массива, указанному в аргументе index.
[Метод InterfaceTraits:: Verify](#verify)                     | Проверяет правильность `Base` наследования.

### <a name="public-constants"></a>Открытые константы

Имя                                   | Описание
-------------------------------------- | ---------------------------------------------------------------------------------------
[Метод InterfaceTraits:: IidCount](#iidcount) | Содержит число идентификаторов интерфейса, связанных с текущим `InterfaceTraits` объектом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InterfaceTraits`

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="interfacetraitscancastto"></a><a name="cancastto"></a>Метод InterfaceTraits:: CanCastTo

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
template<typename T>
static __forceinline bool CanCastTo(
   _In_ T* ptr,
   REFIID riid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*ptr*<br/>
Имя указателя на тип.

*riid*<br/>
Идентификатор интерфейса `Base` .

*ппв*<br/>
Если эта операция выполнена успешно, *ППВ* указывает на интерфейс, указанный параметром `Base` . В противном случае *ППВ* имеет значение **`nullptr`** .

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если эта операция выполнена успешно, и тип *ptr* преобразуется в указатель на `Base` ; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Указывает, может ли указанный указатель быть приведен к указателю на `Base` .

Дополнительные сведения о `Base` см. в разделе [общедоступные определения типов](#public-typedefs) .

## <a name="interfacetraitscasttobase"></a><a name="casttobase"></a>Метод InterfaceTraits:: CastToBase

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
template<typename T>
static __forceinline Base* CastToBase(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра *ptr*.

*ptr*<br/>
Указатель на тип *T*.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `Base`.

### <a name="remarks"></a>Примечания

Приводит определенный указатель к указателю на `Base`.

Дополнительные сведения о `Base` см. в разделе [общедоступные определения типов](#public-typedefs) .

## <a name="interfacetraitscasttounknown"></a><a name="casttounknown"></a>Метод InterfaceTraits:: CastToUnknown

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
template<typename T>
static __forceinline IUnknown* CastToUnknown(
   _In_ T* ptr
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра *ptr*.

*ptr*<br/>
Указатель на тип *T*.

### <a name="return-value"></a>Возвращаемое значение

Указатель на IUnknown, `Base` производный от которого является.

### <a name="remarks"></a>Примечания

Приводит определенный указатель к указателю на `IUnknown`.

Дополнительные сведения о `Base` см. в разделе [общедоступные определения типов](#public-typedefs) .

## <a name="interfacetraitsfillarraywithiid"></a><a name="fillarraywithiid"></a>Метод InterfaceTraits:: FillArrayWithIid

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*номер*<br/>
Указатель на поле, содержащее значение индекса, начинающееся с нуля.

*идентификаторов IID*<br/>
Массив идентификаторов интерфейсов.

### <a name="remarks"></a>Примечания

Присваивает идентификатор интерфейса `Base` элементу массива, указанному в аргументе index.

В отличие от имени этого API, изменяется только один элемент массива. не весь массив.

Дополнительные сведения о `Base` см. в разделе [общедоступные определения типов](#public-typedefs) .

## <a name="interfacetraitsiidcount"></a><a name="iidcount"></a>Метод InterfaceTraits:: IidCount

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
static const unsigned long IidCount = 1;
```

### <a name="remarks"></a>Примечания

Содержит число идентификаторов интерфейса, связанных с текущим `InterfaceTraits` объектом.

## <a name="interfacetraitsverify"></a><a name="verify"></a>Метод InterfaceTraits:: Verify

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
__forceinline static void Verify();
```

### <a name="remarks"></a>Примечания

Проверяет правильность `Base` наследования.

Дополнительные сведения о `Base` см. в разделе [общедоступные определения типов](#public-typedefs) .
