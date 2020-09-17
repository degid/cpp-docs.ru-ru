---
title: Класс CSnapInItemImpl
ms.date: 11/04/2016
f1_keywords:
- CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::CSnapInItemImpl
- ATLSNAP/ATL::CSnapInItemImpl::AddMenuItems
- ATLSNAP/ATL::CSnapInItemImpl::Command
- ATLSNAP/ATL::CSnapInItemImpl::CreatePropertyPages
- ATLSNAP/ATL::CSnapInItemImpl::FillData
- ATLSNAP/ATL::CSnapInItemImpl::GetResultPaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::GetResultViewType
- ATLSNAP/ATL::CSnapInItemImpl::GetScopePaneInfo
- ATLSNAP/ATL::CSnapInItemImpl::Notify
- ATLSNAP/ATL::CSnapInItemImpl::QueryPagesFor
- ATLSNAP/ATL::CSnapInItemImpl::SetMenuInsertionFlags
- ATLSNAP/ATL::CSnapInItemImpl::SetToolbarButtonInfo
- ATLSNAP/ATL::CSnapInItemImpl::UpdateMenuState
- ATLSNAP/ATL::CSnapInItemImpl::UpdateToolbarButton
- ATLSNAP/ATL::CSnapInItemImpl::m_bstrDisplayName
- ATLSNAP/ATL::CSnapInItemImpl::m_resultDataItem
- ATLSNAP/ATL::CSnapInItemImpl::m_scopeDataItem
helpviewer_keywords:
- snap-ins, data items
- snap-ins, ATL support for
- CSnapInItemImpl class
- snap-ins
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
ms.openlocfilehash: 04eeba0239789b9f3220b7bfece3eb41dc7f2826
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746427"
---
# <a name="csnapinitemimpl-class"></a>Класс CSnapInItemImpl

Этот класс предоставляет методы для реализации объекта узла оснастки.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <class T, BOOL bIsExtension = FALSE>
class ATL_NO_VTABLE CSnapInItemImpl : public CSnapInItem
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, полученный из `CSnapInItemImpl`.

