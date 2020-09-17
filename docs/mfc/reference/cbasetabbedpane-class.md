---
title: Класс CBaseTabbedPane
ms.date: 11/04/2016
f1_keywords:
- CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::AddTab
- AFXBASETABBEDPANE/CBaseTabbedPane::AllowDestroyEmptyTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::ApplyRestoredTabInfo
- AFXBASETABBEDPANE/CBaseTabbedPane::CanFloat
- AFXBASETABBEDPANE/CBaseTabbedPane::CanSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::ConvertToTabbedDocument
- AFXBASETABBEDPANE/CBaseTabbedPane::DetachPane
- AFXBASETABBEDPANE/CBaseTabbedPane::EnableSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::FillDefaultTabsOrderArray
- AFXBASETABBEDPANE/CBaseTabbedPane::FindBarByTabNumber
- AFXBASETABBEDPANE/CBaseTabbedPane::FindPaneByID
- AFXBASETABBEDPANE/CBaseTabbedPane::FloatTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetDefaultTabsOrder
- AFXBASETABBEDPANE/CBaseTabbedPane::GetFirstVisibleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetMinSize
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneIcon
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneList
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabArea
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::GetUnderlyingWindow
- AFXBASETABBEDPANE/CBaseTabbedPane::GetVisibleTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::HasAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::IsHideSingleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::RecalcLayout
- AFXBASETABBEDPANE/CBaseTabbedPane::RemovePane
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoDestroy
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::ShowTab
helpviewer_keywords:
- CBaseTabbedPane [MFC], AddTab
- CBaseTabbedPane [MFC], AllowDestroyEmptyTabbedPane
- CBaseTabbedPane [MFC], ApplyRestoredTabInfo
- CBaseTabbedPane [MFC], CanFloat
- CBaseTabbedPane [MFC], CanSetCaptionTextToTabName
- CBaseTabbedPane [MFC], ConvertToTabbedDocument
- CBaseTabbedPane [MFC], DetachPane
- CBaseTabbedPane [MFC], EnableSetCaptionTextToTabName
- CBaseTabbedPane [MFC], FillDefaultTabsOrderArray
- CBaseTabbedPane [MFC], FindBarByTabNumber
- CBaseTabbedPane [MFC], FindPaneByID
- CBaseTabbedPane [MFC], FloatTab
- CBaseTabbedPane [MFC], GetDefaultTabsOrder
- CBaseTabbedPane [MFC], GetFirstVisibleTab
- CBaseTabbedPane [MFC], GetMinSize
- CBaseTabbedPane [MFC], GetPaneIcon
- CBaseTabbedPane [MFC], GetPaneList
- CBaseTabbedPane [MFC], GetTabArea
- CBaseTabbedPane [MFC], GetTabsNum
- CBaseTabbedPane [MFC], GetUnderlyingWindow
- CBaseTabbedPane [MFC], GetVisibleTabsNum
- CBaseTabbedPane [MFC], HasAutoHideMode
- CBaseTabbedPane [MFC], IsHideSingleTab
- CBaseTabbedPane [MFC], RecalcLayout
- CBaseTabbedPane [MFC], RemovePane
- CBaseTabbedPane [MFC], SetAutoDestroy
- CBaseTabbedPane [MFC], SetAutoHideMode
- CBaseTabbedPane [MFC], ShowTab
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
ms.openlocfilehash: 21f2821392d2b9e71837997f5a9a10ab80ba073f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838676"
---
# <a name="cbasetabbedpane-class"></a>Класс CBaseTabbedPane

Расширяет функциональность [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) для поддержки создания окон с вкладками.

## <a name="syntax"></a>Синтаксис

