---
title: Класс CContextMenuManager
ms.date: 11/04/2016
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
ms.openlocfilehash: c676355ebf44d6cc02bfa66ac870757627ae5a58
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754805"
---
# <a name="ccontextmenumanager-class"></a>Класс CContextMenuManager

Объект `CContextMenuManager` управляет меню ярлыков, также известным как контекстные меню.

## <a name="syntax"></a>Синтаксис

```
class CContextMenuManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Формирует объект `CContextMenuManager`.|
|`CContextMenuManager::~CContextMenuManager`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CContextMenuManager::AddMenu](#addmenu)|Добавляет новое меню ярлыка.|
|[Контекстменуменеджер:Гетменомебид](#getmenubyid)|Возвращает ручку в меню, связанную с предоставленным идентификатором ресурса.|
|[CContextMenuManager::GetMenubyname](#getmenubyname)|Возвращает ручку в меню, которое соответствует названию предоставленного меню.|
|[CContextMenuManager::GetMenuNames](#getmenunames)|Возвращает список имен меню.|
|[CContextMenuManager::LoadState](#loadstate)|Загружает меню ярлыков, хранящихся в реестре Windows.|
|[CContextMenuManager::Resetstate](#resetstate)|Очищает меню ярлыка от менеджера контекстного меню.|
|[CContextMenuManager::SaveState](#savestate)|Сохраняет меню ярлыка в реестре Windows.|
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Контролирует ли `CContextMenuManager` закрывается ли активное меню ярлыка, когда оно показывает новое меню ярлыка.|
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Отображает указанное меню ярлыка.|
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Отображает указанное меню ярлыка. Возвращает индекс выбранной команды меню.|

## <a name="remarks"></a>Примечания

`CContextMenuManager`управляет меню ярлыка и гарантирует, что они имеют последовательный внешний вид.

Объект не должен `CContextMenuManager` создаваться вручную. Рамки приложения создают `CContextMenuManager` объект. Тем не менее, вы должны позвонить [CWinAppEx::InitContextMenuManager,](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) когда ваше приложение инициализировано. После инициализации менеджера контекста используйте метод [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) для получения указателя на менеджер контекста для вашего приложения.

Вы можете создать меню ярлыков во `AddMenu`время выполнения, позвонив. Если вы хотите показать меню без предварительного `ShowPopupMenu`получения пользовательского ввода, позвоните . `TrackPopupMenu`используется, когда вы хотите создать меню и ждать ввода пользователя. `TrackPopupMenu`возвращает индекс выбранной команды или 0, если пользователь вышел, не выбрав ничего.

Также `CContextMenuManager` можно сохранить и загрузить его состояние в реестр Windows.

## <a name="example"></a>Пример

В следующем примере показано, как `CContextMenuManager` добавить меню к объекту и как не `CContextMenuManager` закрывать активное всплывающее меню, когда объект отображает новое всплывающее меню. Этот фрагмент кода является частью [образца пользовательских страниц.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CContextMenuManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxcontextmenumanager.h

## <a name="ccontextmenumanageraddmenu"></a><a name="addmenu"></a>CContextMenuManager::AddMenu

Добавляет новое меню ярлыка в [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```
BOOL AddMenu(
    UINT uiMenuNameResId,
    UINT uiMenuResId);

BOOL AddMenu(
    LPCTSTR lpszName,
    UINT uiMenuResId);
