---
title: Класс CMFCToolTipCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
ms.openlocfilehash: 6c8bb41b82d1dca9235e1184c2152a61c07c8071
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377344"
---
# <a name="cmfctooltipctrl-class"></a>Класс CMFCToolTipCtrl

Расширенная реализация всплывающей подсказки на основе класса [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md). Подсказка на основе класса `CMFCToolTipCtrl` может отображать значок, метку и описание. Можно настроить его внешний вид с помощью градиентной заливки, пользовательских цветов текста и границы, полужирного шрифта, скругленных углов или стиля всплывающего предупреждения.

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```cpp
class CMFCToolTipCtrl : public CToolTipCtrl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|Возвращает размер значка во всплывающей подсказке.|
|[CMFCToolTipCtrl::GetParams](#getparams)|Возвращает параметры отображения всплывающей подсказки.|
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|Рисует границу всплывающей подсказки.|
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|Отображает значок во всплывающей подсказке.|
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|Рисует заголовок всплывающей подсказки или вычисляет размер метки.|
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|Рисует разделитель между меткой и описанием во всплывающей подсказке.|
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|Заливает фон всплывающей подсказки.|
|[CMFCToolTipCtrl::SetDescription](#setdescription)|Задает описание, которое отображается во всплывающей подсказке.|
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||
|[CMFCToolTipCtrl::SetLocation](#setlocation)||
|[CMFCToolTipCtrl::SetParams](#setparams)|Задает внешний вид всплывающей подсказки с помощью объекта `CMFCToolTipInfo`.|

## <a name="remarks"></a>Примечания

Используйте `CMFCToolTipCtrl`объекты [класса CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) вместе для реализации индивидуальных наборов инструментов в приложении. `CMFCToolTipInfo`

Например, чтобы реализовать всплывающие подсказки в виде выносок, сделайте следующее:

1. Используйте метод [класса CWinAppEx](../../mfc/reference/cwinappex-class.md) для инициализации менеджера инструментария в приложении.

2. Создайте структуру `CMFCToolTipInfo`, чтобы задать необходимый стиль оформления:

    ```cpp
    CMFCToolTipInfo params;
    params.m_bBoldLabel = FALSE;
    params.m_bDrawDescription = FALSE;
    params.m_bDrawIcon = FALSE;
    params.m_bRoundedCorners = TRUE;
    params.m_bDrawSeparator = FALSE;
    if (m_bCustomColors)
    {
        params.m_clrFill = RGB (255, 255, 255);
        params.m_clrFillGradient = RGB (228, 228, 240);
        params.m_clrText = RGB (61, 83, 80);
        params.m_clrBorder = RGB (144, 149, 168);

    }
    ```

3. Используйте метод [CTooltipManager::SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) для настройки визуального стиля для всех инструментов `CMFCToolTipInfo` в приложении с помощью стилей, определенных в объекте:

    ```cpp
    theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
        RUNTIME_CLASS (CMFCToolTipCtrl), &params);
    ```

Для управления поведением всплывающей подсказки и ее отрисовкой вы также можете получить новый производный класс из класса `CMFCToolTipCtrl`. Чтобы задать новый класс элемента управления "Всплывающая подсказка", используйте метод `CTooltipManager::SetTooltipParams`:

```cpp
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMyToolTipCtrl))
```

Чтобы восстановить класс элемента управления "Всплывающая подсказка" по умолчанию и сбросить оформление подсказки на стандартное, укажите значение NULL в классе среды выполнения и параметрах всплывающей подсказки в методе `SetTooltipParams`:

```cpp
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    NULL,
    NULL);
