---
title: Класс CMFCPropertyGridFontProperty
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFontProperty::GetLogFont
helpviewer_keywords:
- CMFCPropertyGridFontProperty [MFC], CMFCPropertyGridFontProperty
- CMFCPropertyGridFontProperty [MFC], GetColor
- CMFCPropertyGridFontProperty [MFC], GetLogFont
ms.assetid: 83693f33-bbd3-4fcb-a9ad-fa79fcf2ca24
ms.openlocfilehash: a1c9905d8d7f32a049496c4e164c9eaac13455d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361839"
---
# <a name="cmfcpropertygridfontproperty-class"></a>Класс CMFCPropertyGridFontProperty

Класс `CMFCPropertyGridFileProperty` поддерживает элемент управления списком свойств, который открывает диалоговую коробку выбора шрифта.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyGridFontProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty](#cmfcpropertygridfontproperty)|Формирует объект `CMFCPropertyGridFontProperty`.|
|`CMFCPropertyGridFontProperty::~CMFCPropertyGridFontProperty`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCPropertyGridFontProperty::FormatProperty`|Форматирует текстовое представление значения свойства. (Переопределяет [CMFCPropertyGridProperty::ФорматНедвижимость](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridFontProperty::GetColor](#getcolor)|Извлекает цвет шрифта, выбранный пользователем из окна диалога шрифта.|
|[CMFCPropertyGridFontProperty::GetLogFont](#getlogfont)|Извлекает шрифт, выбранный пользователем из окна диалога шрифта.|
|`CMFCPropertyGridFontProperty::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|`CMFCPropertyGridFontProperty::OnClickButton`|Вызывается платформой, когда пользователь нажимает кнопку, содержащуюся в свойстве. (Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|

## <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridFontProperty](../../mfc/reference/cmfcpropertygridfontproperty-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertygridctrl.h

## <a name="cmfcpropertygridfontpropertycmfcpropertygridfontproperty"></a><a name="cmfcpropertygridfontproperty"></a>CMFCPropertyGridFontProperty::CMFCPropertyGridFontProperty

Формирует объект `CMFCPropertyGridFontProperty`.

```
CMFCPropertyGridFontProperty(
    const CString& strName,
    LOGFONT& lf,
    DWORD dwFontDialogFlags = CF_EFFECTS | CF_SCREENFONTS,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0,
    COLORREF color = (COLORREF)-1);
```

### <a name="parameters"></a>Параметры

*strName*<br/>
[in] Имя свойства.

*Если*<br/>
(в) Логическая структура шрифта, которая определяет атрибуты шрифта.

*dwFontDialogФлаги*<br/>
(в) Стили, которые применяются к диалоговому окне шрифта, который отображается при нажатии кнопки выпадения значения свойства. Значение по умолчанию — это битная комбинация (ИЛИ) CF_EFFECTS и CF_SCREENFONTS. Для получения дополнительной *информации* см. [CHOOSEFONT Structure](/windows/win32/api/commdlg/ns-commdlg-choosefontw)

*lpszDescr*<br/>
(в) Описание свойства шрифта. Значение по умолчанию — NULL.

*dwData*<br/>
(в) Данные, связанные с приложениями, такие как целый ряд или указатель на другие данные, связанные с свойством. Значение по умолчанию — 0.

*Цвет*<br/>
(в) Цвет шрифта. Значением по умолчанию является цвет по умолчанию.

### <a name="remarks"></a>Примечания

Объект `CMFCPropertyGridFontProperty` представляет свойство шрифта в управлении шрифтом сетки свойств.

### <a name="example"></a>Пример

Следующий пример показывает, как построить объект `CMFCPropertyGridFontProperty` класса. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#26](../../mfc/reference/codesnippet/cpp/cmfcpropertygridfontproperty-class_1.cpp)]

## <a name="cmfcpropertygridfontpropertygetcolor"></a><a name="getcolor"></a>CMFCPropertyGridFontProperty::GetColor

Извлекает цвет шрифта, выбранный пользователем из окна диалога шрифта.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB, представляющее выбранный цвет шрифта.

### <a name="remarks"></a>Примечания

## <a name="cmfcpropertygridfontpropertygetlogfont"></a><a name="getlogfont"></a>CMFCPropertyGridFontProperty::GetLogFont

Извлекает шрифт, выбранный пользователем из окна диалога шрифта.

```
LPLOGFONT GetLogFont();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру [LOGFONT,](/windows/win32/api/wingdi/ns-wingdi-logfontw) описывающий выбранный шрифт.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
