---
title: Класс CMFCStatusBar
ms.date: 11/19/2018
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
ms.openlocfilehash: 024fbad44af2fb11e967141fc8e7ccc0aad0ccbe
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753467"
---
# <a name="cmfcstatusbar-class"></a>Класс CMFCStatusBar

Класс `CMFCStatusBar` реализует панель статуса, `CStatusBar` похожую на класс. Однако класс `CMFCStatusBar` не содержит функции, предоставляемые классом `CStatusBar` , такие как возможность отображать изображения, анимации и индикаторы выполнения, а также возможность реагировать на двойные нажатия мыши.

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCStatusBar::CalcFixedLayout](#calcfixedlayout)|(Оверлет [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCStatusBar::CommandtoIndex](#commandtoindex)||
|[CMFCStatusBar::Создание](#create)|Создает панель управления и прикрепляет ее к объекту [CPane.](../../mfc/reference/cpane-class.md) (Перекрывает [CPane::Создание](../../mfc/reference/cpane-class.md#create).)|
|[CMFCStatusBar::CreateEx](#createex)|Создает панель управления и прикрепляет ее к объекту [CPane.](../../mfc/reference/cpane-class.md) (Перекрывает [CPane::CreateEx](../../mfc/reference/cpane-class.md#createex).)|
|[CMFCStatusBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|Определяет, может ли еще одно стекло быть динамически вставлено между этим стеклом и родительским кадром. (Переопределяет [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCStatusBar::EnablePaneDoubleClick](#enablepanedoubleclick)|Позволяет или отскакивает от обработки мыши двойными кликами на панели статуса.|
|[CMFCStatusBar::EnablePaneProgressBar](#enablepaneprogressbar)|Отображает панель прогресса на указанном стеле.|
|[CMFCStatusBar::GetCount](#getcount)|Возвращает количество стекол на панели статуса.|
|[CMFCStatusBar::GetDrawExtendedArea](#getdrawextendedarea)||
|[CMFCStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCStatusBar::GetItemID](#getitemid)||
|[CMFCStatusBar::GetItemRect](#getitemrect)||
|[CMFCStatusBar::GetPaneInfo](#getpaneinfo)||
|[CMFCStatusBar::GetPaneProgress](#getpaneprogress)||
|[CMFCStatusBar::GetPaneStyle](#getpanestyle)|Возвращает стиль панели. (Оверлет [CBasePane::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|
|[CMFCStatusBar::GetPaneText](#getpanetext)||
|[CMFCStatusBar::GetPaneWidth](#getpanewidth)|Возвращает ширину в пикселях указанного стека панели статуса.|
|[CMFCStatusBar::GetTipText](#gettiptext)|Возвращает текст наконечника инструмента для указанного панели статуса.|
|[CMFCStatusBar::НедействительноЕСодержимое](#invalidatepanecontent)|Недействительная указанная панель и перерисовка ее содержимого.|
|[CMFCStatusBar::PreCreateWindow](#precreatewindow)|Вызывается фреймворком перед созданием окна `CWnd` Windows, прикрепленного к этому объекту. (Оверлетc [CWnd::PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow).)|
|[CMFCStatusBar::SetDrawExtendedArea](#setdrawextendedarea)||
|[CMFCStatusBar::SetIndicators](#setindicators)||
|[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)|Присваивает анимацию указанному стеку.|
|[CMFCStatusBar::SetPaneBackgroundColor](#setpanebackgroundcolor)|Устанавливает цвет фона для указанного панели статуса.|
|[CMFCStatusBar::SetPaneIcon](#setpaneicon)|Устанавливает значок индикатора для указанного панели состояния.|
|[CMFCStatusBar::SetPaneInfo](#setpaneinfo)||
|[CMFCStatusBar::SetPaneProgress](#setpaneprogress)|Устанавливает текущий ход панели прогресса для указанного панели статуса.|
|[CMFCStatusBar::SetPaneStyle](#setpanestyle)|Устанавливает стиль панели. (Оверлет [CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).)|
|[CMFCStatusBar::SetPaneText](#setpanetext)||
|[CMFCStatusBar::SetPaneTextColor](#setpanetextcolor)|Устанавливает цвет текста для указанного панели статуса.|
|[CMFCStatusBar::SetPaneWidth](#setpanewidth)|Устанавливает ширину пикселей указанного панели состояния.|
|[CMFCStatusBar::SetTipText](#settiptext)|Устанавливает текст наконечника инструмента для указанного панели статуса.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCStatusBar::OnDrawPane](#ondrawpane)|Вызывается фреймворком при перерисовке панели статуса.|

## <a name="remarks"></a>Примечания

На следующей диаграмме показана фигура панели статуса из [приложения Status Bar Demo.](../../overview/visual-cpp-samples.md)

![Пример CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "Пример CMFCStatusBar")

## <a name="example"></a>Пример

В следующем примере показаны локальные переменные, используемые `CMFCStatusBar` приложением для вызова различных методов в классе. Эти переменные заявлены в StatusBarDemoView.h. Основная рамка заявлена в MainFrm.h, документ заявлен в StatusBarDemoDoc.h, а вид заявлен в StatusBarDemoView.h. Этот фрагмент кода является частью [образца демо-версии Status Bar.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCStatusBar` получить ссылку `GetStatusBar` на объект, введя метод в `GetStatusBar` MainFrm.h, а затем вызывая этот метод из метода в StatusBarDemoView.h. Этот фрагмент кода является частью [образца демо-версии Status Bar.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

## <a name="example"></a>Пример

Ниже приводится следующий пример, как `CMFCStatusBar` вызвать различные методы в классе в StatusBarDemoView.cpp. Константы объявляются в MainFrm.h. На примере показано, как установить значок, установить текст инструментария панели состояния, отобразить панель прогресса на указанном стеле, назначить анимацию указанному стеку, установить текст и ширину панели состояния и установить текущий индикатор хода панели прогресса для панели панели состояния. Этот фрагмент кода является частью [образца демо-версии Status Bar.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxstatusbar.h

## <a name="cmfcstatusbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCStatusBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

(в) *bStretch*<br/>
(в) *bHorz*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarcommandtoindex"></a><a name="commandtoindex"></a>CMFCStatusBar::CommandtoIndex

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Параметры

(в) *nIDFind*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarcreate"></a><a name="create"></a>CMFCStatusBar::Создание

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

(в) *pParentWnd*<br/>
(в) *dwStyle*<br/>
(в) *nID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarcreateex"></a><a name="createex"></a>CMFCStatusBar::CreateEx

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

(в) *pParentWnd*<br/>
(в) *dwCtrlStyle*<br/>
(в) *dwStyle*<br/>
(в) *nID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>CMFCStatusBar::DoesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarenablepanedoubleclick"></a><a name="enablepanedoubleclick"></a>CMFCStatusBar::EnablePaneDoubleClick

Позволяет или отскакивает от обработки мыши двойными кликами на панели статуса.

```cpp
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) Если true, включите обработку мыши дважды щелкните. В противном случае отогить от обработки мыши дважды кнопку.

### <a name="remarks"></a>Примечания

Если панель статуса включена в возможность обработки двойных кликов, Windows отправляет уведомление WM_COMMAND вместе с идентификатором ресурса владельцу панели статуса каждый раз, когда пользователь дважды нажимает на панель статуса.

## <a name="cmfcstatusbarenablepaneprogressbar"></a><a name="enablepaneprogressbar"></a>CMFCStatusBar::EnablePaneProgressBar

Отобразите панель прогресса на указанном стеле.

```cpp
void EnablePaneProgressBar(
    int nIndex,
    long nTotal=100,
    BOOL bDisplayText=FALSE,
    COLORREF clrBar=-1,
    COLORREF clrBarDest=-1,
    COLORREF clrProgressText=-1);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Определяет индекс панели, чей план прогресса для включения.

*nВсего*<br/>
(в) Определяет максимальное значение для бара прогресса.

*bDisplayText*<br/>
(в) Определяет, должна ли панель прогресса отображать текущее значение прогресса.

*clrBar*<br/>
(в) Определяет цвет фона панели прогресса.

*clrBarDest*<br/>
(в) Определяет вторичный цвет фона панели прогресса. Используйте различное значение, чем *clrBar,* чтобы заполнить цвет, смешанный с градиентом.

*clrProgressText*<br/>
(в) Определяет цвет текста панели прогресса.

### <a name="remarks"></a>Примечания

Если вы хотите отключить вызов `EnablePaneProgressBar` панели прогресса с *nTotal* набором до -1. По умолчанию *nTotal* установлен на 100. Таким образом, вам не нужны дополнительные расчеты для отображения прогресса в процентах.

Вы должны пройти различные значения для *clrBar* и *clrBarest* так, чтобы цвет фона панели прогресса отображает цвет, смешанный в градиент. .

Чтобы установить текущий прогресс, позвоните в [метод CMFCStatusBar::SetPaneProgress.](#setpaneprogress)

## <a name="cmfcstatusbargetcount"></a><a name="getcount"></a>CMFCStatusBar::GetCount

Извлекает количество стекол в панели статуса.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество стекол в панели статуса.

## <a name="cmfcstatusbargetdrawextendedarea"></a><a name="getdrawextendedarea"></a>CMFCStatusBar::GetDrawExtendedArea

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetextendedarea"></a><a name="getextendedarea"></a>CMFCStatusBar::GetExtendedArea

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetitemid"></a><a name="getitemid"></a>CMFCStatusBar::GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Параметры

(в) *nИндекс*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetitemrect"></a><a name="getitemrect"></a>CMFCStatusBar::GetItemRect

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

(в) *nИндекс*<br/>
(в) *lpRect*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CMFCStatusBar::GetPaneInfo

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Параметры

(в) *nИндекс*<br/>
(в) *nID*<br/>
(в) *nСтиль*<br/>
(в) *cxВимизм*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpaneprogress"></a><a name="getpaneprogress"></a>CMFCStatusBar::GetPaneProgress

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>Параметры

(в) *nИндекс*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpanestyle"></a><a name="getpanestyle"></a>CMFCStatusBar::GetPaneStyle

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Параметры

(в) *nИндекс*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpanetext"></a><a name="getpanetext"></a>CMFCStatusBar::GetPaneText

```cpp
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>Параметры

(в) *nИндекс*<br/>
(в) *s*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpanewidth"></a><a name="getpanewidth"></a>CMFCStatusBar::GetPaneWidth

Извлекает ширину панели статуса.

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Определяет индекс панели панели панели со статуса.

### <a name="return-value"></a>Возвращаемое значение

Ширина панели состояния, очем *nIndex;* в противном случае, ноль, если панель статус-бар не существует.

## <a name="cmfcstatusbargettiptext"></a><a name="gettiptext"></a>CMFCStatusBar::GetTipText

Извлеките текст инструментария панели status.

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Определяет индекс панели, для чего можно получить текст наконечника инструмента.

### <a name="return-value"></a>Возвращаемое значение

Текст инструментария панели status-bar, очем *nIndex.* В противном случае, пустая строка, если панель состояния не существует для указанного *nIndex* или если ее текст инструментария пуст.

## <a name="cmfcstatusbarinvalidatepanecontent"></a><a name="invalidatepanecontent"></a>CMFCStatusBar::НедействительноЕСодержимое

Недействительная панель статуса панели и перерисовка ее содержимого.

```cpp
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Оформляется индекс панели, содержимое которого должно быть признано недействительным и перерисованным.

### <a name="remarks"></a>Примечания

Когда бар статуса аннулируется, она помечается для перерисовки. Windows перерисовывает `UpdateWindow` его, когда метод `OnPaint` отправляет WM_PAINT сообщение методу.

## <a name="cmfcstatusbarondrawpane"></a><a name="ondrawpane"></a>CMFCStatusBar::OnDrawPane

Перерисовка панели статуса.

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства для рисования.

*pPane*<br/>
(в) Указатель на `CMFCStatusBarPaneInfo` структуру, содержащую информацию о панели, которая должна быть перерисована.

### <a name="remarks"></a>Примечания

По умолчанию перерисовывая `OnDrawPane` панель с помощью *pDC* контекста устройства в соответствии со стилем и содержимым панели.

Переопределить этот метод `CMFCStatusBar`в -производное класс, чтобы настроить внешний вид панели.

## <a name="cmfcstatusbarprecreatewindow"></a><a name="precreatewindow"></a>CMFCStatusBar::PreCreateWindow

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Параметры

(в) *cs*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetdrawextendedarea"></a><a name="setdrawextendedarea"></a>CMFCStatusBar::SetDrawExtendedArea

```cpp
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

(в) *bSet*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetindicators"></a><a name="setindicators"></a>CMFCStatusBar::SetIndicators

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Параметры

(в) *lpIDArray*<br/>
(в) *nIDCount*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetpaneanimation"></a><a name="setpaneanimation"></a>CMFCStatusBar::SetPaneAnimation

Присваивает анимацию указанному стеку.

```cpp
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Упоняет индекс панели, которой вы хотите присвоить ему анимацию.

*hImageList*<br/>
(в) Определяет ручку в списке изображений, вмещающие кадры анимации.

*nФреймРат*<br/>
(в) Определяет частоту кадров в миллисекундах для анимации.

*bUpdate*<br/>
(в) Если true, обновить содержимое панели немедленно. В противном случае содержимое панели обновляется, когда оно аннулируется.

### <a name="remarks"></a>Примечания

Если вы хотите отключить текущую анимацию, позвоните `SetPaneAnimation` с `hImageList` набором NULL.

## <a name="cmfcstatusbarsetpanebackgroundcolor"></a><a name="setpanebackgroundcolor"></a>CMFCStatusBar::SetPaneBackgroundColor

Устанавливает фоновый цвет панели панели панели status bar.

```cpp
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Определяет индекс панели, для которой устанавливается новый цвет фона.

*clrBackground*<br/>
[in] Задает новый цвет фона.

*bUpdate*<br/>
(в) Если true, обновить содержимое панели немедленно. В противном случае не обновляйте содержимое панели до тех пор, пока панель не будет признана недействительной другим методом.

## <a name="cmfcstatusbarsetpaneicon"></a><a name="setpaneicon"></a>CMFCStatusBar::SetPaneIcon

Установите значок панели панели статуса.

```cpp
void SetPaneIcon(
    int nIndex,
    HICON hIcon,
    BOOL bUpdate=TRUE);

void SetPaneIcon(
    int nIndex,
    HBITMAP hBmp,
    COLORREF clrTransparent=RGB(255, 0, 255),
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Определяет индекс панели, для которого можно установить изображение.

*hIcon*<br/>
(в) Определяет ручку значка, которая будет установлена в виде изображения панели.

*bUpdate*<br/>
(в) Уточняется, следует ли немедленно обновить содержимое панели.

*hBmp*<br/>
(в) Определяет ручку к биткарте, которая будет установлена в качестве изображения панели.

*clrПрозрачный*<br/>
(в) Определяет прозрачный цвет битовой карты, на который указывает *hBmp.*

### <a name="remarks"></a>Примечания

Вы можете пройти либо HICON или HBITMAP вместе с прозрачным цветом, чтобы установить изображение панели. Если вы больше не хотите отображать изображение, передайте значение NULL в качестве ручки изображения.

Если есть какая-либо запущенная анимация, которую установил [CMFCStatusBar::SetPaneAnimation](#setpaneanimation) установил, анимация будет остановлена.

## <a name="cmfcstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a>CMFCStatusBar::SetPaneInfo

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Параметры

(в) *nИндекс*<br/>
(в) *nID*<br/>
(в) *nСтиль*<br/>
(в) *cxВимизм*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetpaneprogress"></a><a name="setpaneprogress"></a>CMFCStatusBar::SetPaneProgress

Установите текущий индикатор хода панели прогресса для указанной панели.

```cpp
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Определяет индекс панели, для которого можно обновить индикатор хода.

*nCurr*<br/>
(в) Определяет текущее значение индикатора прогресса.

*bUpdate*<br/>
(в) Уточняется, следует ли немедленно обновлять панель.

### <a name="remarks"></a>Примечания

Вызовите этот метод, когда требуется обновить индикатор хода для панели прогресса в указанном стеле.

Чтобы использовать эту функцию для данной панели, вы должны сначала позвонить [в CMFCStatusBar::EnablePaneProgressBar.](#enablepaneprogressbar)

## <a name="cmfcstatusbarsetpanestyle"></a><a name="setpanestyle"></a>CMFCStatusBar::SetPaneStyle

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

(в) *nИндекс*<br/>
(в) *nСтиль*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetpanetext"></a><a name="setpanetext"></a>CMFCStatusBar::SetPaneText

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Параметры

(в) *nИндекс*<br/>
(в) *lpszNewText*<br/>
(в) *bUpdate*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetpanetextcolor"></a><a name="setpanetextcolor"></a>CMFCStatusBar::SetPaneTextColor

Устанавливает цвет текста указанного стекла.

```cpp
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Определяетиндекс панели, к которому требуется присвоить новый цвет текста.

*clrText*<br/>
(в) Определяет цвет текста.

*bUpdate*<br/>
(в) Если true, обновить содержимое панели немедленно. В противном случае не обновляйте содержимое панели до тех пор, пока панель не будет признана недействительной другим методом.

## <a name="cmfcstatusbarsetpanewidth"></a><a name="setpanewidth"></a>CMFCStatusBar::SetPaneWidth

Установите ширину панели панели статуса.

```cpp
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Индекс панели состояния панели, для которого установить новую ширину.

*Cx*<br/>
(в) Новая ширина панели панели статуса, в пикселях.

## <a name="cmfcstatusbarsettiptext"></a><a name="settiptext"></a>CMFCStatusBar::SetTipText

Установите текст tooltip с панельной панели состояния.

```cpp
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
(в) Индекс панели, к которому требуется присвоить текст tooltip.

*pszTipText*<br/>
(в) Новый текст инструментария.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)<br/>
[Класс CStatusBar](../../mfc/reference/cstatusbar-class.md)
