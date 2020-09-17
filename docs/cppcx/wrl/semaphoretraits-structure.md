---
title: SemaphoreTraits - структура
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: 11719576c9fc7b23f4cd318ee1b3ed9ca3f5edaa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360741"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits - структура

Определяет общие характеристики `Semaphore` объекта.

## <a name="syntax"></a>Синтаксис

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

Имя                               | Описание
---------------------------------- | --------------------------------------
[SemaphoreTraits::Разблокировка](#unlock) | Выпускает элемент управления общим ресурсом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers:: HandleTraits

## <a name="semaphoretraitsunlock"></a><a name="unlock"></a>SemaphoreTraits::Разблокировка

Выпускает элемент управления общим ресурсом.

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Обработка `Semaphore` объекта.

### <a name="remarks"></a>Примечания

Если операция разблокировки `Unlock()` не выполнена, испускают ошибку, указывают причину сбоя.
