---
title: Класс CShellManager
ms.date: 11/04/2016
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
ms.openlocfilehash: 1c2f9ac1658f50f0ec5bd9e2f53d270c09bfcb6a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750322"
---
# <a name="cshellmanager-class"></a>Класс CShellManager

Реализует несколько методов, которые позволяют работать с указателями в списках идентификаторов (PIDL).

## <a name="syntax"></a>Синтаксис

```
class CShellManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CShellManager::CShellManager](#cshellmanager)|Формирует объект `CShellManager`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CShellManager:BrowseForFolder](#browseforfolder)|Отображает диалоговую коробку, которая позволяет пользователю выбрать папку оболочки.|
|[CShellManager::ConcatenateItem](#concatenateitem)|Конкатирует два PIDL.|
|[CShellManager::CopyItem](#copyitem)|Создает новый PIDL и копирует поставляемый PIDL к нему.|
|[CShellManager::CreateItem](#createitem)|Создает новый PIDL указанного размера.|
|[CShellManager::FreeItem](#freeitem)|Удаляет поставляемый PIDL.|
|[CShellManager::GetItemCount](#getitemcount)|Возвращает количество элементов в поставляемом PIDL.|
|[CShellManager::GetItemSize](#getitemsize)|Возвращает размер поставляемого PIDL.|
|[CShellManager::GetNextItem](#getnextitem)|Возвращает следующий элемент из PIDL.|
|[CShellManager::GetParentItem](#getparentitem)|Извлекает элемент родительской завоевывает поставляемый товар.|
|[CShellManager::ItemFromPath](#itemfrompath)|Извлекает PIDL для элемента, идентифицированного по поставляемому пути.|

## <a name="remarks"></a>Примечания

Методы `CShellManager` класса имеют дело с PIDL. PIDL является уникальным идентификатором для объекта оболочки.

Объект не должен `CShellManager` создаваться вручную. Он будет создан автоматически в рамках вашего приложения. Тем не менее, вы должны позвонить [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) в процессе инициализации приложения. Чтобы получить указатель на менеджер оболочки для вашего приложения, позвоните [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CShellManager](../../mfc/reference/cshellmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxshellmanager.h

## <a name="cshellmanagerbrowseforfolder"></a><a name="browseforfolder"></a>CShellManager:BrowseForFolder

Отображает диалоговую коробку, которая позволяет пользователю выбрать папку оболочки.

```
BOOL BrowseForFolder(
    CString& strOutFolder,
    CWnd* pWndParent = NULL,
    LPCTSTR lplszInitialFolder = NULL,
    LPCTSTR lpszTitle = NULL,
    UINT ulFlags = BIF_RETURNONLYFSDIRS,
    LPINT piFolderImage = NULL);
```

### <a name="parameters"></a>Параметры

*strOutFolder*<br/>
(ваут) Строка, используемая методом для хранения пути выбранной папки.

*pWndParent*<br/>
(в) Указатель на родительское окно.

*lplszПервоначальныйФолдер*<br/>
(в) Строка, содержащая папку, выбранную по умолчанию при отображении диалогового окна.

*lpszНазвание*<br/>
(в) Название для диалогового окна.

*ulFlags*<br/>
(в) Флаги, указывающие параметры для диалогового окна. Подробное описание можно посмотреть [BROWSEINFO.](/windows/win32/api/shlobj_core/ns-shlobj_core-browseinfow)

*piFolderImage*<br/>
(ваут) Указатель на значение рядового значения, в котором метод записывает индекс изображения выбранной папки.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если пользователь выбирает папку из окна диалога; в противном случае 0.

### <a name="remarks"></a>Примечания

При вызове этого метода приложение создает и показывает диалоговую коробку, позволяющую пользователю выбрать папку. Метод напишет путь папки в параметр *strOutFolder.*

### <a name="example"></a>Пример

В следующем примере показано, как получить `CShellManager` ссылку `CWinAppEx::GetShellManager` на объект с `BrowseForFolder` помощью метода и как использовать метод. Этот фрагмент кода является частью [образца Explorer.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]

## <a name="cshellmanagerconcatenateitem"></a><a name="concatenateitem"></a>CShellManager::ConcatenateItem

Создает новый список, содержащий два PIDL.

```
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,
    LPCITEMIDLIST pidl2);
