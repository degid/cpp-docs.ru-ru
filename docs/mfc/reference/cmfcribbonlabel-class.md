---
title: Класс CMFCRibbonLabel
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::CMFCRibbonLabel
- AFXRIBBONLABEL/CMFCRibbonLabel::SetACCData
helpviewer_keywords:
- CMFCRibbonLabel [MFC], CMFCRibbonLabel
- CMFCRibbonLabel [MFC], SetACCData
ms.assetid: 0346c891-83bf-4f20-b8a1-c84cf2aadced
ms.openlocfilehash: cd30e374441661368d3ea7abf5177424f8dffb3c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375123"
---
# <a name="cmfcribbonlabel-class"></a>Класс CMFCRibbonLabel

Реализует недоступную для щелчка текстовую метку для ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonLabel : public CMFCRibbonButton
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonLabel::CMFCRibbonLabel](#cmfcribbonlabel)|Строит и инициализирует `CMFCRibbonLabel` объект с указанной строкой текста.|
|`CMFCRibbonLabel::~CMFCRibbonLabel`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonLabel::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|`CMFCRibbonLabel::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCRibbonLabel::SetACCData](#setaccdata)|Определяет данные доступности для текущего элемента ленточной метки. (Переопределяет [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

### <a name="remarks"></a>Примечания

После создания ленты этикетки, добавить его в панель, позвонив [CMFCRibbonPanel::Добавить](../../mfc/reference/cmfcribbonpanel-class.md#add).

Вы не можете добавить ленту этикетку для панели инструментов быстрого доступа.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonLabel](../../mfc/reference/cmfcribbonlabel-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonLabel.h

## <a name="cmfcribbonlabelcmfcribbonlabel"></a><a name="cmfcribbonlabel"></a>CMFCRibbonLabel::CMFCRibbonLabel

Строит и инициализирует объект [CMFCRibbonLabel,](../../mfc/reference/cmfcribbonlabel-class.md) который отображает указанную строку текста.

```
CMFCRibbonLabel(
    LPCTSTR lpszText,
    BOOL bIsMultiLine = FALSE);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
(в) Текст, который будет отображаться на этикетке.

*bIsMultiLine*<br/>
(в) TRUE указать, что этикетка является многолинейной этикеткой; в противном случае, FALSE.

## <a name="cmfcribbonlabelsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonLabel::SetACCData

Определяет данные доступности для текущего элемента ленточной метки.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*pРодитель*<br/>
(в) Представляет родительское окно текущей ленты.

*данные*<br/>
(ваут) Объект типа, `CAccessibilityData` населенный данными о доступности текущей метки ленты.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если параметр *данных* был успешно заселен данными о доступности текущей метки ленты; в противном случае, FALSE.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)
