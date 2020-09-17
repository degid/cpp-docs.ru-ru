---
title: Класс CMFCShellListCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayParentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::EnableShellContextMenu
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolderName
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentItemIdList
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentShellFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemPath
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemTypes
- AFXSHELLLISTCTRL/CMFCShellListCtrl::IsDesktop
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnCompareItems
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileDate
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileSize
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemIcon
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemText
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnSetColumns
- AFXSHELLLISTCTRL/CMFCShellListCtrl::Refresh
- AFXSHELLLISTCTRL/CMFCShellListCtrl::SetItemTypes
helpviewer_keywords:
- CMFCShellListCtrl [MFC], DisplayFolder
- CMFCShellListCtrl [MFC], DisplayParentFolder
- CMFCShellListCtrl [MFC], EnableShellContextMenu
- CMFCShellListCtrl [MFC], GetCurrentFolder
- CMFCShellListCtrl [MFC], GetCurrentFolderName
- CMFCShellListCtrl [MFC], GetCurrentItemIdList
- CMFCShellListCtrl [MFC], GetCurrentShellFolder
- CMFCShellListCtrl [MFC], GetItemPath
- CMFCShellListCtrl [MFC], GetItemTypes
- CMFCShellListCtrl [MFC], IsDesktop
- CMFCShellListCtrl [MFC], OnCompareItems
- CMFCShellListCtrl [MFC], OnFormatFileDate
- CMFCShellListCtrl [MFC], OnFormatFileSize
- CMFCShellListCtrl [MFC], OnGetItemIcon
- CMFCShellListCtrl [MFC], OnGetItemText
- CMFCShellListCtrl [MFC], OnSetColumns
- CMFCShellListCtrl [MFC], Refresh
- CMFCShellListCtrl [MFC], SetItemTypes
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
ms.openlocfilehash: 445556535217b0887a02227a0773c287911922a2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753488"
---
# <a name="cmfcshelllistctrl-class"></a>Класс CMFCShellListCtrl

Класс `CMFCShellListCtrl` предоставляет функциональность управления списком Windows и расширяет его, включив в него возможность отображения списка элементов оболочки.

## <a name="syntax"></a>Синтаксис

```
class CMFCShellListCtrl : public CMFCListCtrl
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Отображает список элементов, содержащихся в предоставленной папке.|
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Отображает список элементов, содержащихся в папке, которая является родительской папкой, отображаемым в настоящее время.|
|[CMFCShellListCtrl:EnableShellContextMenu](#enableshellcontextmenu)|Включает или отключит меню ярлыка.|
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Извлекает путь текущей папки.|
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Извлекает имя текущей папки.|
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Возвращает PIDL текущего элемента управления списком.|
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Возвращает указатель в текущую папку Shell.|
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Возвращает текстовый путь элемента.|
|[CMFCShellListCtrl:GetItemTypes](#getitemtypes)|Возвращает типы элементов shell, отображаемые элементом списка.|
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Проверка, является ли выбранная в настоящее время папка папкой папки рабочего стола.|
|[CMFCShelllistctrl::OnCompareItems](#oncompareitems)|Фрейм вызывает этот метод, когда сравнивает два элемента. (Переопределяет [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|
|[CMFCShelllistctrl::OnFormatFileDate](#onformatfiledate)|Вызывается, когда фреймворк получает дату файла, отображаемую элементом управления список.|
|[CMFCShelllistctrl::OnFormatFileSize](#onformatfilesize)|Вызывается при преобразовании фреймворка размера файла управления список.|
|[CMFCShelllistCtrl::OnGetItemIcon](#ongetitemicon)|Вызывается, когда фреймворк получает значок элемента управления списком.|
|[CMFCShelllistctrl::OnGetItemtext](#ongetitemtext)|Вызывается при преобразовании фреймворка текста элемента управления списком.|
|[CMFCShellListCtrl::OnSetКолонки](#onsetcolumns)|Вызывается фреймворками при наборе имен столбцов.|
|[CMFCShellListCtrl::Обновление](#refresh)|Обновляет и перекраивает элемент управления список.|
|[CMFCShellListCtrl:SetItemTypes](#setitemtypes)|Устанавливает тип элементов, отображаемых элементом управления списком.|

## <a name="remarks"></a>Примечания

Класс `CMFCShellListCtrl` расширяет функциональность класса [CMFCListCtrl,](../../mfc/reference/cmfclistctrl-class.md) позволяя программе перечислять элементы оболочки Windows. Используемый формат отображения похож на представление списка для окна Explorer.

Объект [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) может быть `CMFCShellListCtrl` связан с объектом для создания полного окна Explorer. Затем выбор элемента в `CMFCShellTreeCtrl` будет `CMFCShellListCtrl` вызывать объект, чтобы перечислить содержимое выбранного элемента.

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCShellListCtrl` создать объект класса и как отобразить родительскую папку папки отображаемых в настоящее время папки. Этот фрагмент кода является частью [образца Explorer.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclistctrl-class.md)

`CMFCShellListCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxshelllistCtrl.h

## <a name="cmfcshelllistctrldisplayfolder"></a><a name="displayfolder"></a>CMFCShellListCtrl::DisplayFolder

Отображает список элементов, содержащихся в предоставленной папке.

```
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```

### <a name="parameters"></a>Параметры

*lpszPath*<br/>
(в) Строка, содержащая путь папки.

*lpItemInfo*<br/>
(в) Указатель на `LPAFX_SHELLITEMINFO` структуру, описываемую папку для отображения.

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; E_FAIL иначе.

## <a name="cmfcshelllistctrldisplayparentfolder"></a><a name="displayparentfolder"></a>CMFCShellListCtrl::DisplayParentFolder

Обновление объекта [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) для отображения родительской папки отображаемых в настоящее время папок.

```
virtual HRESULT DisplayParentFolder();
```

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; E_FAIL иначе.

## <a name="cmfcshelllistctrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a>CMFCShellListCtrl:EnableShellContextMenu

Включает меню ярлыка.

```cpp
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) Boolean, который определяет, позволяет ли фреймворк меню ярлыков.

## <a name="cmfcshelllistctrlgetcurrentfolder"></a><a name="getcurrentfolder"></a>CMFCShellListCtrl::GetCurrentFolder

Извлекает путь выбранной в настоящее время папки в объекте [CMFCShellListCtrl.](../../mfc/reference/cmfcshelllistctrl-class.md)

```
BOOL GetCurrentFolder(CString& strPath) const;
```

### <a name="parameters"></a>Параметры

*strPath*<br/>
(ваут) Ссылка на параметр строки, где метод пишет путь.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения. В противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод выходит из строя, если `CMFCShellListCtrl`в папке нет папки, выбранной в .

## <a name="cmfcshelllistctrlgetcurrentfoldername"></a><a name="getcurrentfoldername"></a>CMFCShellListCtrl::GetCurrentFolderName

Извлекает имя выбранной в настоящее время папки в объекте [CMFCShellListCtrl.](../../mfc/reference/cmfcshelllistctrl-class.md)

```
BOOL GetCurrentFolderName(CString& strName) const;
```

### <a name="parameters"></a>Параметры

*strName*<br/>
(ваут) Ссылка на параметр строки, где метод пишет имя.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения. В противном случае — 0.

### <a name="remarks"></a>Примечания

Этот метод выходит из строя, если `CMFCShellListCtrl`в папке нет папки, выбранной в .

## <a name="cmfcshelllistctrlgetcurrentitemidlist"></a><a name="getcurrentitemidlist"></a>CMFCShellListCtrl::GetCurrentItemIdList

Возвращает PIDL выбранного в настоящее время элемента.

```
LPITEMIDLIST GetCurrentItemIdList() const;
```

### <a name="return-value"></a>Возвращаемое значение

PIDL текущего элемента.

## <a name="cmfcshelllistctrlgetcurrentshellfolder"></a><a name="getcurrentshellfolder"></a>CMFCShellListCtrl::GetCurrentShellFolder

