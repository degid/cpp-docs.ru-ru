---
title: CmFCRibbonFontComboBox класс
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::CMFCRibbonFontComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::BuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetCharSet
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontDesc
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetFontType
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::GetPitchAndFamily
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::RebuildFonts
- AFXRIBBONCOMBOBOX/CMFCRibbonFontComboBox::SetFont
helpviewer_keywords:
- CMFCRibbonFontComboBox [MFC], CMFCRibbonFontComboBox
- CMFCRibbonFontComboBox [MFC], BuildFonts
- CMFCRibbonFontComboBox [MFC], GetCharSet
- CMFCRibbonFontComboBox [MFC], GetFontDesc
- CMFCRibbonFontComboBox [MFC], GetFontType
- CMFCRibbonFontComboBox [MFC], GetPitchAndFamily
- CMFCRibbonFontComboBox [MFC], RebuildFonts
- CMFCRibbonFontComboBox [MFC], SetFont
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
ms.openlocfilehash: dbf28787e0c0f7d89586fbf98632bd9172c12eed
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754158"
---
# <a name="cmfcribbonfontcombobox-class"></a>CmFCRibbonFontComboBox класс

Реализует поле со списком, содержащее список шрифтов. Необходимо задать поле со списком на панели ленты.

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Деструктор.|

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|Создает и инициализирует объект `CMFCRibbonFontComboBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|Заполняет поле со списком шрифтов на ленте на основе таких заданных параметров, как тип и семейство шрифтов, а также кодировка и шаг.|
|`CMFCRibbonFontComboBox::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|Возвращает указанный набор символов.|
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|Возвращает типы шрифтов, отображаемые в поле со списком. Допустимые значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE, а также любые их битовые комбинации.|
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|Возвращает шаг и семейство шрифтов, отображаемых в поле со списком.|
|`CMFCRibbonFontComboBox::GetThisClass`|Используется фректором для получения указателя на объект [CRuntimeClass,](../../mfc/reference/cruntimeclass-structure.md) связанный с этим типом класса.|
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|Заполняет поле со списком шрифтов на ленте на основе таких ранее заданных параметров, как тип и семейство шрифтов, а также кодировка и шаг.|
|[CMFCRibbonFontComboBox::SetFont](#setfont)|Выбирает указанный шрифт в поле со списком.|

## <a name="remarks"></a>Примечания

После создания `CMFCRibbonFontComboBox` объекта добавьте его в ленточной панели, позвонив [по CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

[CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxRibbonComboBox.h

## <a name="cmfcribbonfontcomboboxbuildfonts"></a><a name="buildfonts"></a>CMFCRibbonFontComboBox:BuildFonts

Заселяет комбо-коробку на ленту шрифтами.

```cpp
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```

### <a name="parameters"></a>Параметры

*nФонТип*<br/>
(в) Определяет тип шрифта для добавления.

*nCharSet*<br/>
(в) Определяет набор символов шрифтов для добавления.

*nPitchAndFamily*<br/>
(в) Определяет поле и семейство шрифтов, чтобы добавить.

## <a name="cmfcribbonfontcomboboxcmfcribbonfontcombobox"></a><a name="cmfcribbonfontcombobox"></a>CMFCRibbonFontComboBox::CMFCRibbonFontComboBox

Строит и инициализирует объект [CMFCRibbonFontComboBox.](../../mfc/reference/cmfcribbonfontcombobox-class.md)

```
CMFCRibbonFontComboBox(
    UINT nID,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    BYTE nPitchAndFamily = DEFAULT_PITCH,
    int nWidth = -1);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Идентификатор команды, выполняемый при выборе элемента из комбо-бокса.

*nФонТип*<br/>
(в) Определяет, какие типы шрифтов отобразяются в комбо-коробке. Допустимые значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE, а также любые их битовые комбинации.

*nCharSet*<br/>
(в) Фильтрует шрифты в комбо-коробке для тех, которые принадлежат к указанному набору символов.

*nPitchAndFamily*<br/>
(в) Определяет поле и семейство шрифтов, которые отображаются в комбо-коробке.

*nWidth*<br/>
(в) Определяет ширину, в пикселях, комбо-коробки.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации о возможных [EnumFontFamProc](/previous-versions/dd162621\(v=vs.85\)) значениях параметров *nFontType* см.

Для получения дополнительной информации об действительных наборах символов, которые могут быть назначены *nCharSet,* и действительных значениях, которые могут быть назначены *nPitchAndFamily,* см. [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) в документации Windows SDK.

## <a name="cmfcribbonfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFCRibbonFontComboBox::GetFontDesc

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;
```

### <a name="parameters"></a>Параметры

(в) *iIndex*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonfontcomboboxrebuildfonts"></a><a name="rebuildfonts"></a>CMFCRibbonFontComboBox::RebuildФоны

Заполняет комбо-коробку на ленте шрифтами ранее указанного типа шрифта, набора символов, а также высоту и семейство.

```cpp
void RebuildFonts();
```

### <a name="remarks"></a>Примечания

Вы можете указать тип шрифта, набор символов, а также шаг и семейство шрифтов, чтобы включить в ленту купюра комбо поле в [конструктор](#cmfcribbonfontcombobox) е-класса, или позвонив [cmfcRibbonFontComboBox::BuildFonts](#buildfonts).

## <a name="cmfcribbonfontcomboboxsetfont"></a><a name="setfont"></a>CMFCRibbonFontComboBox::SetFont

Выбирает указанный шрифт в поле со списком.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet = DEFAULT_CHARSET,
    BOOL bExact = FALSE);
```

### <a name="parameters"></a>Параметры

'lpszName) определяет название шрифта для выбора.

*nCharSet*<br/>
Определяет набор символов для выбранного шрифта.

*bТочный*<br/>
TRUE указать, что набор символов должен соответствовать при выборе шрифта; FALSE указать, что набор символов может быть проигнорирован при выборе шрифта.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если указанный шрифт был найден и выбран; в противном случае, ноль.

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonfontcomboboxgetcharset"></a><a name="getcharset"></a>CMFCRibbonFontComboBox::GetCharset

Возвращает указанный набор символов.

```
BYTE GetCharSet() const;
```

### <a name="return-value"></a>Возвращаемое значение

Набор символов (см. LOGFONT в документации Windows SDK).

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonfontcomboboxgetfonttype"></a><a name="getfonttype"></a>CMFCRibbonFontComboBox::GetFontType

Возвращает типы шрифтов, отображаемые в поле со списком. Допустимые значения: DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE, а также любые их битовые комбинации.

```
int GetFontType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Типы шрифтов (см. EnumFontFamProc в документации Windows SDK).

### <a name="remarks"></a>Примечания

## <a name="cmfcribbonfontcomboboxgetpitchandfamily"></a><a name="getpitchandfamily"></a>CMFCRibbonFontComboBox:GetPitchandFamily

Возвращает шаг и семейство шрифтов, отображаемых в поле со списком.

```
BYTE GetPitchAndFamily() const;
```

### <a name="return-value"></a>Возвращаемое значение

Шаг и семейство (см. LOGFONT в документации Windows SDK).

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)
