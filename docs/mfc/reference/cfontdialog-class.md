---
title: Класс CFontDialog
ms.date: 11/04/2016
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
ms.openlocfilehash: 6a8e24b68f377235c1f1e21fbcd5618aebbe299a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755016"
---
# <a name="cfontdialog-class"></a>Класс CFontDialog

Позволяет включить в приложение диалоговую коробку выбора шрифтов.

## <a name="syntax"></a>Синтаксис

```
class CFontDialog : public CCommonDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFontDialog::CFontDialog](#cfontdialog)|Формирует объект `CFontDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFontDialog::DoModal](#domodal)|Отображает диалог и позволяет пользователю сделать выбор.|
|[CFontDialog::GetCharFormat](#getcharformat)|Извлекает форматирование символа выбранного шрифта.|
|[CFontDialog::GetColor](#getcolor)|Возвращает цвет выбранного шрифта.|
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Присваивает структуре характеристики `LOGFONT` выбранного в настоящее время шрифта.|
|[CFontDialog::GetFaceName](#getfacename)|Возвращает имя лица выбранного шрифта.|
|[CFontDialog::GetSize](#getsize)|Возвращает размер точки выбранного шрифта.|
|[CFontDialog::GetStyleName](#getstylename)|Возвращает имя стиля выбранного шрифта.|
|[CFontDialog::GetWeight](#getweight)|Возвращает вес выбранного шрифта.|
|[CFontDialog::Isbold](#isbold)|Определяет, является ли шрифт смелым.|
|[CFontDialog::Italic](#isitalic)|Определяет, является ли шрифт курсивом.|
|[CFontDialog::IsStrikeout](#isstrikeout)|Определяет, отображается ли шрифт с помощью выстраиваемых.|
|[CFontDialog::IsUnderline](#isunderline)|Определяет, подчеркивается ли шрифт.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFontDialog::m_cf](#m_cf)|Структура, используемая для `CFontDialog` настройки объекта.|

## <a name="remarks"></a>Примечания

Объект `CFontDialog` представляет собой диалоговую коробку со списком шрифтов, которые в настоящее время установлены в системе. Пользователь может выбрать определенный шрифт из списка, и этот выбор затем сообщается обратно в приложение.

Чтобы построить объект, используйте предоставленный `CFontDialog` конструктор или получите новый подкласс и используйте свой собственный пользовательский конструктор.

После `CFontDialog` построения объекта можно использовать `m_cf` структуру для инициализации значений или состояний элементов управления в диалоговом поле. [Структура m_cf](#m_cf) типа [CHOOSEFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw). Для получения дополнительной информации об этой структуре см.

После инициализации элементов управления `DoModal` диалогов позвоните функции участника для отображения диалогового окна и позвольте пользователю выбрать шрифт. `DoModal`возвращает сярот, выбрал ли пользователь кнопку OK (IDOK) или «Отменить» (IDCANCEL).

При `DoModal` возврате IDOK можно `CFontDialog`использовать одну из функций участника для получения информации, вводимых пользователем.

Вы можете использовать функцию Windows [CommDlgExtendedError,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) чтобы определить, произошла ли ошибка во время инициализации диалогового окна, и узнать больше об ошибке. Для получения дополнительной информации об этой функции, см.

`CFontDialog`опирается на COMMDLG. DLL файл, который поставляется с версиями Windows 3.1 и позже.

Чтобы настроить диалоговое окно, вывежьте класс из, `CFontDialog`предоставьте пользовательский шаблон диалогов и добавьте карту сообщений для обработки сообщений уведомлений из расширенных элементов управления. Любые необработанные сообщения должны передаваться базовому классу.

Настройка функции крючка не требуется.

Для получения дополнительной `CFontDialog`информации об использовании см. [Common Dialog Classes](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxdlgs.h

## <a name="cfontdialogcfontdialog"></a><a name="cfontdialog"></a>CFontDialog::CFontDialog

Формирует объект `CFontDialog`.

```
CFontDialog(
    LPLOGFONT lplfInitial = NULL,
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,
    DWORD dwFlags = CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*plfПервоначальный*<br/>
Указатель на структуру данных [LOGFONT,](/windows/win32/api/wingdi/ns-wingdi-logfontw) которая позволяет установить некоторые характеристики шрифта.

*charFormat*<br/>
Указатель на структуру данных [CHARFORMAT,](/windows/win32/api/richedit/ns-richedit-charformata) которая позволяет установить некоторые характеристики шрифта в богатом элементауправления правки.

*dwFlags*<br/>
Указывает один или несколько флагов выбора шрифта. Одно или несколько предустановленных значений можно объединить с помощью побитового оператора OR. Если вы изменяете член структуры `m_cf.Flag`, используйте оператор OR в изменениях, чтобы сохранить поведение по умолчанию. Подробнее о каждом из этих флагов можно узнать в описании структуры [CHOOSEFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw) в SDK Windows.

*pdcPrinter*<br/>
Указатель на контекст принтера. Если этот параметр задан, он указывает на контекст принтера, для которого выбираются шрифты.

*pParentWnd*<br/>
Указатель на родительское окно или окно владельца диалогового окна шрифта.

### <a name="remarks"></a>Примечания

Обратите внимание, что конструктор автоматически заполняет члены структуры `CHOOSEFONT`. Их следует изменять, только если вам требуется диалоговое окно, отличное от стандартного.

> [!NOTE]
> Первая версия этой функции существует, только если элементы управления форматированным редактированием не поддерживаются.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]

## <a name="cfontdialogdomodal"></a><a name="domodal"></a>CFontDialog::DoModal

Вызовите эту функцию для отображения общего окна диалога шрифта Windows и позвольте пользователю выбрать шрифт.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

IDOK или IDCANCEL. Если IDCANCEL возвращается, позвоните в функцию Windows [CommDlgExtendedError,](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) чтобы определить, произошла ли ошибка.

IDOK и IDCANCEL являются константами, указывающими на то, выбрал ли пользователь кнопку OK или Cancel.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные элементы [m_cf](#m_cf) управления диалогом шрифтов, `DoModal`установив элементы m_cf структуры, вы должны сделать это перед вызовом, но после построения объекта диалога.

При `DoModal` возврате IDOK можно вызвать другие функции участника, чтобы получить настройки или ввод информации пользователем в диалоговую будку.

### <a name="example"></a>Пример

  Смотрите примеры [для CFontDialog::CFontDialog](#cfontdialog) и [CFontDialog::GetColor](#getcolor).

## <a name="cfontdialoggetcharformat"></a><a name="getcharformat"></a>CFontDialog::GetCharFormat

Извлекает форматирование символа выбранного шрифта.

```cpp
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Структура [CHARFORMAT,](/windows/win32/api/richedit/ns-richedit-charformata) содержащая информацию о форматировании символов выбранного шрифта.

## <a name="cfontdialoggetcolor"></a><a name="getcolor"></a>CFontDialog::GetColor

Вызовите эту функцию, чтобы получить выбранный цвет шрифта.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет выбранного шрифта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

## <a name="cfontdialoggetcurrentfont"></a><a name="getcurrentfont"></a>CFontDialog::GetCurrentFont

Назовите эту функцию, чтобы назначить характеристики выбранного в настоящее время шрифта членам структуры [LOGFONT.](/windows/win32/api/wingdi/ns-wingdi-logfontw)

```cpp
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>Параметры

*lplf*<br/>
Указатель на `LOGFONT` структуру.

### <a name="remarks"></a>Примечания

Другие `CFontDialog` функции члена предоставляются для доступа к индивидуальным характеристикам текущего шрифта.

Если эта функция вызывается во время вызова [DoModal,](#domodal)она возвращает текущий выбор в то время (то, что пользователь видит или изменил в диалоге). Если эта функция вызывается `DoModal` после вызова `DoModal` (только при возврате IDOK), она возвращает то, что пользователь фактически выбрал.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

## <a name="cfontdialoggetfacename"></a><a name="getfacename"></a>CFontDialog::GetFaceName

Вызовите эту функцию, чтобы получить имя лица выбранного шрифта.

```
CString GetFaceName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Лицо шрифта, выбранное `CFontDialog` в диалоговом окне.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

## <a name="cfontdialoggetsize"></a><a name="getsize"></a>CFontDialog::GetSize

Вызовите эту функцию, чтобы получить размер выбранного шрифта.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер шрифта, в десятых числах точки.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

## <a name="cfontdialoggetstylename"></a><a name="getstylename"></a>CFontDialog::GetStyleName

Вызовите эту функцию, чтобы получить имя стиля выбранного шрифта.

```
CString GetStyleName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название стиля шрифта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

## <a name="cfontdialoggetweight"></a><a name="getweight"></a>CFontDialog::GetWeight

Вызовите эту функцию, чтобы получить вес выбранного шрифта.

```
int GetWeight() const;
```

### <a name="return-value"></a>Возвращаемое значение

Вес выбранного шрифта.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации о весе шрифта, см. [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

## <a name="cfontdialogisbold"></a><a name="isbold"></a>CFontDialog::Isbold

Вызовите эту функцию, чтобы определить, является ли выбранный шрифт смелым.

```
BOOL IsBold() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если выбранный шрифт имеет смелую характеристику включена; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

## <a name="cfontdialogisitalic"></a><a name="isitalic"></a>CFontDialog::Italic

Вызовите эту функцию, чтобы определить, является ли выбранный шрифт курсивом.

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если выбранный шрифт имеет характеристику курсивом включен; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

## <a name="cfontdialogisstrikeout"></a><a name="isstrikeout"></a>CFontDialog::IsStrikeout

Вызовите эту функцию, чтобы определить, отображается ли выбранный шрифт с помощью выстраивательных ударов.

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если выбранный шрифт имеет характеристику Strikeout включен; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

## <a name="cfontdialogisunderline"></a><a name="isunderline"></a>CFontDialog::IsUnderline

Вызовите эту функцию, чтобы определить, выделен ли выбранный шрифт.

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если выбранный шрифт имеет характеристику Underline; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

## <a name="cfontdialogm_cf"></a><a name="m_cf"></a>CFontDialog::m_cf

Структура, члены которой хранят характеристики объекта диалога.

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>Примечания

После построения `CFontDialog` объекта можно `m_cf` использовать для изменения различных аспектов `DoModal` диалогового окна перед вызовом функции участника. Более подробную информацию об этой структуре [можно](/windows/win32/api/commdlg/ns-commdlg-choosefontw) узнать в SDK windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс CCommonДиалог](../../mfc/reference/ccommondialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
