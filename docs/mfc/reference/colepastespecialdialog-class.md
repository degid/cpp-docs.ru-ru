---
title: ColePasteSpecialДиалог класса
ms.date: 11/04/2016
f1_keywords:
- COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::COlePasteSpecialDialog
- AFXODLGS/COlePasteSpecialDialog::AddFormat
- AFXODLGS/COlePasteSpecialDialog::AddLinkEntry
- AFXODLGS/COlePasteSpecialDialog::AddStandardFormats
- AFXODLGS/COlePasteSpecialDialog::CreateItem
- AFXODLGS/COlePasteSpecialDialog::DoModal
- AFXODLGS/COlePasteSpecialDialog::GetDrawAspect
- AFXODLGS/COlePasteSpecialDialog::GetIconicMetafile
- AFXODLGS/COlePasteSpecialDialog::GetPasteIndex
- AFXODLGS/COlePasteSpecialDialog::GetSelectionType
- AFXODLGS/COlePasteSpecialDialog::m_ps
helpviewer_keywords:
- COlePasteSpecialDialog [MFC], COlePasteSpecialDialog
- COlePasteSpecialDialog [MFC], AddFormat
- COlePasteSpecialDialog [MFC], AddLinkEntry
- COlePasteSpecialDialog [MFC], AddStandardFormats
- COlePasteSpecialDialog [MFC], CreateItem
- COlePasteSpecialDialog [MFC], DoModal
- COlePasteSpecialDialog [MFC], GetDrawAspect
- COlePasteSpecialDialog [MFC], GetIconicMetafile
- COlePasteSpecialDialog [MFC], GetPasteIndex
- COlePasteSpecialDialog [MFC], GetSelectionType
- COlePasteSpecialDialog [MFC], m_ps
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
ms.openlocfilehash: 47fb421ef9dedcae7f92d33f55988dbbc2ea452d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753825"
---
# <a name="colepastespecialdialog-class"></a>ColePasteSpecialДиалог класса

Используется для диалогового окна OLE "Вставить специальный объект".

## <a name="syntax"></a>Синтаксис