```
class CBaseTabbedPane : public CDockablePane
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CBaseTabbedPane::CBaseTabbedPane`|Конструктор по умолчанию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBaseTabbedPane:: Аддтаб](#addtab)|Добавляет новую вкладку к панели с вкладками.|
|[CBaseTabbedPane:: Алловдестройемптитаббедпане](#allowdestroyemptytabbedpane)|Указывает, можно ли уничтожить пустую панель с вкладками.|
|[CBaseTabbedPane:: Апплиресторедтабинфо](#applyrestoredtabinfo)|Применяет параметры вкладки, загружаемые из реестра, к области с вкладками.|
|[CBaseTabbedPane:: Канфлоат](#canfloat)|Определяет, может ли панель быть плавающей. (Переопределяет [CBasePane:: канфлоат](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CBaseTabbedPane:: Кансеткаптионтексттотабнаме](#cansetcaptiontexttotabname)|Определяет, должен ли заголовок панели с вкладками отображать тот же текст, что и активная вкладка.|
|[CBaseTabbedPane:: Конверттотаббеддокумент](#converttotabbeddocument)|(Переопределяет [CDockablePane:: конверттотаббеддокумент](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|
|[CBaseTabbedPane::D Етачпане](#detachpane)|Преобразует одну или несколько закрепляемых областей в документы с вкладками MDI.|
|[CBaseTabbedPane:: Енаблесеткаптионтексттотабнаме](#enablesetcaptiontexttotabname)|Включает или отключает возможность панели с вкладками для синхронизации текста заголовка с текстом метки на активной вкладке.|
|[CBaseTabbedPane:: Филлдефаулттабсордераррай](#filldefaulttabsorderarray)|Восстанавливает внутренний порядок табуляции до состояния по умолчанию.|
|[CBaseTabbedPane:: Финдбарбитабнумбер](#findbarbytabnumber)|Возвращает область, находящейся на вкладке, если вкладка определяется с помощью индекса табуляции, начинающегося с нуля.|
|[CBaseTabbedPane:: Финдпанебид](#findpanebyid)|Возвращает панель, определяемую ИДЕНТИФИКАТОРом панели.|
|[CBaseTabbedPane:: Флоаттаб](#floattab)|Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.|
|[CBaseTabbedPane:: Жетдефаулттабсордер](#getdefaulttabsorder)|Возвращает порядок вкладок на панели по умолчанию.|
|[CBaseTabbedPane:: Жетфирствисиблетаб](#getfirstvisibletab)|Извлекает указатель на первую отображаемую вкладку.|
|[CBaseTabbedPane:: Жетминсизе](#getminsize)|Возвращает минимально допустимый размер панели. (Переопределяет [CPane:: жетминсизе](../../mfc/reference/cpane-class.md#getminsize).)|
|[CBaseTabbedPane:: Жетпанеикон](#getpaneicon)|Возвращает маркер значка панели. (Переопределяет [CBasePane:: жетпанеикон](../../mfc/reference/cbasepane-class.md#getpaneicon).)|
|[CBaseTabbedPane:: копанель](#getpanelist)|Возвращает список панелей, содержащихся в области с вкладками.|
|[CBaseTabbedPane:: Жеттабареа](#gettabarea)|Возвращает ограничивающие прямоугольники для верхних и нижних областей вкладок.|
|[CBaseTabbedPane:: Жеттабснум](#gettabsnum)|Возвращает число вкладок в окне вкладки.|
|[CBaseTabbedPane:: Жетундерлингвиндов](#getunderlyingwindow)|Возвращает базовое окно вкладки (с оболочкой).|
|[CBaseTabbedPane:: Жетвисиблетабснум](#getvisibletabsnum)|Возвращает число отображаемых вкладок.|
|[CBaseTabbedPane:: Хасаутохидемоде](#hasautohidemode)|Определяет, можно ли переключать панель с вкладками на режим автоматического скрытия.|
|[CBaseTabbedPane:: Ишидесинглетаб](#ishidesingletab)|Определяет, скрывается ли панель с вкладками, если отображается только одна вкладка.|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Используется внутри во время сериализации.|
|[CBaseTabbedPane:: RecalcLayout](#recalclayout)|Повторно вычисляет сведения о макете для панели. (Переопределяет [CPane:: RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|
|[CBaseTabbedPane:: Ремовепане](#removepane)|Удаляет панель из панели с вкладками.|
|`CBaseTabbedPane::SaveSiblingBarIDs`|Используется внутри во время сериализации.|
|`CBaseTabbedPane::Serialize`|(Переопределяет [CDockablePane:: Serialize](cdockablepane-class.md).)|
|`CBaseTabbedPane::SerializeTabWindow`|Используется внутри во время сериализации.|
|[CBaseTabbedPane:: Сетаутодестрой](#setautodestroy)|Определяет, будет ли автоматически уничтожена панель элементов управления с вкладками.|
|[CBaseTabbedPane:: Сетаутохидемоде](#setautohidemode)|Переключает закрепляемую область между отображением и режимом автоматического скрытия. (Переопределяет [CDockablePane:: сетаутохидемоде](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|
|[CBaseTabbedPane:: Шовтаб](#showtab)|Показывает или скрывает вкладку.|

## <a name="remarks"></a>Примечания

Этот класс является абстрактным и не может быть создан. Он реализует службы, общие для всех видов панелей с вкладками.

В настоящее время библиотека содержит два производных класса панели с вкладками: [Ктаббедпане Class](../../mfc/reference/ctabbedpane-class.md) и [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).

`CBaseTabbedPane`Объект заключает указатель на объект [класса CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) . После этого [Класс CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md) станет дочерним окном области с вкладками.

Дополнительные сведения о создании панелей с вкладками см. в разделе [класс CDockablePane](../../mfc/reference/cdockablepane-class.md), [класс Ктаббедпане](../../mfc/reference/ctabbedpane-class.md)и [Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

`CBaseTabbedPane`

## <a name="requirements"></a>Требования

**Заголовок:** афксбасетаббедпане.h

## <a name="cbasetabbedpaneaddtab"></a><a name="addtab"></a> CBaseTabbedPane:: Аддтаб

Добавляет новую вкладку к панели с вкладками.

```
virtual BOOL AddTab(
    CWnd* pNewBar,
    BOOL bVisible = TRUE,
    BOOL bSetActive = TRUE,
    BOOL bDetachable = TRUE);
```

### <a name="parameters"></a>Параметры

*пневбар*<br/>
[вход, выход] Указатель на область, которую необходимо добавить. Этот указатель может стать недействительным после вызова этого метода. Дополнительные сведения см. в разделе "Замечания".

*бвисибле*<br/>
окне Значение TRUE, чтобы сделать вкладку видимой; в противном случае — значение FALSE.

*бсетактиве*<br/>
окне Значение TRUE, чтобы сделать вкладку активной вкладкой; в противном случае — значение FALSE.

*bDetachable*<br/>
окне Значение TRUE, чтобы можно было отсоединять вкладку. в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если панель была успешно добавлена в виде вкладки и не была уничтожена в процессе. Значение FALSE, если добавляемая панель является объектом типа `CBaseTabbedPane` . Дополнительные сведения см. в разделе "Замечания".

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы добавить область в качестве новой вкладки на панели с вкладками. Если *пневбар* указывает на объект типа `CBaseTabbedPane` , все его вкладки копируются на панель с вкладками, а затем *пневбар* уничтожается. Таким словами, *пневбар* превращается в недопустимый указатель и не должен использоваться.

## <a name="cbasetabbedpaneallowdestroyemptytabbedpane"></a><a name="allowdestroyemptytabbedpane"></a> CBaseTabbedPane:: Алловдестройемптитаббедпане

Указывает, можно ли уничтожить пустую панель с вкладками.

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если пустая область с вкладками может быть удалена; в противном случае — значение FALSE. Реализация по умолчанию всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Если пустая область с вкладками не может быть уничтожена, платформа скрывает панель.

## <a name="cbasetabbedpaneapplyrestoredtabinfo"></a><a name="applyrestoredtabinfo"></a> CBaseTabbedPane:: Апплиресторедтабинфо

Загружает параметры вкладки из реестра и применяет их к панели с вкладками.

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>Параметры

*бусетабиндексес*<br/>
окне Этот параметр используется платформой для внутренних целей.

### <a name="remarks"></a>Примечания

Этот метод вызывается платформой при перезагрузке сведений о состоянии закрепления из реестра. Метод получает сведения о порядке табуляции и именах вкладок для панели с вкладками.

## <a name="cbasetabbedpanecanfloat"></a><a name="canfloat"></a> CBaseTabbedPane:: Канфлоат

Указывает, может ли панель с вкладками перемещаться.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если панель может быть плавающей; в противном случае — значение FALSE.

## <a name="cbasetabbedpanecansetcaptiontexttotabname"></a><a name="cansetcaptiontexttotabname"></a> CBaseTabbedPane:: Кансеткаптионтексттотабнаме

Определяет, должен ли заголовок панели с вкладками отображать тот же текст, что и активная вкладка.

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текст заголовка панели с вкладками установлен на текст активной вкладки; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Метод используется для определения того, что текст, отображаемый в заголовке панели с вкладками, дублирует метку активной вкладки. Вы можете включить или отключить эту функцию, вызвав [CBaseTabbedPane:: енаблесеткаптионтексттотабнаме](#enablesetcaptiontexttotabname).

## <a name="cbasetabbedpaneconverttotabbeddocument"></a><a name="converttotabbeddocument"></a> CBaseTabbedPane:: Конверттотаббеддокумент

Преобразует одну или несколько закрепляемых областей в документы с вкладками MDI.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>Параметры

*бактиветабонли*<br/>
окне При преобразовании панели с вкладками укажите значение TRUE, чтобы преобразовать только активную вкладку. Укажите значение FALSE, чтобы преобразовать все вкладки на панели.

## <a name="cbasetabbedpanedetachpane"></a><a name="detachpane"></a> CBaseTabbedPane::D Етачпане

Отсоединяет панель от панели с вкладками.

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

*пбар*<br/>
окне Указатель на область для отсоединения.

*bHide*<br/>
окне Логический параметр, указывающий, скрывает ли структура панель после отсоединения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если платформа успешно отсоединяет панель. Значение FALSE, если *пбар* имеет значение null или ссылается на область, которая не находится в области с вкладками.

### <a name="remarks"></a>Примечания

По возможности платформа будет переключаться на отсоединенную область. Дополнительные сведения см. в разделе [CBasePane:: канфлоат](../../mfc/reference/cbasepane-class.md#canfloat).

## <a name="cbasetabbedpaneenablesetcaptiontexttotabname"></a><a name="enablesetcaptiontexttotabname"></a> CBaseTabbedPane:: Енаблесеткаптионтексттотабнаме

Включает или отключает возможность панели с вкладками для синхронизации текста заголовка с текстом метки на активной вкладке.

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
окне Значение TRUE, чтобы синхронизировать заголовок области с вкладками с заголовком активной вкладки; в противном случае — значение FALSE.

## <a name="cbasetabbedpanefilldefaulttabsorderarray"></a><a name="filldefaulttabsorderarray"></a> CBaseTabbedPane:: Филлдефаулттабсордераррай

Восстанавливает внутренний порядок табуляции до состояния по умолчанию.

```cpp
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>Примечания

Этот метод вызывается, когда платформа восстанавливает исходное состояние панели Outlook.

## <a name="cbasetabbedpanefindpanebyid"></a><a name="findpanebyid"></a> CBaseTabbedPane:: Финдпанебид

Возвращает панель, определяемую ИДЕНТИФИКАТОРом панели.

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>Параметры

*убарид*<br/>
окне Указывает идентификатор области для поиска.

### <a name="return-value"></a>Возвращаемое значение

Указатель на область, если она найдена; в противном случае значение NULL.

### <a name="remarks"></a>Примечания

Этот метод сравнивает все вкладки на панели и возвращает объект с ИДЕНТИФИКАТОРом, указанным в параметре *убарид* .

## <a name="cbasetabbedpanefindbarbytabnumber"></a><a name="findbarbytabnumber"></a> CBaseTabbedPane:: Финдбарбитабнумбер

Возвращает панель, расположенную на вкладке.

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>Параметры

*nTabNum*<br/>
окне Указывает отсчитываемый от нуля индекс извлекаемой вкладки.

*бжетвраппедбар*<br/>
окне Значение TRUE, чтобы возвратить базовое (упакованное) окно панели, а не саму панель; в противном случае — FALSE. Это относится только к панелям, производным от [кдоккаблепанеадаптер](../../mfc/reference/cdockablepaneadapter-class.md).

### <a name="return-value"></a>Возвращаемое значение

Если панель найдена, возвращается допустимый указатель на панель, в которой выполняется поиск. в противном случае значение NULL.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы получить панель, размещенную на вкладке, указанной параметром *нтабнум* .

## <a name="cbasetabbedpanefloattab"></a><a name="floattab"></a> CBaseTabbedPane:: Флоаттаб

Преобразует панель в плавающую, но только если она расположена на отделяемой вкладке.

```
virtual BOOL FloatTab(
    CWnd* pBar,
    int nTabID,
    AFX_DOCK_METHOD dockMethod,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Параметры

*пбар*<br/>
[вход, выход] Указатель на область с плавающей запятой.

*нтабид*<br/>
окне Указывает отсчитываемый от нуля индекс вкладки для перемещения.

*dockMethod*<br/>
окне Указывает метод, используемый, чтобы сделать панель плавающей. Дополнительные сведения см. в разделе "Замечания".

*bHide*<br/>
окне Значение TRUE, чтобы скрыть панель перед плавающей; в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если панель перемещена; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы перечислить область, которая в данный момент находится в отсоединенной вкладке.

Если необходимо отключить панель программным путем, укажите DM_SHOW для параметра *доккмесод* . Если вы хотите переместить область в ту же позицию, где она была перемещена ранее, укажите DM_DBL_CLICK в качестве параметра *доккмесод* .

## <a name="cbasetabbedpanegetdefaulttabsorder"></a><a name="getdefaulttabsorder"></a> CBaseTabbedPane:: Жетдефаулттабсордер

Возвращает порядок вкладок на панели по умолчанию.

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>Возвращаемое значение

`CArray`Объект, указывающий порядок вкладок в панели по умолчанию.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод при сбросе панели Outlook в исходное состояние.

## <a name="cbasetabbedpanegetfirstvisibletab"></a><a name="getfirstvisibletab"></a> CBaseTabbedPane:: Жетфирствисиблетаб

Извлекает указатель на первую отображаемую вкладку.

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>Параметры

*iTabNum*<br/>
окне Ссылка на целое число. Этот метод записывает Отсчитываемый от нуля индекс первой отображаемой вкладки к этому параметру или значение-1, если отображаемая вкладка не найдена.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха указатель на первую отображаемую вкладку; в противном случае значение NULL.

## <a name="cbasetabbedpanegetminsize"></a><a name="getminsize"></a> CBaseTabbedPane:: Жетминсизе

Возвращает минимально допустимый размер панели.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Параметры

*size*<br/>
заполняет `CSize` Объект, который заполняется минимальным допустимым размером.

### <a name="remarks"></a>Примечания

Если активна постоянная обработка минимальных размеров панели ( [CPane:: m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *Размер* заполняется минимальным допустимым размером активной вкладки. в противном случае *Размер* заполняется возвращаемым значением [CPane:: жетминсизе](../../mfc/reference/cpane-class.md#getminsize).

## <a name="cbasetabbedpanegetpaneicon"></a><a name="getpaneicon"></a> CBaseTabbedPane:: Жетпанеикон

Возвращает минимально допустимый размер панели.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Параметры

*size*<br/>
заполняет `CSize` Объект, который заполняется минимальным допустимым размером.

### <a name="remarks"></a>Примечания

Если активна постоянная обработка минимальных размеров панели ( [CPane:: m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *Размер* заполняется минимальным допустимым размером активной вкладки. в противном случае *Размер* заполняется возвращаемым значением [CPane:: жетминсизе](../../mfc/reference/cpane-class.md#getminsize).

## <a name="cbasetabbedpanegetpanelist"></a><a name="getpanelist"></a> CBaseTabbedPane:: копанель

Возвращает список панелей, содержащихся в области с вкладками.

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>Параметры

*LST*<br/>
заполняет Объект `CObList` , который заполняется панелями, содержащимися в области с вкладками.

*прткфилтер*<br/>
окне Если значение не равно NULL, возвращаемый список содержит только те панели, которые относятся к указанному классу среды выполнения.

## <a name="cbasetabbedpanegettabarea"></a><a name="gettabarea"></a> CBaseTabbedPane:: Жеттабареа

Возвращает ограничивающие прямоугольники для верхних и нижних областей вкладок.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>Параметры

*rectTabAreaTop*<br/>
заполняет Получает экранные координаты верхней области вкладки.

*rectTabAreaBottom*<br/>
заполняет Получает координаты экрана нижней области вкладки.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы определить ограничивающие прямоугольники (в экранных координатах) для верхних и нижних областей вкладок.

## <a name="cbasetabbedpanegettabsnum"></a><a name="gettabsnum"></a> CBaseTabbedPane:: Жеттабснум

Возвращает число вкладок в окне вкладки.

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число вкладок на панели с вкладками.

## <a name="cbasetabbedpanegetunderlyingwindow"></a><a name="getunderlyingwindow"></a> CBaseTabbedPane:: Жетундерлингвиндов

Возвращает базовое окно вкладки (с оболочкой).

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на базовое окно вкладки.

## <a name="cbasetabbedpanegetvisibletabsnum"></a><a name="getvisibletabsnum"></a> CBaseTabbedPane:: Жетвисиблетабснум

Возвращает число видимых вкладок.

```
virtual int GetVisibleTabsNum() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число видимых вкладок, которые будут больше или равны нулю.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы определить количество видимых вкладок на панели с вкладками.

## <a name="cbasetabbedpanehasautohidemode"></a><a name="hasautohidemode"></a> CBaseTabbedPane:: Хасаутохидемоде

Определяет возможность переключения панели с вкладками в режим автоматического скрытия.

```
virtual BOOL HasAutoHideMode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если панель можно переключить в режим автоскрытия; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если режим автоскрытия отключен, в заголовке панели с вкладками не отображается кнопка закрепить.

## <a name="cbasetabbedpaneishidesingletab"></a><a name="ishidesingletab"></a> CBaseTabbedPane:: Ишидесинглетаб

Определяет, скрывается ли панель с вкладками, если отображается только одна вкладка.

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если окно вкладки не отображается, если имеется только одна видимая вкладка; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если панель не отображается, поскольку открыта только одна вкладка, можно вызвать этот метод, чтобы определить, правильно ли работает панель с вкладками.

## <a name="cbasetabbedpaneremovepane"></a><a name="removepane"></a> CBaseTabbedPane:: Ремовепане

Удаляет панель из панели с вкладками.

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>Параметры

*пбар*<br/>
[вход, выход] Указатель на область, которую необходимо удалить из панели с вкладками.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если панель была успешно удалена из панели с вкладками, и если панель с вкладками все еще является допустимой. Значение FALSE, если последняя панель была удалена из панели с вкладками, а область с вкладками будет уничтожена. Если возвращаемое значение равно FALSE, больше не используйте панель с вкладками.

### <a name="remarks"></a>Примечания

Вызовите этот метод, чтобы удалить область, указанную параметром *пбар* , из панели с вкладками.

## <a name="cbasetabbedpanesetautodestroy"></a><a name="setautodestroy"></a> CBaseTabbedPane:: Сетаутодестрой

Определяет, будет ли автоматически уничтожена панель элементов управления с вкладками.

```cpp
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*баутодестрой*<br/>
окне Значение TRUE, если панель с вкладками создана динамически и вы не управляете ее временем существования. в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Установите для режима автоматического удаления значение TRUE, если панель с вкладками динамически создается и не контролируется ее время существования. Если режим автоматического удаления имеет значение TRUE, то панель с вкладками автоматически уничтожается платформой.

## <a name="cbasetabbedpaneshowtab"></a><a name="showtab"></a> CBaseTabbedPane:: Шовтаб

Показывает или скрывает вкладку.

```
virtual BOOL ShowTab(
    CWnd* pBar,
    BOOL bShow,
    BOOL bDelay,
    BOOL bActivate);
```

### <a name="parameters"></a>Параметры

*пбар*<br/>
окне Указатель на панель, которую нужно показать или скрыть.

*bShow*<br/>
окне Значение TRUE, чтобы отобразить панель; Значение FALSE, чтобы скрыть панель.

*бделай*<br/>
окне Значение TRUE, чтобы задержать настройку макета вкладки; в противном случае — значение FALSE.

*bActivate*<br/>
окне Значение TRUE, чтобы сделать вкладку активной вкладкой; в противном случае — значение FALSE.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если вкладка была успешно отображена или скрыта; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

При вызове этого метода Панель либо отображается, либо скрывается в зависимости от значения параметра *бшов* . Если скрыть вкладку и она является последней видимой вкладкой в соответствующем окне вкладки, то панель с вкладками будет скрыта. Если при отображении вкладки ранее не отображались вкладки, отображается панель с вкладками.

## <a name="cbasetabbedpanerecalclayout"></a><a name="recalclayout"></a> CBaseTabbedPane:: RecalcLayout

Повторно вычисляет сведения о макете для панели.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Примечания

Если панель является плавающей, этот метод уведомляет платформу, чтобы изменить размер панели до текущего размера мини-кадра.

Если панель закреплена, этот метод не выполняет никаких действий.

## <a name="cbasetabbedpanesetautohidemode"></a><a name="setautohidemode"></a> CBaseTabbedPane:: Сетаутохидемоде

Задает режим автоматического скрытия для отсоединяемых панелей на панели с вкладками.

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>Параметры

*бмоде*<br/>
окне Значение TRUE, чтобы включить режим автоматического скрытия; Значение FALSE, чтобы включить обычный режим закрепления.

*двалигнмент*<br/>
окне Задает выравнивание создаваемой области автоматических скрытий. Список возможных значений см. в разделе [CPane:: мовебялигнмент](../../mfc/reference/cpane-class.md#movebyalignment).

*пкурраутохидебар*<br/>
[вход, выход] Указатель на текущую панель инструментов автоматического скрытия. Может иметь значение NULL.

*бусетимер*<br/>
окне Указывает, следует ли использовать автоматическое скрытие, когда пользователь переключает панель в режим автоматического скрытия или сразу же скрывать эту область.

### <a name="return-value"></a>Возвращаемое значение

Указатель на панель инструментов автоматического скрытия, созданный при переключении в режим автоматического скрытия, или значение NULL, если панель инструментов не создана.

### <a name="remarks"></a>Примечания

Платформа вызывает этот метод, когда пользователь нажимает кнопку закрепить, чтобы переключить панель с вкладками на режим автоматического скрытия или обычный режим закрепления.

Режим автоматического скрытия задается для каждой соединяемой области на панели с вкладками. Панели, которые не могут быть отсоединены, игнорируются. Дополнительные сведения см. в разделе [CMFCBaseTabCtrl:: енаблетабдетач](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).

Вызовите этот метод, чтобы переключить панель с вкладками на режим автоматического скрытия программным способом. Панель должна быть закреплена в главном окне фрейма ( [CDockablePane:: жетдефаултпанедивидер](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) должен возвращать допустимый указатель на [кпанедивидер](../../mfc/reference/cpanedivider-class.md)).

## <a name="see-also"></a>См. также раздел

[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CDockablePane](../../mfc/reference/cdockablepane-class.md)
