---
title: Пошаговое руководство. создание традиционного классического приложения Windows (C++)
description: Создание минимального традиционного классического приложения Windows с помощью Visual Studio, C++ и API Win32
ms.custom: get-started-article
ms.date: 05/28/2020
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: 01b1f4a1d021dee6d1d7afbf55bbd13211af247d
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686604"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>Пошаговое руководство. создание традиционного классического приложения Windows (C++)

В этом пошаговом руководстве показано, как создать традиционное классическое приложение Windows в Visual Studio. В примере приложения, которое вы создадите, будет использоваться API Windows для вывода "Hello, Windows Desktop!" "Hello, World!". Код, созданный в этом пошаговом руководстве, можно использовать в качестве шаблона для создания других классических приложений Windows.

API Windows (также известный как API Win32, Windows Desktop API и Windows Classic API) — это платформа на основе языка C для создания приложений Windows. Он уже существует, так как 1980-х и использовался для создания приложений Windows в течение десятилетий. Более сложные и удобные платформы были построены поверх Windows API. Например, MFC, ATL, .NET Frameworks. Даже самый современный код среда выполнения Windows для приложений UWP и Store, написанных на C++/WinRT, использует API Windows под. Дополнительные сведения об API Windows см. в разделе [индекс Windows API](/windows/win32/apiindex/windows-api-list). Существует множество способов создания приложений Windows, но описанный выше процесс был первым.

