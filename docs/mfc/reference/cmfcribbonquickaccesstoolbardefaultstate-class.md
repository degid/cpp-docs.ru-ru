---
title: CMFCRibbonКваAccessToolToolDefaultState Класс
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
ms.openlocfilehash: eb6b36066f34036ae599a94f4d1c07b2c633e730
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753523"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonКваAccessToolToolDefaultState Класс

Вспомогательный класс, который управляет состоянием по умолчанию для панели инструментов быстрого доступа, которая расположена на ленте бар [(CMFCRibbonBar класса](../../mfc/reference/cmfcribbonbar-class.md)).

## <a name="syntax"></a>Синтаксис

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonКваAccessToolBarDefaultState::CMFCRibbonБыстрыйAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|Формирует объект `CMFCRibbonQuickAccessToolbarDefaultState`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCRibbonКвикеАкТулБарДефолтгосударство::AddCommand](#addcommand)|Добавляет команду в состояние по умолчанию для панели инструментов быстрого доступа. Это не меняет саму панель инструментов.|
|[CMFCRibbonБыстрыйAccessToolToolDefaultState::CopyFrom](#copyfrom)|Копирует свойства одной панели инструментов быстрого доступа в другую.|
|[CMFCRibbonКвикеAccessToolToolDefaultState::RemoveAll](#removeall)|Удаляет все команды из панели инструментов быстрого доступа. Это не меняет саму панель инструментов.|

## <a name="remarks"></a>Примечания

После создания панели инструментов быстрого доступа в приложении мы рекомендуем установить состояние по умолчанию, позвонив по [CMFCRibbonBar::Set'uickAccessDefaultState.](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) Это состояние по умолчанию восстанавливается, когда пользователь нажимает кнопку **Сбросить** на странице **настройки** диалогового окна **опций** приложения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCRibbonКваAccessToolToolDefaultStateгосударство](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCRibbonQuickAccessToolbarDefaultState` построить объект класса и как добавить команду в состояние по умолчанию для панели инструментов быстрого доступа.

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>Требования

**Заголовок:** afxribbonquickaccesstoolbar.h

## <a name="cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a>CMFCRibbonКвикеАкТулБарДефолтгосударство::AddCommand

Добавляет команду в состояние по умолчанию для панели инструментов быстрого доступа.

```cpp
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>Параметры

*(в) uiCmd*<br/>
Определяет идентификатор команды.

*(в) bIsVisible*<br/>
Устанавливает видимость команды при настройке панели инструментов быстрого доступа в состоянии по умолчанию.

### <a name="remarks"></a>Примечания

Добавление команды в CMFCRibbonКвикеВАйтПрикТулПромятгосударство достигает трех результатов. Во-первых, каждая добавленная команда указана на выпадении на правой стороне панели инструментов быстрого доступа. Таким образом, пользователь может легко добавить или удалить эту команду из панели инструментов быстрого доступа. Во-вторых, панель инструментов быстрого доступа сбрана, чтобы показать только те команды, которые указаны как видимые в состоянии по умолчанию, когда пользователь нажимает кнопку **Сбросить** в поле **настраиваемый** диалог. В-третьих, если вы не вызвали [CMFCRibbonBar::Set'uickAccessCommands,](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands)панель инструментов быстрого доступа использует видимые команды из этого списка, поскольку видимые по умолчанию команды при первом запуске приложения пользователем. После того как вы добавили все команды, которые вы хотите, позвоните [CMFCRibbonBar::Set'uickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) установить этот экземпляр в качестве состояния по умолчанию для панели инструментов быстрого доступа, что лента бар.

## <a name="cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a>CMFCRibbonБыстрыйAccessToolToolDefaultState::CopyFrom

Копирует свойства одной панели инструментов быстрого доступа в другую.

```cpp
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
(в) Ссылка на `CMFCRibbonQuickAccessToolBarDefaultState` исходный объект для копирования.

### <a name="remarks"></a>Примечания

Этот метод копирует каждую `CMFCRibbonQuickAccessToolBarDefaultState` команду от исходного объекта к этому объекту с помощью [cmFCRibbon'uickAccessToolBarDefaultState::AddCommand](#addcommand) метод.

## <a name="cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a>CMFCRibbonКваAccessToolBarDefaultState::CMFCRibbonБыстрыйAccessToolBarDefaultState

Строит объект состояния состояния панели инструментов быстрого доступа.

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>Примечания

По умолчанию список команд, который содержит новый экземпляр [CMFRibbon,uickAccessToolBarDefaultState,](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) пуст.

## <a name="cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a>CMFCRibbonКвикеAccessToolToolDefaultState::RemoveAll

Очищает список команд по умолчанию в панели инструментов быстрого доступа.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Эта функция удаляет из этого экземпляра все команды, которые предыдущие вызовы [cmfcRibbon'uickAccessToolToolDefaultState::AddCommand](#addcommand) добавил.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)
