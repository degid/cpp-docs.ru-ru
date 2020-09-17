---
title: Класс CMFCShellTreeCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
helpviewer_keywords:
- CMFCShellTreeCtrl [MFC], EnableShellContextMenu
- CMFCShellTreeCtrl [MFC], GetFlags
- CMFCShellTreeCtrl [MFC], GetItemPath
- CMFCShellTreeCtrl [MFC], GetRelatedList
- CMFCShellTreeCtrl [MFC], OnChildNotify
- CMFCShellTreeCtrl [MFC], OnGetItemIcon
- CMFCShellTreeCtrl [MFC], OnGetItemText
- CMFCShellTreeCtrl [MFC], Refresh
- CMFCShellTreeCtrl [MFC], SelectPath
- CMFCShellTreeCtrl [MFC], SetFlags
- CMFCShellTreeCtrl [MFC], SetRelatedList
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
ms.openlocfilehash: c6f5856e92c2aca1d23ee6a37b99ea9700ea6db0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753445"
---
# <a name="cmfcshelltreectrl-class"></a>Класс CMFCShellTreeCtrl

Класс `CMFCShellTreeCtrl` расширяет функциональность [класса CTreeCtrl,](../../mfc/reference/ctreectrl-class.md) отображая иерархию элементов Shell.

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCShellTreeCtrl : public CTreeCtrl
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCShellTreeCtrl:EnableShellContextMenu](#enableshellcontextmenu)|Включает или отключит меню ярлыка.|
|[CMFCShellTreeCtrl::GetFlags](#getflags)|Возвращает комбинацию флагов, которые передаются [IShellFolder::EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects).|
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|Извлекает путь к элементу.|
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|Возвращает указатель на объект [класса CMFCShellListCtrl,](../../mfc/reference/cmfcshelllistctrl-class.md) который `CMFCShellTreeCtrl` используется вместе с этим объектом для создания окна, похожего на Explorer.|
|[CMFCShellTreeCtrl::OnchildNotify](#onchildnotify)|Эта функция участника вызывается родительским окном этого окна, когда оно получает сообщение об уведомлении, применивщее к этому окну. (Оверлет: [OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||
|[CMFCShellTreeCtrl::Обновление](#refresh)|Обновляет и перекраивает `CMFCShellTreeCtrl` текущий объект.|
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|Выбирает подходящий элемент управления деревом на основе поставляемого PIDL или строки.|
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Наборы флагов для фильтрации контекста `IShellFolder::EnumObjects`дерева (по аналогии с флагами, используемыми).|
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|Устанавливает связь между `CMFCShellTreeCtrl` текущим `CMFCShellListCtrl` объектом и объектом.|

## <a name="remarks"></a>Примечания

Этот класс расширяет `CTreeCtrl` класс, позволяя программе включать элементы Windows Shell в дерево. Этот класс может быть `CMFCShellListCtrl` связан с объектом для создания полного окна Explorer. Затем при выборе элемента в дереве будет отображаться список элементов Windows Shell в связанном списке.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CTreeCtrl](../../mfc/reference/ctreectrl-class.md)

`CMFCShellTreeCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxshelltreeCtrl.h

## <a name="example"></a>Пример

В следующем примере показывается, как создать объект класса `CMFCShellTreeCtrl`. Этот фрагмент кода является частью [образца Explorer.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]

## <a name="cmfcshelltreectrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a>CMFCShellTreeCtrl:EnableShellContextMenu

Включает меню ярлыка.

```cpp
void EnableShellContextMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) Boolean, который определяет, следует ли включить меню ярлыка.

## <a name="cmfcshelltreectrlgetflags"></a><a name="getflags"></a>CMFCShellTreeCtrl::GetFlags

Возвращает флаги, установленные для объекта [класса CMFCShellTreeCtrl.](../../mfc/reference/cmfcshelltreectrl-class.md)

```
DWORD GetFlags() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD, которое определяет комбинацию флагов, установленных в настоящее время.

### <a name="remarks"></a>Примечания

Флаги, установленные в `CMFCShellTreeCtrl` них, отправляются в метод [IShellFolder::EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects) всякий раз, когда объект обновляется. Вы можете изменить флаги с помощью метода [CMFCShellTreeCtrl::SetFlags.](#setflags)

## <a name="cmfcshelltreectrlgetitempath"></a><a name="getitempath"></a>CMFCShellTreeCtrl::GetItemPath

Извлекает путь элемента в объекте [класса CMFCShellTreeCtrl.](../../mfc/reference/cmfcshelltreectrl-class.md)

```
BOOL GetItemPath(
    CString& strPath,
    HTREEITEM htreeItem = NULL) const;
```

### <a name="parameters"></a>Параметры

*strPath*<br/>
(ваут) Ссылка на параметр строки. Метод записывает путь элемента к этому параметру.

*htreeItem*<br/>
(в) Метод получает путь для этого элемента управления деревом.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения. В противном случае — 0.

### <a name="remarks"></a>Примечания

Если этот метод не удается, *strPath* содержит пустую строку.

Если вы не указали *hTreeItem,* этот метод пытается получить строку для выбранного в настоящее время элемента. Если элемент не выбран и *hTreeItem* является NULL, этот метод не удается.

## <a name="cmfcshelltreectrlgetrelatedlist"></a><a name="getrelatedlist"></a>CMFCShellTreeCtrl::GetRelatedList

Возвращает указатель на объект [класса CMFCShellListCtrl,](../../mfc/reference/cmfcshelllistctrl-class.md) связанный с этим объектом [CMFCShellTreeCtrl.](../../mfc/reference/cmfcshelltreectrl-class.md)

```
CMFCShellListCtrl* GetRelatedList() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMFCShellListCtrl` объект, связанный с этим объектом управления деревом.

### <a name="remarks"></a>Примечания

Используя `CMFCShellListCtrl` объект вместе с `CMFCShellTreeCtrl` объектом, можно создать окно, похожее на Explorer. Используйте метод [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) для ассоциировать два класса. После их ассоциированного `CMFCShellListCtrl` фреймворка автоматически обновляет, если выбор в изменении. `CMFCShellTreeCtrl`

## <a name="cmfcshelltreectrlonchildnotify"></a><a name="onchildnotify"></a>CMFCShellTreeCtrl::OnchildNotify

```
virtual BOOL OnChildNotify(
    UINT message,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT* pLResult);
```

### <a name="parameters"></a>Параметры

(в) *сообщение*<br/>
(в) *wParam*<br/>
(в) *lПарам*<br/>
(в) *pLResult*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcshelltreectrlongetitemicon"></a><a name="ongetitemicon"></a>CMFCShellTreeCtrl::OnGetItemIcon

```
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,
    BOOL bSelected);
```

### <a name="parameters"></a>Параметры

(в) *pItem*<br/>
(в) *bВыбор*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcshelltreectrlongetitemtext"></a><a name="ongetitemtext"></a>CMFCShellTreeCtrl::OnGetItemtext

```
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```

### <a name="parameters"></a>Параметры

(в) *pItem*<br/>

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

## <a name="cmfcshelltreectrlrefresh"></a><a name="refresh"></a>CMFCShellTreeCtrl::Обновление

Освежает и перекрашивает [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md).

```cpp
void Refresh();
```

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы обновить иерархию `CMFCShellTreeCtrl`элементов, отображаемых в .

## <a name="cmfcshelltreectrlselectpath"></a><a name="selectpath"></a>CMFCShellTreeCtrl::SelectPath

Выбирает элемент в [классе CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) на основе поставленного пути.

```
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```

### <a name="parameters"></a>Параметры

*lpszPath*<br/>
(в) Строка, опоедая траекторию элемента.

*lpidl*<br/>
(в) PIDL, который определяет элемент

### <a name="return-value"></a>Возвращаемое значение

S_OK в случае успеха; E_FAIL иначе.

## <a name="cmfcshelltreectrlsetflags"></a><a name="setflags"></a>CMFCShellTreeCtrl::SetFlags

Устанавливает флаги для фильтрации контекста дерева.

```cpp
void SetFlags(
    DWORD dwFlags,
    BOOL bRefresh = TRUE);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
(в) Флаги для установки.

*bRefresh*<br/>
(в) Boolean, который определяет, `CMFCShellTreeCtrl` следует ли обновляться немедленно.

### <a name="remarks"></a>Примечания

Проходы `CMFCShellTreeCtrl` все набор флаги [IShellFolder::EnumObjects](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects). Для получения дополнительной информации о значениях различных флагов, [см.](/windows/win32/api/shobjidl_core/nf-shobjidl_core-ishellfolder-enumobjects)

## <a name="cmfcshelltreectrlsetrelatedlist"></a><a name="setrelatedlist"></a>CMFCShellTreeCtrl::SetRelatedList

Ассоциирует объект [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) с объектом [CMFCShellTreeCtrl.](../../mfc/reference/cmfcshelltreectrl-class.md)

```cpp
void SetRelatedList(CMFCShellListCtrl* pShellList);
```

### <a name="parameters"></a>Параметры

*pShellList*<br/>
(в) Указатель на `CMFCShellListCtrl` объект.

### <a name="remarks"></a>Примечания

Этот метод `CMFCShellListCtrl` ассоциируется с . `CMFCShellTreeCtrl` Эти объекты могут отображаться как окно, похожее на Explorer: `CMFCShellTreeCtrl`если пользователь выбирает `CMFCShellListCtrl` объект в, связанные элементы в будет автоматически обновляться.

Используйте метод [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) для `CMFCShellListCtrl` получения `CMFCShellTreeCtrl`связанного с .

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)<br/>
[Класс CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)
