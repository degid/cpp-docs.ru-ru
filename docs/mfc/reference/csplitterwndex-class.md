---
title: Класс CSplitterWndEx
ms.date: 11/04/2016
f1_keywords:
- CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx
- AFXSPLITTERWNDEX/CSplitterWndEx::OnDrawSplitter
helpviewer_keywords:
- CSplitterWndEx [MFC], OnDrawSplitter
ms.assetid: 33e5eef3-05e1-4a07-a968-bf9207ce8598
ms.openlocfilehash: d7952e3082bf68cff7ad9ba218073081ee522320
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363924"
---
# <a name="csplitterwndex-class"></a>Класс CSplitterWndEx

Представляет настроенное окно-разделитель.

## <a name="syntax"></a>Синтаксис

```
class CSplitterWndEx : public CSplitterWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|`CSplitterWndEx::CSplitterWndEx`|Конструктор по умолчанию.|
|`CSplitterWndEx::~CSplitterWndEx`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSplitterWndEx::OnDrawSplitter](#ondrawsplitter)|Вызывается по фреймворку, чтобы нарисовать окно сплиттера. (Переопределяет [CSplitterWnd::OnDrawSplitter](csplitterwnd-class.md#ondrawsplitter).)|

## <a name="remarks"></a>Примечания

Переопределить `OnDrawSplitter` метод настройки внешнего вида графических компонентов окна сплиттера.

Класс `CSplitterWndEx` используется вместе с методами [OnDrawSplitterBorder,](cmfcvisualmanager-class.md#ondrawsplitterborder) [OnDrawSplitterBox](cmfcvisualmanager-class.md#ondrawsplitterbox)и [OnFillSplitterBackground,](cmfcvisualmanager-class.md#onfillsplitterbackground) которые реализуются визуальным менеджером. Чтобы заставить визуального менеджера нарисовать окно сплиттера `CSplitterWnd` в `CSplitterWndEx` приложении, замените декларации класса классом. Для приложений окна кадра класс окна сплиттера объявляется в классе CMainFrame, который находится в mainfrm.h. Например, смотрите `OutlookDemo` образец в каталоге «Образцы».

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

[CSplitterWnd](csplitterwnd-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxsplitterwndex.h

## <a name="csplitterwndexondrawsplitter"></a><a name="ondrawsplitter"></a>CSplitterWndEx::OnDrawSplitter

Вызывается по фреймворку, чтобы нарисовать окно сплиттера.

```
virtual void OnDrawSplitter(
   CDC* pDC,
   ESplitType nType,
   const CRect& rect
);
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
(в) Указатель на контекст устройства. Если этот параметр NULL, фреймворк перерисовывает активное окно.

*nType*<br/>
(в) Одно из `CSplitterWnd::ESplitType` значений перечисления, которое определяет элемент окна сплиттера для рисования. Допустимые значения: `splitBox`, `splitBar`, `splitIntersection` и `splitBorder`.

*rect*<br/>
(в) Ограничивающий прямоугольник, который определяет размеры и местоположение для рисования указанного элемента окна сплиттера.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../hierarchy-chart.md)<br/>
[Классы](mfc-classes.md)<br/>
[Класс CSplitterWnd](csplitterwnd-class.md)<br/>
[Класс CMFCVisualManager](cmfcvisualmanager-class.md)
