---
title: Класс CTooltipManager
ms.date: 11/04/2016
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
ms.openlocfilehash: 4e721740fc100a34ea08dd7ff5f9291eea2d9b36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752164"
---
# <a name="ctooltipmanager-class"></a>Класс CTooltipManager

Хранит сведения среды выполнения о подсказках. Экземпляр класса `CTooltipManager` создается один раз для каждого приложения.

## <a name="syntax"></a>Синтаксис

```
class CTooltipManager : public CObject
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTooltipManager::CreateToolTip](#createtooltip)|Создает элемент управления "Всплывающая подсказка" для указанных типов  элементов управления Windows.|
|[CTooltipManager::DeleteToolTip](#deletetooltip)|Удаляет элемент управления "Всплывающая подсказка".|
|[CTooltipManager::SetTooltipParams](#settooltipparams)|Настраивает внешний вид элемента управления "Всплывающая подсказка" для указанных типов элементов управления Windows.|
|[CTooltipManager::SetTooltipText](#settooltiptext)|Задает текст и описание для элемента управления "Всплывающая подсказка".|
|[CTooltipManager::UpdateTooltips](#updatetooltips)||

## <a name="remarks"></a>Примечания

Используйте [CMFCToolTipCtrl класса](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`и `CTooltipManager` вместе для реализации индивидуальных инструментов в вашем приложении. Пример того, как использовать эти классы наборов инструментов, можно ознакомьтесь с темой [класса CMFCToolToolTipCtrl.](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtooltipmanager.h

## <a name="ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a>CTooltipManager::CreateToolTip

Создает инструментарий управления.

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>Параметры

*pToolTip*<br/>
(ваут) Ссылка на указатель наборов инструментов. Он устанавливается, чтобы указать на вновь созданный набор инструментов, когда функция возвращается.

*pWndParent*<br/>
(в) Родитель инструментария.

*nType*<br/>
(в) Тип инструментария.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если набор инструментов был успешно создан.

### <a name="remarks"></a>Примечания

Вы должны позвонить [CTooltipManager::DeleteToolTip,](#deletetooltip) чтобы удалить элемент управления, который передается обратно в *pToolTip*.

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) устанавливает параметры визуального отображения каждого набора инструментов, которые он создает, на основе типа инструментария, который указывает *nType.* Чтобы изменить параметры для одного или нескольких типов инструментов, позвоните [CTooltipManager::SetTooltipParams](#settooltipparams).

Действительные типы наборов инструментов перечислены в следующей таблице:

|Тип инструментария|Категория управления|Типы примеров|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|Кнопка.|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Заголовок бар.|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|Любой элемент управления, который не соответствует другой категории.|Нет.|
|AFX_TOOLTIP_TYPE_DOCKBAR|Док-панель.|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|Текстовое поле.|Нет.|
|AFX_TOOLTIP_TYPE_MINIFRAME|Миникадр.|CPaneFrameWnd|
|AFX_TOOLTIP_TYPE_PLANNER|Планировщик.|Нет.|
|AFX_TOOLTIP_TYPE_RIBBON|Ленточный бар.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|
|AFX_TOOLTIP_TYPE_TAB|Контроль вкладок.|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|Панель инструментов.|CMFCToolBar, CMFCPopupMenuBar|
|AFX_TOOLTIP_TYPE_TOOLBOX|Набор инструментов.|Нет.|

## <a name="ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a>CTooltipManager::DeleteToolTip

Удаляет элемент управления "Всплывающая подсказка".

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>Параметры

*pToolTip*<br/>
(в, вне) Ссылка на указатель на инструмент, который должен быть уничтожен.

### <a name="remarks"></a>Примечания

Назовите этот метод для каждого [класса CToolTipCtrl,](../../mfc/reference/ctooltipctrl-class.md) созданного [CTooltipManager::CreateToolTip](#createtooltip). Родительский элемент должен вызвать `OnDestroy` этот метод из его обработчика. Это необходимо для правильного удаления инструментария из платформы. Этот метод устанавливает *pToolTip* в NULL, прежде чем он вернется.

## <a name="ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a>CTooltipManager::SetTooltipParams

Настраивает внешний вид управления набором инструментов для указанных типов управления Windows.

```cpp
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>Параметры

*nТипы*<br/>
(в) Определяет типы управления.

*pRTC*<br/>
(в) Runtime класс пользовательских инструментов.

*pParams*<br/>
(в) Параметры Tooltip.

### <a name="remarks"></a>Примечания

Этот метод устанавливает класс времени выполнения и начальные параметры, которые использует [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) при создаете инструменты. Когда элемент управления вызывает [CTooltipManager::CreateToolTip](#createtooltip) и передает сярприза в типе tooltip, который является одним из типов, указанных *nTypes,* менеджер инструментария создает элементуправления, который является экземпляром класса времени выполнения, указанного *pRTC,* и передает параметры, указанные *pParams,* в новый набор инструментов.

При вызове этого метода все существующие владельцы наборов инструментов получают AFX_WM_UPDATETOOLTIPS сообщение, и они должны воссоздать свои инструменты с помощью [CTooltipManager::CreateToolTip](#createtooltip).

*nTypes* может быть любой комбинацией действительных типов инструментов, которые использует [CTooltipManager::CreateToolTip,](#createtooltip) или это может быть AFX_TOOLTIP_TYPE_ALL. Если вы проходите AFX_TOOLTIP_TYPE_ALL, все типы tooltip затронуты.

### <a name="example"></a>Пример

В следующем примере показано, `SetTooltipParams` как `CTooltipManager` использовать метод класса. Этот фрагмент кода входит в состав [примера Draw Client](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

## <a name="ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a>CTooltipManager::SetTooltipText

Устанавливает текст и описание для инструментария.

```
static void SetTooltipText(
    TOOLINFO* pTI,
    CToolTipCtrl* pToolTip,
    UINT nType,
    const CString strText,
    LPCTSTR lpszDescr=NULL);
```

### <a name="parameters"></a>Параметры

*Pti*<br/>
(в) Указатель на объект TOOLINFO.

*pToolTip*<br/>
(в, вне) Указатель на элемент управления набором инструментов, для которого можно установить текст и описание.

*nType*<br/>
(в) Определяет тип управления, с которым связан этот набор инструментов.

*strText*<br/>
(в) Текст для установки в качестве текста tooltip.

*lpszDescr*<br/>
(в) Указатель на описание инструментария. Может иметь значение NULL.

### <a name="remarks"></a>Примечания

Значение *nType* должно быть таким же значением, как и параметр *nType* [CTooltipManager::CreateToolTip](#createtooltip) при создании инструментария.

## <a name="ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a>CTooltipManager::UpdateTooltips

Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

```cpp
void UpdateTooltips();
```

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[Класс CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)
