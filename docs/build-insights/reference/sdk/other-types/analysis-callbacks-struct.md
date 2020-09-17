---
title: структура ANALYSIS_CALLBACKS
description: Ссылка на структуру СЗ Build Insights SDK ANALYSIS_CALLBACKS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3c6de999b19657f999f884075ee53e21a4d2f2b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323511"
---
# <a name="analysis_callbacks-structure"></a>структура ANALYSIS_CALLBACKS

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `ANALYSIS_CALLBACKS` используется при инициализации [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md) объекта. В нем указывается, какие функции следует вызывать во время анализа или перезапуска трассировки событий для отслеживания событий для отслеживания Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct ANALYSIS_CALLBACKS_TAG
{
    OnAnalysisEventFunc     OnStartActivity;
    OnAnalysisEventFunc     OnStopActivity;
    OnAnalysisEventFunc     OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginAnalysis;
    OnBeginEndPassFunc      OnEndAnalysis;
    OnBeginEndPassFunc      OnBeginAnalysisPass;
    OnBeginEndPassFunc      OnEndAnalysisPass;
} ANALYSIS_CALLBACKS;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `OnStartActivity` | Вызывается для обработки события начала действия. |
| `OnStopActivity` | Вызывается для обработки события остановки активности. |
| `OnSimpleEvent` | Вызывается для обработки простого события. |
| `OnTraceInfo` | Для анализа сеансов, вызванных в начале каждого анализа, проходят. Для повторного опрокидки сеансов, вызванных в начале каждого анализа, проходите, а также снова в начале перезаписи. Эта функция вызывается только после вызова OnBeginAnalysisPass. |
| `OnBeginAnalysis` | Для анализа сессий, вызванных до начала любого анализа. Для повторного просачивания сеансов, вызванных дважды до начала фазы анализа: один раз объявить о начале сеанса перезаписи и еще раз объявить о начале этапа анализа. |
| `OnEndAnalysis` | Для сеансов анализа эта функция вызывается после окончания всех анализов. Для сеансов повторного заработка эта функция вызывается по окончании всех проходов анализа фазы анализа. Затем он снова вызывается после окончания перезаписи. |
| `OnBeginAnalysisPass` | Вызывается при начале анализа пройти или перезаписи пройти, перед обработкой любого события. |
| `OnEndAnalysisPass` | Вызывается при завершении анализа проходит или пропуск перезаписи, после обработки всех событий. |

## <a name="remarks"></a>Примечания

Этап анализа сеанса перезаписи считается частью сеанса перезаписи и может содержать несколько проходов анализа. По этой `OnBeginAnalysis` причине, вызывается два раза подряд в начале сеанса перезаписи. `OnEndAnalysis`называется в конце фазы анализа, перед началом фазы перезапуска и еще раз в конце фазы перезапуска. Фаза перезарядки всегда содержит один пропуск для перезарядки.

Анализаторы могут быть частью как анализа, так и фазы перезаписи сеанса перезаписи. Эти анализаторы могут определить, какая фаза в настоящее время продолжается, отслеживая onBeginAnalysis и `OnEndAnalysis` пары вызовов. Два `OnBeginAnalysis` вызова `OnEndAnalysis` без вызова означают, что этап анализа продолжается. Два `OnBeginAnalysis` вызова `OnEndAnalysis` и один вызов означает, что этап перезаписи продолжается. Два OnBeginAnalysis `OnEndAnalysis` и два вызова означают, что обе фазы закончились.

Все члены `ANALYSIS_CALLBACKS` структуры должны указать на действительную функцию. Для получения дополнительной информации о принятых подписях функции, см. [OnAnalysisEventFunc](on-analysis-event-func-typedef.md), [OnTraceInfoFunc](on-trace-info-func-typedef.md), и [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
