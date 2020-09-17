---
title: Класс COleChangeSourceDialog
ms.date: 11/04/2016
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
ms.openlocfilehash: 78da0a495de6ea951deab984550756a2d6f3e2bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321874"
---
# <a name="colechangesourcedialog-class"></a>Класс COleChangeSourceDialog

Используется для диалогового окна OLE "Изменить источник".

## <a name="syntax"></a>Синтаксис

```
class COleChangeSourceDialog : public COleDialog
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeChangeИсточникДиалог::COleChangeИсточникДиалог](#colechangesourcedialog)|Формирует объект `COleChangeSourceDialog`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeChangeИсточникДиалог::DoModal](#domodal)|Отображает диалоговую коробку источника изменений OLE.|
|[ColeChangeSourceДиалог::GetDisplayName](#getdisplayname)|Получает полное имя отображения исходного кода.|
|[ColeChangeИсточникДиалог::GetFileName](#getfilename)|Получает имя файла из имени источника.|
|[ColeChangeИсточникДиалог::GetFromPrefix](#getfromprefix)|Получает приставку предыдущего источника.|
|[ColeChangeИсточникДиалог::GetItemName](#getitemname)|Получает имя элемента из имени источника.|
|[ColeChangeИсточник::GetToPrefix](#gettoprefix)|Получает приставку нового источника|
|[ColeChangeИсточникДиалог::IsValidИсточник](#isvalidsource)|Указывает, является ли источник действительным.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[ColeChangeИсточникДиалог::m_cs](#m_cs)|Структура, контролирующая поведение диалогового окна.|

## <a name="remarks"></a>Примечания

Создайте объект `COleChangeSourceDialog` класса, когда вы хотите вызвать этот диалоговый ящик. После `COleChangeSourceDialog` построения объекта можно использовать [структуру m_cs](#m_cs) для инициализации значений или состояний элементов управления в диалоговом поле. Структура `m_cs` типа [OLEUICHANGESOURCE.](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) Для получения дополнительной информации об [использовании](#domodal) этого класса диалогов см.

Для получения дополнительной [информации, см OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) структуры в Windows SDK.

Для получения дополнительной информации о OL-специфических диалоговых ящиков, [см.](../../mfc/dialog-boxes-in-ole.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[COleDialog](../../mfc/reference/coledialog-class.md)

`COleChangeSourceDialog`

## <a name="requirements"></a>Требования

**Заголовок:** afxodlgs.h

## <a name="colechangesourcedialogcolechangesourcedialog"></a><a name="colechangesourcedialog"></a>ColeChangeИсточникДиалог::COleChangeИсточникДиалог

Эта функция строит `COleChangeSourceDialog` объект.

```
explicit COleChangeSourceDialog(
    COleClientItem* pItem,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>Параметры

*pItem*<br/>
Указатель на связанный [COleClientItem,](../../mfc/reference/coleclientitem-class.md) источник которого должен быть обновлен.

*pParentWnd*<br/>
Указывает на объект окна родителя `CWnd`или владельца (типа), к которому принадлежит объект диалога. Если это NULL, родительское окно окна диалогов будет установлено на основное окно приложения.

### <a name="remarks"></a>Примечания

Чтобы отобразить диалоговую будку, позвоните в функцию [DoModal.](#domodal)

Для получения дополнительной информации, см [OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) структуры и [OleUIChangeSource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) функции в Windows SDK.

## <a name="colechangesourcedialogdomodal"></a><a name="domodal"></a>ColeChangeИсточникДиалог::DoModal

Вызовите эту функцию для отображения диалогового окна источника изменений OLE.

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние завершения для диалогового окна. Одно из следующих значений:

- IDOK, если диалоговая коробка была успешно отображана.

- IDCANCEL, если пользователь отменил диалоговую будку.

- IDABORT, если произошла ошибка. Если IDABORT возвращается, позвоните в функцию [COleDialog::GetLastError,](../../mfc/reference/coledialog-class.md#getlasterror) чтобы получить больше информации о типе ошибки, которая произошла. Список возможных ошибок [OleUIChangeSource](/windows/win32/api/oledlg/nf-oledlg-oleuichangesourcew) можно найти в SDK Windows.

### <a name="remarks"></a>Примечания

Если вы хотите инициализировать различные элементы управления диалоговой коробкой, установив элементы [структуры m_cs,](#m_cs) вы должны сделать это перед вызовом, `DoModal`но после построения объекта диалога.

При `DoModal` возврате IDOK можно вызвать функции участника для извлечения введенных пользователем настроек или информации из диалогового окна. В следующем списке указаны типичные функции запроса:

- [GetFileName](#getfilename)

- [GetDisplayName](#getdisplayname)

- [GetItemName](#getitemname)

## <a name="colechangesourcedialoggetdisplayname"></a><a name="getdisplayname"></a>ColeChangeSourceДиалог::GetDisplayName

Вызовите эту функцию, чтобы получить полное имя отображения для связанного элемента клиента.

```
CString GetDisplayName();
```

### <a name="return-value"></a>Возвращаемое значение

Полное имя отображения исходного кода (моникер) для [COleClientItem,](../../mfc/reference/coleclientitem-class.md) указанное в конструкторе.

## <a name="colechangesourcedialoggetfilename"></a><a name="getfilename"></a>ColeChangeИсточникДиалог::GetFileName

Вызовите эту функцию, чтобы получить часть файла кличка отображения для связанного элемента клиента.

```
CString GetFileName();
```

### <a name="return-value"></a>Возвращаемое значение

Файл моникер часть исходного дисплея имя для [COleClientItem](../../mfc/reference/coleclientitem-class.md) указано в конструкторе.

### <a name="remarks"></a>Примечания

Кличка файла вместе с псевдонимом элемента дает полное имя дисплея.

## <a name="colechangesourcedialoggetfromprefix"></a><a name="getfromprefix"></a>ColeChangeИсточникДиалог::GetFromPrefix

Вызовите эту функцию, чтобы получить предыдущую строку префикса для источника.

```
CString GetFromPrefix();
```

### <a name="return-value"></a>Возвращаемое значение

Предыдущая строка префикса источника.

### <a name="remarks"></a>Примечания

Вызовите эту функцию только после того, как [DoModal](#domodal) вернет IDOK.

Это значение происходит `lpszFrom` непосредственно от члена структуры [OLEUICHANGESOURCE.](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)

Для получения дополнительной [информации, см OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) структуры в Windows SDK.

## <a name="colechangesourcedialoggetitemname"></a><a name="getitemname"></a>ColeChangeИсточникДиалог::GetItemName

Вызовите эту функцию, чтобы получить часть кличка элемента отображения для связанного элемента клиента.

```
CString GetItemName();
```

### <a name="return-value"></a>Возвращаемое значение

Элемент прозвище часть исходного дисплея имя для [COleClientItem](../../mfc/reference/coleclientitem-class.md) указано в конструкторе.

### <a name="remarks"></a>Примечания

Кличка файла вместе с псевдонимом элемента дает полное имя дисплея.

## <a name="colechangesourcedialoggettoprefix"></a><a name="gettoprefix"></a>ColeChangeИсточник::GetToPrefix

Вызовите эту функцию, чтобы получить новую строку префикса для источника.

```
CString GetToPrefix();
```

### <a name="return-value"></a>Возвращаемое значение

Новая строка префикса источника.

### <a name="remarks"></a>Примечания

Вызовите эту функцию только после того, как [DoModal](#domodal) вернет IDOK.

Это значение происходит `lpszTo` непосредственно от члена структуры [OLEUICHANGESOURCE.](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)

Для получения дополнительной [информации, см OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) структуры в Windows SDK.

## <a name="colechangesourcedialogm_cs"></a><a name="m_cs"></a>ColeChangeИсточникДиалог::m_cs

Этот член данных представляет собой структуру типа [OLEUICHANGESOURCE.](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew)

```
OLEUICHANGESOURCE m_cs;
```

### <a name="remarks"></a>Примечания

`OLEUICHANGESOURCE`используется для управления поведением диалогового окна источника изменений OLE. Члены этой структуры могут быть изменены непосредственно.

Для получения дополнительной [информации, см OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) структуры в Windows SDK.

## <a name="colechangesourcedialogisvalidsource"></a><a name="isvalidsource"></a>ColeChangeИсточникДиалог::IsValidИсточник

Вызовите эту функцию, чтобы определить, является ли новый источник действительным.

```
BOOL IsValidSource();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если новый источник действителен, в противном случае 0.

### <a name="remarks"></a>Примечания

Вызовите эту функцию только после того, как [DoModal](#domodal) вернет IDOK.

Для получения дополнительной [информации, см OLEUICHANGESOURCE](/windows/win32/api/oledlg/ns-oledlg-oleuichangesourcew) структуры в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс COleDialog](../../mfc/reference/coledialog-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс COleDialog](../../mfc/reference/coledialog-class.md)
