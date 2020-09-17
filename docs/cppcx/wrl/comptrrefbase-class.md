---
title: ComPtrRefBase - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
- client/Microsoft::WRL::Details::ComPtrRefBase::ptr_
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRefBase class
- Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable** operator
- Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown** operator
- Microsoft::WRL::Details::ComPtrRefBase::ptr_ data member
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
ms.openlocfilehash: 4f6dd6449cf8135ad14486d64cea95d8329e0014
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372620"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
class ComPtrRefBase;
```

### <a name="parameters"></a>Параметры

*T*<br/>
[ComPtr\<T>](comptr-class.md) тип или тип, полученный из него, а не только интерфейс, представленный `ComPtr`.

## <a name="remarks"></a>Примечания

Представляет базовый класс для класса [ComPtrRef.](comptrref-class.md)

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя            | Описание
--------------- | -------------------------------------------------
`InterfaceType` | Синоним типа параметра *шаблона T*.

### <a name="public-operators"></a>Открытые операторы

Имя                                                                       | Описание
-------------------------------------------------------------------------- | -----------------------------------------------------------------------------------------------------
[ComPtrRefBase::оператор IInspectable](#operator-iinspectable-star-star) | Отбрасывает [текущий](#ptr) ptr_ член данных на указатель на указатель `IInspectable` на интерфейс.
[ComPtrRefBase::оператор IUnknown](#operator-iunknown-star-star)         | Отбрасывает [текущий](#ptr) ptr_ член данных на указатель на указатель `IUnknown` на интерфейс.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                        | Описание
--------------------------- | ----------------------------------------------------------------
[ComPtrRefBase::ptr](#ptr) | Указатель на тип, заданный текущим параметром шаблона.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtrRefBase`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="comptrrefbaseoperator-iinspectable-operator"></a><a name="operator-iinspectable-star-star"></a>ComPtrRefBase::оператор IInspectable\* \* Оператор

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
operator IInspectable**() const;
```

### <a name="remarks"></a>Примечания

Отбрасывает [текущий](#ptr) ptr_ член данных на указатель на указатель `IInspectable` на интерфейс.

Ошибка испускается, если `ComPtrRefBase` ток не `IInspectable`происходит от .

Этот бросок доступен только в том случае, если `__WRL_CLASSIC_COM__` он определен.

## <a name="comptrrefbaseoperator-iunknown-operator"></a><a name="operator-iunknown-star-star"></a>ComPtrRefBase:Оператор IUnknown

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
operator IUnknown**() const;
```

### <a name="remarks"></a>Примечания

Отбрасывает [текущий](#ptr) ptr_ член данных на указатель на указатель `IUnknown` на интерфейс.

Ошибка испускается, если `ComPtrRefBase` ток не `IUnknown`происходит от .

## <a name="comptrrefbaseptr_"></a><a name="ptr"></a>ComPtrRefBase::ptr

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
T* ptr_;
```

### <a name="remarks"></a>Примечания

Указатель на тип, заданный текущим параметром шаблона. `ptr_`защищенный член данных.