*bIsExtension*<br/>
TRUE, если объект является расширением оснастки; в противном случае FALSE.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSnapInItemImpl::CSnapInItemImpl](#csnapinitemimpl)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSnapInItemImpl::AddMenuitems](#addmenuitems)|Добавляет элементы меню в контекстное меню.|
|[CSnapInItemImpl::Команда](#command)|Вызывается консолью при выборе пользовательского элемента меню.|
|[CSnapInItemImpl::CreatePropertyPages](#createpropertypages)|Добавляет страницы в лист свойств оснастки.|
|[CSnapInItemImpl:FillData](#filldata)|Копирует информацию об объекте оснастки в указанный поток.|
|[CSnapInItemImpl::GetResultPaneInfo](#getresultpaneinfo)|Извлекает `RESULTDATAITEM` структуру оснастки.|
|[CSnapInItemImpl::GetResultViewType](#getresultviewtype)|Определяет тип представления, используемого в панели результата.|
|[CSnapInItemImpl::GetScopePaneInfo](#getscopepaneinfo)|Извлекает `SCOPEDATAITEM` структуру оснастки.|
|[CSnapInItemImpl::Уведомление](#notify)|Вызывается консолью, чтобы уведомить о привязке действий, предпринятых пользователем.|
|[CSnapInItemImpl::QueryPagesFor](#querypagesfor)|Вызывается, чтобы увидеть, поддерживает ли узла snap-in страницы свойств.|
|[CSnapInItemImpl::SetMenuInsertionFlags](#setmenuinsertionflags)|Изменяет флаги вставки меню для объекта оснастки.|
|[CSnapInItemImpl::SetToolbarButtonInfo](#settoolbarbuttoninfo)|Устанавливает информацию указанной кнопки панели инструментов.|
|[CSnapInItemImpl::UpdateMenuState](#updatemenustate)|Обновление состояния элемента контекстного меню.|
|[CSnapInItemImpl::UpdateToolbarButton](#updatetoolbarbutton)|Обновляет состояние указанной кнопки панели инструментов.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CSnapInItemImpl::m_bstrDisplayName](#m_bstrdisplayname)|Название объекта сотового в.|
|[CSnapInItemImpl::m_resultDataItem](#m_resultdataitem)|Структура `RESULTDATAITEM` Windows, используемая объектом. `CSnapInItemImpl`|
|[CSnapInItemImpl::m_scopeDataItem](#m_scopedataitem)|Структура `SCOPEDATAITEM` Windows, используемая объектом. `CSnapInItemImpl`|

## <a name="remarks"></a>Примечания

`CSnapInItemImpl`обеспечивает базовую реализацию для объекта узла оснастки, например добавление элементов меню и баров инструментов, а также переадресовывание команд для узла оснастки на соответствующую функцию обработчика. Эти функции реализованы с использованием нескольких различных интерфейсов и типов карт. Реализация по умолчанию обрабатывает уведомления, отправленные объекту узла, определяя правильный экземпляр производного класса, а затем перенаправляя сообщение в правильный экземпляр.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CSnapInItem`

`CSnapInItemImpl`

## <a name="requirements"></a>Требования

**Заголовок:** atlsnap.h

## <a name="csnapinitemimpladdmenuitems"></a><a name="addmenuitems"></a>CSnapInItemImpl::AddMenuitems

Этот метод реализует функцию Win32 [IExtendContextMenu::AddMenuItems](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-addmenuitems).

```
AddMenuItems(
    LPCONTEXTMENUCALLBACK piCallback,
    long* pInsertionAllowed,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Параметры

*piCallback*<br/>
(в) Указатель на `IContextMenuCallback` то, что можно добавить элементы в контекстное меню.

*pInsertionРазрешено*<br/>
(в, вне) Определяет точки вставки Microsoft Management Console (MMC), определяемые в меню. Это может быть сочетание следующих флагов:

- CCM_INSERTIONALLOWED_TOP элементы могут быть вставлены в верхней части контекстного меню.

- CCM_INSERTIONALLOWED_NEW элементы могут быть вставлены в Создать новый подменю.

- CCM_INSERTIONALLOWED_TASK элементы могут быть вставлены в подменю задачи.

- CCM_INSERTIONALLOWED_VIEW элементы могут быть вставлены в меню представления панели инструментов или в подменю представления меню контекста панели результатов.

*type*<br/>
(в) Определяет тип объекта. Может иметь одно из следующих значений:

- CCT_SCOPE объект данных для контекста панели области.

- CCT_RESULT объект данных для контекста панели результатов.

- CCT_SNAPIN_MANAGER объект данных для контекста менеджера оснастки.

- CCT_UNINITIALIZED объект data имеет недействительный тип.

## <a name="csnapinitemimplcommand"></a><a name="command"></a>CSnapInItemImpl::Команда

Этот метод реализует функцию Win32 [IExtendContextMenu::Command](/windows/win32/api/mmc/nf-mmc-iextendcontextmenu-command).

```
Command(long lCommandID, DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Параметры

*lCommandID*<br/>
(в) Определяет идентификатор команды элемента меню.

*type*<br/>
(в) Определяет тип объекта. Может иметь одно из следующих значений:

- CCT_SCOPE объект данных для контекста панели области.

- CCT_RESULT объект данных для контекста панели результатов.

- CCT_SNAPIN_MANAGER объект данных для контекста менеджера оснастки.

- CCT_UNINITIALIZED объект data имеет недействительный тип.

## <a name="csnapinitemimplcreatepropertypages"></a><a name="createpropertypages"></a>CSnapInItemImpl::CreatePropertyPages

Этот метод реализует функцию Win32 [IExtendPropertySheet::CreatePropertyPages](/windows/win32/api/mmc/nn-mmc-iextendpropertysheet2).

```
CreatePropertyPages(
    LPPROPERTYSHEETCALLBACK lpProvider,
    long handle,
    IUnknown* pUnk,
    DATA_OBJECT_TYPES type);
```

### <a name="parameters"></a>Параметры

*lpProvider*<br/>
[in] Указатель на интерфейс `IPropertySheetCallback`.

*Обрабатывать*<br/>
(в) Определяет ручку, используемую для маршрутизания MMCN_PROPERTY_CHANGE сообщения уведомлений в соответствующий класс данных.

*Панк*<br/>
(в) Указатель на `IExtendPropertySheet` интерфейс объекта, содержащего контекстную информацию о узлах.

*type*<br/>
(в) Определяет тип объекта. Может иметь одно из следующих значений:

- CCT_SCOPE объект данных для контекста панели области.

- CCT_RESULT объект данных для контекста панели результатов.

- CCT_SNAPIN_MANAGER объект данных для контекста менеджера оснастки.

- CCT_UNINITIALIZED объект data имеет недействительный тип.

## <a name="csnapinitemimplcsnapinitemimpl"></a><a name="csnapinitemimpl"></a>CSnapInItemImpl::CSnapInItemImpl

Формирует объект `CSnapInItemImpl`.

```
CSnapInItemImpl();
```

## <a name="csnapinitemimplfilldata"></a><a name="filldata"></a>CSnapInItemImpl:FillData

Эта функция называется для получения информации о элементе.

```
FillData(CLIPFORMAT cf, LPSTREAM pStream);
```

### <a name="parameters"></a>Параметры

*CF*<br/>
(в) Формат (текст, богатый текст или богатый текст с элементами OLE) Clipboard.

*pStream*<br/>
(в) Указатель на поток, содержащий данные объекта.

### <a name="remarks"></a>Примечания

Чтобы правильно реализовать эту функцию, скопируйте правильную информацию в потоке *(pStream),* в зависимости от формата Clipboard, указанного *cf.*

## <a name="csnapinitemimplgetresultviewtype"></a><a name="getresultviewtype"></a>CSnapInItemImpl::GetResultViewType

Вызов ими функции для получения типа представления для итогового панели объекта оснастки.

```
GetResultViewType(
    LPOLESTR* ppViewType,
    long* pViewOptions);
```

### <a name="parameters"></a>Параметры

*ppViewType*<br/>
(ваут) Указатель на адрес возвращенного типа представления.

*pViewOptions*<br/>
(ваут) Указатель на MMC_VIEW_OPTIONS перечисление, которое обеспечивает консоль с опциями, указанными владеющим оснастки в. Значение может быть одним из следующих.

- MMC_VIEW_OPTIONS_NOLISTVIEWS 0x00000001 говорит консоли воздерживаться от представления стандартных вариантов представления списка в меню **View.** Позволяет оснастки в отображать свои собственные пользовательские представления только в панели представления результата. Это единственный вариант флага, определенный в настоящее время.

- MMC_VIEW_OPTIONS_NONE No 0 Позволяет параметры представления по умолчанию.

## <a name="csnapinitemimplgetscopepaneinfo"></a><a name="getscopepaneinfo"></a>CSnapInItemImpl::GetScopePaneInfo

Вызовите эту функцию, чтобы получить структуру `SCOPEDATAITEM` оснастки.

```
GetScopePaneInfo (SCOPEDATAITEM* pScopeDataItem);
```

### <a name="parameters"></a>Параметры

*pScopeDataItem*<br/>
(ваут) Указатель на `SCOPEDATAITEM` структуру `CSnapInItemImpl` объекта.

## <a name="csnapinitemimplgetresultpaneinfo"></a><a name="getresultpaneinfo"></a>CSnapInItemImpl::GetResultPaneInfo

Вызовите эту функцию, чтобы получить структуру `RESULTDATAITEM` оснастки.

```
GetResultPaneInfo (RESULTDATAITEM* pResultDataItem);
```

### <a name="parameters"></a>Параметры

*pResultDataItem*<br/>
(ваут) Указатель на `RESULTDATAITEM` структуру `CSnapInItemImpl` объекта.

## <a name="csnapinitemimplm_bstrdisplayname"></a><a name="m_bstrdisplayname"></a>CSnapInItemImpl::m_bstrDisplayName

Содержит строку, отображаемую для элемента узла.

```
CComBSTR m_bstrDisplayName;
```

## <a name="csnapinitemimplm_scopedataitem"></a><a name="m_scopedataitem"></a>CSnapInItemImpl::m_scopeDataItem

Структура `SCOPEDATAITEM` объекта данных.

```
SCOPEDATAITEM m_scopeDataItem;
```

## <a name="csnapinitemimplm_resultdataitem"></a><a name="m_resultdataitem"></a>CSnapInItemImpl::m_resultDataItem

Структура [RESULTDATAITEM](/windows/win32/api/mmc/ns-mmc-resultdataitem) объекта данных.

```
RESULTDATAITEM m_resultDataItem;
```

## <a name="csnapinitemimplnotify"></a><a name="notify"></a>CSnapInItemImpl::Уведомление

Вызывается, когда объект оснастки действует на пользователя.

```
STDMETHOD(Notify)(
    MMC_NOTIFY_TYPE event,
    long arg,
    long param,
    IComponentData* pComponentData,
    IComponent* pComponent,
    DATA_OBJECT_TYPES type) = 0;
```

### <a name="parameters"></a>Параметры

*event*<br/>
(в) Идентифицирует действие, предпринятое пользователем. Возможны следующие уведомления:

- MMCN_ACTIVATE Отправлено при активации и отключении окна.

- MMCN_ADD_IMAGES отправлены, чтобы добавить изображения в панель результата.

- MMCN_BTN_CLICK отправлено, когда пользователь нажимает одну из кнопок панели инструментов.

- MMCN_CLICK отправлено, когда пользователь нажимает кнопку мыши на элемент езды представления списка.

- MMCN_DBLCLICK Отправлено, когда пользователь дважды нажимает кнопку мыши на элемент езды представления списка.

- MMCN_DELETE отправлено сообщить о том, что объект должен быть удален.

- MMCN_EXPAND Отправлено, когда папка должна быть расширена или заключена.

- MMCN_MINIMIZED Отправлено, когда окно сводится к минимуму или максимизируется.

- MMCN_PROPERTY_CHANGE отправлено уведомлять объект оснастки о том, что представление объекта оснастки вот-вот изменится.

- MMCN_REMOVE_CHILDREN отправлено, когда оснастка должна удалить все поддерево, добавленное под указанным узлом.

- MMCN_RENAME отправлен в первый раз, чтобы запрос на переименование и второй раз, чтобы сделать переименование.

- MMCN_SELECT отправлено при выборе элемента в области действия или панели представления результата.

- MMCN_SHOW Отправлено, когда элемент области выбран или отбирается в первый раз.

- MMCN_VIEW_CHANGE отправлено при повторном сходе, возможное обновление всех представлений при изменении.

*Arg*<br/>
(в) Зависит от типа уведомления.

*Param*<br/>
(в) Зависит от типа уведомления.

*pComponentData*<br/>
(ваут) Указатель на реализацию `IComponentData`объекта. Этот параметр является NULL, если уведомление `IComponentData::Notify`не пересылается из.

*pКомпонент*<br/>
(ваут) Указатель на объект, который `IComponent`реализует. Этот параметр является NULL, если уведомление `IComponent::Notify`не пересылается из.

*type*<br/>
(в) Определяет тип объекта. Может иметь одно из следующих значений:

- CCT_SCOPE объект данных для контекста панели области.

- CCT_RESULT объект данных для контекста панели результатов.

- CCT_SNAPIN_MANAGER объект данных для контекста менеджера оснастки.

- CCT_UNINITIALIZED объект data имеет недействительный тип.

## <a name="csnapinitemimplquerypagesfor"></a><a name="querypagesfor"></a>CSnapInItemImpl::QueryPagesFor

Вызывается, чтобы увидеть, поддерживает ли узла snap-in страницы свойств.

```
QueryPagesFor(DATA_OBJECT_TYPES type);
```

## <a name="csnapinitemimplsetmenuinsertionflags"></a><a name="setmenuinsertionflags"></a>CSnapInItemImpl::SetMenuInsertionFlags

Вызовите эту функцию, чтобы изменить флаги вставки меню, указанные *pInsertionAllowed,* для объекта оснастки.

```cpp
void SetMenuInsertionFlags(
    bool bBeforeInsertion,
    long* pInsertionAllowed);
```

### <a name="parameters"></a>Параметры

*bПередвайктии*<br/>
(в) Nonzero, если функция должна быть вызвана до добавления элементов в контекстное меню; в противном случае 0.

*pInsertionРазрешено*<br/>
(в, вне) Определяет точки вставки Microsoft Management Console (MMC), определяемые в меню. Это может быть сочетание следующих флагов:

- CCM_INSERTIONALLOWED_TOP элементы могут быть вставлены в верхней части контекстного меню.

- CCM_INSERTIONALLOWED_NEW элементы могут быть вставлены в Создать новый подменю.

- CCM_INSERTIONALLOWED_TASK элементы могут быть вставлены в подменю задачи.

- CCM_INSERTIONALLOWED_VIEW элементы могут быть вставлены в меню представления панели инструментов или в подменю представления меню контекста панели результатов.

### <a name="remarks"></a>Примечания

При разработке первичного набора ввода можно сбросить любой из флагов вставки, чтобы ограничить тип элементов меню, которые может добавить стороннее расширение. Например, основной оснастки может очистить CCM_INSERTIONALLOWED_NEW флаг, чтобы предотвратить расширение от добавления своих собственных Создать новые элементы меню.

Вы не должны пытаться установить биты в *pInsertionAllowed,* которые были первоначально очищены. Будущие версии MMC могут использовать биты, которые в настоящее время не определены, поэтому не следует изменять биты, которые в настоящее время не определены.

## <a name="csnapinitemimplsettoolbarbuttoninfo"></a><a name="settoolbarbuttoninfo"></a>CSnapInItemImpl::SetToolbarButtonInfo

Вызовите эту функцию, чтобы изменить любые стили кнопки панели инструментов, объекта оснастки, прежде чем панель инструментов будет создана.

```cpp
void SetToolbarButtonInfo(
    UINT id,
    BYTE* fsState,
    BYTE* fsType);
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
(в) Идентификатор кнопки панели инструментов, который будет установлен.

*fsState*<br/>
(в) Государственные флаги кнопки. Может быть один или несколько из следующих:

- TBSTATE_CHECKED Кнопка имеет TBSTYLE_CHECKED стиль и нажата.

- TBSTATE_ENABLED кнопка принимает пользовательский ввод. Кнопка, которая не имеет этого состояния, не принимает пользовательский ввод и седой.

- TBSTATE_HIDDEN Кнопка не видна и не может принимать пользовательский вход.

- TBSTATE_INDETERMINATE Кнопка серая.

- TBSTATE_PRESSED Кнопка нажата.

- TBSTATE_WRAP разрыв линии следует за кнопкой. Кнопка также должна иметь TBSTATE_ENABLED.

*fsType*<br/>
(в) Государственные флаги кнопки. Может быть один или несколько из следующих:

- TBSTYLE_BUTTON создает стандартную кнопку.

- TBSTYLE_CHECK создает кнопку, которая переключается между нажатыми и не нажатыми состояниями каждый раз, когда пользователь нажимает на нее. Кнопка имеет другой цвет фона, когда она находится в нажатом состоянии.

- TBSTYLE_CHECKGROUP создает кнопку проверки, которая остается нажатой до тех пор, пока не будет нажата другая кнопка в группе.

- TBSTYLE_GROUP создает кнопку, которая остается нажатой до тех пор, пока не будет нажата другая кнопка в группе.

- TBSTYLE_SEP создает сепаратор, обеспечивая небольшой зазор между группами кнопок. Кнопка с этим стилем не получает ввода пользователей.

## <a name="csnapinitemimplupdatemenustate"></a><a name="updatemenustate"></a>CSnapInItemImpl::UpdateMenuState

Вызовите эту функцию, чтобы изменить элемент меню, прежде чем он будет вставлен в контекстное меню объекта привязки.

```cpp
void UpdateMenuState(
    UINT id,
    LPTSTR pBuf,
    UINT* flags);
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
(в) Идентификатор элемента меню, который будет установлен.

*pBuf*<br/>
(в) Указатель на строку для элемента меню, который будет обновляться.

*flags*<br/>
(в) Определяет новые государственные флаги. Это может быть сочетание следующих флагов:

- MF_POPUP указывает, что это подменю в контексте меню. Элементы меню, точки вставки и дальнейшие подменю могут `lCommandID` быть `IInsertionPointID`добавлены в этот подменю, используя его в качестве .

- MF_BITMAP и MF_OWNERDRAW Эти флаги не допускаются и приведут к возврату стоимости E_INVALIDARG.

- MF_SEPARATOR рисует горизонтальную разделительную линию. Добавлять элементы меню с MF_SEPARATOR набором разрешается только `IContextMenuProvider` в меню.

- MF_CHECKED устанавливает галочку рядом с пунктом меню.

- MF_DISABLED отменяет элемент меню, поэтому его нельзя выбрать, но флаг не серый.

- MF_ENABLED включает элемент меню, чтобы он мог быть выбран, восстанавливая его из серого состояния.

- MF_GRAYED отменяет элемент меню, седой его, чтобы он не может быть выбран.

- MF_MENUBARBREAK функции так же, как MF_MENUBREAK флаг для панели меню. Для меню выпадающих, подменю или меню ярлыка новый столбец отделен от старого столбца вертикальной линией.

- MF_MENUBREAK помещает элемент в новую строку (для панели меню) или в новую колонку (для меню выпадения, подменю или меню ярлыка) без разделения столбцов.

- MF_UNCHECKED не помещает галоценку рядом с товаром (по умолчанию).

Следующие группы флагов не могут быть использованы вместе:

- MF_DISABLED, MF_ENABLED и MF_GRAYED.

- MF_MENUBARBREAK и MF_MENUBREAK.

- MF_CHECKED и MF_UNCHECKED.

## <a name="csnapinitemimplupdatetoolbarbutton"></a><a name="updatetoolbarbutton"></a>CSnapInItemImpl::UpdateToolbarButton

Вызовите эту функцию, чтобы изменить кнопку панели инструментов, объекта оснастки, прежде чем она отображается.

```
BOOL UpdateToolbarButton(UINT id, BYTE fsState);
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
Уфиксирует идентификатор кнопки кнопки для обновления.

*fsState*<br/>
Определяет состояние кнопки панели инструментов. Если это состояние должно быть установлено, верните TRUE. Это может быть сочетание следующих флагов:

- КНОПКа ENABLED принимает пользовательский ввод. Кнопка, которая не имеет этого состояния, не принимает пользовательский ввод и седой.

- CHECKED Кнопка имеет стиль CHECKED и нажимается.

- HIDDEN Кнопка не видна и не может принимать пользовательский вход.

- INDETERMINATE Кнопка серая.

- BUTTONPRESSED Кнопка нажата.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
