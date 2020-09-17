---
title: Класс CMFCRibbonSlider
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
helpviewer_keywords:
- CMFCRibbonSlider [MFC], CMFCRibbonSlider
- CMFCRibbonSlider [MFC], GetPos
- CMFCRibbonSlider [MFC], GetRangeMax
- CMFCRibbonSlider [MFC], GetRangeMin
- CMFCRibbonSlider [MFC], GetRegularSize
- CMFCRibbonSlider [MFC], GetZoomIncrement
- CMFCRibbonSlider [MFC], HasZoomButtons
- CMFCRibbonSlider [MFC], OnDraw
- CMFCRibbonSlider [MFC], SetPos
- CMFCRibbonSlider [MFC], SetRange
- CMFCRibbonSlider [MFC], SetZoomButtons
- CMFCRibbonSlider [MFC], SetZoomIncrement
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
ms.openlocfilehash: 304581371c68817c6031153c3cec227137771c5d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754072"
---
# <a name="cmfcribbonslider-class"></a>Класс CMFCRibbonSlider

Класс `CMFCRibbonSlider` реализует элемент управления ползунок, который можно добавить в ленточку или ленту статус-бар. Элемент управления "ползунок" ленты напоминает ползунки масштаба, отображаемые в приложениях Office 2007.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonSlider : public CMFCRibbonBaseElement
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Конструирует и инициализирует управление слайдером ленты.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonSlider:GetPos](#getpos)|Возвращает текущее положение элемента управления ползунок.|
|[CMFCRibbonSlider:GetRangeMax](#getrangemax)|Возвращает максимальное значение ползунка.|
|[CMFCRibbonSlider:GetRangeMin](#getrangemin)|Возвращает минимальное значение ползунка.|
|[CMFCRibbonSlider:GetRegularSize](#getregularsize)|Возвращает стандартный размер элемента ленты. (Оверлет [CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|
|[CMFCRibbonSlider::Get'mIncrement](#getzoomincrement)|Возвращает размер приращения зума для управления ползунок.|
|[CMFCRibbonSlider::Хас-ЗумБаттонс](#haszoombuttons)|Уточняется, есть ли в слайдере кнопки масштабирования.|
|[CMFCRibbonSlider::OnDraw](#ondraw)|Вызывается платформой для отрисовки элемента ленты. (Переопределяет [CMFCRibbonBaseElement::Ondraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|
|[CMFCRibbonSlider::SetPos](#setpos)|Устанавливает текущее положение управления ползунок.|
|[CMFCRibbonSlider::SetRange](#setrange)|Определяет диапазон управления ползунок, установив минимальные и максимальные значения.|
|[CMFCRibbonSlider::Set'mButtons](#setzoombuttons)|Показывает или скрывает кнопки масштабирования.|
|[CMFCRibbonSlider::Set'mIncrement](#setzoomincrement)|Устанавливает размер приращения зума для управления ползунок.|

## <a name="remarks"></a>Примечания

Этот `SetRange` метод можно настроить для настройки диапазона приращений увеличения для ползунка. Можно установить текущее положение слайдера с помощью метода. `SetPos`

Вы можете отображать круговые кнопки масштабирования на левой и `SetZoomButtons` правой стороне управления ползунок с помощью метода. По умолчанию ползунок горизонтальный, левая кнопка масштабирования отображает знак минус, а правая кнопка масштабирования отображает знак плюс.

Метод `SetZoomIncrement` определяет приращение, чтобы добавить или вычесть из текущего положения, когда пользователь нажимает кнопки масштабирования.

## <a name="example"></a>Пример

В следующем примере показано, как использовать `CMFCRibbonSlider` различные методы в классе для установки свойств ползунка. На примере показано, `CMFCRibbonSlider` как построить объект, отобразить кнопки масштабирования, установить текущее положение управления ползунок и установить диапазон значений для управления ползунок.

[!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonslider.h

## <a name="cmfcribbonslidercmfcribbonslider"></a><a name="cmfcribbonslider"></a>CMFCRibbonSlider::CMFCRibbonSlider

Постройте ленточный ползунок.

```
CMFCRibbonSlider(
    UINT nID,
    int nWidth=100);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Идентификатор слайдера.

[in]. *nWidth* Ширина слайдера в пикселях.

### <a name="remarks"></a>Примечания

Конструирует ленточный ползунок, который *nWidth* пикселей широкий в категории панели, где ползунок добавляется. По умолчанию ползунок является горизонтальным.

## <a name="cmfcribbonslidergetpos"></a><a name="getpos"></a>CMFCRibbonSlider:GetPos

Возвращает текущее положение элемента управления ползунок.

```
int GetPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее положение управления ползунок, которое является положением относительно начала слайдера.

## <a name="cmfcribbonslidergetrangemax"></a><a name="getrangemax"></a>CMFCRibbonSlider:GetRangeMax

Получает максимальный прирост ползунка, который ползунок может перемещать на элементе управления ползунок.

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное увеличение ползунка, что ползунок может путешествовать на ползунок управления.

## <a name="cmfcribbonslidergetrangemin"></a><a name="getrangemin"></a>CMFCRibbonSlider:GetRangeMin

Возвращает минимальный прирост, который ползунок может перемещать на элементе управления ползунок.

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальный прирост, который ползунок может перемещать на элементе управления ползунок.

## <a name="cmfcribbonslidergetregularsize"></a><a name="getregularsize"></a>CMFCRibbonSlider:GetRegularSize

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

(в) *pDC*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonslidergetzoomincrement"></a><a name="getzoomincrement"></a>CMFCRibbonSlider::Get'mIncrement

Получите приращение зума для управления ползунок.

```
int GetZoomIncrement() const;
```

### <a name="return-value"></a>Возвращаемое значение

Увеличение приращения для управления ползунок.

## <a name="cmfcribbonsliderhaszoombuttons"></a><a name="haszoombuttons"></a>CMFCRibbonSlider::Хас-ЗумБаттонс

Уточняется, есть ли в слайдере кнопки масштабирования.

```
BOOL HasZoomButtons() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ползунок имеет кнопки масштабирования; FALSE в противном случае.

## <a name="cmfcribbonsliderondraw"></a><a name="ondraw"></a>CMFCRibbonSlider::OnDraw

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

(в) *pDC*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonslidersetpos"></a><a name="setpos"></a>CMFCRibbonSlider::SetPos

Установите текущее положение управления ползунок.

```cpp
void SetPos(
    int nPos,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
(в) Определяет положение для установки для ползунка. Позиция относительно начала слайдера.

*bRedraw*<br/>
(в) Если true, слайдер будет перерисован.

## <a name="cmfcribbonslidersetrange"></a><a name="setrange"></a>CMFCRibbonSlider::SetRange

Установите диапазон значений для управления ползунок.

```cpp
void SetRange(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Параметры

*nMin*<br/>
(в) Определяет минимальное значение управления ползунок.

*nMax*<br/>
(в) Определяет максимальное значение управления ползунок.

### <a name="remarks"></a>Примечания

Определяет диапазон значений для управления ползунок, установив минимальные и максимальные значения.

## <a name="cmfcribbonslidersetzoombuttons"></a><a name="setzoombuttons"></a>CMFCRibbonSlider::Set'mButtons

Отображение или сокрытие кнопок масштабирования.

```cpp
void SetZoomButtons(BOOL bSet=TRUE);
```

### <a name="parameters"></a>Параметры

[in]. *bSet* TRUE для отображения кнопок масштабирования; FALSE, чтобы скрыть их.

## <a name="cmfcribbonslidersetzoomincrement"></a><a name="setzoomincrement"></a>CMFCRibbonSlider::Set'mIncrement

Установите приращение зума для управления ползунок.

```cpp
void SetZoomIncrement(int nZoomIncrement);
```

### <a name="parameters"></a>Параметры

*nЗумИнкремент*<br/>
(в) Определяет увеличение приращения управления ползунок.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)
