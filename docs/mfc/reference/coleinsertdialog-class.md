---
title: Класс COleInsertDialog
ms.date: 11/04/2016
f1_keywords:
- COleInsertDialog
- AFXODLGS/COleInsertDialog
- AFXODLGS/COleInsertDialog::COleInsertDialog
- AFXODLGS/COleInsertDialog::CreateItem
- AFXODLGS/COleInsertDialog::DoModal
- AFXODLGS/COleInsertDialog::GetClassID
- AFXODLGS/COleInsertDialog::GetDrawAspect
- AFXODLGS/COleInsertDialog::GetIconicMetafile
- AFXODLGS/COleInsertDialog::GetPathName
- AFXODLGS/COleInsertDialog::GetSelectionType
- AFXODLGS/COleInsertDialog::m_io
helpviewer_keywords:
- COleInsertDialog [MFC], COleInsertDialog
- COleInsertDialog [MFC], CreateItem
- COleInsertDialog [MFC], DoModal
- COleInsertDialog [MFC], GetClassID
- COleInsertDialog [MFC], GetDrawAspect
- COleInsertDialog [MFC], GetIconicMetafile
- COleInsertDialog [MFC], GetPathName
- COleInsertDialog [MFC], GetSelectionType
- COleInsertDialog [MFC], m_io
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
ms.openlocfilehash: b5de4ff5daa80e1d8727444a4cfd275597e18c08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374973"
---
# <a name="coleinsertdialog-class"></a>Класс COleInsertDialog

Используется для диалогового окна OLE "Вставить объект".

## <a name="syntax"></a>Синтаксис