Получает указатель на выбранный в настоящее время элемент в объекте [CMFCShellListCtrl.](../../mfc/reference/cmfcshelllistctrl-class.md)

```
const IShellFolder* GetCurrentShellFolder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на [интерфейс IShellFolder](/windows/win32/api/shobjidl_core/nn-shobjidl_core-ishellfolder) для выбранного объекта.

### <a name="remarks"></a>Примечания

Этот метод возвращает NULL, если объект в настоящее время не выбран.

## <a name="cmfcshelllistctrlgetitempath"></a><a name="getitempath"></a>CMFCShellListCtrl::GetItemPath

Извлекает путь для элемента.

```
BOOL GetItemPath(
    CString& strPath,
    int iItem) const;
```

### <a name="parameters"></a>Параметры

*strPath*<br/>
(ваут) Ссылка на строку, которая получает путь.

*iItem*<br/>
(в) Индекс элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE в случае успешного выполнения. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Индекс, поставляемый *iItem,* основан на элементах, которые в настоящее время отображаются объектом [класса CMFCShellListCtrl.](../../mfc/reference/cmfcshelllistctrl-class.md)

## <a name="cmfcshelllistctrlgetitemtypes"></a><a name="getitemtypes"></a>CMFCShellListCtrl:GetItemTypes

Возвращает тип элементов, отображаемых объектом [CMFCShellListCtrl.](../../mfc/reference/cmfcshelllistctrl-class.md)

```
SHCONTF GetItemTypes() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение [SHCONTF,](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf) содержащее тип элементов, перечисленных в `CMFCShellListCtrl`.

### <a name="remarks"></a>Примечания

