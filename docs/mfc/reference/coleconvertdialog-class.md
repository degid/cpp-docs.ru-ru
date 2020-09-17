---
title: Класс COleConvertДиалогДиалог
ms.date: 11/04/2016
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
helpviewer_keywords:
- COleConvertDialog [MFC], COleConvertDialog
- COleConvertDialog [MFC], DoConvert
- COleConvertDialog [MFC], DoModal
- COleConvertDialog [MFC], GetClassID
- COleConvertDialog [MFC], GetDrawAspect
- COleConvertDialog [MFC], GetIconicMetafile
- COleConvertDialog [MFC], GetSelectionType
- COleConvertDialog [MFC], m_cv
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
ms.openlocfilehash: 6d6690b8d06df29ce9fcd323eb8724009ee3cca9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366169"
---
# <a name="coleconvertdialog-class"></a>Класс COleConvertДиалогДиалог

Для получения дополнительной [OLEUICONVERT](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) информации см.

## <a name="syntax"></a>Синтаксис

```
class COleConvertDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeConvertДиалог::COleConvertДиалогДиалог](#coleconvertdialog)|Формирует объект `COleConvertDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeConvertДиалог::DoПреобразование](#doconvert)|Выполняет преобразование, указанное в диалоговом поле.|
|[ColeConvertДиалог::DoModal](#domodal)|Отображает диалоговую коробку элемента изменения OLE.|
|[ColeConvertДиалог::GetClassID](#getclassid)|Получает CLSID, связанный с выбранным элементом.|
|[ColeConvertДиалог::GetDrawAspect](#getdrawaspect)|Определяет, следует ли рисовать элемент в виде значка.|
|[ColeConvertДиалог::GetIconicMetafile](#geticonicmetafile)|Получает ручку метафайла, связанную с культовой формой этого элемента.|
|[ColeConvertДиалог::GetSelectionType](#getselectiontype)|Получает выбранный тип выбора.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeConvertДиалог:::m_cv](#m_cv)|Структура, контролирующая поведение диалогового окна.|

## <a name="remarks"></a>Примечания

> [!NOTE]
> Этот класс используется с генерируемым приложением Wizard.?

Для получения дополнительной информации о OL-специфических диалоговых ящиков, [см.](../../mfc/dialog-boxes-in-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleConvertDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="coleconvertdialogcoleconvertdialog"></a><a name="coleconvertdialog"></a>ColeConvertДиалог::COleConvertДиалогДиалог

Строит только `COleConvertDialog` объект.

```
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Очки на элемент, который будет преобразован или активирован.

*dwFlags*<br/>
Флаг создания, который содержит любое количество следующих значений, объединенных с помощью bitwise-или оператора:

- CF_SELECTCONVERTTO указывает, что кнопка Convert To radio будет выбрана первоначально при вызове диалогового окна. Это значение по умолчанию.

- CF_SELECTACTIVATEAS указывает, что кнопка «Активация как радио» будет выбрана первоначально при вызове диалогового окна.

- CF_SETCONVERTDEFAULT указывает, что класс, который clSID `clsidConvertDefault` указан членом `m_cv` структуры, будет использоваться в качестве выбора по умолчанию в поле списка классов при выборе кнопки Convert To radio.

- CF_SETACTIVATEDEFAULT указывает, что класс, который clSID `clsidActivateDefault` указан членом `m_cv` структуры, будет использоваться в качестве выбора по умолчанию в поле списка классов при выборе кнопки «Активировать как радио».

- CF_SHOWHELPBUTTON указывает, что при вызове диалогового окна будет отображаться кнопка справки.

*pClassID*<br/>
Очки в CLSID элемента, который будет преобразован или активирован. Если NULL, CLSID, связанный с *pItem,* будет использоваться.

*pParentWnd*<br/>
Указывает на объект окна родителя `CWnd`или владельца (типа), к которому принадлежит объект диалога. Если это NULL, родительское окно окна диалогов устанавливается на основное окно приложения.

### <a name="remarks"></a>Примечания

Чтобы отобразить диалоговую будку, позвоните в функцию [DoModal.](#domodal)

Для получения дополнительной [информации](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) [см.](/windows/win32/com/clsid-key-hklm)

## <a name="coleconvertdialogdoconvert"></a><a name="doconvert"></a>ColeConvertДиалог::DoПреобразование

Вызов эту функцию, после успешного возвращения из [DoModal](#domodal), либо конвертировать или активировать объект типа [COleClientItem](../../mfc/reference/coleclientitem-class.md).

```
BOOL DoConvert(COleClientItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Очки на элемент, который будет преобразован или активирован. Не может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Элемент преобразуется или активируется в соответствии с информацией, выбранной пользователем в диалоговом поле Convert.

## <a name="coleconvertdialogdomodal"></a><a name="domodal"></a>ColeConvertДиалог::DoModal

Вызовите эту функцию для отображения диалогового окна OLE Convert.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если диалоговая коробка была успешно отображана.

- IDCANCEL, если пользователь отменил диалоговую будку.

- IDABORT, если произошла ошибка. Если IDABORT возвращается, позвоните в функцию [COleDialog::GetLastError,](../../mfc/reference/coledialog-class.md#getlasterror) чтобы получить больше информации о типе ошибки, которая произошла. Список возможных ошибок [OleUIConvert](/windows/win32/api/oledlg/nf-oledlg-oleuiconvertw) можно узнать в SDK Windows.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные элементы управления диалоговой коробкой, установив элементы [структуры m_cv,](#m_cv) вы должны сделать это перед вызовом, `DoModal`но после построения объекта диалога.

При `DoModal` возврате IDOK можно вызвать другие функции участника, чтобы получить настройки или информацию, вводимые пользователем в диалоговую будку.

## <a name="coleconvertdialoggetclassid"></a><a name="getclassid"></a>ColeConvertДиалог::GetClassID

Вызовите эту функцию, чтобы получить CLSID, связанный с элементом, выбранным пользователем в диалоговом окне Convert.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Возвращаемое значение

CLSID, связанный с элементом, выбранным в диалоговом окне Convert.

### <a name="remarks"></a>Примечания

Вызовите эту функцию только после того, как [DoModal](#domodal) вернет IDOK.

Для получения дополнительной информации [см. ключ CLSID](/windows/win32/com/clsid-key-hklm) в SDK Windows.

## <a name="coleconvertdialoggetdrawaspect"></a><a name="getdrawaspect"></a>ColeConvertДиалог::GetDrawAspect

Позвоните в эту функцию, чтобы определить, решил ли пользователь отобразить выбранный элемент в качестве значка.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод, необходимый для визуализации объекта.

- DVASPECT_CONTENT возвращен, если флажок Display As As Icon не был проверен.

- DVASPECT_ICON возвращена, если проверка флажка Display As As Icon.

### <a name="remarks"></a>Примечания

Вызовите эту функцию только после того, как [DoModal](#domodal) вернет IDOK.

Более подробную информацию о аспекте рисования можно узнать в структуре данных [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) в SDK Windows.

## <a name="coleconvertdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>ColeConvertДиалог::GetIconicMetafile

Вызовите эту функцию, чтобы получить ручку метафайла, который содержит знаковый аспект выбранного элемента.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к метафайлу, содержащему знаковый аспект выбранного элемента, если флажок Display As As Icon был проверен при отклонении диалога, выбрав OK; в противном случае NULL.

## <a name="coleconvertdialoggetselectiontype"></a><a name="getselectiontype"></a>ColeConvertДиалог::GetSelectionType

Вызовите эту функцию, чтобы определить тип преобразования, выбранного в диалоговом поле Convert.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип выбора сделан.

### <a name="remarks"></a>Примечания

Значения типа возврата определяются `Selection` типом перечисления, `COleConvertDialog` объявленным в классе.

```
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };
```

Краткие описания этих значений следуют:

- `COleConvertDialog::noConversion`Возвращается, если либо диалоговая будка была отменена, либо пользователь не выбрал конверсию. При `COleConvertDialog::DoModal` возврате IDOK возможно, что пользователь выбрал другой значок, чем ранее выбранный.

- `COleConvertDialog::convertItem`Возвращалась, если была проверена кнопка «Преобразование в радио», пользователь выбрал другой элемент для преобразования и `DoModal` вернул IDOK.

- `COleConvertDialog::activateAs`Возвращается, если была проверена радиокнопка «Активировать как `DoModal` радио», пользователь выбрал другой элемент для активации и вернул IDOK.

## <a name="coleconvertdialogm_cv"></a><a name="m_cv"></a>ColeConvertДиалог:::m_cv

Структура типа OLEUICONVERT используется для управления поведением диалогового окна Convert.

```
OLEUICONVERT m_cv;
```

### <a name="remarks"></a>Примечания

Члены этой структуры могут быть изменены либо непосредственно, либо через функции членов.

Для получения дополнительной [OLEUICONVERT](/windows/win32/api/oledlg/ns-oledlg-oleuiconvertw) информации см.

## <a name="see-also"></a>См. также раздел

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
