---
title: Класс CMFCToolTipInfo
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
ms.openlocfilehash: 000a2fd33928e59685efa6f145406542a4935819
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377336"
---
# <a name="cmfctooltipinfo-class"></a>Класс CMFCToolTipInfo

Хранит сведения о внешнем виде подсказок.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolTipInfo
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolTipInfo::operator=](#operator_eq)||

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|Логическая переменная, указывающая, имеет ли всплывающая подсказка вид выноски.|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|Логическая переменная, указывающая, выделяются ли заголовки всплывающих подсказок жирным шрифтом.|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|Логическая переменная, указывающая, содержит ли всплывающая подсказка описание.|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|Логическая переменная, указывающая, содержит ли всплывающая подсказка значок.|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|Логическая переменная, указывающая, имеется ли разделитель между заголовком всплывающей подсказки и описанием.|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|Логическая переменная, указывающая, закруглены ли углы всплывающей подсказки.|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Переменная Boolean, которая указывает, следует ли контролировать внешний вид инструментария визуальным менеджером (см. [CMFCVisualManager Class).](../../mfc/reference/cmfcvisualmanager-class.md)|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Цвет границы всплывающей подсказки.|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Цвет фона всплывающей подсказки.|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Цвет градиентной заливки всплывающей подсказки.|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Цвет текста всплывающей подсказки.|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Угол градиентной заливки всплывающей подсказки.|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|Максимальная возможная ширина описания во всплывающей подсказке (в пикселях).|

## <a name="remarks"></a>Примечания

Используйте [cmFCToolTipCtrl класса](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`и [CTooltipManager класса](../../mfc/reference/ctooltipmanager-class.md) вместе для реализации индивидуальных инструментов в вашем приложении. Пример того, как использовать эти классы наборов инструментов, можно ознакомьтесь с темой [класса CMFCToolToolTipCtrl.](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="example"></a>Пример

В следующем примере демонстрируется задание значений разных переменных-членов класса `CMFCToolTipInfo`.

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtooltipctrl.h

## <a name="cmfctooltipinfom_bballoontooltip"></a><a name="m_bballoontooltip"></a>CMFCToolTipInfo::m_bBalloonTooltip

Определяет стиль отображения всех наборов инструментов.

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>Примечания

TRUE указывает на то, что наконечники инструментов используют стиль шарика, FALSE указывает на то, что наконечники инструментов используют прямоугольный стиль.

## <a name="cmfctooltipinfom_bboldlabel"></a><a name="m_bboldlabel"></a>CMFCToolTipInfo::m_bBoldLabel

Уточняется, является ли шрифт текста tooltip смелым.

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>Примечания

Установите этот член к TRUE для отображения текста tooltip жирным шрифтом, или FALSE для отображения этикеток tooltip с не-смелым шрифтом.

## <a name="cmfctooltipinfom_bdrawdescription"></a><a name="m_bdrawdescription"></a>CMFCToolTipInfo::m_bDrawDescription

Определяет, отображает ли каждый набор инструментов текст описания.

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>Примечания

Установите этот член к TRUE для отображения описания, или FALSE, чтобы скрыть описание. Вы можете указать описание на наборе инструментов, позвонив [по телефону CMFCToolTipCtrl::SetОписание](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)

## <a name="cmfctooltipinfom_bdrawicon"></a><a name="m_bdrawicon"></a>CMFCToolTipInfo::m_bDrawIcon

Определяет, все ли панели инструментов отображают значки.

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>Примечания

Установите этот элемент к TRUE для отображения значка на каждом наборе инструментов, или FALSE для отображения документов без иконок.

## <a name="cmfctooltipinfom_bdrawseparator"></a><a name="m_bdrawseparator"></a>CMFCToolTipInfo::m_bDrawSeparator

Определяет, есть ли у каждого инструмента сепаратор между этикеткой и описанием.

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>Примечания

Установите этот член к TRUE для отображения сепаратора между этикеткой и описанием tooltip, или FALSE для отображения документов без сепаратора.

## <a name="cmfctooltipinfom_broundedcorners"></a><a name="m_broundedcorners"></a>CMFCToolTipInfo::m_bRoundedCorners

Определяет, есть ли все панели инструментов имеют закругленные углы.

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>Примечания

Установите этот член к TRUE для отображения закругленных углов на панели инструментов, или FALSE для отображения прямоугольных углов на панели инструментов.

## <a name="cmfctooltipinfom_clrborder"></a><a name="m_clrborder"></a>CMFCToolTipInfo::m_clrBorder

Определяет цвет границ на всех наконечниках инструментов.

```
COLORREF m_clrBorder;
```

## <a name="cmfctooltipinfom_clrfill"></a><a name="m_clrfill"></a>CMFCToolTipInfo::m_clrFill

Определяет цвет фонов tooltip.

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>Примечания

Если [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) -1, то цвет `m_clrFill`фона tooltip . В `m_clrFill` противном случае определяется цвет начала градиента и `m_clrFillGradient` указывается цвет конца градиента. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) определяет направление градиента.

## <a name="cmfctooltipinfom_clrfillgradient"></a><a name="m_clrfillgradient"></a>CMFCToolTipInfo::m_clrFillGradient

Определяет конечный цвет для градиентного фона для окладных.

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>Примечания

Если `m_clrFillGradient` -1, нет градиента. В противном случае, начальный цвет градиента указан [CMFCToolTipInfo::m_clrFill](#m_clrfill) и цвет отделки градиента указаны `m_clrFillGradient`. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) определяет направление градиента.

## <a name="cmfctooltipinfom_clrtext"></a><a name="m_clrtext"></a>CMFCToolTipInfo::m_clrText

Определяет цвет текста всех наборов инструментов.

```
COLORREF m_clrText;
```

## <a name="cmfctooltipinfom_ngradientangle"></a><a name="m_ngradientangle"></a>CMFCToolTipInfo::m_nGradientAngle

Определяет угол, под которым градиент нарисован на фоне орудия.

```
int m_nGradientAngle;
```

### <a name="remarks"></a>Примечания

`m_nGradientAngle`определяет угол, в градусах, что градиент на фоне орудия смещения от горизонтальной. Если `m_nGradientAngle` 0, градиент обращается слева направо. Если `m_nGradientAngle` это от 1 до 360, градиент вращается по часовой стрелке на это количество градусов. Если `m_nGradientAngle` значение -1 является значением по умолчанию, градиент нарисован сверху вниз. Это то же `m_nGradientAngle` самое, что параметр до 90.

[CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` определяет цвет начала градиента и [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` определяет цвет конца градиента. Если `m_clrFillGradient` -1, нет градиента.

## <a name="cmfctooltipinfom_nmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a>CMFCToolTipInfo::m_nMaxDescrWidth

Упоняет максимальную ширину описания, отображаемого в каждом инструменте. Если ширина описания превышает указанное значение, текст заворачивается.

```
int m_nMaxDescrWidth;
```

## <a name="cmfctooltipinfom_bvislmanagertheme"></a><a name="m_bvislmanagertheme"></a>CMFCToolTipInfo::m_bVislManagerTheme

Определяет, контролирует ли визуальный менеджер приложения внешний вид всех наборов инструментов.

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>Примечания

Если `m_bVislManagerTheme` это правда, каждый набор инструментов запрашивает новый [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) от визуального менеджера приложения, прежде чем они появятся на экране, и использует значения в этом объекте, чтобы определить их внешний вид. Другие члены вашего [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) игнорируются.

## <a name="cmfctooltipinfooperator"></a><a name="operator_eq"></a>CMFCToolTipInfo::оператор

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>Параметры

(в) *src*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)<br/>
[Класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)
