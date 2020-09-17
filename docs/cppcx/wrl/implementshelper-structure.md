---
title: ImplementsHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
- implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
- implements/Microsoft::WRL::Details::ImplementsHelper::IidCount
helpviewer_keywords:
- Microsoft::WRL::Details::ImplementsHelper structure
- Microsoft::WRL::Details::ImplementsHelper::CanCastTo method
- Microsoft::WRL::Details::ImplementsHelper::CastToUnknown method
- Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid method
- Microsoft::WRL::Details::ImplementsHelper::IidCount constant
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
ms.openlocfilehash: d7908670b67df7dbf7b2b74e98f8b59cf30f8e96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184947"
---
# <a name="implementshelper-structure"></a>ImplementsHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename RuntimeClassFlagsT, typename ILst, bool IsDelegateToClass>
friend struct Details::ImplementsHelper;
```

### <a name="parameters"></a>Параметры

*рунтимеклассфлагст*<br/>
Поле флагов, задающее один или несколько перечислителей [RuntimeClassType](runtimeclasstype-enumeration.md) .

*илст*<br/>
Список идентификаторов интерфейсов.

*исделегатетокласс*<br/>
Укажите **`true`** , является ли текущий экземпляр `Implements` базовым классом первого идентификатора интерфейса в *илст*; в противном случае — значение **`false`** .

## <a name="remarks"></a>Примечания

Помогает реализовать структуру [Implements](implements-structure.md) .

Этот шаблон проходит по списку интерфейсов и добавляет их в качестве базовых классов и в качестве сведений, необходимых для включения `QueryInterface` .

## <a name="members"></a>Элементы

### <a name="protected-methods"></a>Защищенные методы

Имя                                                    | Описание
------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------
[Метод implementshelper:: CanCastTo](#cancastto)               | Возвращает указатель на указанный идентификатор интерфейса.
[Метод implementshelper:: CastToUnknown](#casttounknown)       | Возвращает указатель на базовый `IUnknown` интерфейс для текущей `Implements` структуры.
[Метод implementshelper:: FillArrayWithIid](#fillarraywithiid) | Вставляет идентификатор интерфейса, указанный текущим параметром шаблона начальном, в указанный элемент массива.
[Метод implementshelper:: IidCount](#iidcount)                 | Содержит число реализованных идентификаторов интерфейсов в текущем `Implements` объекте.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ImplementsHelper`

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="implementshelpercancastto"></a><a name="cancastto"></a>Метод implementshelper:: CanCastTo

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);

HRESULT CanCastTo(
   _In_ const IID &iid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Параметры

*riid*<br/>
Ссылка на идентификатор интерфейса.

*ппв*<br/>
Если эта операция выполнена успешно, указатель на интерфейс, указанный в *riid* или *IID*.

*IID*<br/>
Ссылка на идентификатор интерфейса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Возвращает указатель на указанный идентификатор интерфейса.

## <a name="implementshelpercasttounknown"></a><a name="casttounknown"></a>Метод implementshelper:: CastToUnknown

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
IUnknown* CastToUnknown();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовый `IUnknown` интерфейс.

### <a name="remarks"></a>Примечания

Возвращает указатель на базовый `IUnknown` интерфейс для текущей `Implements` структуры.

## <a name="implementshelperfillarraywithiid"></a><a name="fillarraywithiid"></a>Метод implementshelper:: FillArrayWithIid

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
void FillArrayWithIid(
   _Inout_ unsigned long *index,
   _Inout_ IID* iids) throw();
```

### <a name="parameters"></a>Параметры

*номер*<br/>
Отсчитываемый от нуля индекс, указывающий начальный элемент массива для данной операции. По завершении этой операции *индекс* увеличивается на 1.

*идентификаторов IID*<br/>
Массив типа идентификаторов IID.

### <a name="remarks"></a>Примечания

Вставляет идентификатор интерфейса, указанный текущим параметром шаблона начальном, в указанный элемент массива.

## <a name="implementshelperiidcount"></a><a name="iidcount"></a>Метод implementshelper:: IidCount

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
static const unsigned long IidCount;
```

### <a name="remarks"></a>Примечания

Содержит число реализованных идентификаторов интерфейсов в текущем `Implements` объекте.
