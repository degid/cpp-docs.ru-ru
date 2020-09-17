---
title: CmFCToolBarFontComboBox класс
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
ms.openlocfilehash: 7b31f4b725a6983171162d9805d08224ad787808
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360467"
---
# <a name="cmfctoolbarfontcombobox-class"></a>CmFCToolBarFontComboBox класс

Кнопка панели инструментов, содержащая элемент управления комбо-коробкой, который позволяет пользователю выбрать шрифт из списка системных шрифтов.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|Формирует объект `CMFCToolBarFontComboBox`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|Возвращает указатель объекту `CMFCFontInfo` для указанного индекса в комбо-коробке.|
|[CMFCToolBarFontComboBox::SetFont](#setfont)|Выбирает шрифт в комбо-коробке шрифта либо по названию шрифта, либо по приставке и набору символов шрифта.|

### <a name="data-members"></a>Элементы данных

[CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)<br/>
Высота символов в купели комбо-коробке.

## <a name="remarks"></a>Примечания

Чтобы добавить кнопку комбо-коробки шрифта в панель инструментов, выполните следующие действия:

1. Зарезервируйте идентификатор ресурсов для кнопки в родительском ресурсе панели инструментов.

1. Постройте `CMFCToolBarFontComboBox` объект.

1. В обработчике сообщений, который обрабатывает AFX_WM_RESETTOOLBAR сообщение, замените исходную кнопку новой кнопкой комбо-бокса с помощью [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).

1. Синхронизируйте шрифт, выбранный в комбо-коробке с шрифтом в документе, используя метод [CMFCToolBarFontComboBox::SetFont.](#setfont)

Чтобы синхронизировать шрифт документа с шрифтом, выбранным в комбо-коробке, используйте метод [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc) для получения атрибутов выбранного шрифта и используйте эти атрибуты для создания объекта [класса CFont.](../../mfc/reference/cfont-class.md)

Кнопка комбо-коробки шрифта вызывает функцию Win32 [EnumFontFamiliesEx,](/windows/win32/api/wingdi/nf-wingdi-enumfontfamiliesexw) чтобы определить доступные для системы шрифты экрана и принтера.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)

[CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbarfontcombobox.h

## <a name="cmfctoolbarfontcomboboxcmfctoolbarfontcombobox"></a><a name="cmfctoolbarfontcombobox"></a>CMFCToolBarFontComboBox::CMFCToolBarFontComboBox

Строит объект [CMFCToolBarFontComboBox.](../../mfc/reference/cmfctoolbarfontcombobox-class.md)

```
public:
CMFCToolBarFontComboBox(
    UINT uiID,
    int iImage,
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,
    BYTE nCharSet = DEFAULT_CHARSET,
    DWORD dwStyle = CBS_DROPDOWN,
    int iWidth = 0,
    BYTE nPitchAndFamily = DEFAULT_PITCH);

protected:
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,
    int nFontType,
    BYTE nCharSet,
    BYTE nPitchAndFamily);

CMFCToolBarFontComboBox();
```

### <a name="parameters"></a>Параметры

*uiID*<br/>
(в) Идентификатор команды комбо-коробки.

*iImage*<br/>
(в) Индекс нулевой основе изображения панели инструментов. Изображение находится в объекте [класса CMFCToolBarImages,](../../mfc/reference/cmfctoolbarimages-class.md) который поддерживает класс [CMFCToolBar.](../../mfc/reference/cmfctoolbar-class.md)

*nФонТип*<br/>
(в) Типы шрифтов, которые содержит комбо-бокс. Этот параметр может быть комбинацией (boolean OR) следующих значений:

DEVICE_FONTTYPE

RASTER_FONTTYPE

TRUETYPE_FONTTYPE

*nCharSet*<br/>
(в) Если установить на DEFAULT_CHARSET, комбо-коробка содержит все однозначно названные шрифты во всех наборах символов. (Если есть два шрифта с одинаковым названием, комбо-коробка содержит один из них.) Если он устанавливается на допустимое значение набора символов, комбо-поле содержит только шрифты в указанном наборе символов. См [LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw) для перечисления возможных наборов символов.

*dwStyle*<br/>
(в) Стиль комбо-коробки. [(см. Стилей Combo-Box)](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)

*iWidth*<br/>
(в) Ширина в пикселях управления отсеивание.

*nPitchAndFamily*<br/>
(в) Если установить на DEFAULT_PITCH, комбо-коробка содержит шрифты независимо от высоты. Если установить на FIXED_PITCH или VARIABLE_PITCH, комбо-коробка содержит только шрифты с этим типом шага. Фильтрация на основе семейства шрифтов в настоящее время не поддерживается.

*pLstФоныВнешний*<br/>
(ваут) Указатель на объект [класса CObList,](../../mfc/reference/coblist-class.md) который хранит доступные шрифты.

### <a name="remarks"></a>Примечания

Обычно `CMFCToolBarFontComboBox` объекты хранят список доступных шрифтов в одном общем `CObList` объекте. Если вы используете вторую перегрузку конструктора и предоставляете действительный указатель *для pLstFontsExternal,* этот `CMFCToolBarFontComboBox` объект вместо этого заполнит `CObList` то, что *pLstFontsExternal* указывает на доступные шрифты.

### <a name="example"></a>Пример

В следующем примере показано, `CMFCToolBarFontComboBox` как построить объект. Этот фрагмент кода входит в состав [примера Word Pad](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]

## <a name="cmfctoolbarfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFCToolBarFontComboBox::GetFontDesc

Возвращает указатель объекту `CMFCFontInfo` для указанного индекса в комбо-коробке.

```
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;
```

### <a name="parameters"></a>Параметры

*iIndex*<br/>
(в) Определяет нулевой индекс комбо-коробки.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект `CMFCFontInfo`. Если *iIndex* не указывает действительный индекс элемента, значение возврата является НУЛЕ.

## <a name="cmfctoolbarfontcomboboxm_nfontheight"></a><a name="m_nfontheight"></a>CMFCToolBarFontComboBox::m_nFontHeight

Определяет высоту, в пикселях, символов в купели комбо-бокс, если комбо-бокс имеет стиль рисования владельца.

```
static int m_nFontHeight
```

### <a name="remarks"></a>Примечания

Если `m_nFontHeight` переменная равна 0, высота рассчитывается автоматически в соответствии с шрифтом комбо-бокса по умолчанию. Высота включает в себя как восхождение символов выше базовой линии, так и спуск символов под базовой линией.

## <a name="cmfctoolbarfontcomboboxsetfont"></a><a name="setfont"></a>CMFCToolBarFontComboBox::SetFont

Выбирает шрифт в комбо-коробке шрифта в соответствии с именем шрифта и набором символов, указанными в параметрах.

```
BOOL SetFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET,
    BOOL bExact=FALSE);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
(в) Упоняет имя шрифта или префикс.

*nCharSet*<br/>
(в) Определяет набор символов.

*bТочный*<br/>
(в) Уточняется, содержит ли *lpszName* имя шрифта или префикс шрифта.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если шрифт был выбран успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Если *bExact* является правдой, этот метод выбирает шрифт, который точно соответствует имени, которое вы указали как *lpszName*. Если *bExact* false, этот метод выбирает шрифт, который начинается с текста, указанного как *lpszName* и который использует набор символов, который вы указали как *nCharSet.* Если *nCharSet* настроен на DEFAULT_CHARSET, набор символов будет проигнорирован, и только *lpszName* будет использоваться для выбора шрифта.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton класс](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[Класс CMFCФонФоФо](../../mfc/reference/cmfcfontinfo-class.md)<br/>
[CMFCToolBar::Заменить кнопку](../../mfc/reference/cmfctoolbar-class.md#replacebutton)<br/>
[Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)
