---
title: CmFCDropDownToolbarButton класс
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
ms.openlocfilehash: f09a2f3fe66abb86a8f220dbdf6744813ad9db0d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752403"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CmFCDropDownToolbarButton класс

Тип кнопки панели инструментов, который при нажатии ведет себя как обычная кнопка. Тем не менее, он открывает панель инструментов для выпадения [(класс CMFCDropDownToolBar,](../../mfc/reference/cmfcdropdowntoolbar-class.md) если пользователь нажимает и удерживает кнопку панели инструментов вниз.

## <a name="syntax"></a>Синтаксис

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Формирует объект `CMFCDropDownToolbarButton`.|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Копирует свойства другой кнопки панели инструментов на текущую кнопку. (Переопределяет [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|
|`CMFCDropDownToolbarButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Открывает панель инструментов для выпадения.|
|[CMFCDropDownToolbarbutton::ExporttoMenuButton](#exporttomenubutton)|Копирует текст из кнопки панели инструментов в меню. (Переопределяет [CMFCToolBarButton::ExporttoMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Извлекает панель инструментов, связанную с кнопкой.|
|`CMFCDropDownToolbarButton::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Определяет, открыта ли панель инструментов для выпадения.|
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Определяет, может ли кнопка отображаться с расширенной границей. (Переопределяет [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|
|[CMFCDropDownToolbarbutton::OncalculateSize](#oncalculatesize)|Вызывается фреймворком для расчета размера кнопки для заданного контекста устройства и состояния стыковки. (Переопределяет [CMFCToolBarButton::OncalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|`CMFCDropDownToolbarButton::OnCancelMode`|Вызывается по системе для обработки [сообщения WM_CANCELMODE.](/windows/win32/winmsg/wm-cancelmode) (Переопределяет `CMCToolBarButton::OnCancelMode`.)|
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Вызывается по фрейму, когда кнопка вставляется в новую панель инструментов. (Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[CMFCDropDownToolbarButton::OnClick](#onclick)|Вызывается по фреймворку, когда пользователь нажимает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Вызывается по фреймворку, когда пользователь выпускает кнопку мыши. (Переопределяет [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|
|[CMFCDropDownToolbarbutton::OnContextHelp](#oncontexthelp)|Вызывается в фреймворке, когда панель родительских инструментов обрабатывает WM_HELPHITTEST сообщение. (Переопределяет [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Изменяет предоставленное меню, когда приложение отображает меню ярлыка на панели родительских инструментов. (Переопределяет [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|
|[CMFCDropDownToolbarButton::Ondraw](#ondraw)|Вызывается в рамках, чтобы нарисовать кнопку с помощью указанных стилей и опций. (Переопределяет [CMFCToolBarButton::Ondraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Вызывается фреймворком, чтобы нарисовать кнопку в панели **команд** в поле **настраивания** диалогов. (Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|
|[CMFCDropDownToolbarКнопка::Сериализация](#serialize)|Читает этот объект из архива или запишет его в архив. (Переопределяет [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Устанавливает команду по умолчанию, которую использует инфраструктура, когда пользователь нажимает на кнопку.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Определяет продолжительность времени, в течение которого пользователь должен удерживать кнопку мыши до того, как появится панель инструментов.|

## <a name="remarks"></a>Примечания

А `CMFCDropDownToolBarButton` отличается от обычной кнопки тем, что она имеет небольшую стрелку в правом нижнем углу кнопки. После того, как пользователь выбирает кнопку из панели инструментов, панель инструментов отображается, фреймворк отображает свою иконку на кнопке панели инструментов верхнего уровня (кнопка с небольшой стрелкой в правом нижнем углу).

Для получения информации о том, как реализовать панель инструментов для выпадающих, [см.](../../mfc/reference/cmfcdropdowntoolbar-class.md)

Объект `CMFCDropDownToolBarButton` может быть экспортирован на объект [класса CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md) и отображаться в виде кнопки меню с всплывающее меню.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdropdowntoolbar.h

## <a name="cmfcdropdowntoolbarbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCDropDownToolbarButton::CopyFrom

Копирует свойства другой кнопки панели инструментов на текущую кнопку.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
(в) Ссылка на кнопку исходного кода, из которой можно скопировать.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы скопировать другую кнопку панели инструментов на эту кнопку панели инструментов. *src* должен быть `CMFCDropDownToolbarButton`типа .

## <a name="cmfcdropdowntoolbarbuttoncmfcdropdowntoolbarbutton"></a><a name="cmfcdropdowntoolbarbutton"></a>CMFCDropDownToolbarButton::CMFCDropDownToolbarButton

Формирует объект `CMFCDropDownToolbarButton`.

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
(в) Текст кнопки по умолчанию.

*pToolBar*<br/>
(в) Указатель на `CMFCDropDownToolBar` объект, который отображается при нажатии кнопки пользователя.

### <a name="remarks"></a>Примечания

Вторая перегрузка конструктора скопирует на кнопку выпадения первой кнопки из панели инструментов, которую указывает *pToolBar.*

Как правило, кнопка панели инструментов сбрасывает сярюние использует текст из самой недавно используемой кнопки в панели инструментов, которую указывает *pToolBar.* Он использует текст, указанный *lpszName,* когда кнопка преобразуется в кнопку меню или отображается во вкладке **Команд** **настраиваемого** диалогового окна. Для получения дополнительной информации о **настраиваемый** диалоговый ящик, [см.](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)

### <a name="example"></a>Пример

В следующем примере показано, как `CMFCDropDownToolbarButton` построить объект класса. Этот фрагмент кода является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

## <a name="cmfcdropdowntoolbarbuttondropdowntoolbar"></a><a name="dropdowntoolbar"></a>CMFCDropDownToolbarButton::DropDownToolbar

Открывает панель инструментов для выпадения.

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Родительское окно выпадающей кадра или NULL для использования родительского окна кнопки панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод успешен; в противном случае 0.

### <a name="remarks"></a>Примечания

[Метод CMFCDropDownToolbarButton::OnClick](#onclick) называет этот метод, чтобы открыть панель инструментов, когда пользователь нажимает и удерживает кнопку панели инструментов вниз.

Этот метод создает панель инструментов сброса вниз с помощью метода [CMFCDropDownFrame::Create.](../../mfc/reference/cmfcdropdownframe-class.md#create) Если панель родительских инструментов пристыкована вертикально, этот метод позиционирует панель инструментов как на левую, так и на правую сторону родительской панели инструментов, в зависимости от подгонки. В противном случае этот метод позиционирует панель инструментов свыки под родительской панелью инструментов.

Этот метод не удается, если *pWnd* является NULL, а кнопка панели инструментов выпадения не имеет родительского окна.

## <a name="cmfcdropdowntoolbarbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCDropDownToolbarbutton::ExporttoMenuButton

Копирует текст из кнопки панели инструментов в меню.

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>Параметры

*менюButton*<br/>
(в) Ссылка на кнопку целевого меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если метод выполнен успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод называет реализацию базового класса [(CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)), а затем прикладывает к кнопке меню целевого меню всплывающее меню, содержащее каждый элемент меню панели инструментов в этой кнопке. Этот метод не приговывает подменю к всплывающем меню.

Этот метод не удается, `m_pToolBar`если панель родительских инструментов, является NULL или реализация базового класса возвращает FALSE.

## <a name="cmfcdropdowntoolbarbuttongetdropdowntoolbar"></a><a name="getdropdowntoolbar"></a>CMFCDropDownToolbarButton::GetDropDownToolBar

Извлекает панель инструментов, связанную с кнопкой.

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>Возвращаемое значение

Панель инструментов выпадения, связанная с кнопкой.

### <a name="remarks"></a>Примечания

Этот метод `m_pToolBar` возвращает член данных.

## <a name="cmfcdropdowntoolbarbuttonisdropdown"></a><a name="isdropdown"></a>CMFCDropDownToolbarButton::IsDropDown

Определяет, открыта ли панель инструментов для выпадения.

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если панель инструментов выпадения в настоящее время открыта; в противном случае 0.

### <a name="remarks"></a>Примечания

Платформа открывает панель инструментов с выпадениеса с помощью метода [CMFCDropDownToolbarButton::DropDownToolbar.](#dropdowntoolbar) Рамка закрывает панель инструментов, когда пользователь нажимает кнопку левой мыши в области неклиента панели инструментов.

## <a name="cmfcdropdowntoolbarbuttonisextrasize"></a><a name="isextrasize"></a>CMFCDropDownToolbarButton::IsExtraSize

Определяет, может ли кнопка отображаться с расширенной границей.

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка панели инструментов может отображаться с расширенной границей; в противном случае 0.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации о расширенных границах, см [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).

## <a name="cmfcdropdowntoolbarbuttonm_uishowbardelay"></a><a name="m_uishowbardelay"></a>CMFCDropDownToolbarButton::m_uiShowBarDelay

Определяет продолжительность времени, в течение которого пользователь должен удерживать кнопку мыши до того, как появится панель инструментов.

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>Примечания

Время задержки измеряется в миллисекундах. По умолчанию используется значение 500. Можно установить еще одну задержку, изменив значение этого общего члена данных.

## <a name="cmfcdropdowntoolbarbuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFCDropDownToolbarbutton::OncalculateSize

Вызывается фреймворком для расчета размера кнопки для заданного контекста устройства и состояния стыковки.

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Контекст устройства, отображаемый кнопкой.

*размерПо умолчанию*<br/>
(в) Размер кнопки по умолчанию.

*bHorz*<br/>
(в) Состояние док-станции родительской панели инструментов. Этот параметр является правдой, если панель инструментов пристыкована горизонтально или плавает, или FALSE, если панель инструментов пристыкована вертикально.

### <a name="return-value"></a>Возвращаемое значение

Структура, `SIZE` содержащая размеры кнопки, в пикселях.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnCalculateSize),](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)добавляя ширину стрелки выпадения в горизонтальное измерение размера кнопки.

## <a name="cmfcdropdowntoolbarbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCDropDownToolbarButton::OnChangeParentWnd

Вызывается по фрейму, когда кнопка вставляется в новую панель инструментов.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Параметры

*pWndParent*<br/>
(в) Новое родительское окно.

### <a name="remarks"></a>Примечания

Этот метод переопределяет реализацию базового класса [(CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) путем очистки текстовой этикетки [(CMFCToolBarButton:::m_strText)](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)и установка [CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) и [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) членов данных false.

## <a name="cmfcdropdowntoolbarbuttononclick"></a><a name="onclick"></a>CMFCDropDownToolbarButton::OnClick

Вызывается по фреймворку, когда пользователь нажимает кнопку мыши.

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Родительское окно кнопки панели инструментов.

*bDelay*<br/>
(в) ПРАВДА, если сообщение должно быть обработано с задержкой.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка обрабатывает сообщение щелчка; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), путем обновления состояния панели инструментов для выпадения.

Когда пользователь нажимает кнопку панели инструментов, этот метод создает таймер, который ждет продолжительность времени, указанного [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay) членом данных, а затем открывает панель инструментов с помощью метода [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) метод. Этот метод закрывает панель инструментов для выпадения во второй раз, когда пользователь нажимает кнопку панели инструментов.

## <a name="cmfcdropdowntoolbarbuttononclickup"></a><a name="onclickup"></a>CMFCDropDownToolbarButton::OnClickUp

Вызывается по фреймворку, когда пользователь выпускает кнопку мыши.

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка обрабатывает сообщение щелчка; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса, [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), путем обновления состояния панели инструментов для выпадающих.

Этот метод останавливает выпадающий таймер панели инструментов, если он активен. Он закрывает панель инструментов, если она открыта.

Для получения дополнительной информации о выпадающих панели инструментов и выпадающих инструментов таймер, см [CMFCDropDownToolbarButton::OnClick](#onclick).

## <a name="cmfcdropdowntoolbarbuttononcontexthelp"></a><a name="oncontexthelp"></a>CMFCDropDownToolbarbutton::OnContextHelp

Вызывается в фреймворке, когда панель родительских инструментов обрабатывает WM_HELPHITTEST сообщение.

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Родительское окно кнопки панели инструментов.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если кнопка обрабатывает сообщение справки; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)), позвонив в [CMFCDropDownToolbarButton::OnClick](#onclick) метод с *bDelay,* установленным на FALSE. Этот метод возвращает значение, которое возвращается [CMFCDropDownToolbarButton::OnClick](#onclick).

Для получения дополнительной информации [TN028: Context-Sensitive Help Support](../../mfc/tn028-context-sensitive-help-support.md)о WM_HELPHITTEST сообщении см.

## <a name="cmfcdropdowntoolbarbuttononcustomizemenu"></a><a name="oncustomizemenu"></a>CMFCDropDownToolbarButton::OnCustomizeMenu

Изменяет предоставленное меню, когда приложение отображает меню ярлыка на панели родительских инструментов.

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>Параметры

*pMenu*<br/>
(в) Меню для настройки.

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает TRUE.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnCustomizeMenu)](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)путем отключения следующих элементов меню:

- **Копирование кнопки изображения**

- **Появление кнопки**

- **ОС контейнера**

- **Текст**

- **Изображение и текст**

Переопределить этот метод, чтобы изменить меню ярлыка, которое отображается в режиме настройки.

## <a name="cmfcdropdowntoolbarbuttonondraw"></a><a name="ondraw"></a>CMFCDropDownToolbarButton::Ondraw

Вызывается в рамках, чтобы нарисовать кнопку с помощью указанных стилей и опций.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Контекст устройства, отображаемый кнопкой.

*rect*<br/>
(в) Ограничивающий прямоугольник кнопки.

*pImages*<br/>
(в) Коллекция изображений панели инструментов, которая связана с кнопкой.

*bHorz*<br/>
(в) Состояние док-станции родительской панели инструментов. Этот параметр является правдой, когда кнопка пристыкована горизонтально и FALSE, когда кнопка пристыкована вертикально.

*bCustomizeMode*<br/>
(в) Определяет, находится ли панель инструментов в режиме настройки. Этот параметр является правдой, когда панель инструментов находится в режиме настройки и FALSE, когда панель инструментов не находится в режиме настройки.

*bHighlight*<br/>
(в) Определяет, выделена ли кнопка. Этот параметр является правдой, когда кнопка выделена и FALSE, когда кнопка не выделена.

*bDrawBorder*<br/>
(в) Определяет, должна ли кнопка отображать свою границу. Этот параметр является правдой, когда кнопка должна отображать свою границу и FALSE, когда кнопка не должна отображать свою границу.

*bGrayDisabledButtons*<br/>
(в) Уточняется, следует ли оттенить кнопки для инвалидов или использовать коллекцию отключенных изображений. Этот параметр является правдой, когда отключенные кнопки должны быть затенены и FALSE, когда этот метод должен использовать коллекцию отключенных изображений.

### <a name="remarks"></a>Примечания

Переопределить этот метод, чтобы настроить рисунок кнопки панели инструментов.

## <a name="cmfcdropdowntoolbarbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCDropDownToolbarButton::OnDrawOnCustomizeList

Вызывается фреймворком, чтобы нарисовать кнопку в панели **команд** в поле **настраивания** диалогов.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Контекст устройства, отображаемый кнопкой.

*rect*<br/>
(в) Ограничивающий прямоугольник кнопки.

*bВыбор*<br/>
(в) Выбрана ли кнопка. Если этот параметр является правдой, кнопка выбрана. Если этот параметр FALSE, кнопка не выбрана.

### <a name="return-value"></a>Возвращаемое значение

Ширина в пикселях кнопки на указанном контексте устройства.

### <a name="remarks"></a>Примечания

Этот метод вызывается полем диалога настройки **(вкладка Команд),** когда кнопка необходима для отображения в поле списка владельца.draw.

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)), изменив текстовую метку кнопки на имя кнопки (т.е. к значению параметра *lpszName,* который вы передали конструктору).

## <a name="cmfcdropdowntoolbarbuttonserialize"></a><a name="serialize"></a>CMFCDropDownToolbarКнопка::Сериализация

Читает этот объект из архива или запишет его в архив.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
(в) Объект, `CArchive` с которого или к которому сериализовать.

### <a name="remarks"></a>Примечания

Этот метод расширяет реализацию базового класса [(CMFCToolBarButton::Serialize)](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)путем сериализации идентификатора ресурсов родительской панели инструментов. При загрузке архива [(CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) возвращает ненулевое `m_pToolBar` значение) этот метод устанавливает член данных в панель инструментов, содержащую идентификатор сериализованного ресурса.

## <a name="cmfcdropdowntoolbarbuttonsetdefaultcommand"></a><a name="setdefaultcommand"></a>CMFCDropDownToolbarButton::SetDefaultCommand

Устанавливает команду по умолчанию, которую использует инфраструктура, когда пользователь нажимает на кнопку.

```cpp
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*uiCmd*<br/>
(в) Идентификатор команды по умолчанию.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы указать команду по умолчанию, которую выполняет инфраструктура, когда пользователь нажимает на кнопку. Элемент с идентификатором команды, указанным *uiCmd,* должен находиться в панели родительских выпадающих инструментов.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCDropDownToolBar](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)
