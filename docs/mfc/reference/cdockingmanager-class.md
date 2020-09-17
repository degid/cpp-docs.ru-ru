---
title: Класс CDockingManager
ms.date: 11/04/2016
f1_keywords:
- CDockingManager
- AFXDOCKINGMANAGER/CDockingManager
- AFXDOCKINGMANAGER/CDockingManager::AddDockSite
- AFXDOCKINGMANAGER/CDockingManager::AddHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::AddMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::AddPane
- AFXDOCKINGMANAGER/CDockingManager::AdjustDockingLayout
- AFXDOCKINGMANAGER/CDockingManager::AdjustPaneFrames
- AFXDOCKINGMANAGER/CDockingManager::AdjustRectToClientArea
- AFXDOCKINGMANAGER/CDockingManager::AlignAutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::AutoHidePane
- AFXDOCKINGMANAGER/CDockingManager::BringBarsToTop
- AFXDOCKINGMANAGER/CDockingManager::BuildPanesMenu
- AFXDOCKINGMANAGER/CDockingManager::CalcExpectedDockedRect
- AFXDOCKINGMANAGER/CDockingManager::Create
- AFXDOCKINGMANAGER/CDockingManager::DeterminePaneAndStatus
- AFXDOCKINGMANAGER/CDockingManager::DisableRestoreDockState
- AFXDOCKINGMANAGER/CDockingManager::DockPane
- AFXDOCKINGMANAGER/CDockingManager::DockPaneLeftOf
- AFXDOCKINGMANAGER/CDockingManager::EnableAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::EnableDocking
- AFXDOCKINGMANAGER/CDockingManager::EnableDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::EnablePaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::FindDockSite
- AFXDOCKINGMANAGER/CDockingManager::FindDockSiteByPane
- AFXDOCKINGMANAGER/CDockingManager::FindPaneByID
- AFXDOCKINGMANAGER/CDockingManager::FixupVirtualRects
- AFXDOCKINGMANAGER/CDockingManager::FrameFromPoint
- AFXDOCKINGMANAGER/CDockingManager::GetClientAreaBounds
- AFXDOCKINGMANAGER/CDockingManager::GetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::GetDockSiteFrameWnd
- AFXDOCKINGMANAGER/CDockingManager::GetEnabledAutoHideAlignment
- AFXDOCKINGMANAGER/CDockingManager::GetMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::GetOuterEdgeBounds
- AFXDOCKINGMANAGER/CDockingManager::GetPaneList
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManager
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingManagerPermanent
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::GetSmartDockingTheme
- AFXDOCKINGMANAGER/CDockingManager::HideAutoHidePanes
- AFXDOCKINGMANAGER/CDockingManager::InsertDockSite
- AFXDOCKINGMANAGER/CDockingManager::InsertPane
- AFXDOCKINGMANAGER/CDockingManager::IsDockSiteMenu
- AFXDOCKINGMANAGER/CDockingManager::IsInAdjustLayout
- AFXDOCKINGMANAGER/CDockingManager::IsOLEContainerMode
- AFXDOCKINGMANAGER/CDockingManager::IsPointNearDockSite
- AFXDOCKINGMANAGER/CDockingManager::IsPrintPreviewValid
- AFXDOCKINGMANAGER/CDockingManager::LoadState
- AFXDOCKINGMANAGER/CDockingManager::LockUpdate
- AFXDOCKINGMANAGER/CDockingManager::OnActivateFrame
- AFXDOCKINGMANAGER/CDockingManager::OnClosePopupMenu
- AFXDOCKINGMANAGER/CDockingManager::OnMoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::OnPaneContextMenu
- AFXDOCKINGMANAGER/CDockingManager::PaneFromPoint
- AFXDOCKINGMANAGER/CDockingManager::ProcessPaneContextMenuCommand
- AFXDOCKINGMANAGER/CDockingManager::RecalcLayout
- AFXDOCKINGMANAGER/CDockingManager::ReleaseEmptyPaneContainers
- AFXDOCKINGMANAGER/CDockingManager::RemoveHiddenMDITabbedBar
- AFXDOCKINGMANAGER/CDockingManager::RemoveMiniFrame
- AFXDOCKINGMANAGER/CDockingManager::RemovePaneFromDockManager
- AFXDOCKINGMANAGER/CDockingManager::ReplacePane
- AFXDOCKINGMANAGER/CDockingManager::ResortMiniFramesForZOrder
- AFXDOCKINGMANAGER/CDockingManager::SaveState
- AFXDOCKINGMANAGER/CDockingManager::SendMessageToMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::Serialize
- AFXDOCKINGMANAGER/CDockingManager::SetAutohideZOrder
- AFXDOCKINGMANAGER/CDockingManager::SetDockingMode
- AFXDOCKINGMANAGER/CDockingManager::SetDockState
- AFXDOCKINGMANAGER/CDockingManager::SetPrintPreviewMode
- AFXDOCKINGMANAGER/CDockingManager::SetSmartDockingParams
- AFXDOCKINGMANAGER/CDockingManager::ShowDelayShowMiniFrames
- AFXDOCKINGMANAGER/CDockingManager::ShowPanes
- AFXDOCKINGMANAGER/CDockingManager::StartSDocking
- AFXDOCKINGMANAGER/CDockingManager::StopSDocking
- AFXDOCKINGMANAGER/CDockingManager::m_bHideDockingBarsInContainerMode
- AFXDOCKINGMANAGER/CDockingManager::m_dockModeGlobal
- AFXDOCKINGMANAGER/CDockingManager::m_nDockSensitivity
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeDockingBarDock
- AFXDOCKINGMANAGER/CDockingManager::m_nTimeOutBeforeToolBarDock
helpviewer_keywords:
- CDockingManager [MFC], AddDockSite
- CDockingManager [MFC], AddHiddenMDITabbedBar
- CDockingManager [MFC], AddMiniFrame
- CDockingManager [MFC], AddPane
- CDockingManager [MFC], AdjustDockingLayout
- CDockingManager [MFC], AdjustPaneFrames
- CDockingManager [MFC], AdjustRectToClientArea
- CDockingManager [MFC], AlignAutoHidePane
- CDockingManager [MFC], AutoHidePane
- CDockingManager [MFC], BringBarsToTop
- CDockingManager [MFC], BuildPanesMenu
- CDockingManager [MFC], CalcExpectedDockedRect
- CDockingManager [MFC], Create
- CDockingManager [MFC], DeterminePaneAndStatus
- CDockingManager [MFC], DisableRestoreDockState
- CDockingManager [MFC], DockPane
- CDockingManager [MFC], DockPaneLeftOf
- CDockingManager [MFC], EnableAutoHidePanes
- CDockingManager [MFC], EnableDocking
- CDockingManager [MFC], EnableDockSiteMenu
- CDockingManager [MFC], EnablePaneContextMenu
- CDockingManager [MFC], FindDockSite
- CDockingManager [MFC], FindDockSiteByPane
- CDockingManager [MFC], FindPaneByID
- CDockingManager [MFC], FixupVirtualRects
- CDockingManager [MFC], FrameFromPoint
- CDockingManager [MFC], GetClientAreaBounds
- CDockingManager [MFC], GetDockingMode
- CDockingManager [MFC], GetDockSiteFrameWnd
- CDockingManager [MFC], GetEnabledAutoHideAlignment
- CDockingManager [MFC], GetMiniFrames
- CDockingManager [MFC], GetOuterEdgeBounds
- CDockingManager [MFC], GetPaneList
- CDockingManager [MFC], GetSmartDockingManager
- CDockingManager [MFC], GetSmartDockingManagerPermanent
- CDockingManager [MFC], GetSmartDockingParams
- CDockingManager [MFC], GetSmartDockingTheme
- CDockingManager [MFC], HideAutoHidePanes
- CDockingManager [MFC], InsertDockSite
- CDockingManager [MFC], InsertPane
- CDockingManager [MFC], IsDockSiteMenu
- CDockingManager [MFC], IsInAdjustLayout
- CDockingManager [MFC], IsOLEContainerMode
- CDockingManager [MFC], IsPointNearDockSite
- CDockingManager [MFC], IsPrintPreviewValid
- CDockingManager [MFC], LoadState
- CDockingManager [MFC], LockUpdate
- CDockingManager [MFC], OnActivateFrame
- CDockingManager [MFC], OnClosePopupMenu
- CDockingManager [MFC], OnMoveMiniFrame
- CDockingManager [MFC], OnPaneContextMenu
- CDockingManager [MFC], PaneFromPoint
- CDockingManager [MFC], ProcessPaneContextMenuCommand
- CDockingManager [MFC], RecalcLayout
- CDockingManager [MFC], ReleaseEmptyPaneContainers
- CDockingManager [MFC], RemoveHiddenMDITabbedBar
- CDockingManager [MFC], RemoveMiniFrame
- CDockingManager [MFC], RemovePaneFromDockManager
- CDockingManager [MFC], ReplacePane
- CDockingManager [MFC], ResortMiniFramesForZOrder
- CDockingManager [MFC], SaveState
- CDockingManager [MFC], SendMessageToMiniFrames
- CDockingManager [MFC], Serialize
- CDockingManager [MFC], SetAutohideZOrder
- CDockingManager [MFC], SetDockingMode
- CDockingManager [MFC], SetDockState
- CDockingManager [MFC], SetPrintPreviewMode
- CDockingManager [MFC], SetSmartDockingParams
- CDockingManager [MFC], ShowDelayShowMiniFrames
- CDockingManager [MFC], ShowPanes
- CDockingManager [MFC], StartSDocking
- CDockingManager [MFC], StopSDocking
- CDockingManager [MFC], m_bHideDockingBarsInContainerMode
- CDockingManager [MFC], m_dockModeGlobal
- CDockingManager [MFC], m_nDockSensitivity
- CDockingManager [MFC], m_nTimeOutBeforeDockingBarDock
- CDockingManager [MFC], m_nTimeOutBeforeToolBarDock
ms.assetid: 98e69c43-55d8-4f43-b861-4fda80ec1e32
ms.openlocfilehash: 76fd12b0817c99d0d08327f9d9156eadf3559dc5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753323"
---
# <a name="cdockingmanager-class"></a>Класс CDockingManager

