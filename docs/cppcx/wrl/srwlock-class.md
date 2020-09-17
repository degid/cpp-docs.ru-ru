---
title: SRWLock - класс
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock_
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::~SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
helpviewer_keywords:
- Microsoft::WRL::Wrappers::SRWLock class
- Microsoft::WRL::Wrappers::SRWLock::LockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::LockShared method
- Microsoft::WRL::Wrappers::SRWLock::SRWLock, constructor
- Microsoft::WRL::Wrappers::SRWLock::SRWLock_ data member
- Microsoft::WRL::Wrappers::SRWLock::~SRWLock, destructor
- Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::TryLockShared method
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
ms.openlocfilehash: e305ad54e30455ce7c25f356c454791da0783591
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377269"
---
# <a name="srwlock-class"></a>SRWLock - класс

Представляет тонкую блокировку чтения и записи.

## <a name="syntax"></a>Синтаксис

```cpp
class SRWLock;
```

## <a name="remarks"></a>Примечания

Тонкий замок читателя/писателя используется для синхронизации доступа между потоками к объекту или ресурсу. Для получения дополнительной [Synchronization Functions](/windows/win32/Sync/synchronization-functions)информации см.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя                | Описание
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Синоним `SRWLock` объекта, приобретенного в эксклюзивном режиме.
`SyncLockShared`    | Синоним `SRWLock` объекта, приобретенного в общем режиме.

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                     | Описание
---------------------------------------- | --------------------------------------------------
[SRWLock::SRWLock](#srwlock-constructor) | Инициализирует новый экземпляр класса `SRWLock`.
[SRWLock:::](#tilde-srwlock)      | Деприиратизирует экземпляр `SRWLock` класса.

### <a name="public-methods"></a>Открытые методы

Имя                                           | Описание
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock::LockExclusive](#lockexclusive)       | Приобретает объект `SRWLock` в эксклюзивном режиме.
[SRWLock::LockShared](#lockshared)             | Приобретает `SRWLock` объект в общем режиме.
[SRWLock::TryLockExclusive](#trylockexclusive) | Попытки приобрести `SRWLock` объект в эксклюзивном режиме для текущего или указанного `SRWLock` объекта.
[SRWLock::TryLockShared](#trylockshared)       | Попытки приобрести `SRWLock` объект в общем режиме `SRWLock` для текущего или указанного объекта.

### <a name="protected-data-member"></a>Защищенный член данных

Имя                                      | Описание
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock::SRWLock_](#srwlock-data-member) | Содержит базовую переменную блокировки для текущего `SRWLock` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SRWLock`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Wrappers

## <a name="srwlocksrwlock"></a><a name="tilde-srwlock"></a>SRWLock:::

Деприиратизирует экземпляр `SRWLock` класса.

```cpp
~SRWLock();
```

## <a name="srwlocklockexclusive"></a><a name="lockexclusive"></a>SRWLock::LockExclusive

Приобретает объект `SRWLock` в эксклюзивном режиме.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Указатель на `SRWLock` объект.

### <a name="return-value"></a>Возвращаемое значение

Объект `SRWLock` в эксклюзивном режиме.

## <a name="srwlocklockshared"></a><a name="lockshared"></a>SRWLock::LockShared

Приобретает `SRWLock` объект в общем режиме.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Указатель на `SRWLock` объект.

### <a name="return-value"></a>Возвращаемое значение

Объект `SRWLock` в общем режиме.

## <a name="srwlocksrwlock"></a><a name="srwlock-constructor"></a>SRWLock::SRWLock

Инициализирует новый экземпляр класса `SRWLock`.

```cpp
SRWLock();
```

## <a name="srwlocksrwlock_"></a><a name="srwlock-data-member"></a>SRWLock::SRWLock_

Содержит базовую переменную блокировки для текущего `SRWLock` объекта.

```cpp
SRWLOCK SRWLock_;
```

## <a name="srwlocktrylockexclusive"></a><a name="trylockexclusive"></a>SRWLock::TryLockExclusive

Попытки приобрести `SRWLock` объект в эксклюзивном режиме для текущего или указанного `SRWLock` объекта. Если вызов выполняется успешно, поток вызова берет на себя ответственность за блокировку.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Указатель на `SRWLock` объект.

### <a name="return-value"></a>Возвращаемое значение

В случае `SRWLock` успеха объект в эксклюзивном режиме и поток вызова берет на себя ответственность за блокировку. В противном случае `SRWLock` объект, состояние которого является недействительным.

## <a name="srwlocktrylockshared"></a><a name="trylockshared"></a>SRWLock::TryLockShared

Попытки приобрести `SRWLock` объект в общем режиме `SRWLock` для текущего или указанного объекта.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Параметры

*lock*<br/>
Указатель на `SRWLock` объект.

### <a name="return-value"></a>Возвращаемое значение

В случае `SRWLock` успеха объект в общем режиме и поток вызова берет на себя ответственность за блокировку. В противном случае `SRWLock` объект, состояние которого является недействительным.