```

### <a name="parameters"></a>Параметры

*pidl1*<br/>
(в) Первый элемент.

*pidl2*<br/>
(в) Второй элемент.

### <a name="return-value"></a>Возвращаемое значение

Указатель на новый список элементов, если функция удана, в противном случае NULL.

### <a name="remarks"></a>Примечания

Этот метод создает новый [ITEMIDLIST достаточно большой,](/windows/win32/api/shtypes/ns-shtypes-itemidlist) чтобы содержать как *pidl1* и *pidl2*. Затем он копирует *pidl1* и *pidl2* в новый список.

## <a name="cshellmanagercopyitem"></a><a name="copyitem"></a>CShellManager::CopyItem

Копирует список элементов.

```
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```

### <a name="parameters"></a>Параметры

*pidlИсточник*<br/>
(в) Исходный список элементов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на вновь созданный список элементов в случае успеха; в противном случае NULL.

### <a name="remarks"></a>Примечания

Вновь созданный список элементов имеет тот же размер, что и список исходных элементов.

## <a name="cshellmanagercreateitem"></a><a name="createitem"></a>CShellManager::CreateItem

Создает новый PIDL.

```
LPITEMIDLIST CreateItem(UINT cbSize);
```

### <a name="parameters"></a>Параметры

*cbSize*<br/>
(в) Размер списка элементов.

### <a name="return-value"></a>Возвращаемое значение

Указатель на созданный список элементов в случае успеха; в противном случае NULL.

## <a name="cshellmanagercshellmanager"></a><a name="cshellmanager"></a>CShellManager::CShellManager

Формирует объект `CShellManager`.

```
CShellManager();
```

### <a name="remarks"></a>Примечания

В большинстве случаев, вам `CShellManager` не придется создавать непосредственно. По умолчанию фреймворк создает один для вас. Чтобы получить указатель `CShellManager`на, позвоните [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager). Если вы создаете вручную, `CShellManager` вы должны инициализировать его с методом [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).

## <a name="cshellmanagerfreeitem"></a><a name="freeitem"></a>CShellManager::FreeItem

Удаляет список элементов.

```cpp
void FreeItem(LPITEMIDLIST pidl);
```

### <a name="parameters"></a>Параметры

*pidl*<br/>
(в) Список элементов для удаления.

## <a name="cshellmanagergetitemcount"></a><a name="getitemcount"></a>CShellManager::GetItemCount

Возвращает количество элементов в списке элементов.

```
UINT GetItemCount(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Параметры

*pidl*<br/>
(в) Указатель на список элементов.

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в списке элементов.

## <a name="cshellmanagergetitemsize"></a><a name="getitemsize"></a>CShellManager::GetItemSize

Возвращает размер списка элементов.

```
UINT GetItemSize(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Параметры

*pidl*<br/>
(в) Указатель на список элементов.

### <a name="return-value"></a>Возвращаемое значение

Размер списка элементов.

## <a name="cshellmanagergetnextitem"></a><a name="getnextitem"></a>CShellManager::GetNextItem

Извлекает следующий элемент из указателя в список идентификаторов элементов (PIDL).

```
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Параметры

*pidl*<br/>
(в) Список элементов для итерата.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующий элемент в списке.

### <a name="remarks"></a>Примечания

Если в списке больше нет элементов, этот метод возвращает NULL.

## <a name="cshellmanagergetparentitem"></a><a name="getparentitem"></a>CShellManager::GetParentItem

Извлекает родительский указатель в список идентификаторов элементов (PIDL).

```
int GetParentItem(
    LPCITEMIDLIST lpidl,
    LPITEMIDLIST& lpidlParent);
```

### <a name="parameters"></a>Параметры

*lpidl*<br/>
(в) PIDL, родитель которого будет извлечен.

*lpidlParent*<br/>
(ваут) Ссылка на PIDL, где метод будет хранить результат.

### <a name="return-value"></a>Возвращаемое значение

Уровень родительского PIDL.

### <a name="remarks"></a>Примечания

Уровень PIDL по отношению к рабочему столу. Считается, что настольный компьютер PIDL имеет уровень 0.

## <a name="cshellmanageritemfrompath"></a><a name="itemfrompath"></a>CShellManager::ItemFromPath

Извлекает указатель в список идентификаторов элементов (PIDL) из элемента, идентифицированного по траектории строки.

```
HRESULT ItemFromPath(
    LPCTSTR lpszPath,
    LPITEMIDLIST& pidl);
```

### <a name="parameters"></a>Параметры

*lpszPath*<br/>
(в) Строка, опоедая путь для элемента.

*pidl*<br/>
(ваут) Ссылка на PIDL. Метод использует этот PIDL для хранения указателя на его значение возврата.

### <a name="return-value"></a>Возвращаемое значение

Возвращает NOERROR в случае успеха; значение ошибки, определяемое OLE.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)
