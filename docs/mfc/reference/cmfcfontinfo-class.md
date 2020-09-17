---
title: Класс CMFCФонФоФо
ms.date: 11/04/2016
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
helpviewer_keywords:
- CMFCFontInfo [MFC], GetFullName
- CMFCFontInfo [MFC], m_nCharSet
- CMFCFontInfo [MFC], m_nPitchAndFamily
- CMFCFontInfo [MFC], m_nType
- CMFCFontInfo [MFC], m_strName
- CMFCFontInfo [MFC], m_strScript
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
ms.openlocfilehash: 6e87971e2afefc9cf1574abe951920c254dcd2ae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367484"
---
# <a name="cmfcfontinfo-class"></a>Класс CMFCФонФоФо

Класс `CMFCFontInfo` описывает имя и другие атрибуты шрифта.

## <a name="syntax"></a>Синтаксис

```
class CMFCFontInfo : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCFontInfo`|Формирует объект `CMFCFontInfo`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCФонФоФоф::GetFullName](#getfullname)|Извлекает concatenated имена шрифта и его набор символов (скрипт).|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCФонФоФо::m_nCharSet](#m_ncharset)|Значение, опознавававое набор символов (скрипт), связанный с шрифтом.|
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Значение, которое определяет поле и семейство шрифта.|
|[CMFCФонФоФо::m_nType](#m_ntype)|Значение, опознававававое тип шрифта.|
|[CMFCФонФоФо::m_strName](#m_strname)|Название шрифта; например, **Arial**.|
|[CMFCФонФоФо::m_strScript](#m_strscript)|Имя набора символов (скрипта), связанного с шрифтом.|

## <a name="remarks"></a>Примечания

Объект можно `CMFCFontInfo` прикрепить к элементу класса [CMFCToolBarFontComboBox.](../../mfc/reference/cmfctoolbarfontcombobox-class.md) Позвоните в [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) метод для извлечения указателя на `CMFCFontInfo` объект.

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCFontInfo` использовать различные члены класса. Пример показывает, как получить `CMFCFontInfo` объект `CMFCRibbonFontComboBox`от , и как получить доступ к его локальным переменным. Этот пример является частью [образца MSOffice 2007 Demo.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_MSOffice2007Demo#6](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbarfontcombobox.h

## <a name="cmfcfontinfocmfcfontinfo"></a><a name="cmfcfontinfo"></a>CMFCФонФофо::CMFCФонФофофо

Формирует объект `CMFCFontInfo`.

```
CMFCFontInfo(
    LPCTSTR lpszName,
    LPCTSTR lpszScript,
    BYTE nCharSet,
    BYTE nPitchAndFamily,
    int nType);

CMFCFontInfo(const CMFCFontInfo& src);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
(в) Название шрифта. Для получения дополнительной `lfFaceName` [информации](/windows/win32/api/wingdi/ns-wingdi-logfontw) см.

*lpszScript*<br/>
(в) Название скрипта (набор символов) шрифта.

*nCharSet*<br/>
(в) Значение, опознавававое набор символов (скрипт) шрифта. Для получения дополнительной `lfCharSet` [информации](/windows/win32/api/wingdi/ns-wingdi-logfontw) см.

*nPitchAndFamily*<br/>
(в) Значение, которое определяет поле и семейство шрифта. Для получения дополнительной `lfPitchAndFamily` [информации](/windows/win32/api/wingdi/ns-wingdi-logfontw) см.

*nType*<br/>
(в) Значение, описававававававаемый тип шрифта. Этот параметр может быть битовидной комбинацией (ИЛИ) DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE.

*src*<br/>
(в) Существующий `CMFCFontInfo` объект, члены которого используются для построения этого `CMFCFontInfo` объекта.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Эта документация использует *набор символов* терминов и *сценарий* взаимозаменяемо. *Сценарий*, который также известен как система письма, представляет собой набор символов и правил для написания этих символов на одном или нескольких языках. Коллекция символов включает алфавит и пунктуацию, используемые в этом скрипте. Например, латинская скрипт используется для английского языка, как это говорят в Соединенных Штатах, и его алфавит включает в себя символы от А до Я. Член `lfCharSet` структуры [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) определяет набор символов. Например, значение ANSI_CHARSET определяет набор символов ANSI, который включает алфавит латинского скрипта.

## <a name="cmfcfontinfogetfullname"></a><a name="getfullname"></a>CMFCФонФоФоф::GetFullName

Извлекает concatenated имена шрифта и его набор символов (скрипт).

```
CString GetFullName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Строка, содержащая имя шрифта и сценарий.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы получить полное имя шрифта. Например, если имя шрифта Является **Arial,** а шрифт - **кириллическим,** этот метод возвращает "Arial (кириллический)".

## <a name="cmfcfontinfom_ncharset"></a><a name="m_ncharset"></a>CMFCФонФоФо::m_nCharSet

Значение, опознавававое набор символов (скрипт), связанный с шрифтом.

```
const BYTE m_nCharSet;
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации см. *nCharSet* параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.

## <a name="cmfcfontinfom_npitchandfamily"></a><a name="m_npitchandfamily"></a>CMFCFontInfo::m_nPitchAndFamily

Значение, опознавающее высоту (размер точек) и семейство (например, засечка, без засечек и монопространство) шрифта.

```
const BYTE m_nPitchAndFamily;
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, см *nPitchAndFamily* параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.

## <a name="cmfcfontinfom_ntype"></a><a name="m_ntype"></a>CMFCФонФоФо::m_nType

Значение, опознававававое тип шрифта.

```
const int m_nType;
```

### <a name="remarks"></a>Примечания

Для получения дополнительной *информации* см. [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo)

## <a name="cmfcfontinfom_strname"></a><a name="m_strname"></a>CMFCФонФоФо::m_strName

Название шрифта: например, **Arial**.

```
const CString m_strName;
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, см *lpszName* параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.

## <a name="cmfcfontinfom_strscript"></a><a name="m_strscript"></a>CMFCФонФоФо::m_strScript

Имя набора символов (скрипта), связанного с шрифтом.

```
const CString m_strScript;
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, *см. lpszScript* параметр [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) конструктор.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CmFCToolBarFontComboBox класс](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[CMFCToolBarFontSizeComboBox класс](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)
