---
title: "Развертывание, запуск и отладка проекта Linux | Документы Майкрософт"
ms.custom: 
ms.date: 11/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 237b6f3dbca8d529362a545f67ee0db4f9770d8d
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2017
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Развертывание, запуск и отладка проекта Linux

После создания проекта Linux и подключения к проекту с помощью [диспетчера соединений Linux](../linux/connect-to-your-remote-linux-computer.md) можно запускать и отлаживать проект. Компиляция, выполнение и отладка кода осуществляются в удаленной системе.

Существует несколько способов взаимодействия с проектом Linux и его отладки.

* Использование традиционных средств Visual Studio, таких как точки останова, окна контрольных значений и наведение указателя мыши на переменную. С их помощью вы можете выполнять отладку так, как вы делаете это для других типов проектов.
* Просмотр выходных данных с целевого компьютера в специальном окне "Консоль Linux". Консоль можно также использовать для отправки входных данных на целевой компьютер.

## <a name="debug-your-linux-project"></a>Отладка проекта Linux

1. Выберите режим отладки на странице свойств **Отладка**.

    GDB используется для отладки приложений на платформе Linux.  Однако он может работать в двух разных режимах, которые выбираются в параметре **Режим отладки** на странице свойств **Отладка** проекта:

    ![Параметры GDB](media/settings_debugger.png)

    - В режиме **gdbserver** GDB выполняется в локальной среде, подключенной к gdbserver, работающем в удаленной системе.  Обратите внимание, что это единственный режим, который поддерживает окно консоли Linux.

    - В режиме **gdb** отладчик Visual Studio управляет GDB в удаленной системе, что более приемлемо, если локальная версия GDB несовместима с версией, установленной на целевом компьютере. |

    > [!NOTE] 
    > Если не удается попасть в точки останова в режиме отладки gdbserver, попробуйте gdb режим. gdb сначала следует [установить](../linux/download-install-and-setup-the-linux-development-workload.md) в удаленной целевой системе.

2. Выберите удаленную целевую систему, используя стандартную панель инструментов **Отладка** в Visual Studio.

    Если удаленная целевая система доступна, вы определите ее по имени или IP-адресу.

    ![Удаленная целевая система](media/remote_target.png)

    Если вы еще не подключились к удаленной целевой системе, вы увидите инструкции по использованию [диспетчера подключений Linux](../linux/connect-to-your-remote-linux-computer.md) для подключения к удаленной целевой системе.

    ![Удаленная архитектура](media/architecture.png)

3. Задайте точку останова, щелкнув в левом поле код, который будет выполняться.

    В строке кода, где вы задали точку останова, появится красная точка.

4. Нажмите клавишу **F5** (или **Отладка > Начать отладку**), чтобы начать отладку.

    При запуске отладки приложение компилируется на удаленном целевом компьютере и после этого запускается. Ошибки компиляции будут показаны в окне **Список ошибок**.

    Если ошибок нет, приложение запустится, и по достижении точки останова отладчик остановится.

    ![Попадание в точку останова](media/hit_breakpoint.png)  

    Теперь можно работать с приложением в его текущем состоянии, просматривать переменные и пошагово выполнять код, нажимая командные клавиши, такие как **F10** или **F11**.

4. Если для взаимодействия с приложением вы хотите использовать консоль Linux, выберите **Отладка > Консоль Linux**.

  ![Меню "Консоль Linux"](media/consolemenu.png)

  Эта консоль отображает выходные данные консоли с целевого компьютера, а также принимает входные данные и отправляет их на целевой компьютер.

  ![Окно "Консоль Linux"](media/consolewindow.png)

## <a name="configure-other-debugging-options"></a>Настройка других параметров отладки

* Аргументы командной строки можно передать в исполняемый файл с помощью элемента **Аргументы программы** на странице свойств **Отладка** проекта.
  
  ![Аргументы командной строки программы](media/settings_programarguments.png)

* Специальные параметры отладчика можно передать в GDB с помощью записи **Дополнительные команды отладчика**.  Например, можно игнорировать сигналы SIGILL (недопустимая инструкция).  Для этого можно использовать команду **handle**.  добавляя следующее в запись **Дополнительные команды отладчика**, как показано выше:

  ```handle SIGILL nostop noprint```

## <a name="see-also"></a>См. также
[Свойства отладки C++ (Linux C++)](../linux/prop-pages/debugging-linux.md).