Чтобы установить тип элементов, перечисленных `CMFCShellListCtrl`в, позвоните [CMFCShellListCtrl::SetItemTypes](#setitemtypes).

## <a name="cmfcshelllistctrlisdesktop"></a><a name="isdesktop"></a>CMFCShellListCtrl::IsDesktop

Определяет, является ли папка, отображаемый в объекте [CMFCShellListCtrl,](../../mfc/reference/cmfcshelllistctrl-class.md) папкой рабочего стола.

```
BOOL IsDesktop() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если отображаемые папки папки рабочего стола папку; FALSE в противном случае.

## <a name="cmfcshelllistctrloncompareitems"></a><a name="oncompareitems"></a>CMFCShelllistctrl::OnCompareItems

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>Параметры

(в) *lParam1*<br/>
(в) *lParam2*<br/>
(в) *iColumn*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcshelllistctrlonformatfiledate"></a><a name="onformatfiledate"></a>CMFCShelllistctrl::OnFormatFileDate

Фрейм вызывает этот метод, когда он должен преобразовать дату, связанную с объектом, в строку.

```
virtual void OnFormatFileDate(
    const CTime& tmFile,
    CString& str);
```

### <a name="parameters"></a>Параметры

*tmFile*<br/>
(в) Дата, связанная с файлом.

*Ул*<br/>
(ваут) Строка, содержащая отформатированную дату файла.

### <a name="remarks"></a>Примечания

Когда объект [класса CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) отображает дату, связанную с файлом, он должен преобразовать эту дату в формат строки. Использует `CMFCShellListCtrl` этот метод, чтобы сделать это преобразование. По умолчанию этот метод использует текущий локаль для формата даты в строку.

## <a name="cmfcshelllistctrlonformatfilesize"></a><a name="onformatfilesize"></a>CMFCShelllistctrl::OnFormatFileSize

Фрейм вызывает этот метод, когда преобразует размер объекта в строку.

```
virtual void OnFormatFileSize(
    long lFileSize,
    CString& str);
```

### <a name="parameters"></a>Параметры

*lFileSize*<br/>
(в) Размер файла, который будет отображаться в фрейм-системе.

*Ул*<br/>
(ваут) Строка, содержащая отформатированный размер файла.

### <a name="remarks"></a>Примечания

Когда объекту [класса CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) необходимо отображать размер файла, ему необходимо преобразовать размер файла в формат строки. Использует `CMFCShellListCtrl` этот метод, чтобы сделать это преобразование. По умолчанию этот метод преобразует размер файла из байтов в килобайт, а затем использует текущий локаль для формата размера в строку.

## <a name="cmfcshelllistctrlongetitemicon"></a><a name="ongetitemicon"></a>CMFCShelllistCtrl::OnGetItemIcon

Фрейм вызывает этот метод для извлечения значка, связанного с элементом списка оболочки.

```
virtual int OnGetItemIcon(
    int iItem,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Параметры

*iItem*<br/>
(в) Индекс элемента.

*pItem*<br/>
(в) Параметр LPAFX_SHELLITEMINFO, описывающий элемент.

### <a name="return-value"></a>Возвращаемое значение

Индекс изображения значка в случае успеха; -1, если функция выходит из строя.

### <a name="remarks"></a>Примечания

Индекс изображения значка основан на списке изображений системы.

По умолчанию этот метод опирается на параметр *pItem.* Значение *iItem* не используется в реализации по умолчанию. Вы можете использовать *iItem* для реализации пользовательского поведения.

## <a name="cmfcshelllistctrlongetitemtext"></a><a name="ongetitemtext"></a>CMFCShelllistctrl::OnGetItemtext

Рамочная система вызывает этот метод, когда он должен получить текст элемента оболочки.

```
virtual CString OnGetItemText(
    int iItem,
    int iColumn,
    LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Параметры

*iItem*<br/>
(в) Индекс элемента.

*iColumn*<br/>
(в) Колонка интереса.

*pItem*<br/>
(в) Параметр LPAFX_SHELLITEMINFO, описывающий элемент.

### <a name="return-value"></a>Возвращаемое значение

A, `CString` содержащий текст, связанный с элементом.

### <a name="remarks"></a>Примечания

Каждый элемент `CMFCShellListCtrl` объекта может иметь текст в одном или нескольких столбцах. Когда фреймворк вызывает этот метод, он определяет интересуемый им столбец. Если вы называете эту функцию вручную, необходимо также указать интересуемый вами столбец.

По умолчанию этот метод опирается на параметр *pItem* для определения того, какой элемент обработать. Значение *iItem* не используется в реализации по умолчанию.

## <a name="cmfcshelllistctrlonsetcolumns"></a><a name="onsetcolumns"></a>CMFCShellListCtrl::OnSetКолонки

Фрейм вызывает этот метод, когда устанавливает имена столбцов.

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>Примечания

По умолчанию фреймворк `CMFCShellListCtrl` создает четыре столбца в объекте. Названия этих **столбцов: Имя,** **Размер,** **Тип**и **Изменено.** Этот метод можно переопределить, чтобы настроить количество столбцов и их имена.

## <a name="cmfcshelllistctrlrefresh"></a><a name="refresh"></a>CMFCShellListCtrl::Обновление

Обновляет и перекрашивает объект [CMFCShellListCtrl.](../../mfc/reference/cmfcshelllistctrl-class.md)

```
virtual HRESULT Refresh();
```

### <a name="return-value"></a>Возвращаемое значение

`S_OK`в случае успеха; в противном случае значение ошибки.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы обновить `CMFCShellListCtrl` список элементов, отображаемых объектом.

## <a name="cmfcshelllistctrlsetitemtypes"></a><a name="setitemtypes"></a>CMFCShellListCtrl:SetItemTypes

Устанавливает тип элементов, перечисленных в объекте [CMFCShellListCtrl.](../../mfc/reference/cmfcshelllistctrl-class.md)

```cpp
void SetItemTypes(SHCONTF nTypes);
```

### <a name="parameters"></a>Параметры

*nТипы*<br/>
(в) Список типов элементов, которые поддерживает `CMFCShellListCtrl` объект.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации о [SHCONTF](/windows/win32/api/shobjidl_core/ne-shobjidl_core-_shcontf)списке типов элементов см.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)<br/>
[Класс CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)
