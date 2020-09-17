---
title: RELOG_RETENTION_SYSTEM_EVENT_FLAGS константы
description: Ссылка на констант SDK Build Insights sDK RELOG_RETENTION_SYSTEM_EVENT_FLAGS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_RETENTION_SYSTEM_EVENT_FLAGS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7110f809a819357b31951c203c1fa6ac9fb9f42e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323474"
---
# <a name="relog_retention_system_event_flags-constants"></a>RELOG_RETENTION_SYSTEM_EVENT_FLAGS константы

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Константы `RELOG_RETENTION_SYSTEM_EVENT_FLAGS` используются для описания событий системы для сохранения перезаписи. Используйте их для [RELOG_DESCRIPTOR](relog-descriptor-struct.md) инициализации `SystemEventsRetentionFlags` поля RELOG_DESCRIPTOR структуры.

## <a name="syntax"></a>Синтаксис

```cpp
static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES = 0x1ULL;

static const unsigned long long
    RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL         = 0xFFFFFFFFFFFFFFFFULL;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_CPU_SAMPLES` | Храните события образца системы процессора в перезаписи. |
| `RELOG_RETENTION_SYSTEM_EVENT_FLAGS_ALL` | Храните все события системы в перезаписи. |

## <a name="remarks"></a>Примечания

::: moniker-end
