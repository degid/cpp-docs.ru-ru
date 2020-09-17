---
title: Класс CMFCFontComboBox
ms.date: 11/04/2016
f1_keywords:
- CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::CMFCFontComboBox
- AFXFONTCOMBOBOX/CMFCFontComboBox::GetSelFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::SelectFont
- AFXFONTCOMBOBOX/CMFCFontComboBox::Setup
- AFXFONTCOMBOBOX/CMFCFontComboBox::m_bDrawUsingFont
helpviewer_keywords:
- CMFCFontComboBox [MFC], CMFCFontComboBox
- CMFCFontComboBox [MFC], GetSelFont
- CMFCFontComboBox [MFC], SelectFont
- CMFCFontComboBox [MFC], Setup
- CMFCFontComboBox [MFC], m_bDrawUsingFont
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
ms.openlocfilehash: 60b4b7cdfdace2332de35dd93c43eacf592e99e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367491"
---
# <a name="cmfcfontcombobox-class"></a>Класс CMFCFontComboBox

Класс `CMFCFontComboBox` создает управление комбо-коробкой, содержащее список шрифтов.

## <a name="syntax"></a>Синтаксис

```
class CMFCFontComboBox : public CComboBox
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCFontComboBox::CMFCFontComboBox](#cmfcfontcombobox)|Формирует объект `CMFCFontComboBox`.|
|`CMFCFontComboBox::~CMFCFontComboBox`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|`CMFCFontComboBox::CompareItem`|Вызывается фреймворком для определения относительного положения нового элемента в отсортированном поле списка текущего управления комбо-коробкой шрифта. (Переопределяет [CComboBox::CompareItem](../../mfc/reference/ccombobox-class.md#compareitem).)|
|`CMFCFontComboBox::DrawItem`|Вызывается фреймворком, чтобы нарисовать указанный элемент в текущем управлении комбо-коробкой шрифта. (Перекрывает [CComboBox::DrawItem](../../mfc/reference/ccombobox-class.md#drawitem).)|
|[CMFCFontComboBox::GetSelFont](#getselfont)|Извлекает информацию о выбранном в настоящее время шрифте.|
|`CMFCFontComboBox::MeasureItem`|Вызывается рамки для информирования Windows о размерах списка поле в текущем шрифта комбо-бокс управления. (Переопределяет [CComboBox::MeasureItem](../../mfc/reference/ccombobox-class.md#measureitem).)|
|`CMFCFontComboBox::PreTranslateMessage`|Переводит оконные сообщения перед отправкой на функции [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) и [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows. (Переопределяет [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCFontComboBox::SelectFont](#selectfont)|Выберите шрифт, который соответствует указанным критериям из комбо-коробки шрифта.|
|[CMFCFontComboBox::Настройка](#setup)|Инициализирует список элементов в комбо-коробке шрифта.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCFontComboBox::m_bDrawUsingFont](#m_bdrawusingfont)|Указывает на рамки, какие шрифты использовать для рисования меток элемента в текущей комбо-коробке шрифта.|

## <a name="remarks"></a>Примечания

Чтобы использовать `CMFCFontComboBox` объект в диалоговом `CMFCFontComboBox` поле, добавьте переменную в класс диалогового окна. Затем в `OnInitDialog` методе класса диалогового окна позвоните в [CMFCFontComboBox::Setup](#setup) метод для инициализации списка элементов в управлении комбо-боксом.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CComboBox](../../mfc/reference/ccombobox-class.md)

[CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxfontcombobox.h

## <a name="cmfcfontcomboboxcmfcfontcombobox"></a><a name="cmfcfontcombobox"></a>CMFCFontComboBox::CMFCFontComboBox

Формирует объект `CMFCFontComboBox`.

```
CMFCFontComboBox();
```

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcfontcomboboxgetselfont"></a><a name="getselfont"></a>CMFCFontComboBox::GetSelFont

Извлекает информацию о выбранном в настоящее время шрифте.

```
CMFCFontInfo* GetSelFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [класса CMFCFontInfo,](../../mfc/reference/cmfcfontinfo-class.md) описывающий шрифт. Он может быть NULL, если шрифт не выбран в комбо-коробке.

