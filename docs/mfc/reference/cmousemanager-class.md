---
title: Класс CMouseManager
ms.date: 11/04/2016
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
ms.openlocfilehash: 1394a1b47a86022e37b11e032b87ee2a2a369862
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752811"
---
# <a name="cmousemanager-class"></a>Класс CMouseManager

Позволяет пользователю связывать различные команды с определенным объектом [CView,](../../mfc/reference/cview-class.md) когда пользователь дважды щелкает внутри этого представления.

## <a name="syntax"></a>Синтаксис

```
class CMouseManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMouseManager::AddView](#addview)|Добавляет `CView` объект в поле диалога **настройки.** Коробка диалога **настройки** позволяет пользователю связать двойной клик с командой для каждого из перечисленных представлений.|
|[CMouseManager::GetViewDblClickCommand](#getviewdblclickcommand)|Возвращает команду, которая выполняется при двойном клике пользователя в предоставленном представлении.|
|[CMouseManager::GetViewIconId](#getviewiconid)|Возвращает значок, связанный с предоставленным идентификатором представления.|
|[CMouseManager::GetViewidbyname](#getviewidbyname)|Возвращает идентификатор представления, связанный с предоставленным именем представления.|
|[CMouseManager::GetViewNames](#getviewnames)|Извлекает список всех добавленных имен представления.|
|[CMouseManager::LoadState](#loadstate)|Загружает `CMouseManager` состояние из реестра Windows.|
|[CMouseManager::SaveState](#savestate)|Записывает `CMouseManager` состояние в реестр Windows.|
|[CMouseManager::SetCommandForDblClk](#setcommandfordblclk)|Associates предоставленную команду и предоставленное представление.|

## <a name="remarks"></a>Примечания

Класс `CMouseManager` поддерживает коллекцию `CView` объектов. Каждое представление идентифицируется по имени и идентификатору. Эти представления отображаются в поле диалога **настройки.** Пользователь может изменить команду, связанную с любым представлением, через поле диалога **настройки.** Связанная команда выполняется при двойном клике пользователя в этом представлении. Чтобы поддержать это с точки зрения кодирования, необходимо обработать WM_LBUTTONDBLCLK сообщение и вызвать функцию [CWinAppEx::OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) в коде для этого `CView` объекта.

Объект не должен `CMouseManager` создаваться вручную. Он будет создан в рамках вашего приложения. Он также будет уничтожаться автоматически, когда пользователь выходит из приложения. Чтобы получить указатель для мыши менеджера для вашего приложения, позвоните [CWinAppEx::GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>Требования

**Заголовок:** afxmousemanager.h

## <a name="cmousemanageraddview"></a><a name="addview"></a>CMouseManager::AddView

Регистрирует объект [CView](../../mfc/reference/cview-class.md) с [классом CMouseManager](../../mfc/reference/cmousemanager-class.md) для поддержки пользовательского поведения мыши.

```
BOOL AddView(
    int iViewId,
    UINT uiViewNameResId,
    UINT uiIconId = 0);

BOOL AddView(
    int iId,
    LPCTSTR lpszViewName,
    UINT uiIconId = 0);
```

### <a name="parameters"></a>Параметры

*iViewId*<br/>
(в) Идентификатор представления.

*uiViewNameResId*<br/>
(в) Идентификатор строки ресурса, который ссылается на имя представления.

*uiIconId*<br/>
(в) Идентификатор значка представления.

*Iid*<br/>
(в) Идентификатор представления.

*lpszViewName*<br/>
(в) Имя представления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Для поддержки пользовательского поведения мыши вид должен `CMouseManager` быть зарегистрирован с объектом. Любой объект, `CView` полученный из класса, может быть зарегистрирован менеджером мыши. Строка и значок, связанные с представлением, отображаются во вкладке **мыши** в поле **настраиваемых** диалогов.

Это ответственность программиста для создания и поддержания идентификаторов представления, таких как *iViewId* и *iId*.

Для получения дополнительной информации о том, как обеспечить пользовательское поведение мыши, см [Клавиатура и мышь настройки](../../mfc/keyboard-and-mouse-customization.md).

### <a name="example"></a>Пример

В следующем примере показано, как получить `CMouseManager` указатель объекта `CWinAppEx::GetMouseManager` с `AddView` помощью `CMouseManager` метода и метода в классе. Этот фрагмент кода является частью [образца Государственной коллекции.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

## <a name="cmousemanagergetviewdblclickcommand"></a><a name="getviewdblclickcommand"></a>CMouseManager::GetViewDblClickCommand

Возвращает команду, которая выполняется при двойном клике пользователя в предоставленном представлении.

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) Идентификатор представления.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор команды, если представление связано с командой; в противном случае 0.

## <a name="cmousemanagergetviewiconid"></a><a name="getviewiconid"></a>CMouseManager::GetViewIconId

Извлекает значок, связанный с идентификатором представления.

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>Параметры

*iViewId*<br/>
(в) Идентификатор представления.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор ресурса значок в случае успеха; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод не удастся, если представление не будет впервые зарегистрировано с помощью [CMouseManager::AddView](#addview).

## <a name="cmousemanagergetviewidbyname"></a><a name="getviewidbyname"></a>CMouseManager::GetViewidbyname

Извлекает идентификатор представления, связанный с именем представления.

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
(в) Имя представления.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор представления в случае успеха; в противном случае 0.

### <a name="remarks"></a>Примечания

Этот метод выполняет поиск по представлениям, зарегистрированным с помощью [CMouseManager::AddView](#addview).

## <a name="cmousemanagergetviewnames"></a><a name="getviewnames"></a>CMouseManager::GetViewNames

Извлекает список всех зарегистрированных имен представлений.

```cpp
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>Параметры