```

## <a name="example"></a>Пример

В следующем примере демонстрируется создание объекта `CMFCToolTipCtrl`, задание описания, отображаемого во всплывающей подсказке, а также задание ширины элемента управления "Всплывающая подсказка".

[!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

[CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtooltipctrl.h

## <a name="cmfctooltipctrlcmfctooltipctrl"></a><a name="cmfctooltipctrl"></a>CMFCToolTipCtrl::CMFCToolTipCtrl

```cpp
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```

### <a name="parameters"></a>Параметры

(в) *pParams*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfctooltipctrlgeticonsize"></a><a name="geticonsize"></a>CMFCToolTipCtrl::GetIconSize

Возвращает размер значка во всплывающей подсказке.

```cpp
virtual CSize GetIconSize();
```

### <a name="return-value"></a>Возвращаемое значение

Размер значка, в пикселях.

## <a name="cmfctooltipctrlgetparams"></a><a name="getparams"></a>CMFCToolTipCtrl:GetParams

Возвращает параметры отображения всплывающей подсказки.

```cpp
const CMFCToolTipInfo& GetParams() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущие настройки отображения инструментов, которые хранятся в объекте [класса CMFCToolTipInfo.](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="cmfctooltipctrlondrawborder"></a><a name="ondrawborder"></a>CMFCToolTipCtrl::OndrawBorder

Рисует границу всплывающей подсказки.

```cpp
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect,
    COLORREF clrLine);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Ограничивающий прямоугольник инструментария.

*clrLine*<br/>
(в) Пограничный цвет.

### <a name="remarks"></a>Примечания

Переопределить этот метод в производном классе, чтобы настроить внешний вид границы tooltip.

## <a name="cmfctooltipctrlondrawdescription"></a><a name="ondrawdescription"></a>CMFCToolTipCtrl::OndrawОписание

```cpp
virtual CSize OnDrawDescription(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Параметры

(в) *pDC*<br/>
[in] *rect*<br/>
(в) *bCalcТолько*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfctooltipctrlondrawicon"></a><a name="ondrawicon"></a>CMFCToolTipCtrl::OndrawIcon

Отображает значок во всплывающей подсказке.

```cpp
virtual BOOL OnDrawIcon(
    CDC* pDC,
    CRect rectImage);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rectImage*<br/>
(в) Координаты иконы.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если значок был нарисован. В противном случае FALSE.

### <a name="remarks"></a>Примечания

Переопределить этот метод в производном классе для отображения пользовательского значка. Вы также должны переопределить [CMFCToolTipCtrl::GetIconSize,](#geticonsize) чтобы инструмент правильно рассчитать макет текста и описания.

## <a name="cmfctooltipctrlondrawlabel"></a><a name="ondrawlabel"></a>CMFCToolTipCtrl::OndrawLabel

Рисует заголовок всплывающей подсказки или вычисляет размер метки.

```cpp
virtual CSize OnDrawLabel(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Связанный прямоугольник области метки.

*bCalcТолько*<br/>
(в) Если true, метка не будет нарисована.

### <a name="return-value"></a>Возвращаемое значение

Размер метки, в пикселях.

### <a name="remarks"></a>Примечания

Переопределить этот метод в производном классе, если вы хотите настроить внешний вид метки tooltip.

## <a name="cmfctooltipctrlondrawseparator"></a><a name="ondrawseparator"></a>CMFCToolTipCtrl::OnDrawСепаратор

Рисует разделитель между меткой и описанием во всплывающей подсказке.

```cpp
virtual void OnDrawSeparator(
    CDC* pDC,
    int x1,
    int x2,
    int y);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*x1*<br/>
(в) Горизонтальные координаты левого конца сепаратора.

*x2*<br/>
(в) Горизонтальные координаты правого конца сепаратора.

*Y*<br/>
(в) Вертикальные координаты сепаратора.

### <a name="remarks"></a>Примечания

Реализация по умолчанию рисует линию от точки (x1, y) до точки (x2, y).

Переопределить этот метод в производном классе, чтобы настроить внешний вид сепаратора.

## <a name="cmfctooltipctrlonfillbackground"></a><a name="onfillbackground"></a>CMFCToolTipCtrl::Onfillbackground

Заливает фон всплывающей подсказки.

```cpp
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect,
    COLORREF& clrText,
    COLORREF& clrLine);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Определяет ограничивающий прямоугольник области для заполнения.

*clrText*<br/>
(в) Tooltip цвет переднего плана.

*clrLine*<br/>
(в) Цвет границ и линия делимитера между этикеткой и описанием.

### <a name="remarks"></a>Примечания

Реализация по умолчанию заполняет прямоугольник, указанный *рект* с цветом или шаблоном, указанным последним вызовом [CMFCToolTipCtrl::SetParams](#setparams).

Переопределить этот метод в производном классе, если вы хотите настроить внешний вид инструмента.

## <a name="cmfctooltipctrlsetdescription"></a><a name="setdescription"></a>CMFCToolTipCtrl::SetОписание

Задает описание, которое отображается во всплывающей подсказке.

```cpp
virtual void SetDescription(const CString strDesrciption);
```

### <a name="parameters"></a>Параметры

*strDesrciption*<br/>
(в) Текст описания.

### <a name="remarks"></a>Примечания

Текст описания отображается на инструменте под сепаратором.

## <a name="cmfctooltipctrlsetfixedwidth"></a><a name="setfixedwidth"></a>CMFCToolTipCtrl::SetFixedWidth

```cpp
void SetFixedWidth(
    int nWidthRegular,
    int nWidthLargeImage);
```

### <a name="parameters"></a>Параметры

(в) *nWidthRegular*<br/>
(в) *nWidthLargeImage*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfctooltipctrlsethotribbonbutton"></a><a name="sethotribbonbutton"></a>CMFCToolTipCtrl::SetHotRibbonButton

```cpp
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```

### <a name="parameters"></a>Параметры

(в) *pRibbonButton*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfctooltipctrlsetlocation"></a><a name="setlocation"></a>CMFCToolTipCtrl:SetLocation

```cpp
void SetLocation(CPoint pt);
```

### <a name="parameters"></a>Параметры

(в) *pt pt*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfctooltipctrlsetparams"></a><a name="setparams"></a>CMFCToolTipCtrl::SetParams

Определяет внешний вид инструментария с помощью объекта [класса CMFCToolTipInfo.](../../mfc/reference/cmfctooltipinfo-class.md)

```cpp
void SetParams(CMFCToolTipInfo* pParams);
```

### <a name="parameters"></a>Параметры

*pParams*<br/>
(в) Указатель на объект [класса CMFCToolTipInfo,](../../mfc/reference/cmfctooltipinfo-class.md) содержащий параметры дисплея.

### <a name="remarks"></a>Примечания

Всякий раз, когда инструмент отображается, он обращается с помощью цветов и визуальных стилей, которые *pParams* указывает. Значение *pParams* хранится в защищенном `m_Params`члене , к которому можно получить доступ к производному классу, который переопределяет [CMFCToolTipCtrl::OnDrawBorder](#ondrawborder), [CMFCToolTipCtrl::OndrawIcon](#ondrawicon), [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel), [CMFCToolToolTipCtrl::OnDrawSeparator](#ondrawseparator), или [CMFCTool.](#onfillbackground)

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)<br/>
[Класс CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)<br/>
[Класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
