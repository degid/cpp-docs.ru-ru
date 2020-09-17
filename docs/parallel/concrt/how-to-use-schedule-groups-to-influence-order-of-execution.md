---
title: Практическое руководство. Использование групп планирования для определения порядка выполнения
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups, using [Concurrency Runtime]
- using schedule groups [Concurrency Runtime]
ms.assetid: 73124194-fc3a-491e-a23f-fbd7b5a4455c
ms.openlocfilehash: 84829664603999893f32caab39af250059bf9788
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141919"
---
# <a name="how-to-use-schedule-groups-to-influence-order-of-execution"></a>Практическое руководство. Использование групп планирования для определения порядка выполнения

В среда выполнения с параллелизмом порядок, в котором запланированы задачи, не является детерминированным. Однако политики планирования можно использовать, чтобы повлиять на порядок выполнения задач. В этом разделе показано, как использовать группы расписаний совместно с политикой [параллелизма:: счедулингпротокол](reference/concurrency-namespace-enums.md#policyelementkey) , чтобы повлиять на порядок выполнения задач.

В этом примере набор задач выполняется два раза, каждый из которых имеет отдельную политику планирования. Обе политики ограничивают максимальное число вычислительных ресурсов двумя. При первом запуске используется политика `EnhanceScheduleGroupLocality`, которая используется по умолчанию, а во втором запуске используется политика `EnhanceForwardProgress`. В соответствии с политикой `EnhanceScheduleGroupLocality` планировщик выполняет все задачи в одной группе расписаний до тех пор, пока каждая задача не завершится или не вернется. В соответствии с политикой `EnhanceForwardProgress` планировщик переходит к следующей группе расписаний по принципу циклического перебора после завершения всего одной задачи или ее передачи.

Если каждая группа расписаний содержит связанные задачи, `EnhanceScheduleGroupLocality` политика, как правило, приводит к повышению производительности, так как локальность кэширования между задачами сохраняется. Политика `EnhanceForwardProgress` позволяет выполнять задачи в прямом направлении и полезна, если требуется равномерное планирование по группам расписаний.

## <a name="example"></a>Пример

В этом примере определяется класс `work_yield_agent`, производный от [concurrency::Agent](../../parallel/concrt/reference/agent-class.md). Класс `work_yield_agent` выполняет единицу работы, выдает текущий контекст, а затем выполняет другую единицу работы. Агент использует функцию [concurrency::wait](reference/concurrency-namespace-functions.md#wait) для совместного получения текущего контекста, чтобы можно было выполнять другие контексты.

В этом примере создаются четыре объекта `work_yield_agent`. Чтобы продемонстрировать, как настроить политики планировщика так, чтобы они влияли на порядок запуска агентов, в примере два первых агента связываются с одной группой расписаний и двумя другими агентами с другой группой расписаний. В примере используется метод [concurrency::CurrentScheduler:: CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) для создания объектов [concurrency::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) . В этом примере все четыре агента выполняются два раза, каждый раз с разными политиками планирования.

[!code-cpp[concrt-scheduling-protocol#1](../../parallel/concrt/codesnippet/cpp/how-to-use-schedule-groups-to-influence-order-of-execution_1.cpp)]

В этом примере формируются следующие данные:

```Output
Using EnhanceScheduleGroupLocality...
group 0,
    task 0: first loop...
group 0,
    task 1: first loop...
group 0,
    task 0: waiting...
group 1,
    task 0: first loop...
group 0,
    task 1: waiting...
group 1,
    task 1: first loop...
group 1,
    task 0: waiting...
group 0,
    task 0: second loop...
group 1,
    task 1: waiting...
group 0,
    task 1: second loop...
group 0,
    task 0: finished...
group 1,
    task 0: second loop...
group 0,
    task 1: finished...
group 1,
    task 1: second loop...
group 1,
    task 0: finished...
group 1,
    task 1: finished...

Using EnhanceForwardProgress...
group 0,
    task 0: first loop...
group 1,
    task 0: first loop...
group 0,
    task 0: waiting...
group 0,
    task 1: first loop...
group 1,
    task 0: waiting...
group 1,
    task 1: first loop...
group 0,
    task 1: waiting...
group 0,
    task 0: second loop...
group 1,
    task 1: waiting...
group 1,
    task 0: second loop...
group 0,
    task 0: finished...
group 0,
    task 1: second loop...
group 1,
    task 0: finished...
group 1,
    task 1: second loop...
group 0,
    task 1: finished...
group 1,
    task 1: finished...
```

Обе политики создают одну и ту же последовательность событий. Однако политика, которая использует `EnhanceScheduleGroupLocality`, запускает оба агента, которые являются частью первой группы расписаний, прежде чем запускать агенты, которые являются частью второй группы. Политика, использующая `EnhanceForwardProgress`, запускает один агент из первой группы, а затем запускает первый агент во второй группе.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `scheduling-protocol.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc счедулинг-протокол. cpp**

## <a name="see-also"></a>См. также раздел

[Группы планирования](../../parallel/concrt/schedule-groups.md)<br/>
[Асинхронные агенты](../../parallel/concrt/asynchronous-agents.md)
