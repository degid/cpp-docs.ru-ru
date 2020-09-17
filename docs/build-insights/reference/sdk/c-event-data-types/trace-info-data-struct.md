---
title: структура TRACE_INFO_DATA
description: Ссылка на структуру СЗ Build Insights SDK TRACE_INFO_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRACE_INFO_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 70ae17a376f79cad7a669d81e482f551afd0ec62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325280"
---
# <a name="trace_info_data-structure"></a>структура TRACE_INFO_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `TRACE_INFO_DATA` описывает анализ или перелогировку трассы.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct TRACE_INFO_DATA_TAG
{
    unsigned long           LogicalProcessorCount;
    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;

} TRACE_INFO_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `LogicalProcessorCount` | Количество логических процессоров на машине, где был собран след. |
| `TickFrequency` | Количество тиков в секунду для использования при оценке продолжительности, измеренной в клещах. |
| `StartTimestamp` | Это поле настроено на значение тика, захваченное во время запуска трассы. |
| `StopTimestamp` | Это поле настроено на значение тика, захваченное во время остановки трассы. |

## <a name="remarks"></a>Примечания

Вычесть `StartTimestamp` `StopTimestamp` из для получения числа клещей, прошедших в течение всего следа. Используйте `TickFrequency` для преобразования полученного значения в единицу времени. Например, что преобразует тиков в единицы времени, [см. EVENT_DATA](event-data-struct.md).

::: moniker-end
