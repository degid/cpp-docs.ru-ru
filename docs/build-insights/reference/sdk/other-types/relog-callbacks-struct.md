---
title: структура RELOG_CALLBACKS
description: Ссылка на структуру СЗ Build Insights SDK RELOG_CALLBACKS.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RELOG_CALLBACKS
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 60e7db81a48731090a23b82332704a79a51e97df
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328972"
---
# <a name="relog_callbacks-structure"></a>структура RELOG_CALLBACKS

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `RELOG_CALLBACKS` используется при инициализации [RELOG_DESCRIPTOR](relog-descriptor-struct.md) объекта. В нем указывается, какие функции следует вызывать во время повторного отслеживания событий для отслеживания событий для отслеживания Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct RELOG_CALLBACKS_TAG
{
    OnRelogEventFunc        OnStartActivity;
    OnRelogEventFunc        OnStopActivity;
    OnRelogEventFunc        OnSimpleEvent;
    OnTraceInfoFunc         OnTraceInfo;
    OnBeginEndPassFunc      OnBeginRelogging;
    OnBeginEndPassFunc      OnEndRelogging;
    OnBeginEndPassFunc      OnBeginReloggingPass;
    OnBeginEndPassFunc      OnEndReloggingPass;
} RELOG_CALLBACKS;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `OnStartActivity` | Вызывается для обработки события начала действия. |
| `OnStopActivity` | Вызывается для обработки события остановки активности. |
| `OnSimpleEvent` | Вызывается для обработки простого события. |
| `OnTraceInfo` | Вызывается один раз в начале `OnBeginReloggingPass` перезаписи прохода, после был вызван. |
| `OnBeginRelogging` | Вызывается при начале сеанса перезаписи, до начала перезаписи. |
| `OnEndRelogging` | Вызывается при завершении сеанса перезаписи после окончания пропуска. |
| `OnBeginReloggingPass` | Вызывается при начале перезаписи пройти, перед обработкой любого события. |
| `OnEndReloggingPass` | Вызывается при окончании перезаписи, после обработки всех событий. |

## <a name="remarks"></a>Примечания

Все члены `RELOG_CALLBACKS` структуры должны указать на действительную функцию. Для получения дополнительной информации о принятых подписях функции, см. [OnRelogEventFunc](on-relog-event-func-typedef.md), [OnTraceInfoFunc](on-trace-info-func-typedef.md), и [OnBeginEndPassFunc](on-begin-end-pass-func-typedef.md).

::: moniker-end