### <a name="remarks"></a>Примечания

## <a name="cmfcfontcomboboxm_bdrawusingfont"></a><a name="m_bdrawusingfont"></a>CMFCFontComboBox::m_bDrawUsingFont

Указывает на рамки, какие шрифты использовать для рисования меток элемента в текущей комбо-коробке шрифта.

```
static BOOL m_bDrawUsingFont;
```

### <a name="remarks"></a>Примечания

Установите этот элемент к TRUE, чтобы направить фреймворк использовать тот же шрифт для рисования этикетки каждого элемента. Установите этот элемент false, чтобы направить фреймворк, чтобы нарисовать каждую метку элемента с шрифтом, имя которого совпадает с меткой. Значение этого участника по умолчанию FALSE.

## <a name="cmfcfontcomboboxselectfont"></a><a name="selectfont"></a>CMFCFontComboBox::SelectFont

Выберите шрифт, который соответствует указанным критериям из комбо-коробки шрифта.

```
BOOL SelectFont(CMFCFontInfo* pDesc);

BOOL SelectFont(
    LPCTSTR lpszName,
    BYTE nCharSet=DEFAULT_CHARSET);
```

### <a name="parameters"></a>Параметры

*pDesc*<br/>
(в) Указывает на объект описания шрифта.

*lpszName*<br/>
(в) Упогоняет имя шрифта.

*nCharSet*<br/>
(в) Определяет набор символов. Значение по умолчанию является DEFAULT_CHARSET. Для получения дополнительной `lfCharSet` [информации](/windows/win32/api/wingdi/ns-wingdi-logfontw) см.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если элемент в комбо-коробке шрифта соответствует указанному объекту описания шрифта или имени шрифта и символу; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Используйте этот метод, чтобы выбрать и прокрутить к элементу в комбо-коробке шрифта, которая соответствует указанному шрифту.

### <a name="example"></a>Пример

В следующем примере показано, `SelectFont` как `CMFCFontComboBox` использовать метод в классе. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#35](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_2.cpp)]

## <a name="cmfcfontcomboboxsetup"></a><a name="setup"></a>CMFCFontComboBox::Настройка

Инициализирует список элементов в комбо-коробке шрифта.

```
BOOL Setup(
    int nFontType=DEVICE_FONTTYPE|RASTER_FONTTYPE|TRUETYPE_FONTTYPE,
    BYTE nCharSet=DEFAULT_CHARSET,
    BYTE nPitchAndFamily=DEFAULT_PITCH);
```

### <a name="parameters"></a>Параметры

*nФонТип*<br/>
(в) Определяет тип шрифта. Значение по умолчанию — это битная комбинация (ИЛИ) DEVICE_FONTTYPE, RASTER_FONTTYPE и TRUETYPE_FONTTYPE.

*nCharSet*<br/>
(в) Определяет набор символов шрифта. Значение по умолчанию является DEFAULT_CHARSET.

*nPitchAndFamily*<br/>
(в) Определяет поле шрифта и семью. Значение по умолчанию является DEFAULT_PITCH.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если шрифт комбо поле было инициализировано успешно; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Этот метод инициализирует комбо-коробку шрифта, перечисляя установленные в настоящее время шрифты, которые соответствуют указанным параметрам, и вставляя эти имена шрифтов в комбо-коробке шрифта.

### <a name="example"></a>Пример

В следующем примере показано, `Setup` как `CMFCFontComboBox` использовать метод в классе. Этот пример является частью [образца новых элементов управления.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_NewControls#34](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#36](../../mfc/reference/codesnippet/cpp/cmfcfontcombobox-class_3.cpp)]

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CmFCToolBarFontComboBox класс](../../mfc/reference/cmfctoolbarfontcombobox-class.md)<br/>
[Класс CMFCФонФоФо](../../mfc/reference/cmfcfontinfo-class.md)
