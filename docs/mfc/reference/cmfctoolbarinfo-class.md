---
title: Класс CMFCToolBarInfo
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
helpviewer_keywords:
- CMFCToolBarInfo [MFC], m_uiColdResID
- CMFCToolBarInfo [MFC], m_uiDisabledResID
- CMFCToolBarInfo [MFC], m_uiHotResID
- CMFCToolBarInfo [MFC], m_uiLargeColdResID
- CMFCToolBarInfo [MFC], m_uiLargeDisabledResID
- CMFCToolBarInfo [MFC], m_uiLargeHotResID
- CMFCToolBarInfo [MFC], m_uiMenuDisabledResID
- CMFCToolBarInfo [MFC], m_uiMenuResID
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
ms.openlocfilehash: 593d1665751f7322fc2a9cee307620df88d46876
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376196"
---
# <a name="cmfctoolbarinfo-class"></a>Класс CMFCToolBarInfo

Содержит идентификаторы ресурса изображений панели инструментов в различных состояниях. `CMFCToolBarInfo`является помощником класса, который используется в качестве параметра [CMFCToolBar::LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) метод.

## <a name="syntax"></a>Синтаксис

```
class CMFCToolBarInfo
```

## <a name="members"></a>Участники

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCToolBarInfo::m_uiColdResID](#m_uicoldresid)|Идентификатор ресурса битовой панели инструментов, содержащий регулярные (холодные) изображения панели инструментов.|
|[CMFCToolBarInfo::m_uiDisabledResID](#m_uidisabledresid)|Идентификатор ресурса битовой панели инструментов, содержащий изображения панели отключок.|
|[CMFCToolBarInfo::m_uiHotResID](#m_uihotresid)|Идентификатор ресурса битовой панели инструментов, содержащий выбранные (горячие) изображения панели инструментов.|
|[CMFCToolBarInfo::m_uiLargeColdResID](#m_uilargecoldresid)|Идентификатор ресурса битовой панели инструментов, содержащий большие регулярные изображения панели инструментов.|
|[CMFCToolBarInfo::m_uiLargeDisabledResID](#m_uilargedisabledresid)|Идентификатор ресурса битовой панели инструментов, содержащий большие изображения панели инструментов с ограниченными возможностями.|
|[CMFCToolBarInfo::m_uiLargeHotResID](#m_uilargehotresid)|Идентификатор ресурса битовой панели инструментов, содержащий большие выбранные изображения панели инструментов.|
|[CMFCToolBarInfo::m_uiMenuDisabledResID](#m_uimenudisabledresid)|Идентификатор ресурса битовой панели инструментов, содержащий изображения отключенных меню.|
|[CMFCToolBarInfo::m_uiMenuResID](#m_uimenuresid)|Идентификатор ресурса битовой панели инструментов, содержащий изображения меню.|

## <a name="remarks"></a>Примечания

Полная бит-карта панели инструментов состоит из небольших изображений панели инструментов (кнопок) фиксированного размера. Каждый идентификатор `CMFCToolBarInfo` ресурса, который хранится в объекте, представляет собой битовую карту, содержащую полный набор изображений панели инструментов в одном состоянии (например, выбранные, отключенные, большие или изображения меню).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxtoolbar.h

## <a name="cmfctoolbarinfom_uicoldresid"></a><a name="m_uicoldresid"></a>CMFCToolBarInfo::m_uiColdResID

Упогоняет идентификатор ресурса для всех обычных изображений кнопки панели инструментов.

```
UINT m_uiColdResID;
```

## <a name="cmfctoolbarinfom_uidisabledresid"></a><a name="m_uidisabledresid"></a>CMFCToolBarInfo::m_uiDisabledResID

Упогоняет идентификатор ресурса для недоступных изображений панели инструментов.

```
UINT m_uiDisabledResID;
```

## <a name="cmfctoolbarinfom_uihotresid"></a><a name="m_uihotresid"></a>CMFCToolBarInfo::m_uiHotResID

Упоняет идентификатор ресурса для всех выделенных изображений кнопки панели инструментов.

```
UINT m_uiHotResID
```

## <a name="cmfctoolbarinfom_uilargecoldresid"></a><a name="m_uilargecoldresid"></a>CMFCToolBarInfo::m_uiLargeColdResID

Определяет идентификатор ресурса для всех больших обычных изображений кнопки панели инструментов.

```
UINT m_uiLargeColdResID
```

## <a name="cmfctoolbarinfom_uilargedisabledresid"></a><a name="m_uilargedisabledresid"></a>CMFCToolBarInfo::m_uiLargeDisabledResID

Упогоняет идентификатор ресурса для всех больших отключенных изображений кнопки панели инструментов.

```
UINT m_uiLargeDisabledResID;
```

## <a name="cmfctoolbarinfom_uilargehotresid"></a><a name="m_uilargehotresid"></a>CMFCToolBarInfo::m_uiLargeHotResID

Упогоняет идентификатор ресурсов для всех больших выделенных изображений панели инструментов.

```
UINT m_uiLargeHotResID;
```

## <a name="cmfctoolbarinfom_uimenudisabledresid"></a><a name="m_uimenudisabledresid"></a>CMFCToolBarInfo::m_uiMenuDisabledResID

Уотек идентификатора ресурсов для недоступных команд изображений панели инструментов.

```
UINT m_uiMenuDisabledResID;
```

## <a name="cmfctoolbarinfom_uimenuresid"></a><a name="m_uimenuresid"></a>CMFCToolBarInfo::m_uiMenuResID

Упоньте идентификатор ресурса для всех обычных изображений элемента меню панели инструментов.

```
UINT m_uiMenuResID;
```

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)
