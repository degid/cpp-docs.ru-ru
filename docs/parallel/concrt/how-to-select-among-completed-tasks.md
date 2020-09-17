---
title: Практическое руководство. Выбор среди завершенных задач
ms.date: 11/04/2016
helpviewer_keywords:
- selecting among completed tasks [Concurrency Runtime]
- completed tasks, selecting among [Concurrency Runtime]
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
ms.openlocfilehash: fd9940dad0cd2f202bdc734a81a7eb37cd79420c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226728"
---
# <a name="how-to-select-among-completed-tasks"></a>Практическое руководство. Выбор среди завершенных задач

В этом примере показано, как использовать классы [concurrency::Choice](../../parallel/concrt/reference/choice-class.md) и [concurrency::Join](../../parallel/concrt/reference/join-class.md) , чтобы выбрать первую задачу для завершения алгоритма поиска.

## <a name="example"></a>Пример

В следующем примере параллельно выполняются два алгоритма поиска и выбирается первый алгоритм для завершения. В этом примере определяется `employee` тип, содержащий числовой идентификатор и зарплату для сотрудника. `find_employee`Функция находит первого сотрудника с указанным идентификатором или заработной платой. `find_employee`Функция также обрабатывает случай, когда ни один из сотрудников не имеет указанного идентификатора или зарплаты. `wmain`Функция создает массив `employee` объектов и ищет несколько значений идентификатора и зарплаты.

В примере объект используется `choice` для выбора из следующих вариантов:

1. Сотрудник с указанным идентификатором существует.

1. Сотрудник, имеющий указанную зарплату, существует.

1. Не существует сотрудника с указанным идентификатором или зарплатой.

В первых двух случаях в примере используется объект [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) для хранения идентификатора и другой `single_assignment` объект для хранения зарплаты. В примере используется `join` объект для третьего случая. `join`Объект состоит из двух дополнительных `single_assignment` объектов: один для случая, когда не существует сотрудника с указанным идентификатором, и один для случая, когда сотрудник с указанной зарплатой не существует. `join`Объект отправляет сообщение, когда каждый из его членов получает сообщение. В этом примере `join` объект отправляет сообщение, когда не существует сотрудника с указанным идентификатором или зарплатой.

В примере используется объект [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) для параллельного выполнения обоих алгоритмов поиска. Каждая задача поиска записывает в один из `single_assignment` объектов, чтобы указать, существует ли данный сотрудник. В примере используется функция [concurrency::Receive](reference/concurrency-namespace-functions.md#receive) , чтобы получить индекс первого буфера, содержащего сообщение, и **`switch`** блок для вывода результата.

[!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/cpp/how-to-select-among-completed-tasks_1.cpp)]

В этом примере формируются следующие данные:

```Output
Employee with id 14758 has salary 27780.00.
Employee with salary 29150.00 has id 84345.
Employee with id 61935 has salary 29905.00.
No employee has id 899 or salary 31223.00.
```

В этом примере используется вспомогательная функция [concurrency::make_choice](reference/concurrency-namespace-functions.md#make_choice) для создания `choice` объектов и вспомогательная функция [concurrency::make_join](reference/concurrency-namespace-functions.md#make_join) для создания `join` объектов.

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем, `find-employee.cpp` а затем выполните следующую команду в окне командной строки Visual Studio.

> **cl.exe/EHsc ФИНД-емплойи. cpp**

## <a name="see-also"></a>См. также статью

[библиотеку асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)<br/>
[Класс choice](../../parallel/concrt/reference/choice-class.md)<br/>
[Класс join](../../parallel/concrt/reference/join-class.md)
