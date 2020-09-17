---
title: Класс CPaneDialog
ms.date: 11/04/2016
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
ms.openlocfilehash: ad1225034cc5eca8ca53b042ebe3b55db4a2cf09
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364127"
---
# <a name="cpanedialog-class"></a>Класс CPaneDialog

Класс `CPaneDialog` поддерживает безрежимный, док-бокс диалогового.

## <a name="syntax"></a>Синтаксис

```
class CPaneDialog : public CDockablePane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CPaneDialog::CPaneDialog`|Конструктор по умолчанию.|
|`CPaneDialog::~CPaneDialog`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CPaneDialog::Создание](#create)|Создает док-окно диалогов и прикрепляет его к объекту. `CPaneDialog`|
|`CPaneDialog::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CPaneDialog::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Обрабатывает [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) сообщение. (Переопределяет `CBasePane::HandleInitDialog`.)|
|`CPaneDialog::OnEraseBkgnd`|Обрабатывает [сообщение WM_ERASEBKGND.](/windows/win32/winmsg/wm-erasebkgnd) (Переопределяет [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|
|`CPaneDialog::OnLButtonDblClk`|Обрабатывает [сообщение WM_LBUTTONDBLCLK.](/windows/win32/inputdev/wm-lbuttondblclk) (Переопределяет [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|Обрабатывает [WM_LBUTTONDOWN](/windows/win32/inputdev/wm-lbuttondown) сообщение. (Переопределяет [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|
|`CPaneDialog::OnUpdateCmdUI`|Вызывается по системе для обновления окна окна окна диалогового окна. (Перекрывает [CDockablePane::OnUpdateCmdUI](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|Обрабатывает [WM_WINDOWPOSCHANGING](/windows/win32/winmsg/wm-windowposchanging) сообщение. (Переопределяет [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Определяет шаблон для диалогового окна, который является контейнером управления OLE.|

## <a name="remarks"></a>Примечания

Постройте `CPaneDialog` объект в два этапа. Во-первых, построить объект в коде. Во-вторых, вызов [CPaneDialog::Создание](#create). Необходимо указать действительное имя шаблона ресурса или идентификатор шаблона и передать указатель в родительское окно. В противном случае процесс создания завершается неудачей. В диалоговом окне должен быть указан WS_CHILD и WS_VISIBLE стиль. Мы рекомендуем также указать WS_CLIPCHILDREN и WS_CLIPSIBLINGS стили. Для получения дополнительной информации [см.](styles-used-by-mfc.md#window-styles)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CPaneDialog](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpanedialog.h

## <a name="cpanedialogcreate"></a><a name="create"></a>CPaneDialog::Создание

Создает стыковочный диалоговый `CPaneDialog` ящик и прикрепляет его к объекту.

```
BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID,
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*lpszWindowName*<br/>
(в) Название стыковочного диалогового ящика.

*pParentWnd*<br/>
(в) Указывает на родительское окно.

*bHasGripper*<br/>
(в) TRUE для создания стыковочного диалогового ящика с заголовком (захват); в противном случае, FALSE.

*lpszTemplateName*<br/>
(в) Название шаблона диалогов ресурсов.

*nStyle*<br/>
(в) Стиль Windows.

*nID*<br/>
(в) Идентификатор управления.

*nIDTemplate*<br/>
(в) Идентификатор ресурса шаблона диалогов.

*dwTabbedStyle*<br/>
(в) Стиль окна с вкладками, который приводит к тому, что пользователь перетаскивает другое панель управления на подпись к этому панели управления. Значение по умолчанию является AFX_CBRS_REGULAR_TABS. Для получения дополнительной информации смотрите раздел Замечания [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) метод.

*dwControlBarStyle*<br/>
(в) Дополнительные атрибуты стиля. Значение по умолчанию является AFX_DEFAULT_DOCKING_PANE_STYLE. Для получения дополнительной информации смотрите раздел Замечания [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) метод.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод удается; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере показано, `Create` как `CPaneDialog` использовать метод в классе. Этот пример является частью [образца Set Pane Size.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

## <a name="cpanedialoghandleinitdialog"></a><a name="handleinitdialog"></a>CPaneDialog::HandleInitDialog

Обрабатывает [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) сообщение.

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Параметры

*wParam*<br/>
(в) Ручка к управлению, которое должно получить фокус клавиатуры по умолчанию.

*lParam*<br/>
(в) Определяет дополнительные данные инициализации.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если этот метод является успешным; в противном случае, FALSE. Кроме того, TRUE устанавливает фокус клавиатуры на элемент управления, указанный параметром *wParam;* FALSE предотвращает установку фокуса клавиатуры по умолчанию.

### <a name="remarks"></a>Примечания

Платформа использует этот метод для инициализации элементов управления и появления диалогового окна. Платформа вызывает этот метод перед отображением диалогового окна.

## <a name="cpanedialogsetoccdialoginfo"></a><a name="setoccdialoginfo"></a>CPaneDialog::SetOccDialogInfo

Определяет шаблон для диалогового окна, который является контейнером управления OLE.

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Параметры

*pOccDialogInfo*<br/>
(в) Указатель на шаблон диалогового окна, который используется для создания объекта коробки диалога. Значение этого параметра впоследствии передается в метод [COccManager::CreateDlgControls.](../../mfc/reference/coccmanager-class.md#createdlgcontrols)

### <a name="return-value"></a>Возвращаемое значение

Всегда TRUE.

### <a name="remarks"></a>Примечания

Этот метод поддерживает класс [COccManager,](../../mfc/reference/coccmanager-class.md) который управляет сайтами управления OLE и управлением ActiveX. Структура _AFX_OCC_DIALOG_INFO определяется в файле заголовка afxocc.h.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)<br/>
[Стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles)