```

### <a name="parameters"></a>Параметры

*uiMenuNameResId*<br/>
(в) Идентификатор ресурса для строки, содержащей имя нового меню.

*uiMenuResId*<br/>
(в) Идентификатор ресурса меню.

*lpszName*<br/>
(в) Строка, содержащая название нового меню.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод был успешным; 0, если метод не удается.

### <a name="remarks"></a>Примечания

Этот метод не удается, если *uiMenuResId* является недействительным или `CContextMenuManager`если другое меню с тем же именем уже находится в .

## <a name="ccontextmenumanagerccontextmenumanager"></a><a name="ccontextmenumanager"></a>CContextMenuManager::CContextMenuManager

Строит объект [CContextMenuManager.](../../mfc/reference/ccontextmenumanager-class.md)

```
CContextMenuManager();
```

### <a name="remarks"></a>Примечания

В большинстве случаев не `CContextMenuManager` следует создавать вручную. Рамки приложения создают `CContextMenuManager` объект. Вы должны позвонить [в CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) во время инициализации приложения. Чтобы получить указатель для менеджера контекста, позвоните [cWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).

## <a name="ccontextmenumanagergetmenubyid"></a><a name="getmenubyid"></a>Контекстменуменеджер:Гетменомебид

Возвращает ручку в меню, связанную с идентификатором ресурса.

```
HMENU GetMenuById(UINT nMenuResId) const;
```

### <a name="parameters"></a>Параметры

*nMenuResId*<br/>
(в) Идентификатор ресурса для меню.

### <a name="return-value"></a>Возвращаемое значение

Ручка к связанного `NULL` меню или если меню не найдено.

## <a name="ccontextmenumanagergetmenubyname"></a><a name="getmenubyname"></a>CContextMenuManager::GetMenubyname

Возвращает ручку в определенное меню.

```
HMENU GetMenuByName(
    LPCTSTR lpszName,
    UINT* puiOrigResID = NULL) const;
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
(в) Строка, содержащая название меню для извлечения.

*puiOrigResID*<br/>
(ваут) Указатель на UINT. Этот параметр содержит идентификатор ресурсов указанного меню, если найден.

### <a name="return-value"></a>Возвращаемое значение

Ручка в меню, которая соответствует имени, указанному *lpszName*. NULL, если нет меню под названием *lpszName*.

### <a name="remarks"></a>Примечания

Если этот метод находит меню, которое `GetMenuByName` соответствует *lpszName,* хранит идентификатор ресурса меню в параметре *puiOrigResID.*

## <a name="ccontextmenumanagergetmenunames"></a><a name="getmenunames"></a>CContextMenuManager::GetMenuNames

Возвращает список имен меню, добавленных в [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).

```cpp
void GetMenuNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Параметры

*listOfNames*<br/>
(ваут) Ссылка на параметр [CStringList.](../../mfc/reference/cstringlist-class.md) Этот метод записывает список имен меню по этому параметру.

## <a name="ccontextmenumanagerloadstate"></a><a name="loadstate"></a>CContextMenuManager::LoadState

Загружает информацию, связанную с [классом CContextMenuManager,](../../mfc/reference/ccontextmenumanager-class.md) из реестра Windows.

```
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Строка, содержащая относительный путь ключа реестра.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод успешен; в противном случае 0.

### <a name="remarks"></a>Примечания

Параметр *lpszProfileName* не является абсолютным путем для входа в реестр. Это относительный путь, который добавляется к концу ключа реестра по умолчанию для приложения. Чтобы получить или установить ключ реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.

