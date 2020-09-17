---
title: Класс CMFCKeyMapDialog
ms.date: 11/04/2016
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
ms.openlocfilehash: 22aa006ce214ca720192bb761e2ff2b35a64fce3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374414"
---
# <a name="cmfckeymapdialog-class"></a>Класс CMFCKeyMapDialog

Класс `CMFCKeyMapDialog` поддерживает элемент управления, который отображает команды к клавишам на клавиатуре.

## <a name="syntax"></a>Синтаксис

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCKeyMapДиалогог::CMFCKeyMapDialog](#cmfckeymapdialog)|Формирует объект `CMFCKeyMapDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCKeyMapDialog::DoModal](#domodal)|Отображает клавиатуру отображение диалогового окна.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMFCKeyMapДиалого::FormatItem](#formatitem)|Вызывается инфраструктурой для создания строки, описывающая ключевое отображение. По умолчанию строка содержит имя команды, используемые клавиши ярлыка и описание ключа ярлыка.|
|[CMFCKeyMapДиалого::GetCommandKeys](#getcommandkeys)|Извлекает строку, содержащую список ключей с коротким срезом, связанных с указанной командой.|
|[CMFCKeyMapDialog::OninsertItem](#oninsertitem)|Вызывается фреймворком перед вставкой нового элемента во внутренний элемент управления списком, который поддерживает элемент отображения клавиатуры.|
|[CMFCKeyMapДиалог::OnPrintHeader](#onprintheader)|Вызывается рамки для печати заголовка для клавиатуры карты на новой странице.|
|[CMFCKeyMapDialog::OnprintItem](#onprintitem)|Вызывается по фреймворку для печати элемента отображения клавиатуры.|
|[CMFCKeyMapДиалого::OnSetКолонки](#onsetcolumns)|Вызывается фректов для установки подписей для столбцов во внутреннем управлении списком, который поддерживает элемент управления отображением клавиатуры.|
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|Вызывается по системе, когда пользователь нажимает кнопку **Печати.**|
|[CMFCKeyMapДиалог::SetColumnsШирин](#setcolumnswidth)|Вызывается фреймворк, чтобы установить ширину столбцов во внутреннем управлении списком, который поддерживает элемент управления отображением клавиатуры.|

## <a name="remarks"></a>Примечания

Используйте `CMFCKeyMapDialog` класс для реализации многоразового клавиатурного картографируного диалогового окна. В диалоговом поле используется элемент управления представлением списка для отображения ярлыков клавиш и связанных с ними команд.

Чтобы использовать `CMFCKeyMapDialog` класс в приложении, передайте указатель на окно основной рамы в качестве параметра `CMFCKeyMapDialog` для конструктора. Затем позвоните в `DoModal` метод, чтобы запустить модальный диалоговый ящик.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxkeymapdialog.h

## <a name="cmfckeymapdialogcmfckeymapdialog"></a><a name="cmfckeymapdialog"></a>CMFCKeyMapДиалогог::CMFCKeyMapDialog

Формирует объект `CMFCKeyMapDialog`.

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>Параметры

*pWndParentFrame*<br/>
(в) Указатель на родительское окно `CMFCKeyMapDialog` объекта.

*bEnablePrint*<br/>
(в) ПРАВДА, если список клавиш акселератора могут быть напечатаны; в противном случае, FALSE. Значение по умолчанию — FALSE.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

В следующем примере показано, как `CMFCKeyMapDialog` построить объект класса. Этот пример является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

## <a name="cmfckeymapdialogdomodal"></a><a name="domodal"></a>CMFCKeyMapDialog::DoModal

Отображает клавиатуру отображение диалогового окна.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Подписанный целый ряд, такой как IDOK или IDCANCEL, который передается методу [CDialog::EndDialog.](../../mfc/reference/cdialog-class.md#enddialog) Метод, в свою очередь, закрывает диалоговую будку. Для получения дополнительной информации, [см. CDialog: :DoModal](../../mfc/reference/cdialog-class.md#domodal).

### <a name="remarks"></a>Примечания

Клавиатура отображение диалоговая коробка позволяет выбрать и назначить клавиши ускорителя для различных категорий команд. Кроме того, вы можете скопировать выбранные клавиши ускорителя и их описание на буфер обмена.

## <a name="cmfckeymapdialogformatitem"></a><a name="formatitem"></a>CMFCKeyMapДиалого::FormatItem

Вызывается инфраструктурой для создания строки, описывающая ключевое отображение. По умолчанию строка содержит имя команды, используемые клавиши ярлыка и описание ключа ярлыка.

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>Параметры

*nItem*<br/>
(в) Индекс элемента с нулевым уровнем в внутреннем списке ключевых карт.

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` содержащий отформатированный текст элемента.

### <a name="remarks"></a>Примечания

## <a name="cmfckeymapdialoggetcommandkeys"></a><a name="getcommandkeys"></a>CMFCKeyMapДиалого::GetCommandKeys

Извлекает значение строки. Строка содержит список ключей с коротким срезом, которые связаны с указанной командой.

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>Параметры

*uiCmdID*<br/>
(в) Идентификатор команды.

### <a name="return-value"></a>Возвращаемое значение

Список ключей с коротким срезом, связанный с указанной командой, имеет список ключей с коротким срезом.

### <a name="remarks"></a>Примечания

## <a name="cmfckeymapdialogoninsertitem"></a><a name="oninsertitem"></a>CMFCKeyMapDialog::OninsertItem

Вызывается фреймворком перед вставкой нового элемента во внутренний элемент управления списком, который поддерживает элемент отображения клавиатуры.

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>Параметры

*pButton*<br/>
(в) Указатель на кнопку панели инструментов, которая используется для отображения комбинации ключей клавиатуры с именем и описанием команды. Элемент карты ключа хранится во внутреннем элементе управления списком.

*nItem*<br/>
(в) Индекс с нулевым уровнем, который определяет, где вставить новый элемент карты ключа во внутренний элемент управления списком.

### <a name="remarks"></a>Примечания

## <a name="cmfckeymapdialogonprintheader"></a><a name="onprintheader"></a>CMFCKeyMapДиалог::OnPrintHeader

Вызывается рамки для печати заголовка для клавиатуры карты на новой странице.

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>Параметры

*Dc*<br/>
(в) Контекст устройства для принтера.

*nСтраница*<br/>
(в) Номер страницы для печати.

*Cx*<br/>
(в) Горизонтальное смещение заголовка, в пикселях.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха, высота печатного текста. Для получения дополнительной информации [:D](../../mfc/reference/cdc-class.md#drawtext)см.

### <a name="remarks"></a>Примечания

Платформа использует этот метод для печати клавиатурной карты. По умолчанию этот метод печатает номер страницы, имя приложения и название диалогового окна.

## <a name="cmfckeymapdialogonprintitem"></a><a name="onprintitem"></a>CMFCKeyMapDialog::OnprintItem

Вызывается по фреймворку для печати элемента отображения клавиатуры.

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>Параметры

*Dc*<br/>
(в) Контекст устройства принтера.

*nItem*<br/>
(в) Индекс нулевой основе элемента для печати.

*Y*<br/>
(в) Вертикальное смещение между верхней частью страницы и положением элемента.

*Cx*<br/>
(в) Горизонтальное смещение между левой частью страницы и положением элемента.

*bCalcHeight*<br/>
(в) TRUE для расчета наилучшей высоты для элемента печати; FALSE усеченный элемент печати так, чтобы он соответствовал пространству по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Высота печатного элемента.

### <a name="remarks"></a>Примечания

Платформа называет этот метод для печати элемента ключа карты диалогового окна. По умолчанию этот метод печатает имя команды элемента, клавиши ярлыка и описание команды.

## <a name="cmfckeymapdialogonsetcolumns"></a><a name="onsetcolumns"></a>CMFCKeyMapДиалого::OnSetКолонки

Вызывается фректов для установки подписей для столбцов во внутреннем управлении списком, который поддерживает элемент управления отображением клавиатуры.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Примечания

По умолчанию этот метод получает подписи для столбцов из трех ресурсов. Подпись к заголовку «Команда» — от IDS_AFXBARRES_COMMAND, подпись ключевой колонки — от IDS_AFXBARRES_KEYS, а подпись столбца описания — от IDS_AFXBARRES_DESCRIPTION.

## <a name="cmfckeymapdialogprintkeymap"></a><a name="printkeymap"></a>CMFCKeyMapDialog::PrintKeyMap

Вызывается по системе, когда пользователь нажимает кнопку **Печати.**

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>Примечания

Метод `PrintKeyMap` печатает карту ключа. Он инициирует новое задание печати, а затем неоднократно вызывает [CMFCKeyMapDialog::OnPrintHeader](#onprintheader) и [CMFCKeyMapDialog::OnPrintItem](#onprintitem) методы до тех пор, пока все ключевые отображения не будут напечатаны.

## <a name="cmfckeymapdialogsetcolumnswidth"></a><a name="setcolumnswidth"></a>CMFCKeyMapДиалог::SetColumnsШирин

Вызывается фреймворк, чтобы установить ширину столбцов во внутреннем управлении списком, который поддерживает элемент управления отображением клавиатуры.

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>Примечания

Этот метод устанавливает столбцы управления внутреннего списка на ширину по умолчанию. Сначала рассчитывается ширина столбца клавиш ярлыка. Затем одна треть оставшейся ширины выделяется на столбец команды, а остальные две трети — в столбец описания.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)
