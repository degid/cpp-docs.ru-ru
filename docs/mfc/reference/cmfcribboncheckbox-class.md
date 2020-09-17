---
title: Класс CMFCRibbonCheckBox
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
helpviewer_keywords:
- CMFCRibbonCheckBox [MFC], CMFCRibbonCheckBox
- CMFCRibbonCheckBox [MFC], GetCompactSize
- CMFCRibbonCheckBox [MFC], GetIntermediateSize
- CMFCRibbonCheckBox [MFC], GetRegularSize
- CMFCRibbonCheckBox [MFC], IsDrawTooltipImage
- CMFCRibbonCheckBox [MFC], OnDraw
- CMFCRibbonCheckBox [MFC], OnDrawMenuImage
- CMFCRibbonCheckBox [MFC], OnDrawOnList
- CMFCRibbonCheckBox [MFC], SetACCData
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
ms.openlocfilehash: 089c8056afebef31ff98a435bf145566ae64fe1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375258"
---
# <a name="cmfcribboncheckbox-class"></a>Класс CMFCRibbonCheckBox

Класс `CMFCRibbonCheckBox` реализует флажок, который можно добавить на панель ленты, панель быстрого доступа или во всплывающее меню.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(Переопределяет [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(Переопределяет [CMFCRibbonButton::GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(Переопределяет [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(Переопределяет `CMFCRibbonButton::IsDrawTooltipImage`.)|
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(Переопределяет [CMFCRibbonButton::Ondraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(Переопределяет [CMFCRibbonbaseElement::OndrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(Переопределяет `CMFCRibbonButton::OnDrawOnList`.)|
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(Переопределяет [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

## <a name="remarks"></a>Примечания

Чтобы использовать класс `CMFCRibbonCheckBox` в вашем приложении, добавьте в код следующий конструктор:

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```

где *nID* является идентификатор команды флажка и *lpszText* является текстовой этикеткой флажка.

Вы можете добавить флажок к ленточной панели с помощью [CMFCRibbonPanel::Добавить](../../mfc/reference/cmfcribbonpanel-class.md#add).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxribboncheckbox.h

## <a name="cmfcribboncheckboxcmfcribboncheckbox"></a><a name="cmfcribboncheckbox"></a>CMFCRibbonCheckBox::CMFCRibbonCheckBox

Конструктор объекта ленточного флажка

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Определяет идентификатор команды.

*lpszText*<br/>
(в) Определяет текстовую метку.

### <a name="return-value"></a>Возвращаемое значение

Конструирует объект коробки флажка ленты.

### <a name="example"></a>Пример

В следующем примере показано, как `CMFCRibbonCheckBox` построить объект класса.

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

## <a name="cmfcribboncheckboxgetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonCheckBox::GetCompactSize

При перегоне получает компактный размер флажка.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на CDC, связанный с флажкой.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CSize` объект, содержащий компактный размер флажка.

### <a name="remarks"></a>Примечания

Если не переопределен, возвращает промежуточный размер флажка.

## <a name="cmfcribboncheckboxgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonCheckBox::GetIntermediateSize

Получает промежуточный размер флажка.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на CDC, связанный с этим флажок.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CSize` содержащий промежуточный размер флажка.

### <a name="remarks"></a>Примечания

Если не переопределить, вычисляет промежуточный размер, как размер флажка по умолчанию () `AFX_CHECK_BOX_DEFAULT_SIZE`плюс размер текста, плюс поля.

## <a name="cmfcribboncheckboxgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonCheckBox::GetRegularSize

Получает обычный размер флажка.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на объект CDC, связанный с этим флажок.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CSize` объект, содержащий обычный размер флажка.

### <a name="remarks"></a>Примечания

Если не переопределен, возвращает промежуточный размер флажка.

## <a name="cmfcribboncheckboxisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>CMFCRibbonCheckBox::IsdrawtooltipImage

Указывает, есть ли изображение tooltip, связанное с флажком.

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если есть инструментарий изображение, связанное с флажком, или FALSE, если нет.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncheckboxondraw"></a><a name="ondraw"></a>CMFCRibbonCheckBox::Ondraw

Вызывается фреймворком для рисования флажка с помощью заданного контекста устройства.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на CDC, в котором нарисовать флажок.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncheckboxondrawmenuimage"></a><a name="ondrawmenuimage"></a>CMFCRibbonCheckBox::OndrawMenuImage

Вызывается рамки, чтобы нарисовать изображение меню для флажка.

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Параметры

(в) *CDC&#42;*<br/>
Указатель на CDC, связанный с флажкой.

*CRect*<br/>
(в) Объект, `CRect` определяющий прямоугольник, в котором можно нарисовать изображение меню.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если изображение было нарисовано, или FALSE, если нет.

### <a name="remarks"></a>Примечания

Если не переопределить, возвращает FALSE.

## <a name="cmfcribboncheckboxondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonCheckBox::Ondrawonlist

Вызывается рамки, чтобы нарисовать флажок в поле списка команд.

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства, в котором можно нарисовать флажок.

*strText*<br/>
[in] Отображаемый текст.

*nTextOffset*<br/>
(в) Расстояние в пикселях от левой стороны окна списка до текста дисплея.

*rect*<br/>
(в) Прямоугольник дисплея для флажка.

*bIsSelected*<br/>
(в) ПРАВДА, если флажок выбран, или FALSE, если нет.

*bНазалион*<br/>
(в) ПРАВДА, если флажок выделен, или FALSE, если нет.

### <a name="remarks"></a>Примечания

## <a name="cmfcribboncheckboxsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonCheckBox::SetACCData

Устанавливает данные о доступности для флажка.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*pРодитель*<br/>
Родительское окно флажка.

*данные*<br/>
Данные о доступности флажка.

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращается TRUE.

### <a name="remarks"></a>Примечания

По умолчанию этот метод устанавливает данные доступности для флажка и всегда возвращает TRUE. Переопределите этот метод, чтобы задать данные специальных возможностей и возвращать значение, указывающее на успешное или неуспешное выполнение.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)
