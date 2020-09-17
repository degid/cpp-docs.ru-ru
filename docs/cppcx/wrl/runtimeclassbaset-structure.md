---
title: Структура RuntimeClassBaseT
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
helpviewer_keywords:
- Microsoft::WRL::Details::RuntimeClassBaseT structure
- Microsoft::WRL::Details::RuntimeClassBaseT::AsIID method
- Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS method
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
ms.openlocfilehash: 06a9f73e00d541b0e5bcbe20c57befe4a67c5132
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375725"
---
# <a name="runtimeclassbaset-structure"></a>Структура RuntimeClassBaseT

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <unsigned int RuntimeClassTypeT>
friend struct Details::RuntimeClassBaseT;
```

### <a name="parameters"></a>Параметры

*RuntimeClassTypeT*<br/>
Поле флагов, которое определяет один или несколько регистраторов [RuntimeClassType.](runtimeclasstype-enumeration.md)

## <a name="remarks"></a>Примечания

Предоставляет вспомогательные методы для операций `QueryInterface` и получения идентификаторов интерфейсов.

## <a name="members"></a>Участники

### <a name="protected-methods"></a>Защищенные методы

Имя                                                         | Описание
------------------------------------------------------------ | -----------------------------------------------------------------------------
[RuntimeClassBaset::ASIID](#asiid)                           | Извлекает указатель на указанный идентификатор интерфейса.
[RuntimeClassBaset::GetImplementedIIDS](#getimplementediids) | Извлекает массив идотов интерфейса, реализованных определенным типом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RuntimeClassBaseT`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="runtimeclassbasetasiid"></a><a name="asiid"></a>RuntimeClassBaset::ASIID

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип, реализуемый идентификаторинтерфейса, указанный по параметру *riid.*

*реализует*<br/>
Переменная типа, указанная параметром шаблона *T*.

*riid*<br/>
Извлекаемый идентификатор интерфейса.

*ppvObject*<br/>
Если эта операция успешна, указатель к указателю на интерфейс, указанный по параметру *riid.*

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, HRESULT, который описывает ошибку.

### <a name="remarks"></a>Примечания

Извлекает указатель на указанный идентификатор интерфейса.

## <a name="runtimeclassbasetgetimplementediids"></a><a name="getimplementediids"></a>RuntimeClassBaset::GetImplementedIIDS

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип параметра *реализации.*

*реализует*<br/>
Указатель на тип, указанный по параметру *T*.

*iidCount*<br/>
Максимальное количество идотов интерфейса для извлечения.

*iids*<br/>
Если эта операция успешно завершена, массив интидоподобных интерфейсов реализован по типу *T.*

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; в противном случае, HRESULT, который описывает ошибку.

### <a name="remarks"></a>Примечания

Извлекает массив идотов интерфейса, реализованных определенным типом.
