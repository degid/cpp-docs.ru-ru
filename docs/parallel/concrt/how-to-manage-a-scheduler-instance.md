---
title: Практическое руководство. Управление экземпляром планировщика
ms.date: 11/04/2016
helpviewer_keywords:
- managing a scheduler instance [Concurrency Runtime]
- scheduler instances, managing [Concurrency Runtime]
ms.assetid: 2cc804f0-5ff3-498b-97f1-a9f67a005448
ms.openlocfilehash: c7ec321eaf0960dc14b61bbd8fdc76b53a31f8c5
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141716"
---
# <a name="how-to-manage-a-scheduler-instance"></a>Практическое руководство. Управление экземпляром планировщика

Экземпляры планировщика позволяют связать определенные политики планирования с различными типами рабочих нагрузок. Этот раздел содержит два основных примера, демонстрирующих создание экземпляра планировщика и управление им.

В примерах создаются планировщики, использующие политики планировщика по умолчанию. Пример создания планировщика, использующего настраиваемую политику, см. в разделе [как указать конкретные политики планировщика](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).

## <a name="to-manage-a-scheduler-instance-in-your-application"></a>Управление экземпляром планировщика в приложении

1. Создайте объект [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) , содержащий значения политики для использования планировщиком.

1. Вызовите метод [concurrency::CurrentScheduler:: Create](reference/currentscheduler-class.md#create) или метод [concurrency::Scheduler:: Create](reference/scheduler-class.md#create) , чтобы создать экземпляр планировщика.

   Если используется метод `Scheduler::Create`, вызовите метод [concurrency::Scheduler:: Attach](reference/scheduler-class.md#attach) , если необходимо связать планировщик с текущим контекстом.

1. Вызовите функцию [CreateEvent](/windows/win32/api/synchapi/nf-synchapi-createeventw) , чтобы создать дескриптор для объекта события, не поддерживающего сигнал, для автоматического сброса.

1. Передайте созданный объект события в метод [concurrency::CurrentScheduler:: регистершутдовневент](reference/currentscheduler-class.md#registershutdownevent) или метод [concurrency::Scheduler:: регистершутдовневент](reference/scheduler-class.md#registershutdownevent) . Он регистрирует событие, которое должно быть задано при уничтожении планировщика.

1. Выполните задачи, которые должен запланировать текущий планировщик.

1. Вызовите метод [concurrency::CurrentScheduler::D етач](reference/currentscheduler-class.md#detach) , чтобы отсоединить текущий планировщик и восстановить предыдущий планировщик в качестве текущего.

   При использовании метода `Scheduler::Create` вызовите метод [concurrency::Scheduler:: Release](reference/scheduler-class.md#release) , чтобы уменьшить число ссылок объекта `Scheduler`.

1. Передайте этот обработчик в функцию [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) , чтобы дождаться завершения работы планировщика.

1. Вызовите функцию [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) , чтобы закрыть маркер объекта события.

## <a name="example"></a>Пример

В следующем коде показаны два способа управления экземпляром планировщика. В каждом примере сначала используется планировщик по умолчанию для выполнения задачи, которая выводит уникальный идентификатор текущего планировщика. Затем в каждом примере используется экземпляр планировщика для выполнения той же задачи. Наконец, каждый пример восстанавливает планировщик по умолчанию в качестве текущего и выполняет задачу еще раз.

В первом примере класс [concurrency::CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) используется для создания экземпляра планировщика и связывания его с текущим контекстом. Во втором примере класс [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) используется для выполнения той же задачи. Как правило, класс `CurrentScheduler` используется для работы с текущим планировщиком. Второй пример, использующий класс `Scheduler`, полезен, если требуется управлять тем, когда планировщик связан с текущим контекстом, или когда требуется связать определенные планировщики с конкретными задачами.

[!code-cpp[concrt-scheduler-instance#1](../../parallel/concrt/codesnippet/cpp/how-to-manage-a-scheduler-instance_1.cpp)]

В этом примере формируются следующие данные:

```Output
Using CurrentScheduler class...

Current scheduler id: 0
Creating and attaching scheduler...
Current scheduler id: 1
Detaching scheduler...
Current scheduler id: 0

Using Scheduler class...

Current scheduler id: 0
Creating scheduler...
Attaching scheduler...
Current scheduler id: 2
Detaching scheduler...
Current scheduler id: 0
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `scheduler-instance.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc счедулер-инстанце. cpp**

## <a name="see-also"></a>См. также раздел

[Экземпляры планировщика](../../parallel/concrt/scheduler-instances.md)<br/>
[Практическое руководство. Задание определенных политик планировщика](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)
