---
title: Класс CFrameWnd
ms.date: 11/04/2016
f1_keywords:
- CFrameWnd
- AFXWIN/CFrameWnd
- AFXWIN/CFrameWnd::CFrameWnd
- AFXWIN/CFrameWnd::ActivateFrame
- AFXWIN/CFrameWnd::BeginModalState
- AFXWIN/CFrameWnd::Create
- AFXWIN/CFrameWnd::CreateView
- AFXWIN/CFrameWnd::DockControlBar
- AFXWIN/CFrameWnd::EnableDocking
- AFXWIN/CFrameWnd::EndModalState
- AFXWIN/CFrameWnd::FloatControlBar
- AFXWIN/CFrameWnd::GetActiveDocument
- AFXWIN/CFrameWnd::GetActiveFrame
- AFXWIN/CFrameWnd::GetActiveView
- AFXWIN/CFrameWnd::GetControlBar
- AFXWIN/CFrameWnd::GetDockState
- AFXWIN/CFrameWnd::GetMenuBarState
- AFXWIN/CFrameWnd::GetMenuBarVisibility
- AFXWIN/CFrameWnd::GetMessageBar
- AFXWIN/CFrameWnd::GetMessageString
- AFXWIN/CFrameWnd::GetTitle
- AFXWIN/CFrameWnd::InitialUpdateFrame
- AFXWIN/CFrameWnd::InModalState
- AFXWIN/CFrameWnd::IsTracking
- AFXWIN/CFrameWnd::LoadAccelTable
- AFXWIN/CFrameWnd::LoadBarState
- AFXWIN/CFrameWnd::LoadFrame
- AFXWIN/CFrameWnd::NegotiateBorderSpace
- AFXWIN/CFrameWnd::OnBarCheck
- AFXWIN/CFrameWnd::OnContextHelp
- AFXWIN/CFrameWnd::OnSetPreviewMode
- AFXWIN/CFrameWnd::OnUpdateControlBarMenu
- AFXWIN/CFrameWnd::RecalcLayout
- AFXWIN/CFrameWnd::SaveBarState
- AFXWIN/CFrameWnd::SetActivePreviewView
- AFXWIN/CFrameWnd::SetActiveView
- AFXWIN/CFrameWnd::SetDockState
- AFXWIN/CFrameWnd::SetMenuBarState
- AFXWIN/CFrameWnd::SetMenuBarVisibility
- AFXWIN/CFrameWnd::SetMessageText
- AFXWIN/CFrameWnd::SetProgressBarPosition
- AFXWIN/CFrameWnd::SetProgressBarRange
- AFXWIN/CFrameWnd::SetProgressBarState
- AFXWIN/CFrameWnd::SetTaskbarOverlayIcon
- AFXWIN/CFrameWnd::SetTitle
- AFXWIN/CFrameWnd::ShowControlBar
- AFXWIN/CFrameWnd::ShowOwnedWindows
- AFXWIN/CFrameWnd::OnCreateClient
- AFXWIN/CFrameWnd::OnHideMenuBar
- AFXWIN/CFrameWnd::OnShowMenuBar
- AFXWIN/CFrameWnd::m_bAutoMenuEnable
- AFXWIN/CFrameWnd::rectDefault
helpviewer_keywords:
- CFrameWnd [MFC], CFrameWnd
- CFrameWnd [MFC], ActivateFrame
- CFrameWnd [MFC], BeginModalState
- CFrameWnd [MFC], Create
- CFrameWnd [MFC], CreateView
- CFrameWnd [MFC], DockControlBar
- CFrameWnd [MFC], EnableDocking
- CFrameWnd [MFC], EndModalState
- CFrameWnd [MFC], FloatControlBar
- CFrameWnd [MFC], GetActiveDocument
- CFrameWnd [MFC], GetActiveFrame
- CFrameWnd [MFC], GetActiveView
- CFrameWnd [MFC], GetControlBar
- CFrameWnd [MFC], GetDockState
- CFrameWnd [MFC], GetMenuBarState
- CFrameWnd [MFC], GetMenuBarVisibility
- CFrameWnd [MFC], GetMessageBar
- CFrameWnd [MFC], GetMessageString
- CFrameWnd [MFC], GetTitle
- CFrameWnd [MFC], InitialUpdateFrame
- CFrameWnd [MFC], InModalState
- CFrameWnd [MFC], IsTracking
- CFrameWnd [MFC], LoadAccelTable
- CFrameWnd [MFC], LoadBarState
- CFrameWnd [MFC], LoadFrame
- CFrameWnd [MFC], NegotiateBorderSpace
- CFrameWnd [MFC], OnBarCheck
- CFrameWnd [MFC], OnContextHelp
- CFrameWnd [MFC], OnSetPreviewMode
- CFrameWnd [MFC], OnUpdateControlBarMenu
- CFrameWnd [MFC], RecalcLayout
- CFrameWnd [MFC], SaveBarState
- CFrameWnd [MFC], SetActivePreviewView
- CFrameWnd [MFC], SetActiveView
- CFrameWnd [MFC], SetDockState
- CFrameWnd [MFC], SetMenuBarState
- CFrameWnd [MFC], SetMenuBarVisibility
- CFrameWnd [MFC], SetMessageText
- CFrameWnd [MFC], SetProgressBarPosition
- CFrameWnd [MFC], SetProgressBarRange
- CFrameWnd [MFC], SetProgressBarState
- CFrameWnd [MFC], SetTaskbarOverlayIcon
- CFrameWnd [MFC], SetTitle
- CFrameWnd [MFC], ShowControlBar
- CFrameWnd [MFC], ShowOwnedWindows
- CFrameWnd [MFC], OnCreateClient
- CFrameWnd [MFC], OnHideMenuBar
- CFrameWnd [MFC], OnShowMenuBar
- CFrameWnd [MFC], m_bAutoMenuEnable
- CFrameWnd [MFC], rectDefault
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
ms.openlocfilehash: 5e40f08447d24eed51588b5c2dfa87e289d99eed
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561582"
---
# <a name="cframewnd-class"></a>Класс CFrameWnd

Реализует функции однодокументного интерфейса Windows (SDI) с наложенным или всплывающим фреймовым окном с элементами для управления окном.

## <a name="syntax"></a>Синтаксис

