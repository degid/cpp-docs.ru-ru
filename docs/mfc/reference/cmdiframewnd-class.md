---
title: Класс CMDIFrameWnd
ms.date: 11/04/2016
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
ms.openlocfilehash: 321ad0364257d7c20d54f9fdc884073381117c6f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222957"
---
# <a name="cmdiframewnd-class"></a>Класс CMDIFrameWnd

Предоставляет функции фреймового окна многодокументного интерфейса Windows (MDI) и элементы для управления окном.

## <a name="syntax"></a>Синтаксис

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMDIFrameWnd:: CMDIFrameWnd](#cmdiframewnd)|Создает документ `CMDIFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMDIFrameWnd:: Креатеклиент](#createclient)|Создает окно МДИКЛИЕНТ Windows для этого `CMDIFrameWnd` . Вызывается `OnCreate` функцией члена класса `CWnd` .|
|[CMDIFrameWnd:: Креатеневчилд](#createnewchild)|Создает новое дочернее окно.|
|[CMDIFrameWnd:: Жетвиндовменупопуп](#getwindowmenupopup)|Возвращает всплывающее меню окна.|
|[CMDIFrameWnd:: Мдиактивате](#mdiactivate)|Активирует другое дочернее окно MDI.|
|[CMDIFrameWnd:: Мдикаскаде](#mdicascade)|Упорядочивает все дочерние окна в каскадном формате.|
|[CMDIFrameWnd:: Мдижетактиве](#mdigetactive)|Извлекает текущее активное дочернее окно MDI вместе с флагом, указывающим, развернут ли дочерний элемент.|
|[CMDIFrameWnd:: Мдииконарранже](#mdiiconarrange)|Упорядочивает все дочерние окна документа.|
|[CMDIFrameWnd:: Мдимаксимизе](#mdimaximize)|Разворачивает дочернее окно MDI.|
|[CMDIFrameWnd:: Мдинекст](#mdinext)|Активирует дочернее окно сразу за текущим активным дочерним окном и размещает текущее активное дочернее окно позади всех остальных дочерних окон.|
|[CMDIFrameWnd:: Мдипрев](#mdiprev)|Активирует предыдущее дочернее окно и размещает текущее активное дочернее окно непосредственно за ним.|
|[CMDIFrameWnd:: Мдиресторе](#mdirestore)|Восстанавливает дочернее окно MDI из развернутого или минимального размера.|
|[CMDIFrameWnd:: Мдисетмену](#mdisetmenu)|Заменяет меню окна фрейма MDI, всплывающего меню окна или и того и другого.|
|[CMDIFrameWnd:: Мдитиле](#mditile)|Упорядочивает все дочерние окна в мозаичном формате.|

## <a name="remarks"></a>Примечания

Чтобы создать полезное окно фрейма MDI для приложения, создайте класс, производный от `CMDIFrameWnd` . Добавьте переменные члена в производный класс для хранения данных, относящихся к вашему приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Можно создать окно фрейма MDI, вызвав функцию-член [CREATE](../../mfc/reference/cframewnd-class.md#create) или [лоадфраме](../../mfc/reference/cframewnd-class.md#loadframe) `CFrameWnd` .

Перед вызовом `Create` или `LoadFrame` необходимо создать объект окна фрейма в куче с помощью **`new`** оператора C++. Перед вызовом можно `Create` также зарегистрировать класс окна с глобальной функцией [афксрегистервндкласс](application-information-and-management.md#afxregisterwndclass) , чтобы задать стили значков и классов для фрейма.

Используйте `Create` функцию члена для передачи параметров создания кадра в качестве непосредственных аргументов.

`LoadFrame`требует меньше аргументов `Create` , чем, и вместо этого извлекает большинство значений по умолчанию из ресурсов, включая заголовок фрейма, значок, таблицу сочетаний клавиш и меню. Для доступа к `LoadFrame` ресурсам все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).

Несмотря `MDIFrameWnd` на то, что является производным от `CFrameWnd` , класс окна фрейма, производный от, `CMDIFrameWnd` не должен объявляться вместе с `DECLARE_DYNCREATE` .

`CMDIFrameWnd`Класс наследует большую часть своей реализации по умолчанию из `CFrameWnd` . Подробный список этих функций см. в описании класса [CFrameWnd](../../mfc/reference/cframewnd-class.md) . `CMDIFrameWnd`Класс имеет следующие дополнительные возможности:

- Окно фрейма MDI управляет окном МДИКЛИЕНТ, перемещает его в сочетании с панелями управления. Окно клиента MDI — это прямой родительский элемент окон дочернего фрейма MDI. Стили окон WS_HSCROLL и WS_VSCROLL, заданные в элементе, `CMDIFrameWnd` применяются к окну клиента MDI, а не к главному окну фрейма, чтобы пользователь мог прокручивать клиентскую область MDI (например, как в диспетчере программ Windows).

- Окно фрейма MDI владеет меню по умолчанию, которое используется в качестве строки меню при отсутствии активного дочернего окна MDI. При наличии активной дочерней MDI строка меню окна фрейма MDI автоматически заменяется меню дочернего окна MDI.

- Окно фрейма MDI работает совместно с текущим дочерним окном MDI, если оно имеется. Например, сообщения команды делегируются активному в данный момент дочернему элементу MDI до окна фрейма MDI.

- Окно фрейма MDI имеет обработчики по умолчанию для следующих стандартных команд меню "окно":

  - ID_WINDOW_TILE_VERT

  - ID_WINDOW_TILE_HORZ

  - ID_WINDOW_CASCADE

  - ID_WINDOW_ARRANGE

- Окно фрейма MDI также имеет реализацию ID_WINDOW_NEW, которая создает новый фрейм и представление в текущем документе. Приложение может переопределять эти реализации команд по умолчанию для настройки обработки окон MDI.

Не используйте **`delete`** оператор C++ для уничтожения окна фрейма. Используйте вместо этого `CWnd::DestroyWindow`. `CFrameWnd`Реализация служб `PostNcDestroy` удалит объект C++ при уничтожении окна. Когда пользователь закрывает окно фрейма, обработчик по умолчанию `OnClose` выполнит вызов `DestroyWindow` .

Дополнительные сведения о см `CMDIFrameWnd` . в разделе [окна с рамками](../../mfc/frame-windows.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="cmdiframewndcmdiframewnd"></a><a name="cmdiframewnd"></a>CMDIFrameWnd:: CMDIFrameWnd

Формирует объект `CMDIFrameWnd`.

```
CMDIFrameWnd();
```

### <a name="remarks"></a>Примечания

Вызовите `Create` функцию-член или, `LoadFrame` чтобы создать видимое окно фрейма MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

## <a name="cmdiframewndcreateclient"></a><a name="createclient"></a>CMDIFrameWnd:: Креатеклиент

Создает клиентское MDI-окно, управляющее `CMDIChildWnd` объектами.

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Параметры

*лпкреатеструкт*<br/>
Длинный указатель на структуру [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) .

*пвиндовмену*<br/>
Указатель на всплывающее меню окна.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эту функцию члена следует вызывать, если вы переопределяете `OnCreate` функцию члена напрямую.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

## <a name="cmdiframewndcreatenewchild"></a><a name="createnewchild"></a>CMDIFrameWnd:: Креатеневчилд

Создает новое дочернее окно.

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>Параметры

*пкласс*<br/>
Класс времени выполнения создаваемого дочернего окна.

*нресаурце*<br/>
Идентификатор общих ресурсов, связанных с дочерним окном.

*hMenu*<br/>
Меню дочернего окна.

*хакцел*<br/>
Ускоритель дочернего окна.

### <a name="remarks"></a>Примечания

Эта функция используется для создания дочерних окон окна фрейма MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

## <a name="cmdiframewndgetwindowmenupopup"></a><a name="getwindowmenupopup"></a>CMDIFrameWnd:: Жетвиндовменупопуп

Вызовите эту функцию-член, чтобы получить маркер текущего всплывающего меню с именем "окно" (всплывающее меню с элементами меню для управления окнами MDI).

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>Параметры

*хменубар*<br/>
Текущая строка меню.

### <a name="return-value"></a>Возвращаемое значение

Всплывающее меню окна, если оно существует; в противном случае — NULL.

### <a name="remarks"></a>Примечания

Реализация по умолчанию ищет всплывающее меню, содержащее стандартные команды меню "окно", такие как ID_WINDOW_NEW и ID_WINDOW_TILE_HORZ.

Переопределите эту функцию-член, если у вас есть меню окон, в котором не используются стандартные идентификаторы команд меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

## <a name="cmdiframewndmdiactivate"></a><a name="mdiactivate"></a>CMDIFrameWnd:: Мдиактивате

Активирует другое дочернее окно MDI.

```cpp
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>Параметры

*пвндактивате*<br/>
Указывает на дочернее окно MDI, которое должно быть активировано.

### <a name="remarks"></a>Примечания

Эта функция члена отправляет сообщение [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) в активируемое дочернее окно и деактивирует дочернее окно.

Это то же сообщение, которое отправляется, если пользователь изменяет фокус на дочернее окно MDI с помощью мыши или клавиатуры.

> [!NOTE]
> Дочернее окно MDI активируется независимо от окна фрейма MDI. Когда кадр становится активным, дочернее окно, которое было активировано последним, отправляет [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) сообщение, чтобы нарисовать кадр активного окна и строку заголовка, но не получить еще одно сообщение WM_MDIACTIVATE.

### <a name="example"></a>Пример

См. пример для [CMDIFrameWnd:: жетвиндовменупопуп](#getwindowmenupopup).

## <a name="cmdiframewndmdicascade"></a><a name="mdicascade"></a>CMDIFrameWnd:: Мдикаскаде

Упорядочивает все дочерние окна MDI в формате Cascade.

```cpp
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Задает флаг Cascade. Можно указать только следующий флаг: MDITILE_SKIPDISABLED, который предотвращает каскадное отображение отключенных дочерних окон MDI.

### <a name="remarks"></a>Примечания

Первая версия, без `MDICascade` параметров, каскадно размещает все дочерние окна MDI, включая отключенные. Вторая версия при необходимости не позволяет каскадно отключить дочерние окна MDI, если для параметра *nуведомления* задано значение MDITILE_SKIPDISABLED.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

## <a name="cmdiframewndmdigetactive"></a><a name="mdigetactive"></a>CMDIFrameWnd:: Мдижетактиве

Извлекает текущее активное дочернее окно MDI вместе с флагом, указывающим, развернуто ли дочернее окно.

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>Параметры

*пбмаксимизед*<br/>
Указатель на возвращаемое логическое значение. Установите значение TRUE для возврата, если окно развернуто. в противном случае — FALSE.

### <a name="return-value"></a>Возвращаемое значение

Указатель на активное дочернее окно MDI.

### <a name="example"></a>Пример

См. пример для [CMDIChildWnd:: мдимаксимизе](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

## <a name="cmdiframewndmdiiconarrange"></a><a name="mdiiconarrange"></a>CMDIFrameWnd:: Мдииконарранже

Упорядочивает все дочерние окна документа.

```cpp
void MDIIconArrange();
```

### <a name="remarks"></a>Примечания

Он не влияет на несведенные дочерние окна.

### <a name="example"></a>Пример

См. пример для [CMDIFrameWnd:: мдикаскаде](#mdicascade).

## <a name="cmdiframewndmdimaximize"></a><a name="mdimaximize"></a>CMDIFrameWnd:: Мдимаксимизе

Разворачивает указанное дочернее окно MDI.

```cpp
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно для максимального увеличения.

### <a name="remarks"></a>Примечания

Когда дочернее окно разворачивается, Windows изменяет его размер, чтобы сделать клиентскую область заполнять окно клиента. Windows размещает меню элемента управления дочернего окна в строке меню фрейма, чтобы пользователь мог восстановить или закрыть дочернее окно. Он также добавляет заголовок дочернего окна в заголовок окна фрейма.

Если другое дочернее окно MDI активируется при разворачивании текущего активного дочернего окна MDI, Windows восстанавливает текущий активный дочерний элемент и разворачивает вновь активированное дочернее окно.

### <a name="example"></a>Пример

См. пример для [CMDIChildWnd:: мдимаксимизе](../../mfc/reference/cmdichildwnd-class.md#mdimaximize).

## <a name="cmdiframewndmdinext"></a><a name="mdinext"></a>CMDIFrameWnd:: Мдинекст

Активирует дочернее окно сразу за текущим активным дочерним окном и размещает текущее активное дочернее окно позади всех остальных дочерних окон.

```cpp
void MDINext();
```

### <a name="remarks"></a>Примечания

Если текущее активное дочернее окно MDI является развернутым, функция-член восстанавливает текущий активный дочерний элемент и разворачивает вновь активированный дочерний элемент.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

## <a name="cmdiframewndmdiprev"></a><a name="mdiprev"></a>CMDIFrameWnd:: Мдипрев

Активирует предыдущее дочернее окно и размещает текущее активное дочернее окно непосредственно за ним.

```cpp
void MDIPrev();
```

### <a name="remarks"></a>Примечания

Если текущее активное дочернее окно MDI является развернутым, функция-член восстанавливает текущий активный дочерний элемент и разворачивает вновь активированный дочерний элемент.

## <a name="cmdiframewndmdirestore"></a><a name="mdirestore"></a>CMDIFrameWnd:: Мдиресторе

Восстанавливает дочернее окно MDI из развернутого или минимального размера.

```cpp
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на окно для восстановления.

### <a name="example"></a>Пример

См. пример для [CMDIChildWnd:: мдиресторе](../../mfc/reference/cmdichildwnd-class.md#mdirestore).

## <a name="cmdiframewndmdisetmenu"></a><a name="mdisetmenu"></a>CMDIFrameWnd:: Мдисетмену

Заменяет меню окна фрейма MDI, всплывающего меню окна или и того и другого.

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>Параметры

*пфрамемену*<br/>
Задает меню нового меню окна фрейма. Если значение равно NULL, меню не изменяется.

*пвиндовмену*<br/>
Задает меню всплывающего меню нового окна. Если значение равно NULL, меню не изменяется.

### <a name="return-value"></a>Возвращаемое значение

Указатель на меню окна фрейма, замененное этим сообщением. Указатель может быть временным. Его не требуется сохранять для дальнейшего использования.

### <a name="remarks"></a>Примечания

После вызова `MDISetMenu` приложение должно вызвать функцию члена [дравменубар](../../mfc/reference/cwnd-class.md#drawmenubar) метода, `CWnd` чтобы обновить строку меню.

Если этот вызов заменяет всплывающее меню окна, элементы меню дочернего окна MDI удаляются из предыдущего меню окна и добавляются во всплывающее меню новое окно.

Если дочернее окно MDI развернуто и этот вызов заменяет меню окна фрейма MDI, меню управления и элементы управления восстановлением удаляются из предыдущего меню окна фрейма и добавляются в новое меню.

Не вызывайте эту функцию-член, если вы используете платформу для управления дочерними окнами MDI.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

## <a name="cmdiframewndmditile"></a><a name="mditile"></a>CMDIFrameWnd:: Мдитиле

Упорядочивает все дочерние окна в мозаичном формате.

```cpp
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Задает флаг мозаичного заполнения. Этот параметр может иметь один из следующих флагов:

- MDITILE_HORIZONTAL плитки дочерних окон MDI, чтобы одно окно появлялось над другим.

- MDITILE_SKIPDISABLED запрещает мозаичное заполнение отключенных дочерних окон MDI.

- MDITILE_VERTICAL плитки дочерних окон MDI, чтобы одно окно появился рядом с другим.

### <a name="remarks"></a>Примечания

Первая версия `MDITile` , без параметров, располагает окна по вертикали в Windows версий 3,1 и более поздних. Вторая версия окна плиток по вертикали или по горизонтали в зависимости от значения параметра *nуведомления* .

### <a name="example"></a>Пример

См. пример для [CMDIFrameWnd:: мдикаскаде](#mdicascade).

## <a name="see-also"></a>См. также статью

[Образец MDI-формы MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример МДИДОКВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример СНАПВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)
