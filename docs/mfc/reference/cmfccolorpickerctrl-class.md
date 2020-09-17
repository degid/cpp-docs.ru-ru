---
title: Класс CMFCColorPickerCtrl
ms.date: 11/19/2018
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
ms.openlocfilehash: fe35ee5d6fc6484788a2636151c386689f4bdd96
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752538"
---
# <a name="cmfccolorpickerctrl-class"></a>Класс CMFCColorPickerCtrl

Класс `CMFCColorPickerCtrl` предоставляет функциональность для элемента управления, используемого для выбора цветов.

## <a name="syntax"></a>Синтаксис

```
class CMFCColorPickerCtrl : public CButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Формирует объект `CMFCColorPickerCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Извлекает цвет, выбранный пользователем.|
|[CMFCColorPickerCtrl:GetHLS](#gethls)|Извлекает значения оттенка, яркости и насыщенности цвета, который выбирает пользователь.|
|[CMFCColorPickerCtrl:GetHue](#gethue)|Извлекает компонент оттенка цвета, который выбирает пользователь.|
|[CMFCColorPickerCtrl:GetLuminance](#getluminance)|Извлекает светящийся компонент цвета, который выбирает пользователь.|
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Извлекает компонент насыщения цвета, который выбирает пользователь.|
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Устанавливает текущий цвет к цвету, определенному указанными компонентами цвета RGB или указанной ячейкой шестиугольника.|
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Устанавливает текущий цвет в указанное значение цвета RGB.|
|[CMFCColorPickerCtrl:SetHLS](#sethls)|Устанавливает текущий цвет к указанному цвету HLS.|
|[CMFCColorPickerCtrl:SetHue](#sethue)|Изменяет компонент оттенка выбранного цвета.|
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Изменяет компонент яркости выбранного цвета.|
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Устанавливает ширину панели яркости в управлении сборщиком цветов.|
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|Устанавливает начальный выбранный цвет.|
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Устанавливает текущую цветовую палитру.|
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Изменяет компонент насыщения выбранного цвета.|
|[CMFCColorPickerCtrl:SetType](#settype)|Устанавливает тип управления сборщиком цветов для отображения.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Вызывается фреймворком перед отображением курсора, указываючего на выбранный цвет.|

## <a name="remarks"></a>Примечания

Стандартные цвета выбираются из шестиугольной цветовой палитры, а пользовательские цвета выбираются из панели яркости, где цвета определяются с использованием либо красной/зеленой/синей обозначения, либо оттенка/санурации/светимости.

На следующей иллюстрации изображено несколько `CMFCColorPickerCtrl` объектов.

![Диалоговое окно для CMFCColorPickerCtrl](../../mfc/reference/media/colorpicker.png "Диалоговое окно для CMFCColorPickerCtrl")

Поддерживает `CMFCColorPickerCtrl` две пары стилей. Стили HEX и HEX_GREYSCALE подходят для стандартного выбора цвета. Стили PICKER и LUMINANCE подходят для индивидуального выбора цвета.

Выполните следующие шаги, чтобы включить `CMFCColorPickerCtrl` элемент управления в диалоговую будку:

1. Если вы используете **ClassWizard,** вставьте новый элемент управления `CMFCColorPickerCtrl` кнопкой в шаблон `CButton` диалогового окна (потому что класс наследуется от класса).

1. Вставьте переменную участника, связанную с новым управлением кнопкой, в класс диалогового окна. Затем измените переменный тип с `CButton` к `CMFCColorPickerCtrl`.

1. Вставьте `WM_INITDIALOG` обработчик сообщений для класса диалогового окна. В обработчике установите тип, палитру `CMFCColorPickerCtrl` и начальный выбранный цвет элемента управления.

## <a name="example"></a>Пример

В следующем примере показано, `CMFCColorPickerCtrl` как настроить объект с `CMFCColorPickerCtrl` помощью различных методов в классе. Пример показывает, как установить тип управления сборщика, и как установить его цвет, оттенок, яркость и насыщенность. Пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxcolorpickerctrl.h

## <a name="cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a>CMFCColorPickerCtrl::CMFCColorPickerCtrl

Формирует объект `CMFCColorPickerCtrl`.

```
CMFCColorPickerCtrl();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a>CMFCColorPickerCtrl::DrawCursor

Вызывается фреймворком перед отображением курсора, указываючего на выбранный цвет.

```
virtual void DrawCursor(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

*rect*<br/>
(в) Определяет прямоугольную область вокруг выбранного цвета.

### <a name="remarks"></a>Примечания

Переопределить этот метод, когда вам нужно изменить форму курсора, который указывает на выбранный цвет.

## <a name="cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a>CMFCColorPickerCtrl::GetColor

Извлекает цвет, выбранный пользователем.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение RGB выбранного цвета.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlgethls"></a><a name="gethls"></a>CMFCColorPickerCtrl:GetHLS

Извлекает значения оттенка, яркости и насыщенности цвета, который выбирает пользователь.

```cpp
void GetHLS(
    double* hue,
    double* luminance,
    double* saturation);
```

### <a name="parameters"></a>Параметры

*Оттенок*<br/>
(ваут) Указатель на переменную типа double, которая получает информацию оттенка.

*Яркости*<br/>
(ваут) Указатель на переменную типа двойной, которая получает информацию о яркости.

*Насыщенность*<br/>
(ваут) Указатель на переменную типа double, которая получает информацию о насыщении.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlgethue"></a><a name="gethue"></a>CMFCColorPickerCtrl:GetHue

Извлекает компонент оттенка цвета, который выбирает пользователь.

```
double GetHue() const;
```

### <a name="return-value"></a>Возвращаемое значение

Компонент оттенка выбранного цвета.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a>CMFCColorPickerCtrl:GetLuminance

Извлекает светящийся компонент цвета, который выбирает пользователь.

```
double GetLuminance() const;
```

### <a name="return-value"></a>Возвращаемое значение

Светящийся компонент выбранного цвета.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a>CMFCColorPickerCtrl::GetSaturation

Извлекает значение насыщения цвета, выбранного пользователем.

```
double GetSaturation() const;
```

### <a name="return-value"></a>Возвращаемое значение

Компонент насыщения выбранного цвета.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a>CMFCColorPickerCtrl::SelectCellHexagon

Устанавливает текущий цвет к цвету, определенному указанными компонентами цвета RGB или указанной ячейкой шестиугольника.

```cpp
void SelectCellHexagon(
    BYTE R,
    BYTE G,
    BYTE B);

BOOL SelectCellHexagon(
    int x,
    int y);
```

### <a name="parameters"></a>Параметры

*R*<br/>
(в) Компонент красного цвета.

*Г*<br/>
(в) Компонент зеленого цвета.

*B*<br/>
(в) Компонент синего цвета.

*x*<br/>
(в) X-координат курсора, который указывает на шестиугольник клетки.

*Y*<br/>
(в) Y-координат курсора, который указывает на шестиугольник клетки.

### <a name="return-value"></a>Возвращаемое значение

Вторая перегрузка этого метода всегда возвращает FALSE.

### <a name="remarks"></a>Примечания

Первая перегрузка этого метода устанавливает текущий цвет к цвету, который соответствует указанным красным, зеленым и синим компонентам цвета.

Вторая перегрузка этого метода устанавливает текущий цвет к цвету шестиугольника клетки, на который указывается указанное местоположение курсора.

## <a name="cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a>CMFCColorPickerCtrl::SetColor

Устанавливает текущий цвет в указанное значение цвета RGB.

```cpp
void SetColor(COLORREF Color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Значение цвета RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlsethls"></a><a name="sethls"></a>CMFCColorPickerCtrl:SetHLS

Устанавливает текущий цвет к указанному цвету HLS.

```cpp
void SetHLS(
    double hue,
    double luminance,
    double saturation,
    BOOL bInvalidate=TRUE);
```

### <a name="parameters"></a>Параметры

*Оттенок*<br/>
(в) Значение оттенка.

*Яркости*<br/>
(в) Значение яркости.

*Насыщенность*<br/>
(в) Значение насыщения.

*bНедействительно*<br/>
(в) TRUE, чтобы заставить окно немедленно обновить новый цвет; в противном случае, FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlsethue"></a><a name="sethue"></a>CMFCColorPickerCtrl:SetHue

Изменяет оттенок выбранного в настоящее время цвета.

```cpp
void SetHue(double Hue);
```

### <a name="parameters"></a>Параметры

*Hue*<br/>
(в) Значение оттенка.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a>CMFCColorPickerCtrl::SetLuminance

Изменяет яркость выбранного в настоящее время цвета.

```cpp
void SetLuminance(double Luminance);
```

### <a name="parameters"></a>Параметры

*Освещенность*<br/>
(в) Значение яркости.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a>CMFCColorPickerCtrl::SetLuminanceBarWidth

Устанавливает ширину панели яркости в управлении сборщиком цветов.

```cpp
void SetLuminanceBarWidth(int w);
```

### <a name="parameters"></a>Параметры

*w*<br/>
(в) Ширина панели яркости измеряется в пикселях.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы изменить размер панели яркости, которая находится на **пользовательской** вкладке управления сборщиком цветов. Параметр *w* определяет новую ширину панели яркости. Значение ширины игнорируется, если оно превышает три четверти ширины области клиента.

## <a name="cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a>CMFCColorPickerCtrl::SetOriginalColor

Устанавливает начальный выбранный цвет.

```cpp
void SetOriginalColor(COLORREF ref);
```

### <a name="parameters"></a>Параметры

*ref*<br/>
(в) Значение цвета RGB.

### <a name="remarks"></a>Примечания

Вызовите этот метод, когда управление сборщиком цветов инициализировано.

## <a name="cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a>CMFCColorPickerCtrl::SetPalette

Устанавливает текущую цветовую палитру.

```cpp
void SetPalette(CPalette* pPalette);
```

### <a name="parameters"></a>Параметры

*pPalette*<br/>
(в) Указатель на цветовую палитру.

### <a name="remarks"></a>Примечания

Цветовая палитра определяет массив цветов, представленных в управлении сборщиком цветов.

## <a name="cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a>CMFCColorPickerCtrl::SetSaturation

Изменяет насыщенность выбранного в настоящее время цвета.

```cpp
void SetSaturation(double Saturation);
```

### <a name="parameters"></a>Параметры

*Насыщенность*<br/>
(в) Значение насыщения.

### <a name="remarks"></a>Примечания

## <a name="cmfccolorpickerctrlsettype"></a><a name="settype"></a>CMFCColorPickerCtrl:SetType

Устанавливает тип управления сборщиком цветов для отображения.

```cpp
void SetType(COLORTYPE colorType);
```

### <a name="parameters"></a>Параметры

*colorType*<br/>
(в) Тип управления сборщиком цветов.

Типы определяются `CMFCColorPickerCtrl::COLORTYPE` перечислением. Возможные типы: LUMINANCE, PICKER, HEX и HEX_GREYSCALE. Тип по умолчанию PICKER.

### <a name="remarks"></a>Примечания

Чтобы указать тип управления сборщиком цветов, позвоните по этому методу до создания элемента управления Windows.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)