Используйте метод [CContextMenuManager::SaveState,](#savestate) чтобы сохранить меню ярлыка в реестр.

## <a name="ccontextmenumanagerresetstate"></a><a name="resetstate"></a>CContextMenuManager::Resetstate

Очищает все элементы из меню ярлыка, связанных с [классом CContextMenuManager.](../../mfc/reference/ccontextmenumanager-class.md)

```
virtual BOOL ResetState();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод успешен; FALSE, если происходит сбой.

### <a name="remarks"></a>Примечания

Этот метод очищает всплывающие меню и удаляет их `CContextMenuManager`из .

## <a name="ccontextmenumanagersavestate"></a><a name="savestate"></a>CContextMenuManager::SaveState

Сохраняет информацию, связанную с [классом CContextMenuManager в](../../mfc/reference/ccontextmenumanager-class.md) реестре Windows.

```
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Строка, содержащая относительный путь ключа реестра.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если метод успешен; в противном случае 0.

### <a name="remarks"></a>Примечания

Параметр *lpszProfileName* не является абсолютным путем для входа в реестр. Это относительный путь, который добавляется к концу ключа реестра по умолчанию для приложения. Чтобы получить или установить ключ реестра по умолчанию, используйте методы [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) и [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) соответственно.

Используйте метод [CContextMenuManager::LoadState](#loadstate) для загрузки меню ярлыка из реестра.

## <a name="ccontextmenumanagersetdontcloseactivemenu"></a><a name="setdontcloseactivemenu"></a>CContextMenuManager::SetDontCloseActiveMenu

Контролирует, закрывает ли [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) активное всплывающее меню при отображении нового всплывающее меню.

```cpp
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```

### <a name="parameters"></a>Параметры

*bSet*<br/>
(в) Параметр Boolean, который контролирует, следует ли закрыть активное всплывающее меню. Значение TRUE указывает на то, что активное всплывающее меню не закрыто. FALSE указывает на то, что активное всплывающее меню закрыто.

### <a name="remarks"></a>Примечания

По умолчанию `CContextMenuManager` замыкает активное всплывающее меню.

## <a name="ccontextmenumanagershowpopupmenu"></a><a name="showpopupmenu"></a>CContextMenuManager::ShowPopupMenu

Отображает указанное меню ярлыка.

```
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bRightAlign = FALSE);

virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bOwnMessage = FALSE,
    BOOL bAutoDestroy = TRUE,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>Параметры

*uiMenuResId*<br/>
(в) Идентификатор ресурса меню, который будет отображать этот метод.

*x*<br/>
(в) Горизонтальное смещение меню ярлыков в координатах клиента.

*Y*<br/>
(в) Вертикальное смещение меню ярлыков в координатах клиента

*pWndВладелец*<br/>
(в) Указатель на родительское окно меню ярлыка.

*bOwnMessage*<br/>
(в) Параметр Boolean, указывающий, как направляются сообщения. Если *bOwnMessage* является FALSE, используется стандартная routing MFC. В противном *случае, pWndOwner* получает сообщения.

*hmenuPopup*<br/>
(в) Ручка меню, которую будет отображать этот метод.

*bAutoDestroy*<br/>
(в) Параметр Boolean, указывающий, будет ли меню автоматически уничтожено.

*bRightAlign*<br/>
(в) Параметр Boolean, указывающий на выравнивание элементов меню. Если *bRightAlign* является правдой, меню является право выровнены для справа налево порядка чтения.

### <a name="return-value"></a>Возвращаемое значение

Первый метод перегрузки возвращается ненулевой, если метод показывает меню успешно; в противном случае 0. Перегрузка второго метода возвращает указатель [cmFCPopupMenu,](../../mfc/reference/cmfcpopupmenu-class.md) если меню ярлыка отображается правильно; в противном случае NULL.

### <a name="remarks"></a>Примечания

Этот метод напоминает метод [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) в том, что оба метода отображают меню ярлыка. Тем `TrackPopupMenu` не менее, возвращаетиндекс выбранной команды меню.

Если параметр *bAutoDestroy* является FALSE, необходимо вручную вызвать унаследованный `DestroyMenu` метод для выпуска ресурсов памяти. По умолчанию `ShowPopupMenu` реализация не использует параметр *bAutoDestroy*. Он предназначен для использования в будущем или `CContextMenuManager` для пользовательских классов, полученных из класса.

## <a name="ccontextmenumanagertrackpopupmenu"></a><a name="trackpopupmenu"></a>CContextMenuManager::TrackPopupMenu

Отображает указанное меню ярлыка и возвращает индекс выбранной команды меню ярлыка.

```
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,
    int x,
    int y,
    CWnd* pWndOwner,
    BOOL bRightAlign = FALSE);
```

### <a name="parameters"></a>Параметры

*hmenuPopup*<br/>
(в) Ручка меню ярлыка, отображаемого этим методом.

*x*<br/>
(в) Горизонтальное смещение меню ярлыков в координатах клиента.

*Y*<br/>
(в) Вертикальное смещение меню ярлыка в координатах клиента.

*pWndВладелец*<br/>
(в) Указатель на родительское окно меню ярлыка.

*bRightAlign*<br/>
(в) Параметр Boolean, указывающий, как выравниваются элементы меню. Если *bRightAlign* является правдой, меню является право выровнены для справа налево порядка чтения. Если *bRightAlign* является FALSE, меню левое выравнивание для слева направо порядка чтения.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды меню, который выбирает пользователь; 0, если пользователь закрывает меню ярлыка, не выбирая команду меню.

### <a name="remarks"></a>Примечания

Этот метод функционирует как модальный вызов для отображения меню ярлыка. Приложение не будет продолжать следующую строку в коде до тех пор, пока пользователь не закроет меню ярлыка или не выберет команду. Альтернативный метод, который можно использовать для отображения меню ярлыка [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Этот метод не является модальным вызовом и не вернет идентификатор выбранной команды.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)
