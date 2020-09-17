---
title: CMFCDragFrameImpИмпл класс
ms.date: 10/18/2018
f1_keywords:
- CMFCDragFrameImpl
helpviewer_keywords:
- CMFCDragFrameImpl class [MFC]
ms.assetid: 500cd824-8188-43c2-8754-b7bb46b5648a
ms.openlocfilehash: 527fd089962e05c44a7e47b1ae52345116da4470
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752439"
---
# <a name="cmfcdragframeimpl-class"></a>CMFCDragFrameImpИмпл класс

Класс `CMFCDragFrameImpl` рисует прямоугольник перетаскивания, который появляется, когда пользователь перетаскивает панель в стандартном режиме док.
Для получения более подробной информации смотрите исходный код, расположенный в папке **VC\\atlmfc\\src\\mfc** установки Visual Studio.

## <a name="syntax"></a>Синтаксис

```
class CMFCDragFrameImpl
```

## <a name="remarks"></a>Примечания

Объект этого класса встраивается в каждый объект [класса CPane.](../../mfc/reference/cpane-class.md) Таким образом, каждая `CanFloat` панель, используюая метод, отображает прямоугольник перетаскивания, когда пользователь перетаскивает его.

Вы можете контролировать толщину прямоугольника перетаскивания, используя [AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](afx-global-data-structure.md#m_ndragframethicknessfloat) и [AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](afx-global-data-structure.md#m_ndragframethicknessdock).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CMFCDragFrameImpl](../../mfc/reference/cmfcdragframeimpl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxdragframeimpl.h

## <a name="cmfcdragframeimplenddrawdragframe"></a><a name="enddrawdragframe"></a>CMFCDragFrameImpl::EndDrawDragFrame

```cpp
void EndDrawDragFrame(BOOL bClearInternalRects = TRUE);
```

### <a name="parameters"></a>Параметры

(в) *bClearInternalRects*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcdragframeimplinit"></a><a name="init"></a>CMFCDragFrameImpl::Init

```cpp
void Init(CWnd* pDraggedWnd);
```

### <a name="parameters"></a>Параметры

(в) *pDraggedWnd*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcdragframeimplmovedragframe"></a><a name="movedragframe"></a>CMFCDragFrameImpl::MoveDragFrame

```cpp
void MoveDragFrame(BOOL bForceMove = FALSE);
```

### <a name="parameters"></a>Параметры

(в) *bForceMove*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcdragframeimplplacetabpredocking"></a><a name="placetabpredocking"></a>CMFCDragFrameImpl::PлейтакТабДокинг

```cpp
void PlaceTabPreDocking(
    CBaseTabbedPane* pTabbedBar,
    BOOL bFirstTime);

void PlaceTabPreDocking(CWnd* pCBarToPlaceOn);
```

### <a name="parameters"></a>Параметры

(в) *pTabbedBar*<br/>

(в) *bFirstTime*<br/>

(в) *pCbartoplaceon*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcdragframeimplremovetabpredocking"></a><a name="removetabpredocking"></a>CMFCDragFrameImpl::RemoveTabPreDocking

```cpp
void RemoveTabPreDocking(CDockablePane* pOldTargetBar = NULL);
```

### <a name="parameters"></a>Параметры

(в) *pOldTargetBar*<br/>

### <a name="remarks"></a>Примечания

## <a name="cmfcdragframeimplresetstate"></a><a name="resetstate"></a>CMFCDragFrameImpl::Resetstate

```cpp
void ResetState();
```

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)
