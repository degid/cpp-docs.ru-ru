---
title: структура TRACING_SESSION_STATISTICS
description: Ссылка на структуру СЗ Build Insights SDK TRACING_SESSION_OPTIONS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACING_SESSION_STATISTICS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 96cff3a231fd515ec1c52a048b8350a63ba46a39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323383"
---
# <a name="tracing_session_statistics-structure"></a>структура TRACING_SESSION_STATISTICS

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `TRACING_SESSION_STATISTICS` описывает статистические данные о собранном следе. Его поля устанавливаются при остановке сеанса отслеживания.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct TRACING_SESSION_STATISTICS_TAG
{
    unsigned long MSVCEventsLost;
    unsigned long MSVCBuffersLost;
    unsigned long SystemEventsLost;
    unsigned long SystemBuffersLost;

} TRACING_SESSION_STATISTICS;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `MSVCEventsLost` | Количество событий MSVC, которые были удалены. |
| `MSVCBuffersLost` | Количество буферов событий MSVC, которые были удалены. |
| `SystemEventsLost` | Количество системных событий, которые были удалены. |
| `SystemBuffersLost` | Количество буферов событий системы, которые были удалены. |

## <a name="remarks"></a>Примечания

Эта структура заполняется при вызове следующих функций:

- [StopTracingSession](../functions/stop-tracing-session.md)
- [СтопТрейсингИя](../functions/stop-tracing-session-a.md)
- [StopTracingRacingSessionW](../functions/stop-tracing-session-w.md)
- [StopandAnalyzeTracingSession](../functions/stop-and-analyze-tracing-session.md)
- [СтопэндАнализТрейсингЕЯ](../functions/stop-and-analyze-tracing-session-a.md)
- [StopandAnalyzeTracingSessionw](../functions/stop-and-analyze-tracing-session-w.md)
- [СтопАндрелогТрейсингСессия](../functions/stop-and-relog-tracing-session.md)
- [СтопАндрелогТрейсингСея](../functions/stop-and-relog-tracing-session-a.md)
- [СтопАндрелогТрейсингСессияW](../functions/stop-and-relog-tracing-session-w.md)

::: moniker-end
