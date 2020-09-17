---
title: СтопАндрелогТрейсингСессия
description: Ссылка на функцию функции «СИ Тиз СборкА» SDK StopAndRelogRacingSession.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndRelogTracingSession
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1f6f5af63d25504226707d977791430463374328
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323669"
---
# <a name="stopandrelogtracingsession"></a>СтопАндрелогТрейсингСессия

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `StopAndRelogTracingSession` останавливает текущий сеанс отслеживания и сохраняет полученный след во временном файле. Затем сеанс перезаписи немедленно начинает использовать временный файл в качестве ввода. Окончательный перезаписированный след, производимый сеансом перезаписи, сохраняется в файле, указанном абонентом. Исполнители вызова этой функции должны иметь привилегии администратора.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const char*                                   sessionName,
    const char*                                   outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);

template <
    typename... TAnalyzerGroupMembers,
    typename... TReloggerGroupMembers>
RESULT_CODE StopAndRelogTracingSession(
    const wchar_t*                                sessionName,
    const wchar_t*                                outputLogFile,
    TRACING_SESSION_STATISTICS*                   statistics,
    unsigned                                      numberOfAnalysisPasses,
    unsigned long long                            systemEventsRetentionFlags,
    StaticAnalyzerGroup<TAnalyzerGroupMembers...> analyzerGroup,
    StaticReloggerGroup<TReloggerGroupMembers...> reloggerGroup);
```

### <a name="parameters"></a>Параметры

*sessionName*\
Название сеанса отслеживания, чтобы остановить. Используйте то же имя сеанса, что и имя, которое было передано [StartTracingSession,](start-tracing-session.md) [StartTracingSessionA](start-tracing-session-a.md)или [StartTracingSessionW.](start-tracing-session-w.md)

*выходНопок*\
Файл, в котором можно написать перезаписированный след, созданный сеансом перезаписи.

*Статистика*\
Указатель на [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) объект. `StopAndRelogTracingSession`записывает статистику сбора следов на этом объекте перед возвращением.

*numberOfAnalysisPasses*\
Количество анализов проходит для запуска на следе. След проходит через предоставленную группу анализаторов один раз за анализ.

*системаСобытияУтУдержаниеФлаги*\
Один [RELOG_RETENTION_SYSTEM_EVENT_FLAGS](../other-types/relog-retention-system-event-flags-constants.md) бит-маски, которая определяет, какая система ETW событий держать в перелогированных след.

*анализаторГруппа*\
Группа анализаторов, используемая для фазы анализа сеанса перезаписи. Позвоните [MakeStaticAnalyzerGroup,](make-static-analyzer-group.md) чтобы создать группу анализаторов. Если вы хотите использовать динамическую группу анализаторов, полученную от [MakeDynamicAnalyzerGroup,](make-dynamic-analyzer-group.md)сначала инкапсулируйте `MakeStaticAnalyzerGroup`его внутри группы статического анализатора, передав его адрес .

*reloggerGroup*\
Группа перелогов, которая переобораживает события в файл трассировки, указанный в *outputLogFile.* Позвоните [MakeStaticReloggerGroup,](make-static-relogger-group.md) чтобы создать группу перелогов. Если вы хотите использовать динамическую группу перелоггеров, полученную от [MakeDynamicReloggerGroup,](make-dynamic-relogger-group.md)сначала инкапсулируйте `MakeStaticReloggerGroup`ее внутри статической группы перелоггеров, передав свой адрес .

### <a name="return-value"></a>Возвращаемое значение

Код результата из [RESULT_CODE](../other-types/result-code-enum.md) enum.

### <a name="remarks"></a>Примечания

Вхотовый след проходит через номер группы *анализатораOfAnalysisPasses* раз. Аналогичной опции для перезаписи пропусков нет. След передается корыта relogger группы только один раз, после того, как все анализ проходит завершены.

Повторная запись системных событий, таких как образцы процессора из класса relogger, не поддерживается. Используйте параметр *systemEventsRetentionFlags,* чтобы решить, какие события системы следует держать в выходном следе.

::: moniker-end
