---
title: Класс SyncLockWithStatusT
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_
- corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT class
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked method
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::status_ data member
- Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::SyncLockWithStatusT, constructor
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
ms.openlocfilehash: 4b7dbe8ae1648e4185a9eb1e1142df4a3869aa2f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216548"
---
# <a name="synclockwithstatust-class"></a>Класс SyncLockWithStatusT

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename SyncTraits>
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;
```

### <a name="parameters"></a>Параметры

*синктраитс*<br/>
Тип, который может принимать монопольное или совместное владение ресурсом.

## <a name="remarks"></a>Примечания

Представляет тип, который может принимать монопольное или совместное владение ресурсом.

`SyncLockWithStatusT`Класс используется для реализации классов [мьютекса](mutex-class.md) и [семафора](semaphore-class.md) .

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                             | Описание
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT:: SyncLockWithStatusT](#synclockwithstatust) | Инициализирует новый экземпляр класса `SyncLockWithStatusT`.

### <a name="protected-constructors"></a>Защищенные конструкторы

Имя                                                             | Описание
---------------------------------------------------------------- | --------------------------------------------------------------
[SyncLockWithStatusT:: SyncLockWithStatusT](#synclockwithstatust) | Инициализирует новый экземпляр класса `SyncLockWithStatusT`.

### <a name="public-methods"></a>Открытые методы

name                                         | Описание
-------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT::/Status](#getstatus) | Возвращает состояние ожидания текущего `SyncLockWithStatusT` объекта.
[SyncLockWithStatusT:: NOLOCK](#islocked)   | Указывает `SyncLockWithStatusT` , владеет ли текущий объект ресурсом, т `SyncLockWithStatusT` . е. объект *заблокирован*.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                                    | Описание
--------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------
[SyncLockWithStatusT:: status_](#status) | Содержит результат базовой операции ожидания после операции блокировки объекта на основе текущего `SyncLockWithStatusT` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SyncLockT`

`SyncLockWithStatusT`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Microsoft:: WRL:: оболочки::D состояния

## <a name="synclockwithstatustgetstatus"></a><a name="getstatus"></a>SyncLockWithStatusT::/Status

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
DWORD GetStatus() const;
```

### <a name="return-value"></a>Возвращаемое значение

Результат операции ожидания для объекта, основанного на `SyncLockWithStatusT` классе, например [мьютекса](mutex-class.md) или [семафора](semaphore-class.md). Ноль (0) указывает, что операция ожидания вернула сигнальное состояние; в противном случае произошло другое состояние, например прошло значение времени ожидания.

### <a name="remarks"></a>Примечания

Возвращает состояние ожидания текущего `SyncLockWithStatusT` объекта.

Функция Status () получает значение базового элемента данных [status_](#status) . Когда объект, основанный на `SyncLockWithStatusT` классе, выполняет операцию блокировки, объект сначала ждет, пока объект станет доступным. Результат этой операции ожидания сохраняется в элементе `status_` данных. Возможными значениями `status_` элемента данных являются возвращаемые значения операции ожидания. Дополнительные сведения см. в разделе возвращаемые значения [`WaitForSingleObjectEx`](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobjectex) функции.

## <a name="synclockwithstatustislocked"></a><a name="islocked"></a>SyncLockWithStatusT:: NOLOCK

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
bool IsLocked() const;
```

### <a name="remarks"></a>Примечания

Указывает `SyncLockWithStatusT` , владеет ли текущий объект ресурсом, т `SyncLockWithStatusT` . е. объект *заблокирован*.

### <a name="return-value"></a>Возвращаемое значение

**`true`**`SyncLockWithStatusT`значение, если объект заблокирован; в противном случае — **`false`** .

## <a name="synclockwithstatuststatus_"></a><a name="status"></a>SyncLockWithStatusT:: status_

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
DWORD status_;
```

### <a name="remarks"></a>Примечания

Содержит результат базовой операции ожидания после операции блокировки объекта на основе текущего `SyncLockWithStatusT` объекта.

## <a name="synclockwithstatustsynclockwithstatust"></a><a name="synclockwithstatust"></a>SyncLockWithStatusT:: SyncLockWithStatusT

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
SyncLockWithStatusT(
   _Inout_ SyncLockWithStatusT&& other
);

explicit SyncLockWithStatusT(
   typename SyncTraits::Type sync,
   DWORD status
);
```

### <a name="parameters"></a>Параметры

*иной*<br/>
Ссылка rvalue на другой `SyncLockWithStatusT` объект.

*nosync*<br/>
Ссылка на другой `SyncLockWithStatusT` объект.

*status*<br/>
Значение элемента данных [status_](#status) *другого* параметра или параметра *синхронизации* .

### <a name="remarks"></a>Примечания

Инициализирует новый экземпляр класса `SyncLockWithStatusT`.

Первый конструктор инициализирует текущий `SyncLockWithStatusT` объект из другого `SyncLockWithStatusT` , указанного параметром *other*, а затем делает недействительным другой `SyncLockWithStatusT` объект. Второй конструктор — **`protected`** и инициализирует текущий `SyncLockWithStatusT` объект в недопустимом состоянии.
