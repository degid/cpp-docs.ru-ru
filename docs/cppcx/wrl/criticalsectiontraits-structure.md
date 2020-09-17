---
title: CriticalSectionTraits - структура
ms.date: 09/26/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock method
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
ms.openlocfilehash: 3573cad21734a97629cbc12b76d73b99024cbc2f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220513"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits - структура

Специализирует `CriticalSection` объект для поддержки недопустимого критического раздела или функции для освобождения критического раздела.

## <a name="syntax"></a>Синтаксис

```
struct CriticalSectionTraits;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя   | Описание
------ | -----------------------------------------------------------------------------------------------------------------
`Type` | Объект **`typedef`** , определяющий указатель на критическую секцию. `Type` определяется как `typedef CRITICAL_SECTION* Type;`.

### <a name="public-methods"></a>Открытые методы

name                                                       | Описание
---------------------------------------------------------- | -----------------
[Метод criticalsectiontraits:: GetInvalidValue](#getinvalidvalue) | Специализирует `CriticalSection` шаблон так, чтобы шаблон всегда был недействительным.
[Метод criticalsectiontraits:: Unlock](#unlock)                   | Специализирует `CriticalSection` шаблон таким образом, чтобы он поддерживал владение заданным объектом критического раздела.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CriticalSectionTraits`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Microsoft:: WRL:: оболочки:: метод HandleTraits

## <a name="criticalsectiontraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a>Метод criticalsectiontraits:: GetInvalidValue

Специализирует `CriticalSection` шаблон так, чтобы шаблон всегда был недействительным.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает указатель на недопустимую критическую секцию.

### <a name="remarks"></a>Примечания

Модификатор `Type` определен как `typedef CRITICAL_SECTION* Type;`.

## <a name="criticalsectiontraitsunlock"></a><a name="unlock"></a>Метод criticalsectiontraits:: Unlock

Специализирует `CriticalSection` шаблон таким образом, чтобы он поддерживал владение заданным объектом критического раздела.

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>Параметры

*сложных*<br/>
Указатель на объект критической секции.

### <a name="remarks"></a>Примечания

Модификатор `Type` определен как `typedef CRITICAL_SECTION* Type;`.

Дополнительные сведения см. в разделе **функция LeaveCriticalSection** раздела " **функции синхронизации** " документации по API Windows.
