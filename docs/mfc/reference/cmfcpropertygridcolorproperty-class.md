---
title: Класс CMFCPropertyGridColorProperty
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableAutomaticButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::EnableOtherButton
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::GetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColor
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetColumnsNumber
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridColorProperty::SetOriginalValue
helpviewer_keywords:
- CMFCPropertyGridColorProperty [MFC], CMFCPropertyGridColorProperty
- CMFCPropertyGridColorProperty [MFC], EnableAutomaticButton
- CMFCPropertyGridColorProperty [MFC], EnableOtherButton
- CMFCPropertyGridColorProperty [MFC], GetColor
- CMFCPropertyGridColorProperty [MFC], SetColor
- CMFCPropertyGridColorProperty [MFC], SetColumnsNumber
- CMFCPropertyGridColorProperty [MFC], SetOriginalValue
ms.assetid: af37be93-a91e-40a2-9a65-0f3412c6f0f8
ms.openlocfilehash: 393a871a881aa4bddd786b1d4333e02d5e0dbef1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751829"
---
# <a name="cmfcpropertygridcolorproperty-class"></a>Класс CMFCPropertyGridColorProperty

Класс `CMFCPropertyGridColorProperty` поддерживает элемент управления списка свойств, открывающий диалоговое окно выбора цвета.

## <a name="syntax"></a>Синтаксис

