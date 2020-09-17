---
title: Класс CStatusBar
ms.date: 11/04/2016
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
ms.openlocfilehash: 969edb3b1c87da851d83d390ab9d4e707bd2eb1e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753057"
---
# <a name="cstatusbar-class"></a>Класс CStatusBar

Панель элементов управления со строкой областей текстового вывода или "индикаторов".

## <a name="syntax"></a>Синтаксис

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStatusBar:CStatusBar](#cstatusbar)|Формирует объект `CStatusBar`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStatusBar::CommandtoIndex](#commandtoindex)|Получает индекс для идентификатора данного индикатора.|
|[CStatusBar::Создание](#create)|Создает панель состояния, прикрепляет `CStatusBar` ее к объекту и устанавливает начальный шрифт и высоту бара.|
|[CStatusBar::CreateEx](#createex)|Создает `CStatusBar` объект с дополнительными `CStatusBarCtrl` стилями для встроенного объекта.|
|[CStatusBar::DrawItem](#drawitem)|Вызывается при изменении визуального аспекта управления планкой статуса владельца-рисования.|
|[CStatusBar::GetItemID](#getitemid)|Получает идентификатор индикатора для данного индекса.|
|[CStatusBar::GetItemRect](#getitemrect)|Получает прямоугольник отображения для данного индекса.|
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Получает идентификатор индикатора, стиль и ширину для данного индекса.|
|[CStatusBar::GetPaneStyle](#getpanestyle)|Получает стиль индикатора для данного индекса.|
|[CStatusBar::GetPaneText](#getpanetext)|Получает текст индикатора для данного индекса.|
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|Позволяет прямой доступ к базовому общему элементу управления.|
|[CStatusBar::SetIndicators](#setindicators)|Устанавливает иносиндикаторов.|
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Устанавливает идентификатор индикатора, стиль и ширину для данного индекса.|
|[CStatusBar::SetPaneStyle](#setpanestyle)|Устанавливает стиль индикатора для данного индекса.|
|[CStatusBar::SetPaneText](#setpanetext)|Устанавливает текст индикатора для данного индекса.|

## <a name="remarks"></a>Примечания

Выходные панели обычно используются в качестве строк сообщений и индикаторов состояния. Примеры включают строки справки меню, которые кратко объясняют выбранную команду меню и индикаторы, отображающие состояние SCROLL LOCK, NUM LOCK и других ключей.

[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl), функция участника, новая для MFC 4.0, позволяет воспользоваться поддержкой общего элемента управления Windows для настройки статус-бара и дополнительной функциональности. `CStatusBar`функции членов дают вам большую часть функциональности общих элементов управления Windows; однако, когда `GetStatusBarCtrl`вы звоните, вы можете дать ваш статус баров еще больше характеристик Windows 95/98 статус бар. Когда вы `GetStatusBarCtrl`звоните, он возвращает `CStatusBarCtrl` ссылку на объект. Дополнительную информацию о проектировании панелей инструментов с помощью общих элементов управления Windows можно узнать в [CStatusBarCtrl.](../../mfc/reference/cstatusbarctrl-class.md) Более подробную информацию об общих элементах управления [можно](/windows/win32/Controls/common-controls-intro) узнать в SDK Windows.

Рамочные хранилища индикаторной информации в массиве с самым левым индикатором на позиции 0. При создании строки состояния используется массив идентиверенных строк, который фреймворк ассоциирует с соответствующими индикаторами. Затем для доступа к индикатору можно использовать идентификатор строки или индекс.

По умолчанию первый индикатор является «эластичным»: он занимает длину панели статуса, не используемую другими стеклами индикатора, так что другие панели выравниваются по правой выровнены.

Чтобы создать панель статусов, выполните следующие действия:

1. Постройте `CStatusBar` объект.

1. Вызов функции [Create](#create) (или [CreateEx),](#createex)чтобы создать окно панели `CStatusBar` статуса и прикрепить его к объекту.

1. Вызов [SetIndicators,](#setindicators) чтобы связать идентификатор строки с каждым индикатором.

Существует три способа обновления текста в панели status-bar:

1. Вызов [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) для обновления текста только в панели 0.

1. Позвоните [cCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) в ON_UPDATE_COMMAND_UI обработчике ON_UPDATE_COMMAND_UI status.

1. Позвоните [SetPaneText,](#setpanetext) чтобы обновить текст для любой панели.

Позвоните [В SetPaneStyle,](#setpanestyle) чтобы обновить стиль панели status-bar.

Для получения дополнительной `CStatusBar`информации об использовании, см. статью [Статус Бар Реализация в MFC](../../mfc/status-bar-implementation-in-mfc.md) и [техническое примечание 31 : Контроль баров](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[Ccontrolbar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="cstatusbarcommandtoindex"></a><a name="commandtoindex"></a>CStatusBar::CommandtoIndex

Получает индекс индикатора для данного идентификатора.

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Параметры

*nIDFind*<br/>
Строка ID индикатора, индекс которого должен быть извлечен.

### <a name="return-value"></a>Возвращаемое значение

Индекс индикатора в случае успеха; -1, если не удалось.

### <a name="remarks"></a>Примечания

Индекс первого индикатора составляет 0.

## <a name="cstatusbarcreate"></a><a name="create"></a>CStatusBar::Создание

Создает бар статуса (окно ребенка) и `CStatusBar` связывает ее с объектом.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) окно Windows которого является родителем панели статуса.

*dwStyle*<br/>
Стиль статус-бар. В дополнение к стандартным [стилям](../../mfc/reference/styles-used-by-mfc.md#window-styles)Windows, эти стили поддерживаются.

- CBRS_TOP панель управления находится в верхней части окна кадра.

- CBRS_BOTTOM панель управления находится в нижней части окна кадра.

- CBRS_NOALIGN панель управления не перепозиционируется при повторном размере.

*nID*<br/>
Идентификатор панели инструментов для окна ребенка.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Также устанавливает начальный шрифт и устанавливает высоту панели статуса до значения по умолчанию.

## <a name="cstatusbarcreateex"></a><a name="createex"></a>CStatusBar::CreateEx

Вызовите эту функцию, чтобы создать бар статуса `CStatusBar` (окно ребенка) и связать ее с объектом.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
Указатель на объект [CWnd,](../../mfc/reference/cwnd-class.md) окно Windows которого является родителем панели статуса.

*dwCtrlStyle*<br/>
Дополнительные стили для создания встроенного объекта [CStatusBarCtrl.](../../mfc/reference/cstatusbarctrl-class.md) По умолчанию указывается панель статуса без сцепления размеров или поддержки tooltip. Поддерживаемые стили status bar:

- SBARS_SIZEGRIP Управление панели статуса включает в себя сцепление размеров в правом конце панели статуса. Сцепление размеров похоже на границу размеров; это прямоугольная область, которую пользователь может нажать и перетащить, чтобы изменить размер родительского окна.

- SBT_TOOLTIPS Панель статуса поддерживает панели инструментов.

Для получения подробной информации об этих [стилях см.](../../mfc/settings-for-the-cstatusbarctrl.md)

*dwStyle*<br/>
Стиль формата бара статуса. По умолчанию указывается, что видимая строка состояния создается в нижней части окна кадра. Примените любую комбинацию стилей управления ст. в [оконные](../../mfc/reference/styles-used-by-mfc.md#window-styles) панели, перечисленные в стилях окон и [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Однако этот параметр всегда должен включать WS_CHILD и WS_VISIBLE стили.

*nID*<br/>
Идентификатор окна ребенка в status bar.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция также устанавливает исходный шрифт и устанавливает высоту панели статуса до значения по умолчанию.

Используйте, `CreateEx`а не [создать](#create), когда определенные стили должны присутствовать во время создания встроенного управления панели статуса. Например, установите *dwCtrlStyle* для SBT_TOOLTIPS для отображения наконечников инструментов в объекте панели статуса.

## <a name="cstatusbarcstatusbar"></a><a name="cstatusbar"></a>CStatusBar:CStatusBar

Строит `CStatusBar` объект, при необходимости создает шрифт со статусом-баром состояния по умолчанию и устанавливает характеристики шрифта к значениям по умолчанию.

```
CStatusBar();
```

## <a name="cstatusbardrawitem"></a><a name="drawitem"></a>CStatusBar::DrawItem

Эта функция элемента вызывается инфраструктурой при изменении визуального аспекта нарисованной владельцем панели статуса.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на структуру [DRAWITEMSTRUCT,](/windows/win32/api/winuser/ns-winuser-drawitemstruct) содержащую информацию о типе требуемого чертежа.

### <a name="remarks"></a>Примечания

Член `itemAction` `DRAWITEMSTRUCT` структуры определяет действие чертежа, которое должно быть выполнено. Переопределить эту функцию элемента для `CStatusBar` реализации чертежа для объекта владельца-рисования. Приложение должно восстановить все объекты интерфейса графического устройства (GDI), выбранные для контекста отображения, поставляемые в *lpDrawItemStruct* до прекращения этой функции участника.

## <a name="cstatusbargetitemid"></a><a name="getitemid"></a>CStatusBar::GetItemID

Возвращает идентификатор индикатора, указанный *nIndex.*

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс индикатора, идентификатор которого должен быть извлечен.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор индикатора, указанный *nIndex.*

## <a name="cstatusbargetitemrect"></a><a name="getitemrect"></a>CStatusBar::GetItemRect

Копирует координаты индикатора, указанного *nIndex,* в структуру, указанную *lpRect.*

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс индикатора, координаты прямоугольника которого должны быть извлечены.

*lpRect*<br/>
Указывает на структуру [RECT](/windows/win32/api/windef/ns-windef-rect) или объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) который получит координаты индикатора, указанного *nIndex.*

### <a name="remarks"></a>Примечания

Координаты находятся в пикселях относительно верхнего левого угла панели статуса.

## <a name="cstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CStatusBar::GetPaneInfo

Устанавливает *nID,* *nStyle*и *cxWidth* к id, типу и ширине панели индикатора в месте, указанном *nIndex.*

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс панели, информация которого должна быть извлечена.

*nID*<br/>
Ссылка на UINT, установленную на идентификатор евентер панели.

*nStyle*<br/>
Ссылка на UINT, которая установлена на стиль панели.

*cxВимизм*<br/>
Ссылка на ряд, который установлен на ширину панели.

## <a name="cstatusbargetpanestyle"></a><a name="getpanestyle"></a>CStatusBar::GetPaneStyle

Вызовите эту функцию участника, чтобы получить стиль панели status.

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс панели, стиль которого должен быть извлечен.

### <a name="return-value"></a>Возвращаемое значение

Стиль панели статус-бара, указанный *nIndex*.

### <a name="remarks"></a>Примечания

Стиль панели определяет, как отображается панель.

Список стилей, доступных для баров [статуса, см.](#create)

## <a name="cstatusbargetpanetext"></a><a name="getpanetext"></a>CStatusBar::GetPaneText

Вызовите эту функцию участника, чтобы получить текст, который отображается в панели status-bar.

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс панели, текст которого должен быть извлечен.

*rString*<br/>
Ссылка на объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий извлеченный текст.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` содержащий текст панели.

### <a name="remarks"></a>Примечания

Вторая форма этой функции `CString` члена заполняет объект текстом строки.

## <a name="cstatusbargetstatusbarctrl"></a><a name="getstatusbarctrl"></a>CStatusBar::GetStatusBarCtrl

Эта функция члена позволяет прямой доступ к базовому общему элементу управления.

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Содержит ссылку на объект [CStatusBarCtrl.](../../mfc/reference/cstatusbarctrl-class.md)

### <a name="remarks"></a>Примечания

Используйте, `GetStatusBarCtrl` чтобы воспользоваться функциональностью общего элемента управления статус-баром Windows и воспользоваться [поддержкой, которая предоставляет CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) для настройки статус-бара. Например, используя общий элемент управления, можно указать стиль, включающий сцепление размеров в панели статуса, или можно указать стиль, чтобы в верхней части клиентской области родительского окна отображалась панель статуса.

Для получения более подробной информации об общих элементах управления можно ознакомиться [на общих элементах управления](/windows/win32/Controls/common-controls-intro) в SDK Windows.

## <a name="cstatusbarsetindicators"></a><a name="setindicators"></a>CStatusBar::SetIndicators

Устанавливает идентификатор каждого индикатора к значению, указанному соответствующим элементом *массива lpIDArray,* загружает ресурс строки, указанный каждым идентификатором, и устанавливает текст индикатора к строке.

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Параметры

*lpIDArray*<br/>
Указатель на массив идотов.

*nIDCount*<br/>
Количество элементов в массиве, на которые указывает *lpIDArray*.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="cstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a>CStatusBar::SetPaneInfo

Устанавливает указанное панель индикатора в новый идентификатор, стиль и ширину.

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс панели индикатора, стиль которого должен быть установлен.

*nID*<br/>
Новый идентификатор для панели индикатора.

*nStyle*<br/>
Новый стиль для панели индикатора.

*cxВимизм*<br/>
Новая ширина панели индикатора.

### <a name="remarks"></a>Примечания

Поддерживаются следующие стили индикаторов:

- SBPS_NOBORDERS Нет 3-D границы вокруг панели.

- SBPS_POPOUT обратная граница, чтобы текст "выскакивали".

- SBPS_DISABLED Не рисуйте текст.

- SBPS_STRETCH растяжек для заполнения неиспользуемого пространства. Только одна панель на бар статуса может иметь этот стиль.

- SBPS_NORMAL Нет стрейч, границы, или всплывающие.

## <a name="cstatusbarsetpanestyle"></a><a name="setpanestyle"></a>CStatusBar::SetPaneStyle

Вызовите эту функцию участника, чтобы установить стиль панели status.

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс панели, стиль которого должен быть установлен.

*nStyle*<br/>
Стиль панели, стиль которого должен быть установлен.

### <a name="remarks"></a>Примечания

Стиль панели определяет, как отображается панель.

Список стилей, доступных для статусных баров, [см. SetPaneInfo](#setpaneinfo).

## <a name="cstatusbarsetpanetext"></a><a name="setpanetext"></a>CStatusBar::SetPaneText

Вызов иэту функцию участника, чтобы установить текст панели на строку, на которую указывает *lpszNewText.*

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс панели, текст которого должен быть установлен.

*lpszNewText*<br/>
Указатель на новый текст панели.

*bUpdate*<br/>
Если true, панель недействительна после установки текста.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

После вызова `SetPaneText`необходимо добавить обработчик обновления uI для отображения нового текста в панели статуса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[CControlBar Class](../../mfc/reference/ccontrolbar-class.md)
