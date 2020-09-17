---
title: CriticalSection - класс
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::cs_
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::IsValid
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::CriticalSection class
- Microsoft::WRL::Wrappers::CriticalSection::cs_ data member
- Microsoft::WRL::Wrappers::CriticalSection::IsValid method
- Microsoft::WRL::Wrappers::CriticalSection::Lock method
- Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection, destructor
- Microsoft::WRL::Wrappers::CriticalSection::CriticalSection, constructor
- Microsoft::WRL::Wrappers::CriticalSection::TryLock method
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
ms.openlocfilehash: b95e512f89ee1ff32ca9f1bea51bce643d185a2e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220526"
---
# <a name="criticalsection-class"></a>CriticalSection - класс

Представляет объект критической секции.

## <a name="syntax"></a>Синтаксис

```cpp
class CriticalSection;
```

## <a name="members"></a>Участники

### <a name="constructor"></a>Конструктор

Имя                                                        | Описание
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[CriticalSection:: CriticalSection](#criticalsection)        | Инициализирует объект синхронизации, похожий на объект Mutex, но может использоваться только потоками одного процесса.
[CriticalSection:: ~ CriticalSection](#tilde-criticalsection) | Выполняет деинициализацию и уничтожает текущий `CriticalSection` объект.

### <a name="public-methods"></a>Открытые методы

name                                 | Описание
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[CriticalSection:: IsValid](#isvalid) | Указывает, допустима ли текущая критическая секция.
[CriticalSection:: Lock](#lock)       | Ожидает владение заданным объектом критического раздела. Функция возвращает, когда вызывающему потоку предоставляется владение.
[CriticalSection:: TryLock](#trylock) | Пытается войти в критическую секцию без блокировки. Если вызов выполнен успешно, вызывающий поток принимает владение критическим разделом.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                        | Описание
--------------------------- | ----------------------------------------
[CriticalSection:: cs_](#cs) | Объявляет критически важный элемент данных секции.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CriticalSection`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Программы Microsoft:: WRL:: оболочки

## <a name="criticalsectioncriticalsection"></a><a name="tilde-criticalsection"></a>CriticalSection:: ~ CriticalSection

Выполняет деинициализацию и уничтожает текущий `CriticalSection` объект.

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsectioncriticalsection"></a><a name="criticalsection"></a>CriticalSection:: CriticalSection

Инициализирует объект синхронизации, похожий на объект Mutex, но может использоваться только потоками одного процесса.

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Параметры

*спинкаунт*<br/>
Счетчик прокруток для объекта критической секции. Значение по умолчанию — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения о критических разделах и спинкаунтс см. в описании `InitializeCriticalSectionAndSpinCount` функции в `Synchronization` разделе документации по Windows API.

## <a name="criticalsectioncs_"></a><a name="cs"></a>CriticalSection:: cs_

Объявляет критически важный элемент данных секции.

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>Примечания

Эти данные-член защищены.

## <a name="criticalsectionisvalid"></a><a name="isvalid"></a>CriticalSection:: IsValid

Указывает, допустима ли текущая критическая секция.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

По умолчанию всегда возвращает **`true`** .

## <a name="criticalsectionlock"></a><a name="lock"></a>CriticalSection:: Lock

Ожидает владение заданным объектом критического раздела. Функция возвращает, когда вызывающему потоку предоставляется владение.

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Параметры

*сложных*<br/>
Определенный пользователем объект критической секции.

### <a name="return-value"></a>Возвращаемое значение

Объект блокировки, который можно использовать, чтобы разблокировать текущую критическую секцию.

### <a name="remarks"></a>Примечания

Первая функция `Lock` влияет на текущий объект критической секции. Вторая функция `Lock` влияет на указанную пользователем критическую секцию.

## <a name="criticalsectiontrylock"></a><a name="trylock"></a>CriticalSection:: TryLock

Пытается войти в критическую секцию без блокировки. Если вызов выполнен успешно, вызывающий поток принимает владение критическим разделом.

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Параметры

*сложных*<br/>
Определенный пользователем объект критической секции.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если критический раздел успешно указан или текущий поток уже владеет критическим разделом. Нуль, если другой поток уже владеет критическим разделом.

### <a name="remarks"></a>Примечания

Первая функция `TryLock` влияет на текущий объект критической секции. Вторая функция `TryLock` влияет на указанную пользователем критическую секцию.