```
class CMFCPropertyGridColorProperty : public CMFCPropertyGridProperty
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty](#cmfcpropertygridcolorproperty)|Формирует объект `CMFCPropertyGridColorProperty`.|
|`CMFCPropertyGridColorProperty::~CMFCPropertyGridColorProperty`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCPropertyGridColorProperty::EnableAutomaticButton](#enableautomaticbutton)|Включает *автоматическую* кнопку в диалоговом поле выбора цвета. (Стандартная автоматическая кнопка помечена **как автоматическая**.)|
|[CMFCPropertyGridColorProperty::EnableOtherButton](#enableotherbutton)|Включает *другую* кнопку в диалоговом поле выбора цвета. (Стандартная другая кнопка помечена **больше цветов**.)|
|`CMFCPropertyGridColorProperty::FormatProperty`|Форматирует текстовое представление значения свойства. (Переопределяет [CMFCPropertyGridProperty::ФорматНедвижимость](../../mfc/reference/cmfcpropertygridproperty-class.md#formatproperty).)|
|[CMFCPropertyGridColorProperty::GetColor](#getcolor)|Возвращает текущий цвет свойства.|
|`CMFCPropertyGridColorProperty::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|`CMFCPropertyGridColorProperty::OnClickButton`|Вызывается платформой, когда пользователь нажимает кнопку, содержащуюся в свойстве. (Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|
|`CMFCPropertyGridColorProperty::OnDrawValue`|Вызывается платформой для отображения значения свойства. (Переопределяет [CMFCPropertyGridProperty::OndrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue).)|
|`CMFCPropertyGridColorProperty::OnEdit`|Вызывается платформой непосредственно перед изменением значения свойства пользователем. (Переопределяет [CMFCPropertyGridProperty::OnEdit](../../mfc/reference/cmfcpropertygridproperty-class.md#onedit).)|
|`CMFCPropertyGridColorProperty::OnUpdateValue`|Вызывается платформой при присвоении изменяемому свойству нового значения. (Переопределяет [CMFCPropertyGridProperty::OnUpdateValue](../../mfc/reference/cmfcpropertygridproperty-class.md#onupdatevalue).)|
|[CMFCPropertyGridColorProperty::SetColor](#setcolor)|Задает новый цвет свойства.|
|[CMFCPropertyGridColorProperty::SetColumnsNumber](#setcolumnsnumber)|Задает число столбцов в текущей таблице свойств цвета.|
|[CMFCPropertyGridColorProperty::SetOriginalValue](#setoriginalvalue)|Задает изменяемому свойству изначальное значение.|

## <a name="remarks"></a>Примечания

Класс `CMFCPropertyGridColorProperty` поддерживает свойство цвета, которое можно добавить в элемент управления "список свойств". Для получения дополнительной [информации](../../mfc/reference/cmfcpropertygridctrl-class.md)см.

## <a name="example"></a>Пример

В следующем примере демонстрируется создание объекта класса `CMFCPropertyGridColorProperty` и его настройка с помощью различных методов класса `CMFCPropertyGridColorProperty`. В коде показывается, как можно задействовать кнопки автоматического выбора и выбора другого цвета, а также выполняется назначение цвета и количества столбцов. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#13](../../mfc/reference/codesnippet/cpp/cmfcpropertygridcolorproperty-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

[CMFCPropertyGridColorProperty](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxpropertygridctrl.h

## <a name="cmfcpropertygridcolorpropertycmfcpropertygridcolorproperty"></a><a name="cmfcpropertygridcolorproperty"></a>CMFCPropertyGridColorProperty::CMFCPropertyGridColorProperty

Формирует объект `CMFCPropertyGridColorProperty`.

```
CMFCPropertyGridColorProperty(
    const CString& strName,
    const COLORREF& color,
    CPalette* pPalette = NULL,
    LPCTSTR lpszDescr = NULL,
    DWORD_PTR dwData = 0);
```

### <a name="parameters"></a>Параметры

*strName*<br/>
[in] Имя свойства.

*Цвет*<br/>
(в) Цветовая стоимость свойства.

*pPalette*<br/>
(в) Указатель на палитру цветов. Значение по умолчанию — NULL.

*lpszDescr*<br/>
(в) Описание свойства. Значение по умолчанию — NULL.

*dwData*<br/>
(в) Данные, связанные с приложениями, такие как целый ряд или указатель на другие данные, связанные с свойством. Значение по умолчанию — 0.

## <a name="cmfcpropertygridcolorpropertyenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCPropertyGridColorProperty::EnableAutomaticButton

Включает *автоматическую* кнопку в диалоговом поле выбора цвета. (Стандартная автоматическая кнопка помечена **как автоматическая**.)

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Текст этикетки автоматической кнопки.

*colorAutomatic*<br/>
(в) Значение цвета RGB автоматического (по умолчанию) цвета.

*bEnable*<br/>
(в) TRUE для включения автоматической кнопки; в противном случае, FALSE. Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

## <a name="cmfcpropertygridcolorpropertyenableotherbutton"></a><a name="enableotherbutton"></a>CMFCPropertyGridColorProperty::EnableOtherButton

Включает *другую* кнопку в диалоговом поле выбора цвета. (Стандартная другая кнопка помечена **больше цветов**.)

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg = TRUE,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*lpszLabel*<br/>
(в) Текст метки другой кнопки.

*bAltColorDlg*<br/>
(в) TRUE для `CMFCColorDialog` отображения диалогового окна; FALSE для отображения стандартного цветовыбора диалогового окна. Значение по умолчанию — TRUE.

*bEnable*<br/>
(в) TRUE для отображения другой кнопки; в противном случае, FALSE.  Значение по умолчанию — TRUE.

### <a name="remarks"></a>Примечания

## <a name="cmfcpropertygridcolorpropertygetcolor"></a><a name="getcolor"></a>CMFCPropertyGridColorProperty::GetColor

Возвращает текущий цвет свойства.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение цвета RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfcpropertygridcolorpropertysetcolor"></a><a name="setcolor"></a>CMFCPropertyGridColorProperty::SetColor

Задает новый цвет свойства.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
(в) Значение цвета RGB.

### <a name="remarks"></a>Примечания

## <a name="cmfcpropertygridcolorpropertysetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCPropertyGridColorProperty::SetColumnsNumber

Задает число столбцов в текущей таблице свойств цвета.

```cpp
void SetColumnsNumber(int nColumnsNumber);
```

### <a name="parameters"></a>Параметры

*nКолонкиНомер*<br/>
(в) Предпочтительное количество столбцов в сетке цветного свойства.

### <a name="remarks"></a>Примечания

Этот метод устанавливает значение `m_nColumnsNumber` защищенного члена данных.

## <a name="cmfcpropertygridcolorpropertysetoriginalvalue"></a><a name="setoriginalvalue"></a>CMFCPropertyGridColorProperty::SetOriginalValue

Задает изменяемому свойству изначальное значение.

```
virtual void SetOriginalValue(const COleVariant& varValue);
```

### <a name="parameters"></a>Параметры

*varValue*<br/>
(в) Значение.

### <a name="remarks"></a>Примечания

Используйте метод [CMFCPropertyGridProperty::ResetOriginalValue](../../mfc/reference/cmfcpropertygridproperty-class.md#resetoriginalvalue) для сброса исходного значения отредактированного свойства.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)<br/>
[Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
