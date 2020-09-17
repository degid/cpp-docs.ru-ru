---
title: SyncLockT - класс
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::sync_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockT class
- Microsoft::WRL::Wrappers::Details::SyncLockT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockT::sync_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT, constructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::~SyncLockT, destructor
- Microsoft::WRL::Wrappers::Details::SyncLockT::Unlock method
ms.assetid: a967f6f7-3555-43d1-b210-2bb65d63d15e
ms.openlocfilehash: 6a6e176020624f02e778ba5684a374abfbafa9e4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87184674"
---
# <a name="synclockt-class"></a>SyncLockT - класс

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename SyncTraits>
class SyncLockT;
```

### <a name="parameters"></a>Параметры

*синктраитс*<br/>
Тип, который может стать владельцем ресурса.

## <a name="remarks"></a>Примечания

Представляет тип, который может принимать монопольное или совместное владение ресурсом.

`SyncLockT`Класс используется, например, для реализации класса [SRWLock](srwlock-class.md) .

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                      | Описание
----------------------------------------- | ----------------------------------------------------
[SyncLockT:: SyncLockT](#synclockt)        | Инициализирует новый экземпляр класса `SyncLockT`.
[SyncLockT:: ~ SyncLockT](#tilde-synclockt) | Выполняет деинициализацию экземпляра `SyncLockT` класса.

### <a name="protected-constructors"></a>Защищенные конструкторы

Имя                               | Описание
---------------------------------- | ----------------------------------------------------
[SyncLockT:: SyncLockT](#synclockt) | Инициализирует новый экземпляр класса `SyncLockT`.

### <a name="public-methods"></a>Открытые методы

name                             | Описание
-------------------------------- | --------------------------------------------------------------------------------------------------------------
[SyncLockT:: NOLOCK](#islocked) | Указывает `SyncLockT` , владеет ли текущий объект ресурсом, т `SyncLockT` . е. объект *заблокирован*.
[SyncLockT:: Unlock](#unlock)     | Освобождает управление ресурсом, удерживаемым текущим `SyncLockT` объектом, если он есть.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                      | Описание
------------------------- | -------------------------------------------------------------------
[SyncLockT:: sync_](#sync) | Содержит базовый ресурс, представленный `SyncLockT` классом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SyncLockT`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Microsoft:: WRL:: оболочки::D состояния

## <a name="synclocktsynclockt"></a><a name="tilde-synclockt"></a>SyncLockT:: ~ SyncLockT

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
~SyncLockT();
```

### <a name="remarks"></a>Примечания

Выполняет деинициализацию экземпляра `SyncLockT` класса.

Этот деструктор также разблокирует текущий `SyncLockT` экземпляр.

## <a name="synclocktislocked"></a><a name="islocked"></a>SyncLockT:: NOLOCK

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
bool IsLocked() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`true`**`SyncLockT`значение, если объект заблокирован; в противном случае — **`false`** .

### <a name="remarks"></a>Примечания

Указывает `SyncLockT` , владеет ли текущий объект ресурсом, т `SyncLockT` . е. объект *заблокирован*.

## <a name="synclocktsync_"></a><a name="sync"></a>SyncLockT:: sync_

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
typename SyncTraits::Type sync_;
```

### <a name="remarks"></a>Примечания

Содержит базовый ресурс, представленный `SyncLockT` классом.

## <a name="synclocktsynclockt"></a><a name="synclockt"></a>SyncLockT:: SyncLockT

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
SyncLockT(
   _Inout_ SyncLockT&& other
);

explicit SyncLockT(
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()
);
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Ссылка rvalue на другой `SyncLockT` объект.

*nosync*<br/>
Ссылка на другой `SyncLockWithStatusT` объект.

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `SyncLockT`.

Первый конструктор инициализирует текущий объект `SyncLockT` из другого `SyncLockT` объекта, указанного параметром *other*, а затем делает недействительным другой `SyncLockT` объект. Второй конструктор — **`protected`** и инициализирует текущий `SyncLockT` объект в недопустимом состоянии.

## <a name="synclocktunlock"></a><a name="unlock"></a>SyncLockT:: Unlock

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
void Unlock();
```

### <a name="remarks"></a>Примечания

Освобождает управление ресурсом, удерживаемым текущим `SyncLockT` объектом, если он есть.