```
class COleInsertDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeInsertДиалог::COleInsertДиалог](#coleinsertdialog)|Формирует объект `COleInsertDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeInsertДиалог::CreateItem](#createitem)|Создает элемент, выбранный в диалоговом окне.|
|[Клевесстедиал::DoМодал](#domodal)|Отображает диалоговую коробку объекта вставки OLE.|
|[ColeinsertDialog::GetClassID](#getclassid)|Получает CLSID, связанный с выбранным элементом.|
|[ColeinsertDialog::GetDrawAspect](#getdrawaspect)|Сообщает, следует ли нарисовать элемент в виде значка.|
|[ColeInsertДиалог::GetIconicMetafile](#geticonicmetafile)|Получает ручку метафайла, связанную с культовой формой этого элемента.|
|[ColeinsertDialog::GetPathName](#getpathname)|Получает полный путь к файлу, выбранному в диалоговом поле.|
|[ColeinsertDialog::GetSelectionType](#getselectiontype)|Выбирает тип объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeinsertDialog::m_io](#m_io)|Структура типа OLEUIINSERTOBJECT, которая контролирует поведение диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект `COleInsertDialog` класса, когда вы хотите вызвать этот диалоговый ящик. После `COleInsertDialog` построения объекта можно использовать [структуру m_io](#m_io) для инициализации значений или состояний элементов управления в диалоговом поле. Структура `m_io` типа OLEUIINSERTOBJECT. Для получения дополнительной информации об [использовании](#domodal) этого класса диалогов см.

> [!NOTE]
> Этот класс используется с генерируемым приложением Wizard.?

Для получения дополнительной [OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) информации см.

Для получения дополнительной информации о OLE конкретных диалоговых коробок, [см.](../../mfc/dialog-boxes-in-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleInsertDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="coleinsertdialogcoleinsertdialog"></a><a name="coleinsertdialog"></a>ColeInsertДиалог::COleInsertДиалог

Эта функция строит `COleInsertDialog` только объект.

```
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаг создания, содержащий любое количество следующих значений, которые должны быть объединены с помощью оператора bitwise-OR:

- IOF_SHOWHELP указывает, что при вызове диалогового окна будет отображаться кнопка справки.

- IOF_SELECTCREATENEW указывает, что кнопка «Создание нового радио» будет выбрана первоначально при вызове диалогового окна. Это значение по умолчанию и не может быть использовано с IOF_SELECTCREATEFROMFILE.

- IOF_SELECTCREATEFROMFILE указывает, что кнопка «Создание из файла» будет выбрана первоначально при вызове диалогового окна. Нельзя использовать с IOF_SELECTCREATENEW.

- IOF_CHECKLINK указывает, что флажок Link будет проверен первоначально, когда диалоговая коробка называется.

- IOF_DISABLELINK указывает, что флажок Link будет отключен при вызове диалогового окна.

- IOF_CHECKDISPLAYASICON указывает, что флажок Display As As Icon будет проверен на начальном этапе, будет отображаться текущий значок, а при вызове диалогового окна будет включена кнопка «Значок изменения».

- IOF_VERIFYSERVERSEXIST указывает, что диалоговое окно должно проверять классы, которые он добавляет в поле списка, гарантируя, что серверы, указанные в базе данных регистрации, существуют до отображения диалогового окна. Установка этого флага может значительно ухудшить производительность.

*pParentWnd*<br/>
Указывает на объект окна родителя `CWnd`или владельца (типа), к которому принадлежит объект диалога. Если это NULL, родительское окно объекта диалога устанавливается к основному окну приложения.

### <a name="remarks"></a>Примечания

Чтобы отобразить диалоговую будку, позвоните в функцию [DoModal.](#domodal)

## <a name="coleinsertdialogcreateitem"></a><a name="createitem"></a>ColeInsertДиалог::CreateItem

Вызовите эту функцию, чтобы создать объект типа [COleClientItem](../../mfc/reference/coleclientitem-class.md) только в том случае, если [DoModal](#domodal) возвращает IDOK.

```
BOOL CreateItem(COleClientItem* pItem);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Очки на создаваемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если элемент был создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Вы должны `COleClientItem` выделить объект, прежде чем вы сможете вызвать эту функцию.

## <a name="coleinsertdialogdomodal"></a><a name="domodal"></a>Клевесстедиал::DoМодал

Вызовите эту функцию для отображения диалогового окна объекта вставки OLE.

```
virtual INT_PTR
    DoModal();

INT_PTR
    DoModal(DWORD  dwFlags);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Одно из следующих значений:

`COleInsertDialog::DocObjectsOnly`вставляет только DocObjects.

`COleInsertDialog::ControlsOnly`вставляет только элементы управления ActiveX.

Нулевой вставки ни DocObject, ни ActiveX управления. Это значение приводит к той же реализации, что и первый прототип, перечисленный выше.

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если диалоговая коробка была успешно отображана.

- IDCANCEL, если пользователь отменил диалоговую будку.

- IDABORT, если произошла ошибка. Если IDABORT возвращается, позвоните в функцию [COleDialog::GetLastError,](../../mfc/reference/coledialog-class.md#getlasterror) чтобы получить больше информации о типе ошибки, которая произошла. Список возможных ошибок [OleUIInsertObject](/windows/win32/api/oledlg/nf-oledlg-oleuiinsertobjectw) можно узнать в SDK Windows.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные элементы управления диалоговой коробкой, установив элементы [m_io](#m_io) структуры, вы должны сделать это перед вызовом, `DoModal`но после построения объекта диалога.

При `DoModal` возврате IDOK можно вызвать другие функции участника, чтобы получить настройки или ввод информации в диалоговую поле пользователя.

## <a name="coleinsertdialoggetclassid"></a><a name="getclassid"></a>ColeinsertDialog::GetClassID

Вызовите эту функцию, чтобы получить CLSID, связанный с выбранным элементом, только в том случае, если [DoModal](#domodal) возвращает IDOK и тип `COleInsertDialog::createNewItem`выбора.

```
REFCLSID GetClassID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает CLSID, связанный с выбранным элементом.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см. ключ CLSID](/windows/win32/com/clsid-key-hklm) в SDK Windows.

## <a name="coleinsertdialoggetdrawaspect"></a><a name="getdrawaspect"></a>ColeinsertDialog::GetDrawAspect

Позвоните в эту функцию, чтобы определить, решил ли пользователь отобразить выбранный элемент в качестве значка.

```
DVASPECT GetDrawAspect() const;
```

### <a name="return-value"></a>Возвращаемое значение

Метод, необходимый для визуализации объекта.

- DVASPECT_CONTENT возвращен, если флажок Display As As Icon не был проверен.

- DVASPECT_ICON возвращена, если проверка флажка Display As As Icon.

### <a name="remarks"></a>Примечания

Вызовите эту функцию только в том случае, если [DoModal](#domodal) возвращает IDOK.

Более подробную информацию о чертежном аспекте можно узнать в структуре данных [FORMATETC](/windows/win32/api/objidl/ns-objidl-formatetc) в SDK Windows.

## <a name="coleinsertdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>ColeInsertДиалог::GetIconicMetafile

Вызовите эту функцию, чтобы получить ручку метафайла, который содержит знаковый аспект выбранного элемента.

```
HGLOBAL GetIconicMetafile() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ручка к метафайлу, содержащему знаковый аспект выбранного элемента, если флажок Display As As Icon был проверен, когда диалог был отклонен, выбрав **OK;** в противном случае NULL.

## <a name="coleinsertdialoggetpathname"></a><a name="getpathname"></a>ColeinsertDialog::GetPathName

Вызов исчерпать эту функцию, чтобы получить полный путь выбранного файла только в том случае, если [DoModal](#domodal) возвращает IDOK и тип выбора не `COleInsertDialog::createNewItem`является.

```
CString GetPathName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный путь к файлу, выбранного в диалоговом поле. Если тип `createNewItem`выбора, эта функция возвращает `CString` бессмысленно в режиме выпуска или вызывает утверждение в режиме отладки.

## <a name="coleinsertdialoggetselectiontype"></a><a name="getselectiontype"></a>ColeinsertDialog::GetSelectionType

Вызовите эту функцию, чтобы выбранный тип выбора, когда диалоговая коробка «Вставка объекта» была отклонена, выбрав **OK.**

```
UINT GetSelectionType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Тип выбора сделан.

### <a name="remarks"></a>Примечания

Значения типа возврата определяются `Selection` типом перечисления, `COleInsertDialog` объявленным в классе.

```
enum Selection {
    createNewItem,
    insertFromFile,
    linkToFile
    };
```

Краткие описания этих значений следуют:

- `COleInsertDialog::createNewItem`Выбрана кнопка «Создание нового радио».

- `COleInsertDialog::insertFromFile`Была выбрана кнопка «Создание из файла» радиоприемника и не проверена флажок Link.

- `COleInsertDialog::linkToFile`Была выбрана кнопка «Создание из файла» радиоприемника и проверена флажок Link.

## <a name="coleinsertdialogm_io"></a><a name="m_io"></a>ColeinsertDialog::m_io

Структура типа OLEUIINSERTOBJECT используется для управления поведением диалогового окна объекта вставки.

```
OLEUIINSERTOBJECT m_io;
```

### <a name="remarks"></a>Примечания

Члены этой структуры могут быть изменены либо непосредственно, либо через функции членов.

Для получения дополнительной [OLEUIINSERTOBJECT](/windows/win32/api/oledlg/ns-oledlg-oleuiinsertobjectw) информации см.

## <a name="see-also"></a>См. также раздел

[MFC Образец OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
