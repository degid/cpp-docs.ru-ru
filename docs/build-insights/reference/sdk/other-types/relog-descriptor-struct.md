---
title: структура RELOG_DESCRIPTOR
description: Ссылка на структуру СЗ Build Insights SDK RELOG_DESCRIPTOR.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c3aee49fe9f609ca37082693ddcfd5e838cc96a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328941"
---
# <a name="relog_descriptor-structure"></a>структура RELOG_DESCRIPTOR

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `RELOG_DESCRIPTOR` используется с функциями [RelogA](../functions/relog-a.md) и [RelogW.](../functions/relog-w.md) В нем описывается, как следует перезавести отслеживание событий для Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct RELOG_DESCRIPTOR_TAG
{
    unsigned                NumberOfAnalysisPasses;
    ANALYSIS_CALLBACKS      AnalysisCallbacks;
    RELOG_CALLBACKS         RelogCallbacks;
    unsigned long long      SystemEventsRetentionFlags;
    void*                   AnalysisContext;
    void*                   RelogContext;
} RELOG_DESCRIPTOR;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `NumberOfAnalysisPasses` | Количество проходов анализа, которое должно быть сделано по следу ETW на этапе анализа сеанса повторного проведения. |
| `AnalysisCallbacks` | Объект [ANALYSIS_CALLBACKS,](analysis-callbacks-struct.md) который определяет, какие функции можно вызвать на этапе анализа сеанса записи. |
| `RelogCallbacks` | Объект [RELOG_CALLBACKS,](relog-callbacks-struct.md) который определяет, какие функции можно вызвать во время фазы перезаписи сеанса. |
| `SystemEventsRetentionFlags` | Один [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](relog-retention-system-event-flags-constants.md) бит-маски, которая определяет, какая система ETW событий держать в перелогированных след. |
| `AnalysisContext` | Контекст, предоставленный пользователем, который передается в качестве аргумента для всех функций обратного вызова, указанных в`AnalysisCallbacks` |
| `RelogContext` | Контекст, предоставленный пользователем, который передается в качестве аргумента для всех функций обратного вызова, указанных в`RelogCallbacks` |

## <a name="remarks"></a>Примечания

Повторное перезапись событий ETW во время сеанса перезаписи контролируется `RelogCallbacks`пользователем через функции обратного вызова, указанные в. Однако события системы ETW, такие как образцы процессора, не перенаправляются на эти функции обратного вызова. Используйте `SystemEventsRetentionFlags` поле для управления перезаписью системных событий ETW.

Структуры `AnalysisCallbacks` `RelogCallbacks` и структуры принимают только указатели на функции, не являещиеся членами. Вы можете обойти это ограничение, установив их на указатель объекта. Этот указатель объекта будет передан в качестве аргумента всем вашим функциям обратного вызова, не являешься участником. Используйте этот указатель для вызова функций членов из ваших функций обратного вызова, не являваемых членами.

Этап анализа сеанса перезаписи всегда выполняется до этапа перезаписи.

::: moniker-end