```
class CFrameWnd : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFrameWnd:: CFrameWnd](#cframewnd)|Формирует объект `CFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFrameWnd:: Активатефраме](#activateframe)|Делает фрейм видимым и доступным для пользователя.|
|[CFrameWnd:: Бегинмодалстате](#beginmodalstate)|Устанавливает модальное окно фрейма.|
|[CFrameWnd:: Create](#create)|Вызовите метод, чтобы создать и инициализировать окно фрейма Windows, связанное с `CFrameWnd` объектом.|
|[CFrameWnd:: CreateView](#createview)|Создает представление внутри фрейма, который не является производным от `CView` .|
|[CFrameWnd::D Оккконтролбар](#dockcontrolbar)|Закрепляет панель элементов управления.|
|[CFrameWnd:: Енабледоккинг](#enabledocking)|Позволяет закреплять панель элементов управления.|
|[CFrameWnd:: Ендмодалстате](#endmodalstate)|Завершает модальное состояние окна фрейма. Включает все окна, отключенные с помощью `BeginModalState` .|
|[CFrameWnd:: Флоатконтролбар](#floatcontrolbar)|Перемещает панель элементов управления в плавающую область.|
|[CFrameWnd:: Жетактиведокумент](#getactivedocument)|Возвращает активный `CDocument` объект.|
|[CFrameWnd:: Жетактивефраме](#getactiveframe)|Возвращает активный `CFrameWnd` объект.|
|[CFrameWnd:: Жетактивевиев](#getactiveview)|Возвращает активный `CView` объект.|
|[CFrameWnd:: Жетконтролбар](#getcontrolbar)|Извлекает панель управления.|
|[CFrameWnd:: Жетдоккстате](#getdockstate)|Получает состояние закрепления окна фрейма.|
|[CFrameWnd:: Жетменубарстате](#getmenubarstate)|Извлекает состояние отображения меню в текущем приложении MFC.|
|[CFrameWnd:: Жетменубарвисибилити](#getmenubarvisibility)|Указывает, является ли поведение по умолчанию меню в текущем приложении MFC скрытым или видимым.|
|[CFrameWnd:: Жетмессажебар](#getmessagebar)|Возвращает указатель на строку состояния, принадлежащую окну фрейма.|
|[CFrameWnd:: Жетмессажестринг](#getmessagestring)|Извлекает сообщение, соответствующее ИДЕНТИФИКАТОРу команды.|
|[CFrameWnd:: "заголовок"](#gettitle)|Извлекает заголовок связанной панели элементов управления.|
|[CFrameWnd:: Инитиалупдатефраме](#initialupdateframe)|Приводит к `OnInitialUpdate` вызову функции члена, принадлежащей всем представлениям в окне фрейма.|
|[CFrameWnd:: Инмодалстате](#inmodalstate)|Возвращает значение, указывающее, находится ли окно фрейма в модальном состоянии.|
|[CFrameWnd:: прослеживание](#istracking)|Определяет, выполняется ли перемещение полосы разделения в данный момент.|
|[CFrameWnd:: Лоадакцелтабле](#loadacceltable)|Вызовите метод, чтобы загрузить таблицу сочетаний клавиш.|
|[CFrameWnd:: Лоадбарстате](#loadbarstate)|Вызовите, чтобы восстановить параметры панели управления.|
|[CFrameWnd:: Лоадфраме](#loadframe)|Вызовите, чтобы динамически создать окно фрейма из сведений о ресурсе.|
|[CFrameWnd:: Неготиатебордерспаце](#negotiateborderspace)|Согласовывает пространство границ в окне фрейма.|
|[CFrameWnd:: Онбарчекк](#onbarcheck)|Вызывается при каждом выполнении действия на указанной панели элементов управления.|
|[CFrameWnd:: Онконтексселп](#oncontexthelp)|Обрабатывает клавиши SHIFT + F1 для элементов на месте.|
|[CFrameWnd:: Онсетпревиевмоде](#onsetpreviewmode)|Задает окно главного фрейма приложения в режиме предварительного просмотра и выход из него.|
|[CFrameWnd:: Онупдатеконтролбармену](#onupdatecontrolbarmenu)|Вызывается структурой при обновлении связанного меню.|
|[CFrameWnd:: RecalcLayout](#recalclayout)|Перемещает панели элементов управления `CFrameWnd` объекта.|
|[CFrameWnd:: Савебарстате](#savebarstate)|Вызов для сохранения параметров панели управления.|
|[CFrameWnd:: Сетактивепревиеввиев](#setactivepreviewview)|Определяет указанное представление как активное представление для расширенного просмотра.|
|[CFrameWnd:: Сетактивевиев](#setactiveview)|Задает активный `CView` объект.|
|[CFrameWnd:: Сетдоккстате](#setdockstate)|Вызовите, чтобы закрепить окно фрейма в главном окне.|
|[CFrameWnd:: Сетменубарстате](#setmenubarstate)|Задает состояние отображения меню в текущем приложении MFC для скрытия или отображения.|
|[CFrameWnd:: Сетменубарвисибилити](#setmenubarvisibility)|Задает поведение по умолчанию для меню в текущем приложении MFC, которое должно быть скрытым или видимым.|
|[CFrameWnd:: Сетмессажетекст](#setmessagetext)|Задает текст стандартной строки состояния.|
|[CFrameWnd:: Сетпрогрессбарпоситион](#setprogressbarposition)|Задает текущую положение индикатора выполнения Windows 7, отображаемого на панели задач.|
|[CFrameWnd:: Сетпрогрессбарранже](#setprogressbarrange)|Задает диапазон для индикатора выполнения Windows 7, отображаемого на панели задач.|
|[CFrameWnd:: Сетпрогрессбарстате](#setprogressbarstate)|Задает тип и состояние индикатора хода выполнения, отображаемого на кнопке панели задач.|
|[CFrameWnd:: Сеттаскбароверлайикон](#settaskbaroverlayicon)|Перегружен. Применяет наложение к кнопке на панели задач для указания состояния приложения или уведомления пользователю.|
|[CFrameWnd:: Сеттитле](#settitle)|Задает заголовок связанной панели элементов управления.|
|[CFrameWnd:: Шовконтролбар](#showcontrolbar)|Вызовите, чтобы отобразить панель управления.|
|[CFrameWnd:: Шововнедвиндовс](#showownedwindows)|Показывает все окна, являющиеся потомками `CFrameWnd` объекта.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CFrameWnd:: Онкреатеклиент](#oncreateclient)|Создает клиентское окно для рамки.|
|[CFrameWnd:: Онхидеменубар](#onhidemenubar)|Вызывается до скрытия меню в текущем приложении MFC.|
|[CFrameWnd:: Оншовменубар](#onshowmenubar)|Вызывается перед отображением меню в текущем приложении MFC.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFrameWnd:: m_bAutoMenuEnable](#m_bautomenuenable)|Управляет автоматическим включением и отключением функций для пунктов меню.|
|[CFrameWnd:: Ректдефаулт](#rectdefault)|Передайте этот статический `CRect` параметр в качестве параметра при создании `CFrameWnd` объекта, чтобы разрешить Windows выбирать исходный размер и расположение окна.|

## <a name="remarks"></a>Примечания

Чтобы создать полезное окно фрейма для приложения, создайте класс, производный от `CFrameWnd` . Добавьте переменные члена в производный класс для хранения данных, относящихся к вашему приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Существует три способа создания окна фрейма:

- Он создается напрямую с помощью инструкции [CREATE](#create).

- Он напрямую создается с помощью [лоадфраме](#loadframe).

- Косвенно создать его с помощью шаблона документа.

Перед вызовом `Create` или `LoadFrame` необходимо создать объект окна фрейма в куче с помощью **`new`** оператора C++. Перед вызовом `Create` можно также зарегистрировать класс окна с глобальной функцией [афксрегистервндкласс](../../mfc/reference/application-information-and-management.md#afxregisterwndclass) , чтобы задать стили значков и классов для фрейма.

Используйте `Create` функцию члена для передачи параметров создания кадра в качестве непосредственных аргументов.

`LoadFrame` требует меньше аргументов `Create` , чем, и вместо этого извлекает большинство значений по умолчанию из ресурсов, включая заголовок фрейма, значок, таблицу сочетаний клавиш и меню. Чтобы иметь доступ к `LoadFrame` , все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).

Если `CFrameWnd` объект содержит представления и документы, они создаются косвенно платформой, а не непосредственно программистом. `CDocTemplate`Объект управляет созданием фрейма, созданием содержащихся представлений и подключением представлений к соответствующему документу. Параметры `CDocTemplate` конструктора указывают, какие `CRuntimeClass` из трех участвующих классов (документ, фрейм и представление). `CRuntimeClass`Объект используется платформой для динамического создания новых кадров при их указании пользователем (например, с помощью команды файл создать или окна Создание многодокументного интерфейса (MDI)).

Класс фреймового окна, производный от, `CFrameWnd` должен быть объявлен с DECLARE_DYNCREATE, чтобы механизм RUNTIME_CLASS работал правильно.

`CFrameWnd`Содержит реализации по умолчанию для выполнения следующих функций главного окна в обычном приложении для Windows:

- `CFrameWnd`Окно фрейма отслеживает текущее активное представление, которое не зависит от активного окна Windows или текущего фокуса ввода. При повторной активации кадра активное представление уведомляется путем вызова `CView::OnActivateView` .

- Сообщения команд и многие распространенные сообщения с уведомлениями о кадрах, включая те, которые обрабатываются `OnSetFocus` `OnHScroll` функциями, и `OnVScroll` `CWnd` , делегируются `CFrameWnd` окном фрейма в текущее активное представление.

- В текущем активном представлении (или в текущем активном окне дочернего фрейма MDI в случае фрейма MDI) можно определить заголовок окна фрейма. Эту функцию можно отключить, отключив бит стиля FWS_ADDTOTITLE окна фрейма.

- `CFrameWnd`Окно фрейма управляет положением панелей управления, представлений и других дочерних окон в клиентской области окна фрейма. Фрейм окна также выполняет обновление панели инструментов и других кнопок панели управления во время простоя. `CFrameWnd`Фрейм окна также имеет стандартные реализации команд для включения и отключения панели инструментов и строки состояния.

- `CFrameWnd`Окно фрейма управляет главной строкой меню. При отображении всплывающего меню окно фрейма использует механизм UPDATE_COMMAND_UI, чтобы определить, какие пункты меню должны быть включены, отключены или отмечены флажком. Когда пользователь выбирает пункт меню, окно фрейма обновляет строку состояния строкой сообщения для этой команды.

- `CFrameWnd`Окно фрейма содержит необязательную таблицу сочетаний клавиш, которая автоматически преобразует сочетания клавиш.

- `CFrameWnd`Окно фрейма содержит необязательный идентификатор справки, заданный с помощью `LoadFrame` , который используется для контекстной справки. Окно фрейма — это основная Orchestrator семимодал состояний, таких как контекстно-зависимая справка (SHIFT + F1) и режимы предварительного просмотра.

- В `CFrameWnd` окне фрейма откроется файл, который перетаскивается из диспетчера файлов и удаляется в окне фрейма. Если расширение файла зарегистрировано и связано с приложением, окно фрейма реагирует на запрос на открытие динамического обмена данными (DDE), который происходит, когда пользователь открывает файл данных в диспетчере файлов или когда `ShellExecute` вызывается функция Windows.

- Если окно фрейма является основным окном приложения (то есть `CWinThread::m_pMainWnd` ), когда пользователь закрывает приложение, в окне фрейма пользователю предлагается сохранить измененные документы (для `OnClose` и `OnQueryEndSession` ).

- Если окно фрейма является основным окном приложения, окно фрейма является контекстом для запуска WinHelp. Закрытие окна фрейма приведет к выключению WINHELP.EXE, если оно было запущено для получения справки по этому приложению.

Не используйте **`delete`** оператор C++ для уничтожения окна фрейма. Используйте вместо этого `CWnd::DestroyWindow`. `CFrameWnd`Реализация служб `PostNcDestroy` удалит объект C++ при уничтожении окна. Когда пользователь закрывает окно фрейма, обработчик по умолчанию `OnClose` выполнит вызов `DestroyWindow` .

Дополнительные сведения о см `CFrameWnd` . в разделе [окна с рамками](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cframewndactivateframe"></a><a name="activateframe"></a> CFrameWnd:: Активатефраме

Вызовите эту функцию-член, чтобы активировать и восстановить окно фрейма, чтобы оно было видимым и доступным для пользователя.

```
virtual void ActivateFrame(int nCmdShow = -1);
```

### <a name="parameters"></a>Параметры

*нкмдшов*<br/>
Указывает параметр для передачи в [CWnd:: ShowWindow](../../mfc/reference/cwnd-class.md#showwindow). По умолчанию кадр отображается и правильно восстанавливается.

### <a name="remarks"></a>Примечания

Эта функция-член обычно вызывается после события нестандартного интерфейса, такого как DDE, OLE или другое событие, которое может показывать окно фрейма или его содержимое пользователю.

Реализация по умолчанию активирует фрейм и перемещает его в верхнюю часть Z-порядка и при необходимости выполняет те же действия для главного окна приложения.

Переопределите эту функцию-член, чтобы изменить способ активации кадра. Например, можно принудительно развернуть дочерние окна MDI. Добавьте соответствующие функциональные возможности, а затем вызовите версию базового класса с явной *нкмдшов*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#1](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]

## <a name="cframewndbeginmodalstate"></a><a name="beginmodalstate"></a> CFrameWnd:: Бегинмодалстате

Данная функция-член вызывается для преобразования окна фрейма в модальное.

```
virtual void BeginModalState();
```

## <a name="cframewndcframewnd"></a><a name="cframewnd"></a> CFrameWnd:: CFrameWnd

Создает `CFrameWnd` объект, но не создает видимое окно фрейма.

```
CFrameWnd();
```

### <a name="remarks"></a>Примечания

Вызовите `Create` , чтобы создать видимое окно.

## <a name="cframewndcreate"></a><a name="create"></a> CFrameWnd:: Create

Вызовите метод, чтобы создать и инициализировать окно фрейма Windows, связанное с `CFrameWnd` объектом.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CWnd* pParentWnd = NULL,
    LPCTSTR lpszMenuName = NULL,
    DWORD dwExStyle = 0,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзкласснаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая именует класс Windows. Именем класса может быть любое имя, зарегистрированное в `AfxRegisterWndClass` глобальной функции или `RegisterClass` функции Windows. Если значение равно NULL, использует стандартные атрибуты по умолчанию `CFrameWnd` .

*лпсзвиндовнаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая представляет имя окна. Используется в качестве текста для заголовка окна.

*двстиле*<br/>
Задает атрибуты [стиля](../../mfc/reference/styles-used-by-mfc.md#window-styles) окна. Включите стиль FWS_ADDTOTITLE, если нужно, чтобы в строке заголовка автоматически отображалось имя документа, представленного в окне.

*rect*<br/>
Задает размер и расположение окна. Значение *ректдефаулт* позволяет Windows указать размер и расположение нового окна.

*ппарентвнд*<br/>
Указывает родительское окно этого окна фрейма. Этот параметр должен иметь значение NULL для окон фрейма верхнего уровня.

*лпсзменунаме*<br/>
Определяет имя ресурса меню, который будет использоваться в окне. Используйте МАКЕИНТРЕСАУРЦЕ, если меню содержит целочисленный идентификатор, а не строку. Этот параметр может иметь значение NULL.

*двексстиле*<br/>
Задает атрибуты расширенного [стиля](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) окна.

*pContext*<br/>
Указывает указатель на структуру [ккреатеконтекст](../../mfc/reference/ccreatecontext-structure.md) . Этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Создайте `CFrameWnd` объект в два этапа. Сначала вызовите конструктор, который создает `CFrameWnd` объект, а затем вызовите `Create` , который создаст окно фрейма Windows и присоединяет его к `CFrameWnd` объекту. `Create` Инициализирует имя класса и имя окна окна и регистрирует значения по умолчанию для соответствующего стиля, родительского и связанного меню.

Используйте `LoadFrame` вместо `Create` для загрузки окна фрейма из ресурса вместо указания его аргументов.

## <a name="cframewndcreateview"></a><a name="createview"></a> CFrameWnd:: CreateView

Вызовите `CreateView` , чтобы создать представление внутри рамки.

```
CWnd* CreateView(
    CCreateContext* pContext,
    UINT nID = AFX_IDW_PANE_FIRST);
```

### <a name="parameters"></a>Параметры

*pContext*<br/>
Указывает тип представления и документа.

*nID*<br/>
ИДЕНТИФИКАЦИОНный номер представления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект в случае `CWnd` успеха; в противном случае — null.

### <a name="remarks"></a>Примечания

Используйте эту функцию-член для создания представлений, которые не являются `CView` производными внутри рамки. После вызова `CreateView` необходимо вручную задать для представления значение активно и сделать его видимым; эти задачи не выполняются автоматически `CreateView` .

## <a name="cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a> CFrameWnd::D Оккконтролбар

Вызывает прикрепление панели элементов управления к окну фрейма.

```cpp
void DockControlBar(
    CControlBar* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

*пбар*<br/>
Указывает на панель элементов управления, которую необходимо закрепить.

*ндоккбарид*<br/>
Определяет, какие стороны фрейма окна следует учитывать при закреплении. Он может иметь значение 0 или один или несколько из следующих элементов:

- AFX_IDW_DOCKBAR_TOP закрепляться в верхней части окна фрейма.

- AFX_IDW_DOCKBAR_BOTTOM закрепить в нижней части окна фрейма.

- AFX_IDW_DOCKBAR_LEFT закрепить в левой части окна фрейма.

- AFX_IDW_DOCKBAR_RIGHT закрепить в правой части окна фрейма.

Если значение равно 0, панель элементов управления можно закрепить на любой стороне, включенной для закрепления в окне конечного фрейма.

*лпрект*<br/>
Определяет, в экранных координатах, где панель управления будет закреплена в неклиентской области окна конечного фрейма.

### <a name="remarks"></a>Примечания

Панель элементов управления будет закреплена на одной из сторон окна фрейма, указанного в вызовах методов [CControlBar:: енабледоккинг](../../mfc/reference/ccontrolbar-class.md#enabledocking) и [CFrameWnd:: енабледоккинг](#enabledocking). Выбранная сторона определяется *ндоккбарид*.

## <a name="cframewndenabledocking"></a><a name="enabledocking"></a> CFrameWnd:: Енабледоккинг

Вызывайте эту функцию, чтобы включить закрепляемые панели элементов управления в окне фрейма.

```cpp
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Параметры

*двдоккстиле*<br/>
Указывает, какие стороны окна фрейма могут использоваться в качестве закрепления узлов для панелей элементов управления. Это может быть одно или несколько из следующих:

- CBRS_ALIGN_TOP допускает стыковку в верхней части клиентской области.

- CBRS_ALIGN_BOTTOM допускает закрепление в нижней части клиентской области.

- CBRS_ALIGN_LEFT допускает стыковку в левой части клиентской области.

- CBRS_ALIGN_RIGHT допускает закрепление в правой части клиентской области.

- CBRS_ALIGN_ANY допускает стыковку на любой стороне клиентской области.

### <a name="remarks"></a>Примечания

По умолчанию панели элементов управления закрепляются сбоку окна фрейма в следующем порядке: сверху, снизу, слева, справа.

### <a name="example"></a>Пример

  См. пример для [CToolBar:: Create](../../mfc/reference/ctoolbar-class.md#create).

## <a name="cframewndendmodalstate"></a><a name="endmodalstate"></a> CFrameWnd:: Ендмодалстате

Данная функция-член вызывается для изменения состояния окна с модального на немодальное.

```
virtual void EndModalState();
```

### <a name="remarks"></a>Примечания

`EndModalState` включает все окна, отключенные [бегинмодалстате](#beginmodalstate).

## <a name="cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a> CFrameWnd:: Флоатконтролбар

Вызовите эту функцию, чтобы не прикрепить панель управления к окну фрейма.

```cpp
void FloatControlBar(
    CControlBar* pBar,
    CPoint point,
    DWORD dwStyle = CBRS_ALIGN_TOP);
```

### <a name="parameters"></a>Параметры

*пбар*<br/>
Указывает на панель управления, которая должна быть плавающей.

*точки*<br/>
Расположение в экранных координатах, где будет размещен верхний левый угол панели элементов управления.

*двстиле*<br/>
Указывает, следует ли выравнивать панель элементов управления по горизонтали или вертикали в новом окне фрейма. Это может быть одно из следующих:

- CBRS_ALIGN_TOP ориентирует панель элементов управления по вертикали.

- CBRS_ALIGN_BOTTOM ориентирует панель элементов управления по вертикали.

- CBRS_ALIGN_LEFT ориентирует панель элементов управления по горизонтали.

- CBRS_ALIGN_RIGHT ориентирует панель элементов управления по горизонтали.

Если стили передаются с указанием горизонтальной и вертикальной ориентации, панель инструментов будет ориентирована по горизонтали.

### <a name="remarks"></a>Примечания

Как правило, это происходит при запуске приложения, когда программа восстанавливает параметры из предыдущего выполнения.

Эта функция вызывается платформой, когда пользователь вызывает операцию Drop, Отпустив левую кнопку мыши при перетаскивании панели элементов управления на место, недоступное для закрепления.

## <a name="cframewndgetactivedocument"></a><a name="getactivedocument"></a> CFrameWnd:: Жетактиведокумент

Вызовите эту функцию-член для получения указателя на текущий объект, `CDocument` присоединенный к текущему активному представлению.

```
virtual CDocument* GetActiveDocument();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий объект [CDocument](../../mfc/reference/cdocument-class.md). Если текущего документа нет, возвращает значение NULL.

## <a name="cframewndgetactiveframe"></a><a name="getactiveframe"></a> CFrameWnd:: Жетактивефраме

Вызовите эту функцию-член, чтобы получить указатель на дочернее окно активного многодокументного интерфейса (MDI) окна фрейма MDI.

```
virtual CFrameWnd* GetActiveFrame();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на активное дочернее окно MDI. Если приложение является приложением SDI или в окне фрейма MDI нет активного документа, будет возвращен неявный **`this`** указатель.

### <a name="remarks"></a>Примечания

Если нет активного дочернего интерфейса MDI или приложение является единым интерфейсом документа (SDI), возвращается неявный **`this`** указатель.

## <a name="cframewndgetactiveview"></a><a name="getactiveview"></a> CFrameWnd:: Жетактивевиев

Вызовите эту функцию-член, чтобы получить указатель на активное представление (если таковое имеется), присоединенное к окну фрейма ( `CFrameWnd` ).

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий объект [CView](../../mfc/reference/cview-class.md). Если текущее представление отсутствует, возвращает значение NULL.

### <a name="remarks"></a>Примечания

Эта функция возвращает значение NULL при вызове для окна главного фрейма MDI ( `CMDIFrameWnd` ). В приложении MDI окно главного фрейма MDI не имеет связанного с ним представления. Вместо этого у каждого отдельного дочернего окна ( `CMDIChildWnd` ) есть одно или несколько связанных представлений. Активное представление в приложении MDI можно получить, сначала нахождение активного дочернего окна MDI, а затем найдите активное представление для этого дочернего окна. Активное дочернее окно MDI можно найти, вызвав функцию `MDIGetActive` или `GetActiveFrame` как показано ниже:

[!code-cpp[NVC_MFCWindowing#2](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]

## <a name="cframewndgetcontrolbar"></a><a name="getcontrolbar"></a> CFrameWnd:: Жетконтролбар

Вызовите метод, `GetControlBar` чтобы получить доступ к панели управления, связанной с идентификатором.

```
CControlBar* GetControlBar(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
ИДЕНТИФИКАЦИОНный номер панели элементов управления.

### <a name="return-value"></a>Возвращаемое значение

Указатель на панель управления, связанный с ИДЕНТИФИКАТОРом.

### <a name="remarks"></a>Примечания

Параметр *NID* ссылается на уникальный идентификатор, передаваемый `Create` методу панели управления. Дополнительные сведения о панелях управления см. в разделе [панели элементов управления](../../mfc/control-bars.md).

`GetControlBar` Возвращает панель управления, даже если она является плавающей и поэтому в настоящее время не является дочерним окном рамки.

## <a name="cframewndgetdockstate"></a><a name="getdockstate"></a> CFrameWnd:: Жетдоккстате

Вызывайте эту функцию-член для хранения сведений о состоянии панелей управления фрейма окна в `CDockState` объекте.

```cpp
void GetDockState(CDockState& state) const;
```

### <a name="parameters"></a>Параметры

*state*<br/>
Содержит текущее состояние панелей управления фрейма окна при возврате.

### <a name="remarks"></a>Примечания

Затем можно записать содержимое `CDockState` в хранилище с помощью `CDockState::SaveState` или `Serialize` . Если позднее требуется восстановить предыдущее состояние панелей элементов управления, загрузите состояние с помощью `CDockState::LoadState` или `Serialize` , а затем вызовите, `SetDockState` чтобы применить предыдущее состояние к панелям управления окна фрейма.

## <a name="cframewndgetmenubarstate"></a><a name="getmenubarstate"></a> CFrameWnd:: Жетменубарстате

Извлекает состояние отображения меню в текущем приложении MFC.

```
virtual DWORD GetMenuBarState();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение может иметь следующие значения:

- AFX_MBS_VISIBLE (0x01) — меню является видимым.

- AFX_MBS_HIDDEN (0x02) — меню скрыто.

### <a name="remarks"></a>Примечания

При возникновении ошибки времени выполнения этот метод утверждается в режиме отладки и создает исключение, производное от класса [CException](../../mfc/reference/cexception-class.md) .

## <a name="cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a> CFrameWnd:: Жетменубарвисибилити

Указывает, отображается ли скрытое или видимое по умолчанию состояние меню в текущем приложении MFC.

```
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает одно из следующих значений:

- AFX_MBV_KEEPVISIBLE (0x01) — меню отображается всегда, и по умолчанию он не имеет фокуса.

- AFX_MBV_DISPLAYONFOCUS (0x02) — меню скрыто по умолчанию. Если меню скрыто, нажмите клавишу ALT, чтобы отобразить меню и присвоить ему фокус. Если меню отображается, нажмите клавишу ALT или клавишу ESC, чтобы скрыть его.

- AFX_MBV_ ДИСПЛАЙОНФОКУС (0x02) &#124; AFX_MBV_DISPLAYONF10 (0x04) (побитовое сочетание (или)) — меню скрыто по умолчанию. Если меню скрыто, нажмите клавишу F10, чтобы открыть меню и придать ему фокус. Если меню отображается, нажмите клавишу F10, чтобы включить или отключить фокус в меню. Меню отображается до тех пор, пока вы не нажмете клавишу ALT или ESC, чтобы скрыть его.

### <a name="remarks"></a>Примечания

При возникновении ошибки времени выполнения этот метод утверждается в режиме отладки и создает исключение, производное от класса [CException](../../mfc/reference/cexception-class.md) .

## <a name="cframewndgetmessagebar"></a><a name="getmessagebar"></a> CFrameWnd:: Жетмессажебар

Вызовите эту функцию-член, чтобы получить указатель на строку состояния.

```
virtual CWnd* GetMessageBar();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно строки состояния.

## <a name="cframewndgetmessagestring"></a><a name="getmessagestring"></a> CFrameWnd:: Жетмессажестринг

Переопределите эту функцию, чтобы предоставить пользовательские строки для идентификаторов команд.

```
virtual void GetMessageString(
    UINT nID,
    CString& rMessage) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор ресурса требуемого сообщения.

*рмессаже*<br/>
`CString` Объект, в который будет размещено сообщение.

### <a name="remarks"></a>Примечания

Реализация по умолчанию просто загружает строку, указанную параметром *NID* , из файла ресурсов. Эта функция вызывается платформой, когда строка сообщения в строке состояния нуждается в обновлении.

## <a name="cframewndgettitle"></a><a name="gettitle"></a> CFrameWnd:: "заголовок"

Извлекает заголовок объекта Window.

```
CString GetTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащий текущий заголовок объекта Window.

## <a name="cframewndinitialupdateframe"></a><a name="initialupdateframe"></a> CFrameWnd:: Инитиалупдатефраме

Вызов `IntitialUpdateFrame` после создания новой рамки с помощью `Create` .

```cpp
void InitialUpdateFrame(
    CDocument* pDoc,
    BOOL bMakeVisible);
```

### <a name="parameters"></a>Параметры

*pDoc*<br/>
Указывает на документ, с которым связано окно фрейма. Может иметь значение NULL.

*бмакевисибле*<br/>
Если значение — TRUE, кадр должен быть видимым и активным. Если значение равно FALSE, потомки не становятся видимыми.

### <a name="remarks"></a>Примечания

Это приводит к тому, что все представления в этом окне фрейма получат свои `OnInitialUpdate` вызовы.

Кроме того, если ранее не было активное представление, основное представление окна фрейма становится активным. Первичное представление — это представление с ИДЕНТИФИКАТОРом дочернего элемента AFX_IDW_PANE_FIRST. Наконец, окно фрейма становится видимым, если *бмакевисибле* не равно нулю. Если *бмакевисибле* имеет значение 0, текущее фокус и видимое состояние окна фрейма останутся без изменений. Не обязательно вызывать эту функцию при использовании реализации файла New и Open в платформе.

## <a name="cframewndinmodalstate"></a><a name="inmodalstate"></a> CFrameWnd:: Инмодалстате

Вызовите эту функцию-член, чтобы проверить, является ли окно фрейма модальным или немодальным.

```
BOOL InModalState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если да; в противном случае — 0.

## <a name="cframewndistracking"></a><a name="istracking"></a> CFrameWnd:: прослеживание

Вызовите эту функцию-член, чтобы определить, выполняется ли перемещение полосы-разделителя в окне в данный момент.

```
BOOL IsTracking() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполняется операция разделения; в противном случае — 0.

## <a name="cframewndloadacceltable"></a><a name="loadacceltable"></a> CFrameWnd:: Лоадакцелтабле

Вызовите метод, чтобы загрузить указанную таблицу сочетаний клавиш.

```
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```

### <a name="parameters"></a>Параметры

*лпсзресаурценаме*<br/>
Определяет имя ресурса ускорителя. Используйте МАКЕИНТРЕСАУРЦЕ, если ресурс определен с целочисленным ИДЕНТИФИКАТОРом.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если таблица сочетаний клавиш успешно загружена; в противном случае — 0.

### <a name="remarks"></a>Примечания

В каждый момент времени может быть загружена только одна таблица.

Таблицы сочетаний клавиш, загруженные из ресурсов, освобождаются автоматически при завершении работы приложения.

При вызове `LoadFrame` для создания окна фрейма платформа загружает таблицу сочетаний клавиш вместе с ресурсами меню и значками, и последующий вызов этой функции-члена не требуется.

## <a name="cframewndloadbarstate"></a><a name="loadbarstate"></a> CFrameWnd:: Лоадбарстате

Вызовите эту функцию, чтобы восстановить параметры каждой панели элементов управления, принадлежащей окну фрейма.

```cpp
void LoadBarState(LPCTSTR lpszProfileName);
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
Имя раздела в файле инициализации (INI) или ключ в реестре Windows, где хранятся сведения о состоянии.

### <a name="remarks"></a>Примечания

Восстановленная информация включает видимость, ориентацию по горизонтали и вертикали, состояние закрепления и положение на панели элементов управления.

Параметры, которые необходимо восстановить, должны быть записаны в реестр перед вызовом `LoadBarState` . Запишите сведения в реестр, вызвав команду [CWinApp:: сетрегистрикэй](../../mfc/reference/cwinapp-class.md#setregistrykey). Запишите сведения в INI-файл, вызвав [савебарстате](#savebarstate).

## <a name="cframewndloadframe"></a><a name="loadframe"></a> CFrameWnd:: Лоадфраме

Вызовите, чтобы динамически создать окно фрейма из сведений о ресурсе.

```
virtual BOOL LoadFrame(
    UINT nIDResource,
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,
    CWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*нидресаурце*<br/>
Идентификатор общих ресурсов, связанных с окном фрейма.

*двдефаултстиле*<br/>
[Стиль](../../mfc/reference/styles-used-by-mfc.md#window-styles)рамки. Включите стиль FWS_ADDTOTITLE, если нужно, чтобы в строке заголовка автоматически отображалось имя документа, представленного в окне.

*ппарентвнд*<br/>
Указатель на родительский кадр.

*pContext*<br/>
Указатель на структуру [ккреатеконтекст](../../mfc/reference/ccreatecontext-structure.md) . Этот параметр может иметь значение NULL.

### <a name="remarks"></a>Примечания

Создайте `CFrameWnd` объект в два этапа. Сначала следует вызвать конструктор, который создает `CFrameWnd` объект, а затем вызвать метод `LoadFrame` , который загружает окно фрейма Windows и связанные ресурсы и прикрепляет окно фрейма к `CFrameWnd` объекту. Параметр *нидресаурце* указывает меню, таблицу сочетаний клавиш, значок и строковый ресурс заголовка окна фрейма.

Используйте `Create` функцию члена, а не в `LoadFrame` том случае, если необходимо указать все параметры создания окна фрейма.

Платформа вызывает, `LoadFrame` когда создает фрейм окна с помощью объекта шаблона документа.

Платформа использует аргумент *пконтекст* для указания объектов, которые должны быть подключены к окну фрейма, включая все содержащиеся в нем объекты представления. При вызове аргумент *пконтекст* можно установить в значение NULL `LoadFrame` .

## <a name="cframewndm_bautomenuenable"></a><a name="m_bautomenuenable"></a> CFrameWnd:: m_bAutoMenuEnable

Если этот элемент данных включен (по умолчанию), пункты меню, не имеющие ON_UPDATE_COMMAND_UI или ON_COMMAND обработчики, будут автоматически отключены, когда пользователь выберет меню.

```
BOOL m_bAutoMenuEnable;
```

### <a name="remarks"></a>Примечания

Элементы меню с обработчиком ON_COMMAND, но обработчик ON_UPDATE_COMMAND_UI не будет включен автоматически.

Если этот элемент данных задан, элементы меню автоматически включаются так же, как и кнопки панели инструментов.

> [!NOTE]
> `m_bAutoMenuEnable` не влияет на пункты меню верхнего уровня.

Этот элемент данных упрощает реализацию необязательных команд на основе текущего выбора и сокращает необходимость написания ON_UPDATE_COMMAND_UI обработчиков для включения и отключения пунктов меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#3](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]

## <a name="cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a> CFrameWnd:: Неготиатебордерспаце

Вызывайте эту функцию-член для согласования пространства границ в окне фрейма во время активизации OLE-размещения.

```
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,
    LPRECT lpRectBorder);
```

### <a name="parameters"></a>Параметры

*нбордеркмд*<br/>
Содержит одно из следующих значений из `enum BorderCmd` :

- `borderGet` = 1

- `borderRequest` = 2

- `borderSet` = 3

*лпректбордер*<br/>
Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) или объект [крект](../../atl-mfc-shared/reference/crect-class.md) , указывающий координаты границы.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция-член является `CFrameWnd` реализацией согласования границ пространства OLE.

## <a name="cframewndonbarcheck"></a><a name="onbarcheck"></a> CFrameWnd:: Онбарчекк

Вызывается при каждом выполнении действия на указанной панели элементов управления.

```
afx_msg BOOL OnBarCheck(UINT nID);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор отображаемой панели элементов управления.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если панель управления существовала; в противном случае — 0.

## <a name="cframewndoncontexthelp"></a><a name="oncontexthelp"></a> CFrameWnd:: Онконтексселп

Обрабатывает клавиши SHIFT + F1 для элементов на месте.

```
afx_msg void OnContextHelp();
```

### <a name="remarks"></a>Примечания

Чтобы включить контекстную справку, необходимо добавить элемент

[!code-cpp[NVC_MFCDocViewSDI#16](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]

к `CFrameWnd` схеме сообщений класса, а также добавьте запись ускорителя, обычно SHIFT + F1, чтобы включить эту функцию-член.

Если приложение является контейнером OLE, `OnContextHelp` помещает все элементы на месте, содержащиеся в объекте окна фрейма, в режим справки. Курсор превращается в стрелку и вопросительный знак, и пользователь может переместить указатель мыши и нажать левую кнопку мыши, чтобы выбрать диалоговое окно, окно, меню или кнопку команды. Эта функция члена вызывает функцию Windows `WinHelp` с контекстом справки объекта под курсором.

## <a name="cframewndoncreateclient"></a><a name="oncreateclient"></a> CFrameWnd:: Онкреатеклиент

Вызывается платформой во время выполнения `OnCreate` .

```
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,
    CCreateContext* pContext);
```

### <a name="parameters"></a>Параметры

*LPC*<br/>
Указатель на структуру [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) Windows.

*pContext*<br/>
Указатель на структуру [ккреатеконтекст](../../mfc/reference/ccreatecontext-structure.md) .

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Никогда не вызывайте эту функцию.

Реализация по умолчанию этой функции создает `CView` объект из сведений, предоставленных в *пконтекст*, если это возможно.

Переопределите эту функцию, чтобы переопределить значения, переданные в `CCreateContext` объекте, или изменить способ создания элементов управления в основной клиентской области окна фрейма. `CCreateContext`Члены, которые можно переопределить, описаны в классе [ккреатеконтекст](../../mfc/reference/ccreatecontext-structure.md) .

> [!NOTE]
> Не заменяйте значения, переданные в `CREATESTRUCT` структуре. Они предназначены только для использования в информационных целях. Если необходимо переопределить исходный прямоугольник окна, например переопределить `CWnd` функцию члена [PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).

## <a name="cframewndonhidemenubar"></a><a name="onhidemenubar"></a> CFrameWnd:: Онхидеменубар

Эта функция вызывается, когда система собирается скрыть строку меню в текущем приложении MFC.

```
virtual void OnHideMenuBar();
```

### <a name="remarks"></a>Примечания

Этот обработчик событий позволяет приложению выполнять пользовательские действия, когда система собирается скрыть меню. Нельзя запретить скрытие меню, но, например, можно вызвать другие методы для получения стиля или состояния меню.

## <a name="cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a> CFrameWnd:: Онсетпревиевмоде

Вызов этой функции-члена переключает окно главного фрейма приложения в режим предварительного просмотра и из него.

```
virtual void OnSetPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>Параметры

*бпревиев*<br/>
Указывает, следует ли размещать приложение в режиме предварительного просмотра. Задайте значение TRUE для размещения в режиме предварительного просмотра, значение FALSE, чтобы отменить режим предварительного просмотра.

*пстате*<br/>
Указатель на `CPrintPreviewState` структуру.

### <a name="remarks"></a>Примечания

Реализация по умолчанию отключает все стандартные панели инструментов и скрывает главное меню и главное окно клиента. Это превращает окна фрейма MDI во временные окна фрейма SDI.

Переопределите эту функцию члена, чтобы настроить скрытие и отображение панелей элементов управления и других частей окна фрейма во время предварительного просмотра. Вызовите реализацию базового класса из переопределенной версии.

## <a name="cframewndonshowmenubar"></a><a name="onshowmenubar"></a> CFrameWnd:: Оншовменубар

Эта функция вызывается, когда система собирается отобразить строку меню в текущем приложении MFC.

```
virtual void OnShowMenuBar();
```

### <a name="remarks"></a>Примечания

Этот обработчик событий позволяет приложению выполнять пользовательские действия при отображении меню. Нельзя запретить отображение меню, но можно, например, вызвать другие методы для получения стиля или состояния меню.

## <a name="cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a> CFrameWnd:: Онупдатеконтролбармену

Вызывается структурой при обновлении связанного меню.

```
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>Параметры

*пкмдуи*<br/>
Указатель на объект [Поддержка CCmdUI](../../mfc/reference/ccmdui-class.md) , представляющий меню, вызвавшее команду обновления. Обработчик обновлений вызывает функцию-член [Enable](../../mfc/reference/ccmdui-class.md#enable) `CCmdUI` объекта через *пкмдуи* для обновления пользовательского интерфейса.

## <a name="cframewndrecalclayout"></a><a name="recalclayout"></a> CFrameWnd:: RecalcLayout

Вызывается структурой при включении или отключении стандартных панелей элементов управления или при изменении размера окна фрейма.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Параметры

*бнотифи*<br/>
Определяет, получает ли активный элемент на месте фрейма окна уведомление об изменении макета. Если значение равно TRUE, элемент уведомлен; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Реализация по умолчанию этой функции-члена вызывает `CWnd` функцию-член `RepositionBars` для изменения расположения всех панелей элементов управления в кадре, а также в основном клиентском окне (обычно это `CView` или мдиклиент).

Переопределите эту функцию члена, чтобы управлять внешним видом и поведением панелей элементов управления после изменения макета окна фрейма. Например, вызовите его при включении или отключении панелей управления или при добавлении другой панели элементов управления.

## <a name="cframewndrectdefault"></a><a name="rectdefault"></a> CFrameWnd:: Ректдефаулт

Передайте этот статический `CRect` параметр в качестве параметра при создании окна, позволяющего Windows выбрать исходный размер и расположение окна.

```
static AFX_DATA const CRect rectDefault;
```

## <a name="cframewndsavebarstate"></a><a name="savebarstate"></a> CFrameWnd:: Савебарстате

Эта функция вызывается для хранения сведений о каждой панели управления, принадлежащей окну фрейма.

```cpp
void SaveBarState(LPCTSTR lpszProfileName) const;
```

### <a name="parameters"></a>Параметры

*лпсзпрофиленаме*<br/>
Имя раздела в файле инициализации или ключ в реестре Windows, где хранятся сведения о состоянии.

### <a name="remarks"></a>Примечания

Эти сведения можно прочитать из файла инициализации с помощью [лоадбарстате](#loadbarstate). Хранящиеся сведения включают видимость, ориентацию по горизонтали и вертикали, состояние закрепления и положение панели элементов управления.

## <a name="cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a> CFrameWnd:: Сетактивепревиеввиев

Определяет указанное представление как активное представление для расширенного просмотра.

```cpp
void SetActivePreviewView(CView* pViewNew);
```

### <a name="parameters"></a>Параметры

*пвиевнев*<br/>
Указатель на представление, которое необходимо активировать.

### <a name="remarks"></a>Примечания

## <a name="cframewndsetactiveview"></a><a name="setactiveview"></a> CFrameWnd:: Сетактивевиев

Вызовите эту функцию члена, чтобы задать активное представление.

```cpp
void SetActiveView(
    CView* pViewNew,
    BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Параметры

*пвиевнев*<br/>
Указывает указатель на объект [CView](../../mfc/reference/cview-class.md) или значение NULL для отсутствия активного представления.

*бнотифи*<br/>
Указывает, должно ли представление получать уведомления об активации. Если значение равно TRUE, `OnActivateView` вызывается для нового представления; значение false, если нет.

### <a name="remarks"></a>Примечания

Платформа будет вызывать эту функцию автоматически по мере того, как пользователь меняет фокус на представление в окне фрейма. Можно явно вызвать `SetActiveView` , чтобы изменить фокус на указанное представление.

## <a name="cframewndsetdockstate"></a><a name="setdockstate"></a> CFrameWnd:: Сетдоккстате

Вызовите эту функцию-член, чтобы применить сведения о состоянии, хранящиеся в `CDockState` объекте, к панелям управления окна фрейма.

```cpp
void SetDockState(const CDockState& state);
```

### <a name="parameters"></a>Параметры

*state*<br/>
Примените сохраненное состояние к панелям управления окна фрейма.

### <a name="remarks"></a>Примечания

Чтобы восстановить предыдущее состояние панелей элементов управления, можно загрузить сохраненное состояние с помощью `CDockState::LoadState` или `Serialize` , а затем использовать, `SetDockState` чтобы применить его к панелям управления окна фрейма. Предыдущее состояние хранится в `CDockState` объекте с помощью `GetDockState`

## <a name="cframewndsetmenubarstate"></a><a name="setmenubarstate"></a> CFrameWnd:: Сетменубарстате

Задает состояние отображения меню в текущем приложении MFC для скрытия или отображения.

```
virtual BOOL SetMenuBarState(DWORD nState);
```

### <a name="parameters"></a>Параметры

*Nсведения*\
окне Указывает, следует ли отображать или скрывать меню. Параметр *nсведения* может иметь следующие значения:

- `AFX_MBS_VISIBLE` (0x01) — отображает меню, если оно скрыто, но не имеет результата, если оно видимо.
- `AFX_MBS_HIDDEN` (0x02) — скрывает меню, если оно отображается, но не имеет результата, если оно скрыто.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно изменяет состояние меню; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

При возникновении ошибки времени выполнения этот метод утверждается в режиме отладки и создает исключение, производное от класса [CException](../../mfc/reference/cexception-class.md) .

## <a name="cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a> CFrameWnd:: Сетменубарвисибилити

Задает поведение по умолчанию для меню в текущем приложении MFC, которое должно быть скрытым или видимым.

```
virtual void SetMenuBarVisibility(DWORD nStyle);
```

### <a name="parameters"></a>Параметры

*нстиле*\
окне Указывает, скрывается ли меню по умолчанию или является видимым и имеет фокус. Параметр *нстиле* может иметь следующие значения:

- `AFX_MBV_KEEPVISIBLE` (0x01) — меню отображается всегда, и по умолчанию он не имеет фокуса.

- `AFX_MBV_DISPLAYONFOCUS` (0x02) — меню скрыто по умолчанию. Если меню скрыто, нажмите клавишу ALT, чтобы отобразить меню и присвоить ему фокус. Если меню отображается, нажмите клавишу ALT или клавишу ESC, чтобы скрыть меню.

- `AFX_MBV_DISPLAYONFOCUS` (0x02) &#124; `AFX_MBV_DISPLAYONF10` (0x04) (побитовое сочетание (или)) — меню скрыто по умолчанию. Если меню скрыто, нажмите клавишу F10, чтобы открыть меню и придать ему фокус. Если меню отображается, нажмите клавишу F10, чтобы включить или отключить фокус в меню. Меню отображается до тех пор, пока вы не нажмете клавишу ALT или ESC, чтобы скрыть его.

### <a name="remarks"></a>Примечания

Если значение параметра *нстиле* недопустимо, этот метод утверждается в режиме отладки и вызывает [Цинвалидаржексцептион](../../mfc/reference/cinvalidargexception-class.md) в режиме выпуска. В случае других ошибок времени выполнения этот метод утверждается в режиме отладки и создает исключение, производное от класса [CException](../../mfc/reference/cexception-class.md) .

Этот метод влияет на состояние меню в приложениях, написанных для Windows Vista и более поздних версий.

## <a name="cframewndsetmessagetext"></a><a name="setmessagetext"></a> CFrameWnd:: Сетмессажетекст

Вызовите эту функцию, чтобы поместить строку в панель состояния с ИДЕНТИФИКАТОРом 0.

```cpp
void SetMessageText(LPCTSTR lpszText);
void SetMessageText(UINT nID);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указывает на строку, которая будет помещена в строку состояния.

*nID*<br/>
Строковый идентификатор ресурса строки, помещаемой в строку состояния.

### <a name="remarks"></a>Примечания

Обычно это самая левая и длинная область строки состояния.

## <a name="cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a> CFrameWnd:: Сетпрогрессбарпоситион

Задает текущую положение индикатора выполнения Windows 7, отображаемого на панели задач.

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>Параметры

*нпрогресспос*<br/>
Задает устанавливаемое расположение. Он должен находиться в диапазоне, заданном параметром `SetProgressBarRange` .

### <a name="remarks"></a>Примечания

## <a name="cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a> CFrameWnd:: Сетпрогрессбарранже

Задает диапазон для индикатора выполнения Windows 7, отображаемого на панели задач.

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>Параметры

*нранжемин*<br/>
Минимальное значение.

*нранжемакс*<br/>
Максимальное значение.

### <a name="remarks"></a>Примечания

## <a name="cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a> CFrameWnd:: Сетпрогрессбарстате

Задает тип и состояние индикатора хода выполнения, отображаемого на кнопке панели задач.

```cpp
void SetProgressBarState(TBPFLAG tbpFlags);
```

### <a name="parameters"></a>Параметры

*тбпфлагс*<br/>
Флаги, управляющие текущим состоянием кнопки хода выполнения. Укажите только один из следующих флагов, так как все состояния являются взаимоисключающими: TBPF_NOPROGRESS, TBPF_INDETERMINATE, TBPF_NORMAL, TBPF_ERROR, TBPF_PAUSED.

### <a name="remarks"></a>Примечания

## <a name="cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a> CFrameWnd:: Сеттаскбароверлайикон

Перегружен. Применяет наложение к кнопке на панели задач для указания состояния приложения или уведомления пользователя.

```
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,
    LPCTSTR lpcszDescr);

BOOL SetTaskbarOverlayIcon(
    HICON hIcon,
    LPCTSTR lpcszDescr);
```

### <a name="parameters"></a>Параметры

*нидресаурце*<br/>
Указывает идентификатор ресурса значка, используемого в качестве оверлея. Дополнительные сведения см. в описании *Хикон* .

*лпксздескр*<br/>
Указатель на строку, которая предоставляет замещающую текстовую версию информации, переданной наложением, для специальных возможностей.

*hIcon*<br/>
Маркер значка, используемый в качестве наложенного. Это должен быть маленький значок, который измеряет 16x16 пикселей в 96 точках на дюйм (DPI). Если значок оверлея уже применен к кнопке панели задач, то существующий оверлей заменяется. Это значение может быть равно NULL. Способ обработки значения NULL зависит от того, представляет ли кнопка панели задач одно окно или группу окон. Вызывающее приложение несет ответственность за освобождение *Хикон* , когда оно больше не требуется.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE в случае успешного выполнения; Значение FALSE, если версия ОС меньше, чем Windows 7, или если возникает ошибка при установке значка.

### <a name="remarks"></a>Примечания

## <a name="cframewndsettitle"></a><a name="settitle"></a> CFrameWnd:: Сеттитле

Задает заголовок объекта Window.

```cpp
void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>Параметры

*лпсзтитле*<br/>
Указатель на строку символов, содержащую заголовок объекта Window.

## <a name="cframewndshowcontrolbar"></a><a name="showcontrolbar"></a> CFrameWnd:: Шовконтролбар

Вызовите эту функцию члена, чтобы показать или скрыть панель элементов управления.

```cpp
void ShowControlBar(
    CControlBar* pBar,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>Параметры

*пбар*<br/>
Указатель на панель элементов управления, которую необходимо отобразить или скрыть.

*bShow*<br/>
Значение TRUE указывает, что панель элементов управления должна отображаться. Значение FALSE указывает, что панель элементов управления должна быть скрыта.

*бделай*<br/>
При значении TRUE откладывается отображение панели управления. Значение FALSE показывает, что панель управления отображается немедленно.

## <a name="cframewndshowownedwindows"></a><a name="showownedwindows"></a> CFrameWnd:: Шововнедвиндовс

Вызовите эту функцию-член, чтобы отобразить все окна, являющиеся потомками `CFrameWnd` объекта.

```cpp
void ShowOwnedWindows(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
Указывает, должны ли быть отображены или скрыты собственные окна.

## <a name="see-also"></a>См. также

[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)<br/>
[Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)<br/>
[Класс CView](../../mfc/reference/cview-class.md)<br/>
[Класс CDocTemplate](../../mfc/reference/cdoctemplate-class.md)<br/>
[Структура Крунтимекласс](../../mfc/reference/cruntimeclass-structure.md)
