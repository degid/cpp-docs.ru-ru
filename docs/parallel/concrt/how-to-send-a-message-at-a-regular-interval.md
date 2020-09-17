---
title: Практическое руководство. Отправка сообщений через определенные интервалы
ms.date: 11/04/2016
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
ms.openlocfilehash: c51a5cab6fcae5eb45b9d9b54c0dad8e8ec393b2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142464"
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Практическое руководство. Отправка сообщений через определенные интервалы

В этом примере показано, как использовать класс Concurrency::[Timer](../../parallel/concrt/reference/timer-class.md) для отправки сообщения через обычный интервал.

## <a name="example"></a>Пример

В следующем примере объект `timer` используется для сообщения о ходе выполнения во время длительной операции. В этом примере объект `timer` связывается с объектом [concurrency::Call](../../parallel/concrt/reference/call-class.md) . Объект `call` выводит индикатор хода выполнения на консоль с постоянным интервалом. Метод [concurrency::Timer:: Start](reference/timer-class.md#start) запускает таймер в отдельном контексте. Функция `perform_lengthy_operation` вызывает функцию [concurrency::wait](reference/concurrency-namespace-functions.md#wait) в основном контексте для имитации длительной операции.

[!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]

В этом примере выводится следующий пример выходных данных:

```Output
Performing a lengthy operation..........done.
```

## <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `report-progress.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

> **CL. exe/EHsc репорт-прогресс. cpp**

## <a name="see-also"></a>См. также раздел

[Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Функции передачи сообщений](../../parallel/concrt/message-passing-functions.md)