```
class COlePasteSpecialDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Формирует объект `COlePasteSpecialDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColePasteSpecialDialog:AddFormat](#addformat)|Добавляет пользовательские форматы в список форматов, которые может вставить приложение.|
|[ColePasteSpecialDialog:AddLinkEntry](#addlinkentry)|Добавляет новую запись в список поддерживаемых форматов Clipboard.|
|[ColePasteSpecialDialog:AddStandardFormats](#addstandardformats)|Добавляет CF_BITMAP, CF_DIB, CF_METAFILEPICT и опционно CF_LINKSOURCE в список форматов, которые может вставить приложение.|
|[ColePasteSpecialDialog::CreateItem](#createitem)|Создает элемент в контейнерном документе с использованием указанного формата.|
|[ColePasteSpecialDialog::DoModal](#domodal)|Отображает ole Паста Специальный диалоговый ящик.|
|[ColePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Сообщает, рисовать элемент как значок или нет.|
|[ColePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Получает ручку метафайла, связанную с культовой формой этого элемента.|
|[ColePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Получает индекс доступных вариантов вставки, который был выбран пользователем.|
|[ColePasteSpecialDialog::GetSelectionType](#getselectiontype)|Получает выбранный тип выбора.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COlePasteSpecialDialog::m_ps](#m_ps)|Структура типа OLEUIPASTESPECIAL, которая контролирует функцию диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект `COlePasteSpecialDialog` класса, когда вы хотите вызвать этот диалоговый ящик. После `COlePasteSpecialDialog` построения объекта можно использовать функции участника [AddFormat](#addformat) и [AddStandardFormats](#addstandardformats) для добавления форматов Clipboard в диалоговое окно. Можно также использовать [структуру m_ps](#m_ps) для инициализации значений или состояний элементов управления в диалоговом поле. Структура `m_ps` типа OLEUIPASTESPECIAL.

Для получения дополнительной [информации, см OLEUIPASTESPECIAL](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) структуры в Windows SDK.

Для получения дополнительной информации о OLE конкретных диалоговых коробок, [см.](../../mfc/dialog-boxes-in-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COlePasteSpecialDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="colepastespecialdialogaddformat"></a><a name="addformat"></a>ColePasteSpecialDialog:AddFormat

Вызовите эту функцию, чтобы добавить новые форматы в список форматов, которые ваше приложение может поддерживать в операции Paste Special.

```cpp
void AddFormat(
    const FORMATETC& formatEtc,
    LPTSTR lpszFormat,
    LPTSTR lpszResult,
    DWORD flags);

void AddFormat(
    UINT cf,
    DWORD tymed,
    UINT nFormatID,
    BOOL bEnableIcon,
    BOOL bLink);
```

### <a name="parameters"></a>Параметры

*Fmt*<br/>
Ссылка на тип данных для добавления.

*lpszФормат*<br/>
Строка, описывающая формат пользователю.

*lpszResult*<br/>
Строка, описывающая результат, если этот формат выбран в диалоговом поле.

*flags*<br/>
Различные варианты ссылок и встраивания, доступные для этого формата. Этот флаг представляет собой необоснованную комбинацию одного или нескольких различных значений в перечисленном типе OLEUIPASTEFLAG.

*CF*<br/>
Формат буфера обмена для добавления.

*таймед*<br/>
Типы носителей, доступных в этом формате. Это незначительное сочетание одного или нескольких значений в перечисленном типе TYMED.

*nФорматид*<br/>
Идентификатор строки, идентифицирует этот формат. Формат этой строки состоит из двух отдельных строк, разделенных символом 'n'. Первая строка такая же, как и в параметре *lpstrFormat,* а вторая такая же, как параметр *lpstrResult.*

*bEnableIcon*<br/>
Пометить, который определяет, включен ли флажок Display As Icon при выборе этого формата в поле списка.

*Мигать*<br/>
Пометить, который определяет, включена ли радиокнопка Paste Link при выборе этого формата в поле списка.

### <a name="remarks"></a>Примечания

Эту функцию можно назвать для добавления либо стандартных форматов, таких как CF_TEXT или CF_TIFF, либо пользовательских форматов, зарегистрированных в вашем приложении в системе. Для получения дополнительной информации о вставке [Data Objects and Data Sources: Manipulation](../../mfc/data-objects-and-data-sources-manipulation.md)объектов данных в приложение см.

Для получения дополнительной информации смотрите тип перечисления [TYMED](/windows/win32/api/objidl/ne-objidl-tymed) и структуру [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) в SDK Windows.

Для получения дополнительной [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) информации в SDK см.

## <a name="colepastespecialdialogaddlinkentry"></a><a name="addlinkentry"></a>ColePasteSpecialDialog:AddLinkEntry

Добавляет новую запись в список поддерживаемых форматов Clipboard.

```
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
Формат буфера обмена для добавления.

### <a name="return-value"></a>Возвращаемое значение

Структура [OLEUIPASTEFLAG,](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) содержащая информацию для новой ссылки.

## <a name="colepastespecialdialogaddstandardformats"></a><a name="addstandardformats"></a>ColePasteSpecialDialog:AddStandardFormats

Вызовите эту функцию, чтобы добавить следующие форматы Clipboard в список форматов, которые ваше приложение может поддерживать в операции Paste Special:

```cpp
void AddStandardFormats(BOOL bEnableLink = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnableLink*<br/>
Пометить, который определяет, следует ли добавлять CF_LINKSOURCE в список форматов, которые может вставить приложение.

### <a name="remarks"></a>Примечания

- CF_BITMAP

- CF_DIB

- CF_METAFILEPICT

- **"Встроенный объект"**

- (по желанию) **"Источник связи"**

Эти форматы используются для поддержки встраивания и ссылок.

## <a name="colepastespecialdialogcolepastespecialdialog"></a><a name="colepastespecialdialog"></a>ColePasteSpecialDialog::COlePasteSpecialDialog

Формирует объект `COlePasteSpecialDialog`.

```
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,
    COleDataObject* pDataObject = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаг создания, содержит любое количество следующих флагов, объединенных с помощью оператора bitwise-OR:

- PSF_SELECTPASTE указывает, что кнопка радио пасты будет проверена первоначально, когда диалоговая коробка называется. Нельзя использовать в сочетании с PSF_SELECTPASTELINK. Это значение по умолчанию.

- PSF_SELECTPASTELINK указывает, что кнопка радио "Вставка ссылка" будет проверена на начальном этапе, когда диалоговая коробка называется. Нельзя использовать в сочетании с PSF_SELECTPASTE.

- PSF_CHECKDISPLAYASICON указывает, что флажок Display As As Icon будет первоначально проверен, когда будет вызываться диалоговая коробка.

- PSF_SHOWHELP указывает, что при вызове диалогового окна будет отображаться кнопка справки.

*pDataObject*<br/>
Указывает на [COleDataObject](../../mfc/reference/coledataobject-class.md) для вставки. Если это значение NULL, `COleDataObject` оно получает от Clipboard.

*pParentWnd*<br/>
Указывает на объект окна родителя `CWnd`или владельца (типа), к которому принадлежит объект диалога. Если это NULL, родительское окно окна диалогов устанавливается на основное окно приложения.

### <a name="remarks"></a>Примечания

Эта функция только `COlePasteSpecialDialog` строит объект. Чтобы отобразить диалоговую будку, позвоните в функцию [DoModal.](#domodal)

Для получения дополнительной [OLEUIPASTEFLAG](/windows/win32/api/oledlg/ne-oledlg-oleuipasteflag) информации в SDK см.

## <a name="colepastespecialdialogcreateitem"></a><a name="createitem"></a>ColePasteSpecialDialog::CreateItem

Создает новый элемент, который был выбран в папке «Специальный диалог».

```
BOOL CreateItem(COleClientItem* pNewItem);
```

### <a name="parameters"></a>Параметры

*pNewItem*<br/>
Указывает на `COleClientItem` экземпляр. Не может быть NULL.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент был создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция должна вызываться только после того, как [DoModal](#domodal) вернет IDOK.

## <a name="colepastespecialdialogdomodal"></a><a name="domodal"></a>ColePasteSpecialDialog::DoModal

Отображает ole Паста Специальный диалоговый ящик.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если диалоговая коробка была успешно отображана.

- IDCANCEL, если пользователь отменил диалоговую будку.

- IDABORT, если произошла ошибка. Если IDABORT возвращается, `COleDialog::GetLastError` позвоните функции участника, чтобы получить больше информации о типе ошибки, которая произошла. Список возможных ошибок [OleUIPasteSpecial](/windows/win32/api/oledlg/nf-oledlg-oleuipastespecialw) можно узнать в SDK Windows.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные элементы управления диалоговой коробкой, установив элементы [структуры m_ps,](#m_ps) вы должны сделать это перед вызовом, `DoModal`но после построения объекта диалога.

При `DoModal` возврате IDOK можно вызвать другие функции участника, чтобы получить настройки или ввод информации пользователем в диалоговую будку.

## <a name="colepastespecialdialoggetdrawaspect"></a><a name="getdrawaspect"></a>ColePasteSpecialDialog::GetDrawAspect

Определяет, решил ли пользователь отобразить выбранный элемент в качестве значка.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод, необходимый для визуализации объекта.

- DVASPECT_CONTENT возвращен, если флажок Display As Icon не был проверен при отклонении диалогового окна.

- DVASPECT_ICON возвращен, если флажок Display As Icon был проверен при отклонении диалогового окна.

### <a name="remarks"></a>Примечания

Вызов этой функции только после того, как [DoModal](#domodal) возвращает IDOK.

Более подробную информацию о чертежном аспекте можно осваивать в структуре [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) в SDK Windows.

## <a name="colepastespecialdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>ColePasteSpecialDialog::GetIconicMetafile

Получает метафайл, связанный с элементом, выбранным пользователем.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к метафайлу, содержащему знаковый аспект выбранного элемента, если флажок Display As As Icon был выбран, когда диалоговое поле было отклонено, выбрав **OK;** в противном случае NULL.

## <a name="colepastespecialdialoggetpasteindex"></a><a name="getpasteindex"></a>ColePasteSpecialDialog::GetPasteIndex

Получает значение индекса, связанное с выбранной пользователем записью.

```
int GetPasteIndex() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс в массив `OLEUIPASTEENTRY` структур, выбранный пользователем. Формат, соответствующий выбранного индексу, следует использовать при выполнении операции пасты.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, см [OLEUIPASTEENTRY](/windows/win32/api/oledlg/ns-oledlg-oleuipasteentryw) структуры в Windows SDK.

## <a name="colepastespecialdialoggetselectiontype"></a><a name="getselectiontype"></a>ColePasteSpecialDialog::GetSelectionType

Определяет тип выбора, сделанный пользователем.

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает тип выбора сделал.

### <a name="remarks"></a>Примечания

Значения типа возврата определяются `Selection` типом перечисления, `COlePasteSpecialDialog` объявленным в классе.

```
enum Selection {
    pasteLink,
    pasteNormal,
    pasteOther,
    pasteStatic
    };
```

Краткие desccriptions этих значений следуют:

- `COlePasteSpecialDialog::pasteLink`Была проверена радиокнопка «Вставить ссылку», а выбранный формат был стандартным форматом OLE.

- `COlePasteSpecialDialog::pasteNormal`Была проверена радиокнопка «Паста», а выбранный формат был стандартным форматом OLE.

- `COlePasteSpecialDialog::pasteOther`Выбранный формат не является стандартным форматом OLE.

- `COlePasteSpecialDialog::pasteStatic`Выбранный формат был метафайлом.

## <a name="colepastespecialdialogm_ps"></a><a name="m_ps"></a>COlePasteSpecialDialog::m_ps

Структура типа OLEUIPASTESPECIAL используется для управления поведением вставки Специальный диалоговый ящик.

```
OLEUIPASTESPECIAL m_ps;
```

### <a name="remarks"></a>Примечания

Члены этой структуры могут быть изменены непосредственно или через функции членов.

Для получения дополнительной [информации, см OLEUIPASTESPECIAL](/windows/win32/api/oledlg/ns-oledlg-oleuipastespecialw) структуры в Windows SDK.

## <a name="see-also"></a>См. также раздел

[MFC Образец OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