*listOfNames*<br/>
(ваут) Ссылка `CStringList` на объект.

### <a name="remarks"></a>Примечания

Этот метод заполняет `listOfNames` параметр именами всех представлений, зарегистрированных с помощью [CMouseManager::AddView](#addview).

## <a name="cmousemanagerloadstate"></a><a name="loadstate"></a>CMouseManager::LoadState

Загружает состояние [класса CMouseManager](../../mfc/reference/cmousemanager-class.md) из реестра.

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Путь ключа реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Информация о состоянии, загруженная из реестра, включает зарегистрированные представления, идентификаторы представления и связанные с ними команды. Если параметр *lpszProfileName* является NULL, `CMouseManager` эта функция загружает данные из расположения реестра по умолчанию, контролируемого [классом CWinAppEx.](../../mfc/reference/cwinappex-class.md)

В большинстве случаев вам не нужно вызывать эту функцию напрямую. Она называется как часть процесса инициализации рабочей области. Для получения дополнительной информации о процессе инициализации рабочего пространства [см. CWinAppEx:LoadState](../../mfc/reference/cwinappex-class.md#loadstate).

## <a name="cmousemanagersavestate"></a><a name="savestate"></a>CMouseManager::SaveState

Записывает состояние [класса CMouseManager](../../mfc/reference/cmousemanager-class.md) в реестр.

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Путь ключа реестра.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Государственная информация, записанная в реестр, включает в себя все зарегистрированные представления, идентификаторы представлений и связанные с ними команды. Если параметр *lpszProfileName* является NULL, `CMouseManager` эта функция записывает данные в расположение реестра по умолчанию, контролируемое [классом CWinAppEx.](../../mfc/reference/cwinappex-class.md)

В большинстве случаев вам не нужно вызывать эту функцию напрямую. Он называется как часть процесса сериализации рабочего пространства. Для получения дополнительной информации о процессе сериализации рабочего пространства [см. CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).

## <a name="cmousemanagersetcommandfordblclk"></a><a name="setcommandfordblclk"></a>CMouseManager::SetCommandForDblClk

Связывает пользовательскую команду с представлением, которое сначала зарегистрировано менеджером мыши.

```cpp
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>Параметры

*iViewId*<br/>
(в) Идентификатор представления.

*uiCmd*<br/>
[in] Идентификатор команды.

### <a name="remarks"></a>Примечания

Для того, чтобы связать пользовательскую команду с представлением, необходимо сначала зарегистрировать представление с помощью [CMouseManager::AddView](#addview). Метод `AddView` требует идентификатора представления в качестве параметра ввода. После регистрации представления можно `CMouseManager::SetCommandForDblClk` вызвать тот же параметр ввода `AddView`идентификатора представления, который был поставлен под номер. После этого, когда пользователь дважды щелкает мышь юму в зарегистрированном представлении, приложение выполняет команду, указанную *uiCmd.* Для поддержки пользовательского поведения мыши необходимо настроить представление, зарегистрированное менеджером мыши. Для получения дополнительной информации о пользовательском поведении мыши, см [Клавиатура и мышь настройки](../keyboard-and-mouse-customization.md).

Если *uiCmd* настроен до 0, указанное представление больше не связано с командой.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)<br/>
[Настройка мыши и клавиатуры](../../mfc/keyboard-and-mouse-customization.md)
