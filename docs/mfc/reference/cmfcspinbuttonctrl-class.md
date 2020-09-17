---
title: Класс CMFCSpinButtonCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 445b857400d8c82109ca7220b84bac692a2abf89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376174"
---
# <a name="cmfcspinbuttonctrl-class"></a>Класс CMFCSpinButtonCtrl

Класс `CMFCSpinButtonCtrl` поддерживает визуальный менеджер, который рисует управление кнопкой вращения.

## <a name="syntax"></a>Синтаксис

```
class CMFCSpinButtonCtrl : public CSpinButtonCtrl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Конструктор по умолчанию.|
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCSpinButtonCtrl::Ondraw](#ondraw)|Перерисовывает текущее управление кнопкой вращения.|

## <a name="remarks"></a>Примечания

Чтобы использовать визуальный менеджер, чтобы нарисовать управление кнопкой `CSpinButtonCtrl` вращения в `CMFCSpinButtonCtrl` приложении, замените все экземпляры класса классом.

## <a name="example"></a>Пример

В следующем примере показано, как `CMFCSpinButtonCtrl` создать объект `Create` класса и использовать его метод.

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxspinbuttonctrl.h

## <a name="cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a>CMFCSpinButtonCtrl::Ondraw

Перерисовывает текущее управление кнопкой вращения.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства.

### <a name="remarks"></a>Примечания

Платформа вызывает `CMFCSpinButtonCtrl::OnPaint` метод обработки [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) сообщение, и этот `CMFCSpinButtonCtrl::OnDraw` метод, в свою очередь, вызывает этот метод. Переопределить этот метод, чтобы настроить способ управления кнопкой вращения.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)
