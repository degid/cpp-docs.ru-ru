---
title: Структура EVENT_DATA
description: Справочник по структуре EVENT_DATA из пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 468fc30d337e5cfc5ab90f7558904fc90588c3df
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041826"
---
# <a name="event_data-structure"></a>Структура EVENT_DATA

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `EVENT_DATA` описывает событие, полученное из сеанса анализа или повторной записи в журнал. Для запуска такого сеанса вызовите функцию [Analyze](../functions/analyze.md), [AnalyzeA](../functions/analyze-a.md), [AnalyzeW](../functions/analyze-w.md), [Relog](../functions/relog.md), [RelogA](../functions/relog-a.md) или [RelogW](../functions/relog-w.md).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct EVENT_DATA_TAG
{
    unsigned short          EventId;
    unsigned long long      EventInstanceId;

    long long               TickFrequency;
    long long               StartTimestamp;
    long long               StopTimestamp;
    long long               ExclusiveDurationTicks;
    long long               CPUTicks;
    long long               ExclusiveCPUTicks;
    long long               WallClockTimeResponsibilityTicks;
    long long               ExclusiveWallClockTimeResponsibilityTicks;

    const void*             Data;

    unsigned long           ProcessId;
    unsigned long           ThreadId;
    unsigned short          ProcessorIndex;

    const char*             EventName;
    const wchar_t*          EventWideName;

} EVENT_DATA;
```

## <a name="members"></a>Участники

| Имя | Описание |
|--|--|
| `EventId` | Числовое значение, которое идентифицирует событие. Список идентификаторов можно узнать в справочнике по [EVENT_ID](event-id-enum.md). |
| `EventInstanceId` | Это число, которое уникальным образом идентифицирует текущее событие в пределах трассировки. Это значение не изменяется при многократном анализе или повторной записи одной и той же трассировки. Это поле можно применять для идентификации одного события при нескольких этапах анализа или повторной записи для одной трассировки. |
| `TickFrequency` | Количество тактов в секунду, которое используется при оценке длительности, изменяемой в тактах. |
| `StartTimestamp` | Если событие имеет тип *Activity* (Действие), в этом поле сохраняется значение тактов, захваченное в момент запуска действия. Если событие имеет тип *Simple Event* (Простое событие), в этом поле сохраняется значение тактов, захваченное в момент создания этого события. |
| `StopTimestamp` | Если событие имеет тип *Activity* (Действие), в этом поле сохраняется значение тактов, захваченное в момент остановки действия. Если событие завершения для этого действия еще не было получено, это поле имеет нулевое значение. Если событие имеет тип *Simple Event* (Простое событие), это поле имеет нулевое значение. |
| `ExclusiveDurationTicks` | Если событие имеет тип *Activity* (Действие), в этом поле сохраняется количество тактов, прошедших за время выполнения действия. Из него исключается число тактов, прошедших при выполнении дочернего действия. Для типа *Simple Event* (Простое событие) это поле имеет нулевое значение. |
| `CPUTicks` | Если событие имеет тип *Activity* (Действие), в этом поле сохраняется количество тактов ЦП, прошедших за время выполнения действия. Такт ЦП отличается от обычного такта. Такты ЦП учитываются только тогда, когда ЦП исполняет код в этом действии. Такты ЦП не учитываются, пока связанный с действием поток находится в спящем режиме. Для типа *Simple Event* (Простое событие) это поле имеет нулевое значение. |
| `ExclusiveCPUTicks` | Это поле аналогично `CPUTicks`, за исключением того, что здесь не учитываются такты ЦП для действий дочерних элементов. Для типа *Simple Event* (Простое событие) это поле имеет нулевое значение. |
| `WallClockTimeResponsibilityTicks` | Если событие имеет тип *Activity* (Действие), в этом поле сохраняется количество тактов, представляющее вклад этого действия в общее реальное время выполнения. Такт реального времени выполнения часах отличается от обычного такта. В тактах реального времени выполнения учитывается параллелизм при выполнении действий. Предположим, что два действия выполняются параллельно и имеют длительность 50 тактов, а также идентичное время начала и завершения. В этом случае обоим процессам будет присвоено значение 25 тактов реального времени. Для типа *Simple Event* (Простое событие) это поле имеет нулевое значение. |
| `ExclusiveWallClockTimeResponsibilityTicks` | Это поле имеет то же значение, что и `WallClockTimeResponsibilityTicks`, но не включает такты реального времени для дочерних действий. Для типа *Simple Event* (Простое событие) это поле имеет нулевое значение. |
| `Data` | Указывает на дополнительные данные, хранимые в текущем событии. Тип данных, на которые он указывает, может быть разным в зависимости от поля `EventId`. |
| `ProcessId` | Идентификатор процесса, в котором возникло текущее событие. |
| `ThreadId` | Идентификатор потока, в котором возникло текущее событие. |
| `ProcessorIndex` | Номер ЦП, начиная с нуля, в котором возникло текущее событие. |
| `EventName` | Строка ANSI с именем сущности, определяемая по `EventId`. |
| `EventWideName` | Широкая строка с именем сущности, определяемая по `EventId`. |

## <a name="remarks"></a>Примечания

Многие поля в `EVENT_DATA` содержат счетчики тактов. Аналитика сборки C++ использует в качестве источника тактов счетчик производительности Windows. Чтобы преобразовать значение счетчика в традиционные единицы времени (например, в секунды), используйте его в сочетании со значением поля `TickFrequency`. Пример такого преобразования приводится ниже. `EVENT_DATA` не содержит поля с простым значением количества тактов для действия. Чтобы получить это значение, вычтите `StartTimestamp` из `StopTimestamp`. Структура `EVENT_DATA` предназначена для использования пользователями API для C. Для пользователей API для C++ такие классы, как [Event](../cpp-event-data-types/event.md), выполняют преобразование времени автоматически.

Значение поля `EVENT_DATA` `Data` зависит от значения поля `EventId`. Значение поля `Data` описывается в таблице ниже. Некоторые идентификаторы сущностей могут отсутствовать в таблице ниже. В этом случае поле `Data` имеет значение **`nullptr`** или 0.

| Значение `EventId` | Тип, на который указывает `Data` |
|--|--|
| `EVENT_ID_BACK_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_COMMAND_LINE` | `const wchar_t` |
| `EVENT_ID_COMPILER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_ENVIRONMENT_VARIABLE` | [NAME_VALUE_PAIR_DATA](name-value-pair-data-struct.md) |
| `EVENT_ID_EXECUTABLE_IMAGE_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_EXP_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FILE_INPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_FORCE_INLINE` | [FUNCTION_FORCE_INLINEE_DATA](function-force-inlinee-data-struct.md) |
| `EVENT_ID_FRONT_END_FILE` | [FRONT_END_FILE_DATA](front-end-file-data-struct.md) |
| `EVENT_ID_FRONT_END_PASS` | [CL_PASS_DATA](cl-pass-data-struct.md) |
| `EVENT_ID_FUNCTION` | [FUNCTION_DATA](function-data-struct.md) |
| `EVENT_ID_IMP_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LIB_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_LINKER` | [INVOCATION_DATA](invocation-data-struct.md) |
| `EVENT_ID_OBJ_OUTPUT` | [FILE_DATA](file-data-struct.md) |
| `EVENT_ID_SYMBOL_NAME` | [SYMBOL_NAME_DATA](symbol-name-data-struct.md) |
| `EVENT_ID_TEMPLATE_INSTANTIATION` | [TEMPLATE_INSTANTIATION_DATA](template-instantiation-data-struct.md) |

## <a name="tick-conversion-example"></a>Пример преобразования тактов

```cpp
//
// We have the elapsed number of ticks, along with the
// number of ticks per second. We use these values
// to convert to the number of elapsed microseconds.
// To guard against loss-of-precision, we convert
// to microseconds *before* dividing by ticks-per-second.
//

long long ConvertDurationToMicroseconds(const sruct EVENT_DATA& eventData)
{
    long long duration = eventData.StopTimestamp - eventData.StartTimestamp;
    long long duration *= 1000000;
    return duration / eventData.TickFrequency;
}
```

::: moniker-end
