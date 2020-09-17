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
ms.openlocfilehash: 004873ef2696eb9504cdd4df77e700c4a145e886
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686578"
---
# <a name="cmfcstatusbar-class"></a>Класс CMFCStatusBar

`CMFCStatusBar`Класс реализует строку состояния, похожую на `CStatusBar` класс. Однако класс `CMFCStatusBar` не содержит функции, предоставляемые классом `CStatusBar` , такие как возможность отображать изображения, анимации и индикаторы выполнения, а также возможность реагировать на двойные нажатия мыши.

Дополнительные сведения см. в исходном коде, расположенном в папке **VC \\ атлмфк \\ src \\ MFC** в установке Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMFCStatusBar:: Калкфикседлайаут](#calcfixedlayout)|(Переопределяет [CBasePane:: калкфикседлайаут](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[CMFCStatusBar:: Коммандтоиндекс](#commandtoindex)||
|[CMFCStatusBar:: Create](#create)|Создает панель элементов управления и прикрепляет ее к объекту [CPane](../../mfc/reference/cpane-class.md) . (Переопределяет [CPane:: Create](../../mfc/reference/cpane-class.md#create).)|
|[CMFCStatusBar:: Креатикс](#createex)|Создает панель элементов управления и прикрепляет ее к объекту [CPane](../../mfc/reference/cpane-class.md) . (Переопределяет [CPane:: креатикс](../../mfc/reference/cpane-class.md#createex).)|
|[CMFCStatusBar::D Оесалловдининсертбефоре](#doesallowdyninsertbefore)|Определяет, можно ли динамически вставлять другую панель между этой панелью и родительским фреймом. (Переопределяет [CBasePane::D оесалловдининсертбефоре](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFCStatusBar:: Енаблепанедаублекликк](#enablepanedoubleclick)|Включает или отключает обработку двойных щелчков мышью в строке состояния.|
|[CMFCStatusBar:: Енаблепанепрогрессбар](#enablepaneprogressbar)|Отображает индикатор выполнения на указанной панели.|
|[CMFCStatusBar:: NOCOUNT](#getcount)|Возвращает число панелей в строке состояния.|
|[CMFCStatusBar:: Жетдравекстендедареа](#getdrawextendedarea)||
|[CMFCStatusBar:: Жетекстендедареа](#getextendedarea)||
|[CMFCStatusBar:: Жетитемид](#getitemid)||
|[CMFCStatusBar:: Жетитемрект](#getitemrect)||
|[CMFCStatusBar:: Жетпанеинфо](#getpaneinfo)||
|[CMFCStatusBar:: Жетпанепрогресс](#getpaneprogress)||
|[CMFCStatusBar:: Жетпанестиле](#getpanestyle)|Возвращает стиль панели. (Переопределяет [CBasePane:: жетпанестиле](../../mfc/reference/cbasepane-class.md#getpanestyle).)|
|[CMFCStatusBar:: Жетпанетекст](#getpanetext)||
|[CMFCStatusBar:: Жетпаневидс](#getpanewidth)|Возвращает ширину заданной панели строки состояния в пикселях.|
|[CMFCStatusBar:: Жеттиптекст](#gettiptext)|Возвращает текст подсказки для указанной панели строки состояния.|
|[CMFCStatusBar:: Инвалидатепанеконтент](#invalidatepanecontent)|Делает указанную панель недействительной и перерисовывает ее содержимое.|
|[CMFCStatusBar::P Рекреатевиндов](#precreatewindow)|Вызывается платформой перед созданием окна Windows, присоединенного к этому `CWnd` объекту. (Переопределяет [CWnd::P рекреатевиндов](../../mfc/reference/cwnd-class.md#precreatewindow).)|
|[CMFCStatusBar:: Сетдравекстендедареа](#setdrawextendedarea)||
|[CMFCStatusBar:: Сетиндикаторс](#setindicators)||
|[CMFCStatusBar:: Сетпанеаниматион](#setpaneanimation)|Назначает анимацию для указанной панели.|
|[CMFCStatusBar:: Сетпанебаккграундколор](#setpanebackgroundcolor)|Задает цвет фона для указанной панели в строке состояния.|
|[CMFCStatusBar:: Сетпанеикон](#setpaneicon)|Задает значок индикатора для указанной панели в строке состояния.|
|[CMFCStatusBar:: Сетпанеинфо](#setpaneinfo)||
|[CMFCStatusBar:: Сетпанепрогресс](#setpaneprogress)|Задает текущий ход выполнения индикатора выполнения для указанной панели в строке состояния.|
|[CMFCStatusBar:: Сетпанестиле](#setpanestyle)|Задает стиль панели. (Переопределяет [CBasePane:: сетпанестиле](../../mfc/reference/cbasepane-class.md#setpanestyle).)|
|[CMFCStatusBar:: Сетпанетекст](#setpanetext)||
|[CMFCStatusBar:: Сетпанетекстколор](#setpanetextcolor)|Задает цвет текста для указанной панели в строке состояния.|
|[CMFCStatusBar:: Сетпаневидс](#setpanewidth)|Задает ширину заданной панели строки состояния в пикселях.|
|[CMFCStatusBar:: Сеттиптекст](#settiptext)|Задает текст подсказки для указанной панели в строке состояния.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCStatusBar:: Ондравпане](#ondrawpane)|Вызывается структурой при перерисовки панели строки состояния.|

## <a name="remarks"></a>Примечания

На следующей диаграмме показана строка состояния из [демонстрационного примера приложения в строке состояния](../../overview/visual-cpp-samples.md) .

![Пример CMFCStatusBar](../../mfc/reference/media/cmfcstatusbar.png "Пример CMFCStatusBar")

## <a name="examples"></a>Примеры

В следующем примере показаны локальные переменные, используемые приложением для вызова различных методов в `CMFCStatusBar` классе. Эти переменные объявляются в Статусбардемовиев. h. Основной кадр объявляется в Маинфрм. h, документ объявляется в Статусбардемодок. h, а представление объявляется в Статусбардемовиев. h. Этот фрагмент кода является частью [демонстрационного примера в строке состояния](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

В следующем примере показано, как получить ссылку на `CMFCStatusBar` объект путем введения `GetStatusBar` метода в маинфрм. h и последующего вызова этого метода из `GetStatusBar` метода в статусбардемовиев. h. Этот фрагмент кода является частью [демонстрационного примера в строке состояния](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

В следующем примере показано, как вызывать различные методы в `CMFCStatusBar` классе в статусбардемовиев. cpp. Константы объявляются в Маинфрм. h. В примере показано, как задать значок, задать текст подсказки на панели строки состояния, отобразить индикатор выполнения на указанной панели, назначить анимацию для указанной панели, задать текст и ширину панели строки состояния и установить индикатор текущего хода выполнения для панели строки состояния. Этот фрагмент кода является частью [демонстрационного примера в строке состояния](../../overview/visual-cpp-samples.md).

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

**Заголовок:** афксстатусбар. h

## <a name="cmfcstatusbarcalcfixedlayout"></a><a name="calcfixedlayout"></a> CMFCStatusBar:: Калкфикседлайаут

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Параметры

окне *бстретч*<br/>
окне *бхорз*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarcommandtoindex"></a><a name="commandtoindex"></a> CMFCStatusBar:: Коммандтоиндекс

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>Параметры

окне *нидфинд*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarcreate"></a><a name="create"></a> CMFCStatusBar:: Create

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

окне *ппарентвнд*<br/>
окне *двстиле*<br/>
окне *NID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarcreateex"></a><a name="createex"></a> CMFCStatusBar:: Креатикс

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>Параметры

окне *ппарентвнд*<br/>
окне *двктрлстиле*<br/>
окне *двстиле*<br/>
окне *NID*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCStatusBar::D Оесалловдининсертбефоре

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarenablepanedoubleclick"></a><a name="enablepanedoubleclick"></a> CMFCStatusBar:: Енаблепанедаублекликк

Включает или отключает обработку двойных щелчков мышью в строке состояния.

```cpp
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
окне Если значение — TRUE, необходимо включить обработку двойного щелчка мыши. В противном случае отключите обработку двойного щелчка мышью.

### <a name="remarks"></a>Примечания

Если строка состояния включена для обработки двойных щелчков, Windows отправляет уведомление WM_COMMAND вместе с ИДЕНТИФИКАТОРом ресурса владельцу строки состояния каждый раз, когда пользователь дважды щелкает панель строки состояния.

## <a name="cmfcstatusbarenablepaneprogressbar"></a><a name="enablepaneprogressbar"></a> CMFCStatusBar:: Енаблепанепрогрессбар

Отображение индикатора выполнения на указанной панели.

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

*ниндекс*<br/>
окне Указывает индекс области, индикатор выполнения которой необходимо включить.

*нтотал*<br/>
окне Задает максимальное значение индикатора выполнения.

*бдисплайтекст*<br/>
окне Указывает, должен ли индикатор выполнения отображать текущее значение хода выполнения.

*клрбар*<br/>
окне Задает цвет фона индикатора выполнения.

*клрбардест*<br/>
окне Задает вторичный цвет фона индикатора выполнения. Используйте другое значение, отличное от *клрбар* , для заполнения цветом, накладываемым на градиент.

*clrProgressText*<br/>
окне Задает цвет текста индикатора выполнения.

### <a name="remarks"></a>Примечания

Если необходимо отключить вызов индикатора выполнения с параметром `EnablePaneProgressBar` *нтотал* , равным-1. По умолчанию *нтотал* имеет значение 100. Поэтому для показа хода выполнения в процентах не требуется никаких дополнительных вычислений.

Необходимо передать разные значения для *клрбар* и *клрбардест* , чтобы цвет фона индикатора выполнения отображался в виде цвета, накладываемого на градиент. .

Чтобы задать текущий ход выполнения, вызовите метод [CMFCStatusBar:: сетпанепрогресс](#setpaneprogress) .

## <a name="cmfcstatusbargetcount"></a><a name="getcount"></a> CMFCStatusBar:: NOCOUNT

Возвращает количество панелей в строке состояния.

```
int GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число панелей в строке состояния.

## <a name="cmfcstatusbargetdrawextendedarea"></a><a name="getdrawextendedarea"></a> CMFCStatusBar:: Жетдравекстендедареа

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetextendedarea"></a><a name="getextendedarea"></a> CMFCStatusBar:: Жетекстендедареа

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>Параметры

[in] *rect*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetitemid"></a><a name="getitemid"></a> CMFCStatusBar:: Жетитемид

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>Параметры

окне *ниндекс*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetitemrect"></a><a name="getitemrect"></a> CMFCStatusBar:: Жетитемрект

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>Параметры

окне *ниндекс*<br/>
окне *лпрект*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpaneinfo"></a><a name="getpaneinfo"></a> CMFCStatusBar:: Жетпанеинфо

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>Параметры

окне *ниндекс*<br/>
окне *NID*<br/>
окне *нстиле*<br/>
окне *кксвидс*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpaneprogress"></a><a name="getpaneprogress"></a> CMFCStatusBar:: Жетпанепрогресс

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>Параметры

окне *ниндекс*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpanestyle"></a><a name="getpanestyle"></a> CMFCStatusBar:: Жетпанестиле

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>Параметры

окне *ниндекс*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpanetext"></a><a name="getpanetext"></a> CMFCStatusBar:: Жетпанетекст

```cpp
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>Параметры

окне *ниндекс*<br/>
окне *с*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbargetpanewidth"></a><a name="getpanewidth"></a> CMFCStatusBar:: Жетпаневидс

Получает ширину панели строки состояния.

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
окне Указывает индекс панели строки состояния.

### <a name="return-value"></a>Возвращаемое значение

Ширина панели строки состояния, *ниндекс* указывает; в противном случае нуль, если панель состояния не существует.

## <a name="cmfcstatusbargettiptext"></a><a name="gettiptext"></a> CMFCStatusBar:: Жеттиптекст

Получение текста подсказки для панели строки состояния.

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
окне Указывает индекс области, для которой нужно получить текст подсказки.

### <a name="return-value"></a>Возвращаемое значение

Текст подсказки на панели строки состояния, *ниндекс* указывает. В противном случае пустая строка, если область строки состояния не существует для указанного *ниндекс* или если ее текст подсказки пуст.

## <a name="cmfcstatusbarinvalidatepanecontent"></a><a name="invalidatepanecontent"></a> CMFCStatusBar:: Инвалидатепанеконтент

Делает недействительной панель строки состояния и перерисовывает ее содержимое.

```cpp
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
окне Указывает индекс области, содержимое которой должно быть недействительным и перерисовано.

### <a name="remarks"></a>Примечания

Когда строка состояния становится недействительной, она помечается для перерисовки. Windows перерисовывает его, когда `UpdateWindow` метод отправляет в метод сообщение WM_PAINT `OnPaint` .

## <a name="cmfcstatusbarondrawpane"></a><a name="ondrawpane"></a> CMFCStatusBar:: Ондравпане

Перерисовка области строки состояния.

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>Параметры

*Хозяин*<br/>
окне Указатель на контекст устройства для рисования.

*ппане*<br/>
окне Указатель на `CMFCStatusBarPaneInfo` структуру, содержащую сведения о перерисуемой области.

### <a name="remarks"></a>Примечания

По умолчанию `OnDrawPane` перерисовывает панель с помощью контекста устройства *основной контроллер домена* в соответствии со стилем и содержимым панели.

Переопределите этот метод в `CMFCStatusBar` классе, производном от, чтобы настроить внешний вид панели.

## <a name="cmfcstatusbarprecreatewindow"></a><a name="precreatewindow"></a> CMFCStatusBar::P Рекреатевиндов

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>Параметры

окне *CS*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetdrawextendedarea"></a><a name="setdrawextendedarea"></a> CMFCStatusBar:: Сетдравекстендедареа

```cpp
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

окне *управляемое bSet*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetindicators"></a><a name="setindicators"></a> CMFCStatusBar:: Сетиндикаторс

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>Параметры

окне *лпидаррай*<br/>
окне *нидкаунт*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetpaneanimation"></a><a name="setpaneanimation"></a> CMFCStatusBar:: Сетпанеаниматион

Назначает анимацию для указанной панели.

```cpp
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
окне Задает индекс панели, которой необходимо присвоить анимацию.

*hImageList*<br/>
окне Задает маркер для списка изображений, содержащего кадры анимации.

*нфрамерате*<br/>
окне Указывает частоту кадров (в миллисекундах) для анимации.

*бупдате*<br/>
окне Если значение — TRUE, немедленно обновите содержимое панели. В противном случае содержимое панели обновляется, когда оно становится недействительным.

### <a name="remarks"></a>Примечания

Если вы хотите отключить текущую анимацию, вызовите `SetPaneAnimation` с параметром с параметром, равным `hImageList` null.

## <a name="cmfcstatusbarsetpanebackgroundcolor"></a><a name="setpanebackgroundcolor"></a> CMFCStatusBar:: Сетпанебаккграундколор

Задает цвет фона для панели строки состояния.

```cpp
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
окне Задает индекс области, для которой задается новый цвет фона.

*clrBackground*<br/>
[in] Задает новый цвет фона.

*бупдате*<br/>
окне Если значение — TRUE, немедленно обновите содержимое панели. В противном случае не обновляйте содержимое панели, пока панель не станет недействительной другим методом.

## <a name="cmfcstatusbarsetpaneicon"></a><a name="setpaneicon"></a> CMFCStatusBar:: Сетпанеикон

Установите значок панели строки состояния.

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

*ниндекс*<br/>
окне Указывает индекс области, для которой задается изображение.

*hIcon*<br/>
окне Задает маркер значка, который должен быть задан в качестве изображения панели.

*бупдате*<br/>
окне Указывает, следует ли немедленно обновлять содержимое панели.

*хбмп*<br/>
окне Задает маркер точечного рисунка, который должен быть задан в качестве изображения панели.

*клртранспарент*<br/>
окне Задает прозрачный цвет точечного рисунка, который указывает *хбмп* .

### <a name="remarks"></a>Примечания

Можно передать либо ХИКОН, либо ХБИТМАП вместе с прозрачным цветом, чтобы задать изображение панели. Если больше не нужно отображать изображение, передайте значение NULL в качестве маркера изображения.

Если имеется какая-либо выполняемая анимация, которая задана [CMFCStatusBar:: сетпанеаниматион](#setpaneanimation) , анимация будет остановлена.

## <a name="cmfcstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a> CMFCStatusBar:: Сетпанеинфо

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>Параметры

окне *ниндекс*<br/>
окне *NID*<br/>
окне *нстиле*<br/>
окне *кксвидс*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetpaneprogress"></a><a name="setpaneprogress"></a> CMFCStatusBar:: Сетпанепрогресс

Задает текущий индикатор хода выполнения для указанной панели.

```cpp
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
окне Указывает индекс области, для которой необходимо обновить индикатор хода выполнения.

*нкурр*<br/>
окне Задает текущее значение индикатора выполнения.

*бупдате*<br/>
окне Указывает, следует ли немедленно обновить область.

### <a name="remarks"></a>Примечания

Этот метод следует вызывать, если необходимо обновить индикатор хода выполнения для индикатора выполнения в указанной области.

Чтобы использовать эту функцию для данной панели, сначала необходимо вызвать метод [CMFCStatusBar:: енаблепанепрогрессбар](#enablepaneprogressbar) .

## <a name="cmfcstatusbarsetpanestyle"></a><a name="setpanestyle"></a> CMFCStatusBar:: Сетпанестиле

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

окне *ниндекс*<br/>
окне *нстиле*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetpanetext"></a><a name="setpanetext"></a> CMFCStatusBar:: Сетпанетекст

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>Параметры

окне *ниндекс*<br/>
окне *лпсзневтекст*<br/>
окне *бупдате*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcstatusbarsetpanetextcolor"></a><a name="setpanetextcolor"></a> CMFCStatusBar:: Сетпанетекстколор

Задает цвет текста указанной панели.

```cpp
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
окне Задает индекс области, которой нужно назначить новый цвет текста.

*clrText*<br/>
окне Задает цвет текста.

*бупдате*<br/>
окне Если значение — TRUE, немедленно обновите содержимое панели. В противном случае не обновляйте содержимое панели, пока панель не станет недействительной другим методом.

## <a name="cmfcstatusbarsetpanewidth"></a><a name="setpanewidth"></a> CMFCStatusBar:: Сетпаневидс

Задайте ширину панели строки состояния.

```cpp
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
окне Индекс области строки состояния, для которой задается новая ширина.

*/CX*<br/>
окне Новая ширина панели строки состояния в пикселях.

## <a name="cmfcstatusbarsettiptext"></a><a name="settiptext"></a> CMFCStatusBar:: Сеттиптекст

Задайте текст подсказки на панели строки состояния.

```cpp
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
окне Индекс панели, которой необходимо назначить текст подсказки.

*псзтиптекст*<br/>
окне Новый текст подсказки.

## <a name="see-also"></a>См. также

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CPane](../../mfc/reference/cpane-class.md)<br/>
[Класс CStatusBar](../../mfc/reference/cstatusbar-class.md)