Реализует базовую функциональность, которая контролирует макет закрепления в окне главного фрейма.

## <a name="syntax"></a>Синтаксис

```
class CDockingManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDockingManager::AddDockSite](#adddocksite)|Создает док-панель и добавляет его в список баров управления.|
|[CDockingManager::AddHiddenMDITabbedBar](#addhiddenmditabbedbar)|Добавляет ручку в панель панели в список скрытых стекалок MDI.|
|[CDockingManager::AddMiniFrame](#addminiframe)|Добавляет кадр в список мини-кадров.|
|[CDockingManager::AddPane](#addpane)|Регистрирует панель с менеджером стыковки.|
|[CdockingManager::AdjustDockingLayout](#adjustdockinglayout)|Пересчитывает и регулирует расположение всех стекол в окне рамы.|
|[CDockingManager::AdjustPaneFrames](#adjustpaneframes)|Вызывает отправку сообщения WM_NCCALCSIZE на все `CPaneFrameWnd` стекла и окна.|
|[CDockingManager::AdjusttToClientArea](#adjustrecttoclientarea)|Регулирует выравнивание прямоугольника.|
|[CDockingManager::AlignAutoHidePane](#alignautohidepane)|Изображки стыковочную панель в режиме автохайда, так что она занимает всю ширину или высоту клиентской области кадра в окружении док-станций.|
|[CDockingManager::AutoHidePane](#autohidepane)|Создает панель инструментов для автоматической ауторазии.|
|[CDockingManager::BringBarsToTop](#bringbarstotop)|Приносит пристыкованные бары, которые имеют указанное выравнивание к верхней части.|
|[CDockingManager::BuildPanesMenu](#buildpanesmenu)|Добавляет названия стыковочных стекол и панели инструментов в меню.|
|[CDockingManager::CalcExpectedDockedRect](#calcexpecteddockedrect)|Вычисляет ожидаемый прямоугольник пристыкованного окна.|
|[CDockingManager::Создание](#create)|Создает стыковку менеджера.|
|[CDockingManager::DeterminePaneAndStatus](#determinepaneandstatus)|Определяет панель, содержащую заданную точку, и ее статус стыковки.|
|[CDockingManager::DisableRestoreDockState](#disablerestoredockstate)|Позволяет или отсваивает загрузку макета стыковки из реестра.|
|[CDockingManager::DockPane](#dockpane)|Пристыкуется к стеку к другому стеку или к окну рамы.|
|[CDockingManager::DockPaneLeftOf](#dockpaneleftof)|Закрепляет область слева от другой области.|
|[CDockingManager::EnableAutoHidePanes](#enableautohidepanes)|Позволяет стыковку панели с основной рамой, создает док-панель и добавляет его в список баров управления.|
|[CDockingManager:EnableDocking](#enabledocking)|Создает док-панель и позволяет стыковки панели к основной раме.|
|[CDockingManager::EnableDockSiteMenu](#enabledocksitemenu)|Отображает дополнительную кнопку, которая открывает всплывающее меню на подписях всех стыковочных стекол.|
|[CDockingManager::EnablePaneContextMenu](#enablepanecontextmenu)|Сообщает библиотеке отобразить специальное контекстное меню, в которое есть список панели инструментов приложений и стыковочные панели, когда пользователь нажимает на правую кнопку мыши и библиотека обрабатывает WM_CONTEXTMENU сообщение.|
|[CDockingManager::FindDockSite](#finddocksite)|Извлекает панель, которая находится в указанном положении и имеет указанное выравнивание.|
|[CDockingManager::FindDockSiteByPane](#finddocksitebypane)|Возвращает панель, которая имеет идентификатор панели бара цели.|
|[CDockingManager::FindPaneByID](#findpanebyid)|Находит панель по указанному идентификатору управления.|
|[CDockingManager::FixupVirtualRects](#fixupvirtualrects)|Замещает все текущие позиции панели инструментов в виртуальные прямоугольники.|
|[CDockingManager::FrameFromPoint](#framefrompoint)|Возвращает кадр, содержащий заданную точку.|
|[CDockingManager::GetClientAreaBounds](#getclientareabounds)|Получает прямоугольник, содержащий границы клиентской области.|
|[CDockingManager::GetDockingMode](#getdockingmode)|Возвращает текущий режим стыковки.|
|[CDockingManager::GetDockSiteFrameWnd](#getdocksiteframewnd)|Получает указатель на родительскую оконную раму.|
|[CDockingManager::GetEnabledAutoHideAlignment](#getenabledautohidealignment)|Возвращает включенное выравнивание стекол.|
|[CDockingManager::GetMiniFrames](#getminiframes)|Получает список минифреймов.|
|[CDockingManager::GetOuterEdgeBounds](#getouteredgebounds)|Получает прямоугольник, содержащий внешние края рамы.|
|[CDockingManager::GetPaneList](#getpanelist)|Возвращает список стекол, принадлежащих менеджеру стыковки. Это включает в себя все плавающие стекла.|
|[CDockingManager::GetSmartDockingManager](#getsmartdockingmanager)|Получает указатель для смарт-менеджера стыковки.|
|[CDockingManager::GetSmartDockingManagerПостоянный](#getsmartdockingmanagerpermanent)|Получает указатель для смарт-менеджера стыковки.|
|[CDockingManager::GetSmartDockingParams](#getsmartdockingparams)|Возвращает параметры смарт-стыковки для менеджера стыковки.|
|[CDockingManager::GetSmartDockingTheme](#getsmartdockingtheme)|Статический метод, который возвращает тему, используемую для отображения интеллектуальных маркеров стыковки.|
|[CDockingManager::HideAutoHidePanes](#hideautohidepanes)|Скрывает панель, которая находится в режиме автохидирования.|
|[CDockingManager::InsertDockSite](#insertdocksite)|Создает док-панель и вставляет его в список контрольных баров.|
|[CDockingManager::InsertPane](#insertpane)|Вставляет элементную панель управления в список контрольных баров.|
|[CDockingManager::IsDockSiteMenu](#isdocksitemenu)|Уточняется, отображается ли всплывающее меню на подписях всех стекол.|
|[CdockingManager::IsInAdjustLayout](#isinadjustlayout)|Определяет, корректируются ли макеты всех стекол.|
|[CDockingManager::IsOLEContainerMode](#isolecontainermode)|Уточняется, находится ли диспетчер стыковки в режиме контейнера OLE.|
|[CDockingManager::IsPointNearDockSite](#ispointneardocksite)|Определяет, находится ли указанная точка рядом с местом дока.|
|[CDockingManager::IsPrintPreviewValid](#isprintpreviewvalid)|Определяет, установлен ли режим предварительного просмотра печати.|
|[CDockingManager::LoadState](#loadstate)|Загружает состояние менеджера стыковки из реестра.|
|[CDockingManager::LockUpdate](#lockupdate)|Запирает данное окно.|
|[CDockingManager::OnActivateFrame](#onactivateframe)|Вызывается фреймворком, когда окно кадра становится активным или деактивировано.|
|[CDockingManager::OnClosePopupMenu](#onclosepopupmenu)|Вызывается платформой, когда активное всплывающее меню обрабатывает сообщение WM_DESTROY.|
|[CDockingManager::OnMoveMiniFrame](#onmoveminiframe)|Вызывается по фреймворку для перемещения окна мини-рамки.|
|[CDockingManager::OnPaneContextMenu](#onpanecontextmenu)|Вызывается фреймворк, когда он строит меню, которое имеет список стекол.|
|[CDockingManager::PaneFromPoint](#panefrompoint)|Возвращает панель, содержащую заданную точку.|
|[CDockingManager::ProcessPaneContextMenuCommand](#processpanecontextmenucommand)|Вызывается фреймворком для выбора или очистки флажка для указанной команды и перерасчета макета показанной панели.|
|[CdockingManager::RecalcLayout](#recalclayout)|Пересчитывает внутреннюю компоновку элементов управления, присутствующих в списке элементов управления.|
|[CDockingManager::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)|Выпускает пустые панели контейнеров.|
|[CDockingManager::RemoveHiddenMDITabbedBar](#removehiddenmditabbedbar)|Удаляет указанное скрытое панельное стекло.|
|[CDockingManager::RemoveMiniFrame](#removeminiframe)|Удаляет указанную рамку из списка мини-кадров.|
|[CDockingManager::RemovePaneFromDockManager](#removepanefromdockmanager)|Отменяет панель и удаляет ее из списка в диспетчере стыковки.|
|[CDockingManager::ReplacePane](#replacepane)|Заменяет одну панель другой.|
|[CDockingManager::ResortMiniFramesFor](#resortminiframesforzorder)|Курорты кадры в списке мини-кадров.|
|[CDockingManager::SaveState](#savestate)|Сохраняет состояние менеджера стыковки в реестр.|
|[CDockingManager::SendMessageToMiniFrames](#sendmessagetominiframes)|Отправляет указанное сообщение на все мини-кадры.|
|[CDockingManager::Serialize](#serialize)|Записывает менеджера стыковки в архив. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CDockingManager::SetAutohide](#setautohidezorder)|Устанавливает размер, ширину и высоту руля и указанного стекла.|
|[CDockingManager::SetDockingMode](#setdockingmode)|Устанавливает режим стыковки.|
|[CDockingManager::SetDockState](#setdockstate)|Устанавливает состояние стыковки баров управления, мини-рам и аутохидных решеток.|
|[CDockingManager::SetPrintPreviewMode](#setprintpreviewmode)|Устанавливает режим предварительного просмотра печати баров, отображаемых в предварительном просмотре печати.|
|[CDockingManager::SetSmartDockingParams](#setsmartdockingparams)|Устанавливает параметры, определяющие поведение смарт-стыковки.|
|[CDockingManager::ShowDelayShowMiniКадры](#showdelayshowminiframes)|Показывает или скрывает окна мини-кадров.|
|[CDockingManager::ShowPanes](#showpanes)|Показывает или скрывает стекла управления и автоматики баров.|
|[CDockingManager::StartSDocking](#startsdocking)|Запускает смарт-стыковку указанного окна в соответствии с выравниванием менеджера смарт-стыковки.|
|[CDockingManager::StopSDocking](#stopsdocking)|Прекращает стыковку.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode)|Уточняется, прячет ли диспетчер стыковки стекла в режиме контейнера OLE.|
|[CDockingManager::m_dockModeGlobal](#m_dockmodeglobal)|Определяет глобальный режим стыковки.|
|[CDockingManager::m_nDockSensitivity](#m_ndocksensitivity)|Определяет чувствительность стыковки.|
|[CDockingManager::m_nTimeOutBeforeDockingBarDock](#m_ntimeoutbeforedockingbardock)|Определяет время, в миллисекундах, до стыковки стыковка в режиме немедленного стыковки.|
|[CDockingManager::m_nTimeOutBeforeToolBarDock](#m_ntimeoutbeforetoolbardock)|Определяет время, в миллисекундах, до того, как панель инструментов пристыкована к окну основной рамы.|

## <a name="remarks"></a>Примечания

Окно основной рамы автоматически создает и инициализирует этот класс.

Объект менеджера стыковки содержит список всех стекол, которые находятся в макете стыковки, а также список всех окон [CPaneFrameWnd,](../../mfc/reference/cpaneframewnd-class.md) которые принадлежат к главному окну кадра.

Класс `CDockingManager` реализует некоторые службы, которые можно использовать для `CPaneFrameWnd` поиска панели или окна. Обычно эти службы не называются напрямую, поскольку они завернуты в объект окна основной рамы. Для получения дополнительной [информации](../../mfc/reference/cpaneframewnd-class.md)см.

## <a name="customization-tips"></a>Советы по настройке

Следующие советы `CDockingManager` применяются к объектам:

- [Класс CDockingManager](../../mfc/reference/cdockingmanager-class.md) поддерживает эти режимы стыковки:

  - `AFX_DOCK_TYPE::DT_IMMEDIATE`

  - `AFX_DOCK_TYPE::DT_STANDARD`

  - `AFX_DOCK_TYPE::DT_SMART`

  Эти режимы стыковки определяются [CDockingManager::m_dockModeGlobal](#m_dockmodeglobal) и устанавливаются по телефону [CDockingManager::SetDockingMode](#setdockingmode).

- Если вы хотите создать неплаватемое, не изрешеханное стекло, позвоните в [CDockingManager::AddPane](#addpane) метод. Этот метод регистрирует панель с менеджером стыковки, который отвечает за расположение панели.

## <a name="example"></a>Пример

В следующем примере показано, как использовать `CDockingManager` различные методы в классе для настройки `CDockingManager` объекта. На примере показано, как отобразить дополнительную кнопку, открывающую всплывающее меню на подписях всех стыковочных стекол, и как установить режим стыковки объекта. Этот фрагмент кода является частью [образца демонстрации Visual Studio.](../../overview/visual-cpp-samples.md)

[!code-cpp[NVC_MFC_VisualStudioDemo#24](../../mfc/codesnippet/cpp/cdockingmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDockingManager](../../mfc/reference/cdockingmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxDockingManager.h

## <a name="cdockingmanageradddocksite"></a><a name="adddocksite"></a>CDockingManager::AddDockSite

Создает док-панель и добавляет его в список баров управления.

```
BOOL AddDockSite(
    const AFX_DOCKSITE_INFO& info,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>Параметры

*Информация*<br/>
(в) Ссылка на структуру информации, содержащую выравнивание док-панели.

*ppDockBar*<br/>
(ваут) Указатель на указатель на новую док-панель.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если док-панель была создана успешно; FALSE в противном случае.

## <a name="cdockingmanageraddhiddenmditabbedbar"></a><a name="addhiddenmditabbedbar"></a>CDockingManager::AddHiddenMDITabbedBar

Добавляет ручку в панель панели в список скрытых стекалок MDI.

```cpp
void AddHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Указатель на барное стекло

## <a name="cdockingmanageraddpane"></a><a name="addpane"></a>CDockingManager::AddPane

Регистрирует панель с менеджером стыковки.

```
BOOL AddPane(
    CBasePane* pWnd,
    BOOL bTail = TRUE,
    BOOL bAutoHide = FALSE,
    BOOL bInsertForOuterEdge = FALSE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в, вне) Определяет панель для добавления в стыковочный менеджер.

*bTail*<br/>
(в) TRUE, чтобы добавить панель в конце списка стекол для стыковки менеджера; в противном случае, FALSE.

*bAutoHide*<br/>
(в) Только для внутреннего использования. Всегда используйте значение по умолчанию FALSE.

*bInsertForOuterEdge*<br/>
(в) Только для внутреннего использования. Всегда используйте значение по умолчанию FALSE.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель была успешно зарегистрирована с менеджером стыковки; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Вызовите этот метод для регистрации неплавающих, неизменяемых стекол с менеджером стыковки. Если вы не зарегистрируете стекла, они не будут отображаться правильно, когда менеджер стыковки будет выложен.

## <a name="cdockingmanageradjustdockinglayout"></a><a name="adjustdockinglayout"></a>CdockingManager::AdjustDockingLayout

Пересчитывает и регулирует расположение всех стекол в окне рамы.

```
virtual void AdjustDockingLayout(HDWP hdwp = NULL);
```

### <a name="parameters"></a>Параметры

*hdwp*<br/>
(в) Определяет структуру отложенного положения окна. Дополнительные сведения см. в разделе [Типы данных Windows](/windows/win32/WinProg/windows-data-types).

### <a name="remarks"></a>Примечания

## <a name="cdockingmanageraddminiframe"></a><a name="addminiframe"></a>CDockingManager::AddMiniFrame

Добавляет кадр в список мини-кадров.

```
virtual BOOL AddMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Указатель на раму.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если кадр не в списке мини-кадров и был добавлен успешно; FALSE в противном случае.

## <a name="cdockingmanageradjustpaneframes"></a><a name="adjustpaneframes"></a>CDockingManager::AdjustPaneFrames

Вызывает отправку сообщения WM_NCCALCSIZE на все `CPaneFrameWnd` стекла и окна.

```
virtual void AdjustPaneFrames();
```

### <a name="remarks"></a>Примечания

## <a name="cdockingmanageradjustrecttoclientarea"></a><a name="adjustrecttoclientarea"></a>CDockingManager::AdjusttToClientArea

Регулирует выравнивание прямоугольника.

```
virtual BOOL AdjustRectToClientArea(
    CRect& rectResult,
    DWORD dwAlignment);
```

### <a name="parameters"></a>Параметры

*rectResult*<br/>
(в) Ссылка на `CRect` объект

*dwAlignment*<br/>
(в) Выравнивание `CRect` объекта

### <a name="return-value"></a>Возвращаемое значение

TRUE, если выравнивание `CRect` объекта было скорректировано; FALSE в противном случае.

### <a name="remarks"></a>Примечания

Параметр *dwAlignment* может иметь одно из следующих значений:

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

## <a name="cdockingmanageralignautohidepane"></a><a name="alignautohidepane"></a>CDockingManager::AlignAutoHidePane

Изображки стыковочную панель в режиме автохайда, так что она занимает всю ширину или высоту клиентской области кадра в окружении док-станций.

```cpp
void AlignAutoHidePane(
    CPaneDivider* pDefaultSlider,
    BOOL bIsVisible = TRUE);
```

### <a name="parameters"></a>Параметры

*pDefaultSlider*<br/>
(в) Стыковка ползунок панели.

*bIsVisible*<br/>
(в) ПРАВДА, если стыковка видна; FALSE в противном случае.

## <a name="cdockingmanagerautohidepane"></a><a name="autohidepane"></a>CDockingManager::AutoHidePane

Создает панель инструментов для автоматической ауторазии.

```
CMFCAutoHideToolBar* AutoHidePane(
    CDockablePane* pBar,
    CMFCAutoHideToolBar* pCurrAutoHideToolBar = NULL);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Указатель на барное стекло.

*pCurrAutoHideToolBar*<br/>
(в) Указатель на автоматическую панель инструментов.

### <a name="return-value"></a>Возвращаемое значение

NULL, если панель инструментов автоматического сокрытия не была создана; в противном случае указатель на новую панель инструментов.

## <a name="cdockingmanagerbringbarstotop"></a><a name="bringbarstotop"></a>CDockingManager::BringBarsToTop

Приносит пристыкованные бары, которые имеют указанное выравнивание к верхней части.

```cpp
void BringBarsToTop(
    DWORD dwAlignment = 0,
    BOOL bExcludeDockedBars = TRUE);
```

### <a name="parameters"></a>Параметры

*dwAlignment*<br/>
(в) Выравнивание док-баров, которые доводятся до верхней части других окон.

*bExcludeDockedBars*<br/>
(в) TRUE, чтобы исключить док-бары из на вершине; в противном случае FALSE.

## <a name="cdockingmanagerbuildpanesmenu"></a><a name="buildpanesmenu"></a>CDockingManager::BuildPanesMenu

Добавляет названия стыковочных стекол и панели инструментов в меню.

```cpp
void BuildPanesMenu(
    CMenu& menu,
    BOOL bToolbarsOnly);
```

### <a name="parameters"></a>Параметры

*Меню*<br/>
(в) Меню для добавления названий стыковочных стекол и панели инструментов.

*bToolbarsТолько*<br/>
(в) TRUE, чтобы добавить только имена панели инструментов в меню; FALSE в противном случае.

## <a name="cdockingmanagercalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>CDockingManager::CalcExpectedDockedRect

Вычисляет ожидаемый прямоугольник пристыкованного окна.

```cpp
void CalcExpectedDockedRect(
    CWnd* pWnd,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Указатель на окно для стыковки.

*ptMouse*<br/>
(в) Расположение мыши.

*rectResult*<br/>
(ваут) Расчетный прямоугольник.

*bDrawTab*<br/>
(в) TRUE, чтобы нарисовать вкладку; в противном случае FALSE.

*ppTargetBar*<br/>
(ваут) Указатель на указатель на целевое стекло.

### <a name="remarks"></a>Примечания

Этот метод вычисляет прямоугольник, который занимал бы окно, если пользователь перетащил окно в точку, указанную *ptMouse,* и пристыковал его туда.

## <a name="cdockingmanagercreate"></a><a name="create"></a>CDockingManager::Создание

Создает стыковку менеджера.

```
BOOL Create(CFrameWnd* pParentWnd);
```

### <a name="parameters"></a>Параметры

*pParentWnd*<br/>
(в) Указатель на родительский кадр менеджера стыковки. Это значение не должно быть NULL.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА всегда.

## <a name="cdockingmanagerdeterminepaneandstatus"></a><a name="determinepaneandstatus"></a>CDockingManager::DeterminePaneAndStatus

Определяет панель, содержащую заданную точку, и ее статус стыковки.

```
virtual AFX_CS_STATUS DeterminePaneAndStatus(
    CPoint pt,
    int nSensitivity,
    DWORD dwEnabledAlignment,
    CBasePane** ppTargetBar,
    const CBasePane* pBarToIgnore,
    const CBasePane* pBarToDock);
```

### <a name="parameters"></a>Параметры

*пт*<br/>
(в) Расположение панели для проверки.

*nЧувствительность*<br/>
(в) Значение для увеличения прямоугольника окна каждого проверенного стекла. Панель удовлетворяет критериям поиска, если данный пункт находится в этом увеличенном регионе.

*dwEnabledAlignment*<br/>
(в) Выравнивание стыковочного стекла.

*ppTargetBar*<br/>
(ваут) Указатель на указатель на целевое стекло.

*pbartoignore*<br/>
(в) Панель, которую игнорирует метод.

*пбартодок*<br/>
(в) Панель, которая пристыкована.

### <a name="return-value"></a>Возвращаемое значение

Статус стыковки.

### <a name="remarks"></a>Примечания

Статус стыковки может быть одним из следующих значений:

|AFX_CS_STATUS значение|Значение|
|---------------------------|-------------|
|CS_NOTHING|Указатель не над док-станцией. Таким образом, держать панель плавающей.|
|CS_DOCK_IMMEDIATELY|Указатель находится над местом дока в непосредственном режиме (DT_IMMEDIATE стиль включен), поэтому панель должна быть пристыкована немедленно.|
|CS_DELAY_DOCK|Указатель находится над док-сайт, который является еще одним стыковки панели или края основной рамы.|
|CS_DELAY_DOCK_TO_TAB|Указатель находится над сайтом дока, что приводит к стыковке панели в окне вкладок. Это происходит, когда мышь находится над подписью другого стыковочного стекла или над областью вкладки панели вкладки.|

## <a name="cdockingmanagerdisablerestoredockstate"></a><a name="disablerestoredockstate"></a>CDockingManager::DisableRestoreDockState

Позволяет или отсваивает загрузку макета стыковки из реестра.

```cpp
void DisableRestoreDockState(BOOL bDisable = TRUE);
```

### <a name="parameters"></a>Параметры

*bDisable*<br/>
(в) TRUE для отправления загрузки стыковочного компоновки из реестра; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Вызовите этот метод, когда необходимо сохранить текущую компоновку стыковочных спрей-панелей и панели инструментов при загрузке состояния приложения.

## <a name="cdockingmanagerdockpane"></a><a name="dockpane"></a>CDockingManager::DockPane

Пристыкуется к стеку к другому стеку или к окну рамы.

```cpp
void DockPane(
    CBasePane* pBar,
    UINT nDockBarID = 0,
    LPCRECT lpRect = NULL);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Указатель на бар панели достыковки.

*nDockBarID*<br/>
(в) Идентификатор бара для стыковки.

*lpRect*<br/>
(в) Прямоугольник назначения.

## <a name="cdockingmanagerdockpaneleftof"></a><a name="dockpaneleftof"></a>CDockingManager::DockPaneLeftOf

Закрепляет область слева от другой области.

```
BOOL DockPaneLeftOf(
    CPane* pBarToDock,
    CPane* pTargetBar);
```

### <a name="parameters"></a>Параметры

*пбартодок*<br/>
(в) Указатель на стекол, чтобы быть пристыкован к левой части *pTargetBar*.

*pTargetBar*<br/>
(в) Указатель на целевое стекло.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если панель была пристыкована успешно; в противном случае, FALSE.

## <a name="cdockingmanagerenableautohidepanes"></a><a name="enableautohidepanes"></a>CDockingManager::EnableAutoHidePanes

Позволяет стыковку панели с основной рамой, создает док-панель и добавляет его в список баров управления.

```
BOOL EnableAutoHidePanes(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
(в) Выравнивание стыковки.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если док-панель была создана успешно; FALSE в противном случае.

## <a name="cdockingmanagerenabledocking"></a><a name="enabledocking"></a>CDockingManager:EnableDocking

Создает док-панель и позволяет стыковки панели к основной раме.

```
BOOL EnableDocking(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
(в) Выравнивание стыковки.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если док-панель была создана успешно; FALSE в противном случае.

## <a name="cdockingmanagerenabledocksitemenu"></a><a name="enabledocksitemenu"></a>CDockingManager::EnableDockSiteMenu

Отображает дополнительную кнопку, которая открывает всплывающее меню на подписях всех стыковочных стекол.

```
static void EnableDockSiteMenu(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) TRUE для включения меню сайта док-станции; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Меню сайта док-станции отображает следующие варианты изменения состояния стыковки панели:

- `Floating`- Плавает панель

- `Docking`- Доки панели на главной раме в месте, где панель была в последний раз состыкован

- `AutoHide`- Переключает панель в режим автохайда

- `Hide`- Скрывает стекло

По умолчанию это меню не отображается.

## <a name="cdockingmanagerenablepanecontextmenu"></a><a name="enablepanecontextmenu"></a>CDockingManager::EnablePaneContextMenu

Сообщает библиотеке отобразить специальное контекстное меню, в которое есть список панели инструментов приложений и стыковочные панели, когда пользователь нажимает на правую кнопку мыши и библиотека обрабатывает WM_CONTEXTMENU сообщение.

```cpp
void EnablePaneContextMenu(
    BOOL bEnable,
    UINT uiCustomizeCmd,
    const CString& strCustomizeText,
    BOOL bToolbarsOnly = FALSE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
(в) Если true, библиотека включает поддержку автоматического контекстного меню; если FALSE библиотека выключает поддержку автоматического контекстного меню.

*uiCustomizeCmd*<br/>
(в) Идентификатор команды для элемента **Настройка** в меню.

*strCustomizeText*<br/>
(в) Текст элемента **Настройка.**

*bToolbarsТолько*<br/>
(в) Если TRUE, меню отображает только список инструментов приложения; если FALSE, библиотека добавляет стыковочные панели приложений в этот список.

## <a name="cdockingmanagerfinddocksite"></a><a name="finddocksite"></a>CDockingManager::FindDockSite

Извлекает панель, которая находится в указанном положении и имеет указанное выравнивание.

```
virtual CDockSite* FindDockSite(
    DWORD dwAlignment,
    BOOL bOuter);
```

### <a name="parameters"></a>Параметры

*dwAlignment*<br/>
(в) Выравнивание панели бара.

*bOuter*<br/>
(в) Если true, получить бар в голову позиции в списке контрольных баров. В противном случае, получить бар в хвосте позиции в списке контрольных баров.

### <a name="return-value"></a>Возвращаемое значение

Стыковочное стекло, имеющее указанное выравнивание; NULL в противном случае.

## <a name="cdockingmanagerfindpanebyid"></a><a name="findpanebyid"></a>CDockingManager::FindPaneByID

Находит панель по указанному идентификатору управления.

```
virtual CBasePane* FindPaneByID(
    UINT uBarID,
    BOOL bSearchMiniFrames = FALSE);
```

### <a name="parameters"></a>Параметры

*uBarID*<br/>
(в) Упоняет идентификатор управления панели, чтобы найти.

*bSearchMiniФреймы*<br/>
(в) TRUE включить все плавающие стекла в поиске. FALSE включить только пристыкованные стекла.

### <a name="return-value"></a>Возвращаемое значение

Объект [CBasePane,](../../mfc/reference/cbasepane-class.md) который имеет указанный идентификатор управления, или NULL, если указанное стекло не может быть найдено.

### <a name="remarks"></a>Примечания

## <a name="cdockingmanagerfinddocksitebypane"></a><a name="finddocksitebypane"></a>CDockingManager::FindDockSiteByPane

Возвращает панель, которая имеет идентификатор панели бара цели.

```
virtual CDockSite* FindDockSiteByPane(CPane* pTargetBar);
```

### <a name="parameters"></a>Параметры

*pTargetBar*<br/>
(в) Указатель на панель целевого бара.

### <a name="return-value"></a>Возвращаемое значение

Панель бара, которая имеет идентификатор панели бара цели; NULL, если такого панели бара не существует.

## <a name="cdockingmanagerfixupvirtualrects"></a><a name="fixupvirtualrects"></a>CDockingManager::FixupVirtualRects

Замещает все текущие позиции панели инструментов в виртуальные прямоугольники.

```
virtual void FixupVirtualRects();
```

### <a name="remarks"></a>Примечания

Когда пользователь начинает перетаскивать панель инструментов, приложение запоминает свое исходное положение в *виртуальном прямоугольнике.* Когда пользователь перемещает панель инструментов по месту док-станции, панель инструментов может сдвинуть другие панели инструментов. Исходные позиции других инструментов хранятся в соответствующих виртуальных прямоугольниках.

## <a name="cdockingmanagerframefrompoint"></a><a name="framefrompoint"></a>CDockingManager::FrameFromPoint

Возвращает кадр, содержащий заданную точку.

```
virtual CPaneFrameWnd* FrameFromPoint(
    CPoint pt,
    CPaneFrameWnd* pFrameToExclude,
    BOOL bFloatMultiOnly) const;
```

### <a name="parameters"></a>Параметры

*пт*<br/>
(в) Определяет точку, в координатах экрана, для проверки.

*pFrameToExclude*<br/>
(в) Указатель на кадр, чтобы исключить.

*bFloatMultiТолько*<br/>
(в) TRUE, чтобы исключить кадры, `CMultiPaneFrameWnd`которые не являются экземплярами; FALSE в противном случае.

### <a name="return-value"></a>Возвращаемое значение

Кадр, содержащий заданную точку; NULL в противном случае.

## <a name="cdockingmanagergetclientareabounds"></a><a name="getclientareabounds"></a>CDockingManager::GetClientAreaBounds

Получает прямоугольник, содержащий границы клиентской области.

```
CRect GetClientAreaBounds() const;

void GetClientAreaBounds(CRect& rcClient);
```

### <a name="parameters"></a>Параметры

*rcКлиент*<br/>
(ваут) Ссылка на прямоугольник, содержащий границы клиентской зоны.

### <a name="return-value"></a>Возвращаемое значение

Прямоугольник, содержащий границы клиентской области.

## <a name="cdockingmanagergetdockingmode"></a><a name="getdockingmode"></a>CDockingManager::GetDockingMode

Возвращает текущий режим стыковки.

```
static AFX_DOCK_TYPE GetDockingMode();
```

### <a name="return-value"></a>Возвращаемое значение

Значение регистратора, представляющее текущий режим стыковки. Может иметь одно из следующих значений.

- DT_STANDARD

- DT_IMMEDIATE

- DT_SMART

### <a name="remarks"></a>Примечания

Чтобы установить режим стыковки, позвоните [CDockingManager::SetDockingMode](#setdockingmode).

## <a name="cdockingmanagergetdocksiteframewnd"></a><a name="getdocksiteframewnd"></a>CDockingManager::GetDockSiteFrameWnd

Получает указатель на родительскую оконную раму.

```
CFrameWnd* GetDockSiteFrameWnd() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на родительскую оконную раму.

## <a name="cdockingmanagergetenabledautohidealignment"></a><a name="getenabledautohidealignment"></a>CDockingManager::GetEnabledAutoHideAlignment

Возвращает включенное выравнивание стекол.

```
DWORD GetEnabledAutoHideAlignment() const;
```

### <a name="return-value"></a>Возвращаемое значение

Битовая комбинация CBRS_ALIGN_ флагов, или 0, если автоматида не включена. Для получения дополнительной информации [см. CFrameWnd::EnableDocking](../../mfc/reference/cframewnd-class.md#enabledocking).

### <a name="remarks"></a>Примечания

Метод возвращает включенное выравнивание для баров управления автохидов. Для включения баров автохид, [позвоните CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes).

## <a name="cdockingmanagergetminiframes"></a><a name="getminiframes"></a>CDockingManager::GetMiniFrames

Получает список минифреймов.

```
const CObList& GetMiniFrames() const;
```

### <a name="return-value"></a>Возвращаемое значение

Список минифреймов, содержащих панели управления, принадлежащие менеджеру стыковки.

## <a name="cdockingmanagergetouteredgebounds"></a><a name="getouteredgebounds"></a>CDockingManager::GetOuterEdgeBounds

Получает прямоугольник, содержащий внешние края рамы.

```
CRect GetOuterEdgeBounds() const;
```

### <a name="return-value"></a>Возвращаемое значение

Прямоугольник, содержащий внешние края рамы.

## <a name="cdockingmanagergetpanelist"></a><a name="getpanelist"></a>CDockingManager::GetPaneList

Возвращает список стекол, принадлежащих менеджеру стыковки. Это включает в себя все плавающие стекла.

```cpp
void GetPaneList(
    CObList& lstBars,
    BOOL bIncludeAutohide = FALSE,
    CRuntimeClass* pRTCFilter = NULL,
    BOOL bIncludeTabs = FALSE);
```

### <a name="parameters"></a>Параметры

*lstBars*<br/>
(в, вне) Содержит все панели текущего менеджера стыковки.

*bВключитьАвтохидэ*<br/>
(в) TRUE включить стекла, которые находятся в режиме автохидирования; в противном случае, FALSE.

*pRTCFilter*<br/>
(в) Если не NULL, то в списке возвращается только панели указанного класса времени выполнения.

*bВключитьудары*<br/>
(в) TRUE для включения вкладок; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

Если в диспетчере стыковки есть какие-либо табло, метод возвращает указатели на объекты [класса CBaseTabbedPane,](../../mfc/reference/cbasetabbedpane-class.md) и вы должны точно перечислить вкладки.

Используйте *pRTCFilter* для получения определенного класса стекол. Например, можно получить только панели инструментов, установив это значение соответствующим образом.

## <a name="cdockingmanagergetsmartdockingmanager"></a><a name="getsmartdockingmanager"></a>CDockingManager::GetSmartDockingManager

Получает указатель для смарт-менеджера стыковки.

```
CSmartDockingManager* GetSmartDockingManager();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на смарт-менеджера стыковки.

## <a name="cdockingmanagergetsmartdockingmanagerpermanent"></a><a name="getsmartdockingmanagerpermanent"></a>CDockingManager::GetSmartDockingManagerПостоянный

Получает указатель для смарт-менеджера стыковки.

```
CSmartDockingManager* GetSmartDockingManagerPermanent() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на смарт-менеджера стыковки.

## <a name="cdockingmanagergetsmartdockingparams"></a><a name="getsmartdockingparams"></a>CDockingManager::GetSmartDockingParams

Возвращает параметры смарт-стыковки для менеджера стыковки.

```
static CSmartDockingInfo& GetSmartDockingParams();
```

### <a name="return-value"></a>Возвращаемое значение

Класс, содержащий интеллектуальные параметры стыковки для текущего менеджера стыковки. Для получения дополнительной [CSmartDockingInfo Class](../../mfc/reference/csmartdockinginfo-class.md)информации см.

### <a name="remarks"></a>Примечания

## <a name="cdockingmanagerhideautohidepanes"></a><a name="hideautohidepanes"></a>CDockingManager::HideAutoHidePanes

Скрывает панель, которая находится в режиме автохидирования.

```cpp
void HideAutoHidePanes(
    CDockablePane* pBarToExclude = NULL,
    BOOL bImmediately = FALSE);
```

### <a name="parameters"></a>Параметры

*pbartoExclude*<br/>
(в) Указатель на бар, чтобы исключить из укрытия.

*bImmediately*<br/>
(в) ПРАВДА, чтобы скрыть панель немедленно; FALSE, чтобы скрыть панель с эффектом автоматики.

## <a name="cdockingmanagerinsertdocksite"></a><a name="insertdocksite"></a>CDockingManager::InsertDockSite

Создает док-панель и вставляет его в список контрольных баров.

```
BOOL InsertDockSite(
    const AFX_DOCKSITE_INFO& info,
    DWORD dwAlignToInsertAfter,
    CDockSite** ppDockBar = NULL);
```

### <a name="parameters"></a>Параметры

*Информация*<br/>
(в) Структура, содержащая информацию о выравнивании стыковки.

*dwAlignToInsertAfter*<br/>
(в) Выравнивание док-панели.

*ppDockBar*<br/>
(ваут) Указатель на указатель на док-панель.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если док-панель была создана успешно; FALSE в противном случае.

## <a name="cdockingmanagerinsertpane"></a><a name="insertpane"></a>CDockingManager::InsertPane

Вставляет элементную панель управления в список контрольных баров.

```
BOOL InsertPane(
    CBasePane* pControlBar,
    CBasePane* pTarget,
    BOOL bAfter = TRUE);
```

### <a name="parameters"></a>Параметры

*pControlBar*<br/>
(в) Указатель на контрольное стекло.

*pTarget*<br/>
(в) Указатель на целевое стекло.

*bПосле*<br/>
(в) TRUE вставить панель после положения целевого стекла; FALSE в противном случае.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если элемент управления успешно добавлен в список контрольных баров; FALSE в противном случае.

### <a name="remarks"></a>Примечания

Этот метод возвращается ложным, если панель управления уже находится в списке контрольных баров или если целевое стекло не существует в списке контрольных баров.

## <a name="cdockingmanagerisdocksitemenu"></a><a name="isdocksitemenu"></a>CDockingManager::IsDockSiteMenu

Уточняется, отображается ли всплывающее меню на подписях всех стекол.

```
static BOOL IsDockSiteMenu();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если меню сайта док-станции отображается на подписи всех стыковочных стекол; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Вы можете включить меню сайта док-станции, позвонив [cDockingManager::EnableDockSiteMenu](#enabledocksitemenu).

## <a name="cdockingmanagerisinadjustlayout"></a><a name="isinadjustlayout"></a>CdockingManager::IsInAdjustLayout

Определяет, корректируются ли макеты всех стекол.

```
BOOL IsInAdjustLayout() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если макеты всех стекол скорректированы; FALSE в противном случае.

## <a name="cdockingmanagerisolecontainermode"></a><a name="isolecontainermode"></a>CDockingManager::IsOLEContainerMode

Уточняется, находится ли диспетчер стыковки в режиме контейнера OLE.

```
BOOL IsOLEContainerMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если менеджер стыковки находится в режиме контейнера OLE; в противном случае, FALSE.

### <a name="remarks"></a>Примечания

В режиме контейнера OLE все стыковочные панели и панели инструментов приложений скрыты. Панели также скрыты в этом режиме, если вы установили [CDockingManager::m_bHideDockingBarsInContainerMode](#m_bhidedockingbarsincontainermode) true.

## <a name="cdockingmanagerispointneardocksite"></a><a name="ispointneardocksite"></a>CDockingManager::IsPointNearDockSite

Определяет, находится ли указанная точка рядом с местом дока.

```
BOOL IsPointNearDockSite(
    CPoint point,
    DWORD& dwBarAlignment,
    BOOL& bOuterEdge) const;
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
(в) Указанная точка.

*dwBarAlignment*<br/>
(ваут) Определяет, какой край находится рядом. Возможные значения CBRS_ALIGN_LEFT, CBRS_ALIGN_RIGHT, CBRS_ALIGN_TOP и CBRS_ALIGN_BOTTOM.

*bOuterEdge*<br/>
(ваут) TRUE, если точка находится вблизи внешней границы дока; FALSE в противном случае.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если точка находится рядом с док-станции; в противном случае FALSE.

## <a name="cdockingmanagerisprintpreviewvalid"></a><a name="isprintpreviewvalid"></a>CDockingManager::IsPrintPreviewValid

Определяет, установлен ли режим предварительного просмотра печати.

```
BOOL IsPrintPreviewValid() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если режим предварительного просмотра печати установлен; FALSE в противном случае.

## <a name="cdockingmanagerloadstate"></a><a name="loadstate"></a>CDockingManager::LoadState

Загружает состояние менеджера стыковки из реестра.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Имя профиля.

*uiID*<br/>
(в) Ид менеджера стыковки.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если состояние менеджера стыковки было загружено успешно; в противном случае FALSE.

## <a name="cdockingmanagerlockupdate"></a><a name="lockupdate"></a>CDockingManager::LockUpdate

Запирает данное окно.

```cpp
void LockUpdate(BOOL bLock);
```

### <a name="parameters"></a>Параметры

*Блок*<br/>
(в) ПРАВДА, если окно заблокировано; FALSE в противном случае.

### <a name="remarks"></a>Примечания

Когда окно заблокировано, оно не может быть перемещено и не может быть перерисовано.

## <a name="cdockingmanagerm_bhidedockingbarsincontainermode"></a><a name="m_bhidedockingbarsincontainermode"></a>CDockingManager::m_bHideDockingBarsInContainerMode

Уточняется, прячет ли диспетчер стыковки стекла в режиме контейнера OLE.

```
AFX_IMPORT_DATA static BOOL m_bHideDockingBarsInContainerMode;
```

### <a name="remarks"></a>Примечания

Установите это значение false, если вы хотите сохранить все панели пристыкован к основной кадр видна, когда приложение находится в режиме контейнера OLE. По умолчанию это значение является правдой.

## <a name="cdockingmanagerm_dockmodeglobal"></a><a name="m_dockmodeglobal"></a>CDockingManager::m_dockModeGlobal

Определяет глобальный режим стыковки.

```
AFX_IMPORT_DATA static AFX_DOCK_TYPE m_dockModeGlobal;
```

### <a name="remarks"></a>Примечания

По умолчанию каждая стыковка использует этот режим стыковки. Для получения дополнительной информации о значениях, которые это поле может быть установлено, [см. CBasePane::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).

## <a name="cdockingmanagerm_ndocksensitivity"></a><a name="m_ndocksensitivity"></a>CDockingManager::m_nDockSensitivity

Определяет чувствительность стыковки.

```
AFX_IMPORT_DATA static int m_nDockSensitivity;
```

### <a name="remarks"></a>Примечания

Чувствительность стыковки определяет, насколько близко плавающее стекло может приблизиться к стыковочную панель, место стыковки или другую панель до того, как фреймворк изменит свое состояние на стыковку.

## <a name="cdockingmanagerm_ntimeoutbeforedockingbardock"></a><a name="m_ntimeoutbeforedockingbardock"></a>CDockingManager::m_nTimeOutBeforeDockingBarDock

Определяет время, в миллисекундах, до стыковки стыковка в режиме немедленного стыковки.

```
static UINT m_nTimeOutBeforeDockingBarDock;
```

### <a name="remarks"></a>Примечания

Перед стыковкой панели фреймворк ждет указанный промежуток времени. Это предотвращает случайное пристыкование панели к местоположению, пока пользователь все еще перетаскивает его.

## <a name="cdockingmanagerm_ntimeoutbeforetoolbardock"></a><a name="m_ntimeoutbeforetoolbardock"></a>CDockingManager::m_nTimeOutBeforeToolBarDock

Определяет время, в миллисекундах, до того, как панель инструментов пристыкована к окну основной рамы.

```
static UINT m_nTimeOutBeforeToolBarDock;
```

### <a name="remarks"></a>Примечания

Перед стыковкой панели инструментов фреймворк ждет указанный промежуток времени. Это предотвращает случайное пристыкование панели инструментов к местоположению, пока пользователь все еще перетаскивает ее.

## <a name="cdockingmanageronactivateframe"></a><a name="onactivateframe"></a>CDockingManager::OnActivateFrame

Вызывается фреймворком, когда окно кадра становится активным или деактивировано.

```
virtual void OnActivateFrame(BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*bActivate*<br/>
(в) Если TRUE, окно рамы становится активным; если FALSE, окно рамы отключается.

## <a name="cdockingmanageronclosepopupmenu"></a><a name="onclosepopupmenu"></a>CDockingManager::OnClosePopupMenu

Вызывается платформой, когда активное всплывающее меню обрабатывает сообщение WM_DESTROY.

```cpp
void OnClosePopupMenu();
```

### <a name="remarks"></a>Примечания

Платформа отправляет WM_DESTROY сообщение, когда он собирается закрыть текущее основное окно. Переопределить этот метод для `CMFCPopupMenu` обработки уведомлений от `CMFCPopupMenu` объектов, которые принадлежат к окну кадра, когда объект обрабатывает WM_DESTROY сообщение.

## <a name="cdockingmanageronmoveminiframe"></a><a name="onmoveminiframe"></a>CDockingManager::OnMoveMiniFrame

Вызывается по фреймворку для перемещения окна мини-рамки.

```
virtual BOOL OnMoveMiniFrame(CWnd* pFrame);
```

### <a name="parameters"></a>Параметры

*pFrame*<br/>
(в) Указатель на окно мини-рамки.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод удается; в противном случае FALSE.

## <a name="cdockingmanageronpanecontextmenu"></a><a name="onpanecontextmenu"></a>CDockingManager::OnPaneContextMenu

Вызывается фреймворк, когда он строит меню, которое имеет список стекол.

```cpp
void OnPaneContextMenu(CPoint point);
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
(в) Определяет расположение меню.

## <a name="cdockingmanagerpanefrompoint"></a><a name="panefrompoint"></a>CDockingManager::PaneFromPoint

Возвращает панель, содержащую заданную точку.

```
virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    bool bExactBar = false,
    CRuntimeClass* pRTCBarType = NULL,
    BOOL bCheckVisibility = FALSE,
    const CBasePane* pBarToIgnore = NULL) const;

virtual CBasePane* PaneFromPoint(
    CPoint point,
    int nSensitivity,
    DWORD& dwAlignment,
    CRuntimeClass* pRTCBarType = NULL,
    const CBasePane* pBarToIgnore = NULL) const;
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
(в) Определяет точку, в координатах экрана, для проверки.

*nЧувствительность*<br/>
(в) Значение для раздувания прямоугольника окна каждого проверенного стекла. Панель удовлетворяет критериям поиска, если данная точка находится в этом завышенном регионе.

*bExactBar*<br/>
(в) TRUE игнорировать *nSensitivity* параметр; в противном случае, FALSE.

*pRTCBarType*<br/>
(в) Если не NULL, метод выполняет поиск только стекол указанного типа.

*bCheckВидимость*<br/>
(в) TRUE для проверки только видимых стекол; в противном случае, FALSE.

*dwAlignment*<br/>
(ваут) Если панель найдена в указанной точке, этот параметр содержит сторону панели, которая была ближе всего к указанной точке. Дополнительные сведения см. в разделе «Примечания».

*pbartoignore*<br/>
(в) Если не NULL, метод игнорирует стекла, указанные этим параметром.

### <a name="return-value"></a>Возвращаемое значение

[Объект CBasePane,](../../mfc/reference/cbasepane-class.md)содержащий заданную точку, или NULL, если не было найдено стекол.

### <a name="remarks"></a>Примечания

Когда функция возвращается и панель была найдена, *dwAlignment* содержит выравнивание указанной точки. Например, если точка была ближе всего к верхней части панели, *dwAlignment* установлен на CBRS_ALIGN_TOP.

## <a name="cdockingmanagerprocesspanecontextmenucommand"></a><a name="processpanecontextmenucommand"></a>CDockingManager::ProcessPaneContextMenuCommand

Вызывается фреймворком для выбора или очистки флажка для указанной команды и перерасчета макета показанной панели.

```
BOOL ProcessPaneContextMenuCommand(
    UINT nID,
    int nCode,
    void* pExtra,
    AFX_CMDHANDLERINFO* pHandlerInfo);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
(в) Ид контрольной панели в меню.

*nКод*<br/>
(в) Код уведомления команды.

*pExtra*<br/>
(в) Указатель на аннулирование, которое отлито в указатель, `CCmdUI` если *nCode* является CN_UPDATE_COMMAND_UI.

*pHandlerInfo*<br/>
(в) Указатель на структуру информации. Этот параметр не используется.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если *pEXtra* не является NULL и *nCode* равна CN_UPDATE_COMMAND_UI, или если есть панель управления с указанным *nID*.

## <a name="cdockingmanagerrecalclayout"></a><a name="recalclayout"></a>CdockingManager::RecalcLayout

Пересчитывает внутреннюю компоновку элементов управления, присутствующих в списке элементов управления.

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>Параметры

*bNotify*<br/>
(в) Этот параметр не используется.

## <a name="cdockingmanagerreleaseemptypanecontainers"></a><a name="releaseemptypanecontainers"></a>CDockingManager::ReleaseEmptyPaneContainers

Выпускает пустые панели контейнеров.

```cpp
void ReleaseEmptyPaneContainers();
```

## <a name="cdockingmanagerremovehiddenmditabbedbar"></a><a name="removehiddenmditabbedbar"></a>CDockingManager::RemoveHiddenMDITabbedBar

Удаляет указанное скрытое панельное стекло.

```cpp
void RemoveHiddenMDITabbedBar(CDockablePane* pBar);
```

### <a name="parameters"></a>Параметры

*pBar*<br/>
(в) Указатель на панель панели для удаления.

## <a name="cdockingmanagerremoveminiframe"></a><a name="removeminiframe"></a>CDockingManager::RemoveMiniFrame

Удаляет указанную рамку из списка мини-кадров.

```
virtual BOOL RemoveMiniFrame(CPaneFrameWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Указатель на кадр для удаления.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если указанный кадр удален; FALSE в противном случае.

## <a name="cdockingmanagerremovepanefromdockmanager"></a><a name="removepanefromdockmanager"></a>CDockingManager::RemovePaneFromDockManager

Отменяет панель и удаляет ее из списка в диспетчере стыковки.

```cpp
void RemovePaneFromDockManager(
    CBasePane* pWnd,
    BOOL bDestroy,
    BOOL bAdjustLayout,
    BOOL bAutoHide = FALSE,
    CBasePane* pBarReplacement = NULL);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
(в) Указатель на панель, которая должна быть удалена.

*bDestroy*<br/>
(в) Если true, удаленная панель уничтожается.

*bAdjustLayout*<br/>
(в) Если true, отрегулируйте макет стыковки немедленно.

*bAutoHide*<br/>
(в) Если true, панель удаляется из списка баров autohide. Если FALSE, панель удаляется из списка регулярных стекол.

*pBarЗамена*<br/>
(в) Указатель на панель, которая заменяет удаленное стекло.

## <a name="cdockingmanagerreplacepane"></a><a name="replacepane"></a>CDockingManager::ReplacePane

Заменяет одну панель другой.

```
BOOL ReplacePane(
    CDockablePane* pOriginalBar,
    CDockablePane* pNewBar);
```

### <a name="parameters"></a>Параметры

*pOriginalBar*<br/>
(в) Указатель на исходное стекло.

*pNewBar*<br/>
(в) Указатель на панель, которая заменяет исходное стекло.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если панель успешно заменена; FALSE в противном случае.

## <a name="cdockingmanagerresortminiframesforzorder"></a><a name="resortminiframesforzorder"></a>CDockingManager::ResortMiniFramesFor

Курорты кадры в списке мини-кадров.

```cpp
void ResortMiniFramesForZOrder();
```

## <a name="cdockingmanagersavestate"></a><a name="savestate"></a>CDockingManager::SaveState

Сохраняет состояние менеджера стыковки в реестр.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Параметры

*lpszProfileName*<br/>
(в) Путь к ключу реестра.

*uiID*<br/>
(в) Идентификатор менеджера стыковки.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если государство было сохранено успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Сохранение состояния менеджера стыковки в реестр включает в себя сохранение состояний баров управления, состояния баров автохидирования и состояния мини-кадров, присутствующих в менеджере стыковки.

## <a name="cdockingmanagersendmessagetominiframes"></a><a name="sendmessagetominiframes"></a>CDockingManager::SendMessageToMiniFrames

Отправляет указанное сообщение на все мини-кадры.

```
BOOL SendMessageToMiniFrames(
    UINT uMessage,
    WPARAM wParam = 0,
    LPARAM lParam = 0);
```

### <a name="parameters"></a>Параметры

*uMessage*<br/>
(в) Сообщение, чтобы быть отправлено.

*wParam*<br/>
(в) Дополнительная информация, зависящая от сообщений.

*lParam*<br/>
(в) Дополнительная информация, зависящая от сообщений.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА всегда.

## <a name="cdockingmanagerserialize"></a><a name="serialize"></a>CDockingManager::Serialize

Записывает менеджера стыковки в архив.

```cpp
void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*ar*<br/>
(в) Ссылка на объект архива.

### <a name="remarks"></a>Примечания

Запись менеджера стыковки в архив включает определение количества стыковочных баров управления и ползунок, а также написание баров управления, мини-кадров, баров автохидов и баров MDI, склееных в архив.

## <a name="cdockingmanagersetautohidezorder"></a><a name="setautohidezorder"></a>CDockingManager::SetAutohide

Устанавливает размер, ширину и высоту руля и указанного стекла.

```cpp
void SetAutohideZOrder(CDockablePane* pAHDockingBar);
```

### <a name="parameters"></a>Параметры

*pAHDockingBar*<br/>
(в) Указатель на док-станционное стекло.

## <a name="cdockingmanagersetdockingmode"></a><a name="setdockingmode"></a>CDockingManager::SetDockingMode

Устанавливает режим стыковки.

```
static void SetDockingMode(
    AFX_DOCK_TYPE dockMode,
    AFX_SMARTDOCK_THEME theme = AFX_SDT_DEFAULT);
```

### <a name="parameters"></a>Параметры

*dockMode*<br/>
Определяет новый режим стыковки. Дополнительные сведения см. в разделе «Примечания».

*Тема*<br/>
Определяет тему, которая будет использоваться для умных маркеров стыковки. Это может быть одно из следующих перечисленных значений: AFX_SDT_DEFAULT, AFX_SDT_VS2005 AFX_SDT_VS2008.

### <a name="remarks"></a>Примечания

Вызовите этот статический метод, чтобы установить режим стыковки.

*dockMode* может быть одним из следующих значений:

- DT_STANDARD - Стандартный режим стыковки, реализованный в Visual Studio .NET 2003. Панели перетаскиваются без перетаскивания контекста.

- DT_IMMEDIATE - Режим немедленного стыковки, реализованный в Microsoft Visio. Панели перетаскиваются с перетаскиванием контекста, но маркеры не отображаются.

- DT_SMART - Смарт-режим стыковки, реализованный в Visual Studio 2005. Панели перетаскиваются с перетаскиванием контекста и смарт-маркеры отображаются, которые показывают, где панель может быть пристыкован.

## <a name="cdockingmanagersetdockstate"></a><a name="setdockstate"></a>CDockingManager::SetDockState

Устанавливает состояние стыковки баров управления, мини-рам и аутохидных решеток.

```
virtual void SetDockState();
```

## <a name="cdockingmanagersetprintpreviewmode"></a><a name="setprintpreviewmode"></a>CDockingManager::SetPrintPreviewMode

Устанавливает режим предварительного просмотра печати баров, отображаемых в предварительном просмотре печати.

```cpp
void SetPrintPreviewMode(
    BOOL bPreview,
    CPrintPreviewState* pState);
```

### <a name="parameters"></a>Параметры

*bPreview*<br/>
(в) TRUE, если режим предварительного просмотра печати установлен; FALSE в противном случае.

*pState*<br/>
(в) Указатель на состояние предварительного просмотра. Этот параметр не используется.

## <a name="cdockingmanagersetsmartdockingparams"></a><a name="setsmartdockingparams"></a>CDockingManager::SetSmartDockingParams

Устанавливает параметры, определяющие поведение смарт-стыковки.

```
static void SetSmartDockingParams(CSmartDockingInfo& params);
```

### <a name="parameters"></a>Параметры

*params*<br/>
(в, вне) Определяет параметры смарт-стыковки.

### <a name="remarks"></a>Примечания

Вызовите этот метод, если вы хотите настроить внешний вид, цвет или форму умных маркеров стыковки.

Чтобы использовать по умолчанию искать смарт-маркеры стыковки, передать непрепрецизмированный экземпляр [CSmartDockingInfo класса](../../mfc/reference/csmartdockinginfo-class.md) *парамы.*

## <a name="cdockingmanagershowdelayshowminiframes"></a><a name="showdelayshowminiframes"></a>CDockingManager::ShowDelayShowMiniКадры

Показывает или скрывает окна мини-кадров.

```cpp
void ShowDelayShowMiniFrames(BOOL bshow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
(в) TRUE, чтобы сделать окно показанного кадра активным; FALSE, чтобы скрыть окно рамы.

## <a name="cdockingmanagershowpanes"></a><a name="showpanes"></a>CDockingManager::ShowPanes

Показывает или скрывает стекла управления и автоматики баров.

```
virtual BOOL ShowPanes(BOOL bShow);
```

### <a name="parameters"></a>Параметры

*bShow*<br/>
(в) TRUE, чтобы показать стекла; FALSE, чтобы скрыть стекла.

### <a name="return-value"></a>Возвращаемое значение

Всегда значение FALSE.

## <a name="cdockingmanagerstartsdocking"></a><a name="startsdocking"></a>CDockingManager::StartSDocking

Запускает смарт-стыковку указанного окна в соответствии с выравниванием менеджера смарт-стыковки.

```cpp
void StartSDocking(CWnd* pDockingWnd);
```

### <a name="parameters"></a>Параметры

*pDockingWnd*<br/>
(в) Указатель на окно для стыковки.

## <a name="cdockingmanagerstopsdocking"></a><a name="stopsdocking"></a>CDockingManager::StopSDocking

Прекращает стыковку.

```cpp
void StopSDocking();
```

## <a name="cdockingmanagergetsmartdockingtheme"></a><a name="getsmartdockingtheme"></a>CDockingManager::GetSmartDockingTheme

Статический метод, который возвращает тему, используемую для отображения интеллектуальных маркеров стыковки.

```
static AFX_SMARTDOCK_THEME __stdcall GetSmartDockingTheme();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает одно из следующих перечисленных значений: AFX_SDT_DEFAULT, AFX_SDT_VS2005, AFX_SDT_VS2008.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Класс CFrameWndEx](../../mfc/reference/cframewndex-class.md)<br/>
[CDockablePane Class](../../mfc/reference/cdockablepane-class.md)<br/>
[Класс CPaneFrameWnd](../../mfc/reference/cpaneframewnd-class.md)