> [!IMPORTANT]
> Для краткости в тексте пропущены некоторые операторы кода. В разделе [Построение кода](#build-the-code) в конце документа показан полный код.

## <a name="prerequisites"></a>Предварительные требования

- Компьютер под управлением Microsoft Windows 7 или более поздних версий. Для обеспечения оптимальной среды разработки рекомендуется использовать Windows 10.

- Копия Visual Studio. Сведения о скачивании и установке Visual Studio см. в [этой статье](/visualstudio/install/install-visual-studio). Когда вы запускаете установщик, убедитесь, что установлена рабочая нагрузка **Разработка классических приложений на C++** . Не беспокойтесь, если вы не установили эту рабочую нагрузку при установке Visual Studio. Вы можете снова запустить установщик и установить ее сейчас.

   ![Разработка классических приложений на C++](../build/media/desktop-development-with-cpp.png "Разработка классических приложений на C++")

- Базовые значения об использовании интегрированной среды разработки Visual Studio. Если вы уже использовали классические приложения для Windows, вы, вероятно, справитесь. Общие сведения см. в [обзоре возможностей интегрированной среды разработки Visual Studio](/visualstudio/ide/visual-studio-ide).

- Основные навыки владения языком C++. Не волнуйтесь, мы не будем делать ничего сложного.

## <a name="create-a-windows-desktop-project"></a>Создание проекта для настольных систем Windows

Выполните следующие действия, чтобы создать свой первый проект для настольных систем Windows. В процессе работы вы вводите код для рабочего приложения Windows. Чтобы ознакомиться с документацией по предпочтительной версии Visual Studio, используйте селектор **Версия**. Он находится в верхней части оглавления на этой странице.

::: moniker range="vs-2019"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2019"></a>Создание проекта для классических приложений Windows в Visual Studio 2019

1. В главном меню выберите **Файл** > **Создать** > **Проект**, чтобы открыть диалоговое окно **Создание проекта**.

1. В верхней части диалогового окна задайте для параметра **язык** значение **C++**, задайте для параметра **платформа** значение **Windows**и задайте для параметра **тип проекта** значение **Рабочий стол**.

1. В отфильтрованном списке типов проектов выберите **Мастер рабочего стола Windows** , а затем нажмите кнопку **Далее**. На следующей странице введите имя проекта, например *десктопапп*.

1. Нажмите кнопку **Создать**, чтобы создать проект.

1. Откроется диалоговое окно **проекта Windows Desktop** . В разделе **Тип приложения**выберите **классическое приложение (. exe)**. В поле **Дополнительные параметры**выберите **Пустой проект**. Нажмите кнопку **ОК**, чтобы создать проект.

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект **Десктопапп** , выберите **Добавить**, а затем выберите **новый элемент**.

   ![Короткое видео, показывающее, что пользователь добавляет новый элемент в проект Десктопапп в Visual Studio 2019.](../build/media/desktop-app-project-add-new-item-153.gif "Добавить новый элемент в проект Десктопапп")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В поле **имя** введите имя файла, например *хелловиндовсдесктоп. cpp*. Выберите **Добавить**.

   ![Снимок экрана: диалоговое окно "Добавление нового элемента" в Visual Studio 2019 с установленным > Visual C плюс плюс, а также выбранный параметр C плюса/д файла.](../build/media/desktop-app-add-cpp-file-153.png "Добавить CPP файл в проект Десктопапп")

Теперь проект создан и исходный файл открыт в редакторе. Чтобы продолжить, перейдите к [созданию кода](#create-the-code).

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017"></a>Создание проекта для классических приложений Windows в Visual Studio 2017

1. В меню **Файл** выберите команду **Создать**, а затем пункт **Проект**.

1. В левой области диалогового окна **Новый проект** разверните узел **установленные**  >  **Visual C++**, а затем выберите пункт **Windows Desktop**. В средней области выберите **Мастер рабочего стола Windows**.

   В поле **имя** введите имя проекта, например *десктопапп*. Нажмите кнопку **ОК**.

   ![Снимок экрана: диалоговое окно "новый проект" в Visual Studio 2017 с установленным > Visual C плюсом > Windows Desktop, выбранный параметр "Мастер настольных систем Windows" и Десктопапп, введенное в текстовое поле "имя".](../build/media/desktop-app-new-project-name-153.png "Назовите проект Десктопапп.")

1. В диалоговом окне **проект Windows Desktop** в разделе **Тип приложения**выберите **приложение Windows (. exe)**. В поле **Дополнительные параметры**выберите **Пустой проект**. Убедитесь, что **предварительно скомпилированный заголовок** не выбран. Нажмите кнопку **ОК**, чтобы создать проект.

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект **Десктопапп** , выберите **Добавить**, а затем выберите **новый элемент**.

   ![Короткое видео, показывающее, что пользователь добавляет новый элемент в проект Десктопапп в Visual Studio 2017.](../build/media/desktop-app-project-add-new-item-153.gif "Добавить новый элемент в проект Десктопапп")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В поле **имя** введите имя файла, например *хелловиндовсдесктоп. cpp*. Выберите **Добавить**.

   ![Снимок экрана: диалоговое окно "Добавление нового элемента" в Visual Studio 2017 с установленным > Visual C плюс плюс, а также выбранный параметр C плюса/д файла.](../build/media/desktop-app-add-cpp-file-153.png "Добавить CPP файл в проект Десктопапп")

Теперь проект создан и исходный файл открыт в редакторе. Чтобы продолжить, перейдите к [созданию кода](#create-the-code).

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2015"></a>Создание проекта для классических приложений Windows в Visual Studio 2015

1. В меню **Файл** выберите команду **Создать**, а затем пункт **Проект**.

1. В левой области диалогового окна **Новый проект** разверните узел **установленные**  >  **шаблоны**  >  **Visual C++**, а затем выберите пункт **Win32**. В средней области выберите шаблон **Проект Win32**.

   В поле **имя** введите имя проекта, например *десктопапп*. Нажмите кнопку **ОК**.

   ![Снимок экрана: диалоговое окно "новый проект" в Visual Studio 2015 с установленными шаблонами > > Visual C плюсом > Win32, выделенным параметром проекта Win32 и Десктопапп, введенным в текстовом поле "имя".](../build/media/desktop-app-new-project-name-150.png "Назовите проект Десктопапп.")

1. На странице **Обзор** **мастера приложений Win32**нажмите кнопку **Далее**.

   ![Обзор мастера создания Десктопапп в приложении Win32](../build/media/desktop-app-win32-wizard-overview-150.png "Обзор мастера создания Десктопапп в приложении Win32")

1. На странице **Параметры приложения** в разделе **Тип приложения**выберите пункт **приложение Windows**. В разделе **Дополнительные параметры**снимите флажок **предкомпилированный заголовок**, а затем выберите **пустой проект**. Чтобы создать проект, нажмите кнопку **Готово**.

1. В **Обозреватель решений**щелкните правой кнопкой мыши проект десктопапп, выберите **Добавить**, а затем выберите **новый элемент**.

   ![Короткое видео, показывающее, что пользователь добавляет новый элемент в проект Десктопапп в Visual Studio 2015.](../build/media/desktop-app-project-add-new-item-150.gif "Добавить новый элемент в проект Десктопапп")

1. В диалоговом окне **Добавление нового элемента** выберите **Файл C++ (.cpp)**. В поле **имя** введите имя файла, например *хелловиндовсдесктоп. cpp*. Выберите **Добавить**.

   ![Снимок экрана: диалоговое окно "Добавление нового элемента" в Visual Studio 2015 с установленным > Visual C плюс плюс, а также выбранный параметр C плюса/д файла.](../build/media/desktop-app-add-cpp-file-150.png "Добавить CPP файл в проект Десктопапп")

Теперь проект создан и исходный файл открыт в редакторе.

::: moniker-end

## <a name="create-the-code"></a>Создание кода

Далее вы узнаете, как создать код для классического приложения Windows в Visual Studio.

### <a name="to-start-a-windows-desktop-application"></a>Запуск классического приложения Windows

1. Точно так же, как каждое приложение C и приложение C++ должно иметь `main` функцию в качестве отправной точки, каждое классическое приложение Windows должно иметь `WinMain` функцию. `WinMain` имеет следующий синтаксис:

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Сведения о параметрах и возвращаемом значении этой функции см. в разделе [WinMain Entry Point](/windows/win32/api/winbase/nf-winbase-winmain).

   > [!NOTE]
   > Что такое дополнительные слова, такие как, или `CALLBACK` `HINSTANCE` , или `_In_` ? Традиционные API Windows часто используют определения типов и макросов препроцессора для абстракции некоторых сведений о типах и кода для конкретной платформы, таких как соглашения о вызовах, **`__declspec`** объявления и директивы pragma компилятора. В Visual Studio можно использовать функцию " [быстрые сведения](/visualstudio/ide/using-intellisense#quick-info) " IntelliSense, чтобы увидеть, что определяются этими определениями и макросами. Наведите указатель мыши на интересующую слово или выберите его и нажмите клавиши **CTRL** + **K**, **CTRL** + **I** для небольшого всплывающего окна, содержащего определение. Дополнительные сведения см. в разделе [Using IntelliSense](/visualstudio/ide/using-intellisense). Параметры и возвращаемые типы часто используют *аннотации SAL* , чтобы помочь в перехвате ошибок программирования. Дополнительные сведения см. [в разделе Использование аннотаций SAL для сокращения числа дефектов кода C/C++](/cpp/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).

1. Для настольных программ Windows требуется &lt;> Windows.h. &lt;в файле Tchar.h> определен `TCHAR` макрос, который в конечном итоге разрешается в, **`wchar_t`** Если в проекте ОПРЕДЕЛЕН символ Юникода, в противном случае — значение **`char`** .  Если вы всегда создаете Юникод с включенным параметром UNICODE, то не нужно использовать TCHAR и может быть просто использоваться **`wchar_t`** напрямую.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. Наряду с `WinMain` функцией, каждое классическое приложение Windows также должно иметь функцию Window-PROCEDURE. Эта функция обычно называется `WndProc` , но вы можете назвать ее по своему усмотрению. `WndProc` имеет следующий синтаксис:

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hWnd,
      _In_ UINT   message,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   В этой функции вы пишете код для управления *сообщениями* , получаемыми приложением из Windows при возникновении *событий* . Например, если пользователь нажмет кнопку "ОК" в приложении, Windows отправит вам сообщение, и вы сможете написать код внутри `WndProc` функции, который подходит для любой работы. Он называется *обработкой* события. Вы обрабатываете только те события, которые относятся к вашему приложению.

   Дополнительные сведения см. в разделе [Процедуры окна](/windows/win32/winmsg/window-procedures).

### <a name="to-add-functionality-to-the-winmain-function"></a>Добавление функциональных возможностей в функцию WinMain

1. В `WinMain` функции вы заполняете структуру типа [вндклассекс](/windows/win32/api/winuser/ns-winuser-wndclassexw). Структура содержит сведения о окне: значок приложения, цвет фона окна, имя, отображаемое в строке заголовка, помимо прочего. Важно, что он содержит указатель на функцию окна. В приведенном ниже примере показана типичная структура `WNDCLASSEX` .

   ```cpp
   WNDCLASSEX wcex;

   wcex.cbSize         = sizeof(WNDCLASSEX);
   wcex.style          = CS_HREDRAW | CS_VREDRAW;
   wcex.lpfnWndProc    = WndProc;
   wcex.cbClsExtra     = 0;
   wcex.cbWndExtra     = 0;
   wcex.hInstance      = hInstance;
   wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
   wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
   wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
   wcex.lpszMenuName   = NULL;
   wcex.lpszClassName  = szWindowClass;
   wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);
   ```

   Дополнительные сведения о полях приведенной выше структуры см. в разделе [вндклассекс](/windows/win32/api/winuser/ns-winuser-wndclassexw).

1. Зарегистрируйте в `WNDCLASSEX` Windows, чтобы он знал о вашем окне и способах отправки в него сообщений. Воспользуйтесь функцией [RegisterClassEx](/windows/win32/api/winuser/nf-winuser-registerclassexw) и передайте структуру класса окна в качестве аргумента. Этот `_T` макрос используется, так как мы используем `TCHAR` тип.

   ```cpp
   if (!RegisterClassEx(&wcex))
   {
      MessageBox(NULL,
         _T("Call to RegisterClassEx failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

1. Теперь можно создать окно. Воспользуйтесь функцией [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) .

   ```cpp
   static TCHAR szWindowClass[] = _T("DesktopApp");
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   // The parameters to CreateWindow explained:
   // szWindowClass: the name of the application
   // szTitle: the text that appears in the title bar
   // WS_OVERLAPPEDWINDOW: the type of window to create
   // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
   // 500, 100: initial size (width, length)
   // NULL: the parent of this window
   // NULL: this application does not have a menu bar
   // hInstance: the first parameter from WinMain
   // NULL: not used in this application
   HWND hWnd = CreateWindow(
      szWindowClass,
      szTitle,
      WS_OVERLAPPEDWINDOW,
      CW_USEDEFAULT, CW_USEDEFAULT,
      500, 100,
      NULL,
      NULL,
      hInstance,
      NULL
   );
   if (!hWnd)
   {
      MessageBox(NULL,
         _T("Call to CreateWindow failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

   Эта функция возвращает объект `HWND` , который является обработчиком окна. Маркер похож на указатель, используемый Windows для наблюдения за открытыми окнами. Дополнительные сведения см. в разделе [Типы данных Windows](/windows/win32/WinProg/windows-data-types).

1. На этом этапе окно было создано, но нам по-прежнему нужно сообщить Windows, что он стал видимым. Вот что делает этот код:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   Отображаемое окно не содержит много содержимого, так как функция еще не реализована `WndProc` . Иными словами, приложение еще не обрабатывает сообщения, отправляемые Windows в него.

1. Для обработки сообщений сначала нужно добавить цикл обработки сообщений для прослушивания сообщений, отправляемых Windows. Когда приложение получает сообщение, этот цикл отправляет его в вашу `WndProc` функцию для обработки. Цикл обработки сообщений напоминает приведенный ниже код.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   Дополнительные сведения о структурах и функциях, используемых в цикле обработки сообщений, см. в разделах, посвященных [MSG](/windows/win32/api/winuser/ns-winuser-msg), [GetMessage](/windows/win32/api/winuser/nf-winuser-getmessage), [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage).

   На этом этапе функция `WinMain` должна напоминать приведенный ниже код.

   ```cpp
   int WINAPI WinMain(HINSTANCE hInstance,
                      HINSTANCE hPrevInstance,
                      LPSTR lpCmdLine,
                      int nCmdShow)
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application dows not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }
   ```

### <a name="to-add-functionality-to-the-wndproc-function"></a>Добавление функциональных возможностей в функцию WndProc

1. Чтобы включить обработку получаемых приложением сообщений функцией `WndProc` , реализуйте оператор switch.

   Одно важное сообщение для обработчика — [WM_PAINT](/windows/win32/gdi/wm-paint) сообщение. Приложение получает сообщение, `WM_PAINT` когда часть его отображаемого окна необходимо обновить. Это событие может возникать, когда пользователь перемещает окно перед окном, а затем снова перемещает его. Приложение не знает, когда происходят эти события. Только Windows знает, поэтому она уведомляет ваше приложение с `WM_PAINT` сообщением. При первом отображении окна его все должно быть обновлено.

   Для обработки сообщения `WM_PAINT` сначала вызовите метод [BeginPaint](/windows/win32/api/winuser/nf-winuser-beginpaint), далее обработайте логику расположения текста, кнопок и других элементов управления в окне, а затем вызовите метод [EndPaint](/windows/win32/api/winuser/nf-winuser-endpaint). Для приложения логика между начальным вызовом и завершающим вызовом отображает строку "Hello, Windows Desktop!" "Hello, World!". В следующем коде функция [Text](/windows/win32/api/wingdi/nf-wingdi-textoutw) используется для вывода строки.

   ```cpp
   PAINTSTRUCT ps;
   HDC hdc;
   TCHAR greeting[] = _T("Hello, Windows desktop!");

   switch (message)
   {
   case WM_PAINT:
      hdc = BeginPaint(hWnd, &ps);

      // Here your application is laid out.
      // For this introduction, we just print out "Hello, Windows desktop!"
      // in the top left corner.
      TextOut(hdc,
         5, 5,
         greeting, _tcslen(greeting));
      // End application-specific layout section.

      EndPaint(hWnd, &ps);
      break;
   }
   ```

   `HDC` в коде — это обработчик контекста устройства, который используется для рисования в клиентской области окна. Используйте `BeginPaint` функции и `EndPaint` для подготовки и завершения рисования в клиентской области. `BeginPaint` Возвращает маркер контекста устройства отображения, используемый для рисования в клиентской области. `EndPaint` завершает запрос на рисование и освобождает контекст устройства.

1. Приложение обычно обрабатывает много других сообщений. Например, [WM_CREATE](/windows/win32/winmsg/wm-create) при первом создании окна и [WM_DESTROY](/windows/win32/winmsg/wm-destroy) при закрытии окна. В приведенном ниже коде содержится базовое представление полной функции `WndProc` .

   ```cpp
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

## <a name="build-the-code"></a>Сборка кода

Как обещано, вот полный код для рабочего приложения.

### <a name="to-build-this-example"></a>Сборка примера

1. Удалите код, введенный в *хелловиндовсдесктоп. cpp* в редакторе. Скопируйте этот пример кода и вставьте его в *хелловиндовсдесктоп. cpp*:

   ```cpp
   // HelloWindowsDesktop.cpp
   // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c

   #include <windows.h>
   #include <stdlib.h>
   #include <string.h>
   #include <tchar.h>

   // Global variables

   // The main window class name.
   static TCHAR szWindowClass[] = _T("DesktopApp");

   // The string that appears in the application's title bar.
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   HINSTANCE hInst;

   // Forward declarations of functions included in this code module:
   LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);

   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   )
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application does not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }

   //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM)
   //
   //  PURPOSE:  Processes messages for the main window.
   //
   //  WM_PAINT    - Paint the main window
   //  WM_DESTROY  - post a quit message and return
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application-specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

1. В меню **Построение** выберите **Построить решение**. Результаты компиляции должны отобразиться в окне **вывод** в Visual Studio.

   ![Создание проекта Десктопапп](../build/media/desktop-app-project-build-150.gif "Создание проекта Десктопапп")

1. Чтобы запустить приложение, нажмите клавишу **F5**. Окно, содержащее текст "Hello, Windows Desktop!" должно отображаться в левом верхнем углу экрана.

   ![Запуск проекта Десктопапп](../build/media/desktop-app-project-run-157.PNG "Запуск проекта Десктопапп")

Поздравляем! Вы выполнили это пошаговое руководство и создали традиционное классическое приложение для Windows.

## <a name="see-also"></a>См. также

[Классические приложения Windows](../windows/windows-desktop-applications-cpp.md)
