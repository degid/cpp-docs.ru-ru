---
title: Класс COleIPFrameWnd
ms.date: 11/04/2016
f1_keywords:
- COleIPFrameWnd
- AFXOLE/COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::COleIPFrameWnd
- AFXOLE/COleIPFrameWnd::OnCreateControlBars
- AFXOLE/COleIPFrameWnd::RepositionFrame
helpviewer_keywords:
- COleIPFrameWnd [MFC], COleIPFrameWnd
- COleIPFrameWnd [MFC], OnCreateControlBars
- COleIPFrameWnd [MFC], RepositionFrame
ms.assetid: 24abb2cb-826c-4dda-a287-d8a8900a5763
ms.openlocfilehash: 01e259cf01c42add26088b0cbd2f6dab311eb9b1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374954"
---
# <a name="coleipframewnd-class"></a>Класс COleIPFrameWnd

Основа для окна редактирования приложения "на месте".

## <a name="syntax"></a>Синтаксис

```
class COleIPFrameWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleIPFrameWnd::COleIPFrameWnd](#coleipframewnd)|Формирует объект `COleIPFrameWnd`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeIPFrameWnd::OnCreateControlBars](#oncreatecontrolbars)|Вызывается в рамках, когда элемент активирован для редактирования на месте.|
|[ColeIPFrameWnd::RepositionFrame](#repositionframe)|Вызывается в рамках для перепозиционирования окна редактирования на месте.|

## <a name="remarks"></a>Примечания

Этот класс создает и позиционирует панели управления в окне документа приложения контейнера. Он также обрабатывает уведомления, генерируемые встроенным объектом [COleReSizeBar,](../../mfc/reference/coleresizebar-class.md) когда пользователь изменяет окно редактирования на месте.

Для получения дополнительной `COleIPFrameWnd`информации [Activation](../../mfc/activation-cpp.md)об использовании, см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`COleIPFrameWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="coleipframewndcoleipframewnd"></a><a name="coleipframewnd"></a>COleIPFrameWnd::COleIPFrameWnd

Строит `COleIPFrameWnd` объект и инициализирует его информацию о состоянии, которая хранится в структуре типа OLEINPLACEFRAMEINFO.

```
COleIPFrameWnd();
```

### <a name="remarks"></a>Примечания

Для получения дополнительной информации [см. OLEINPLACEFRAMEINFO](/windows/win32/api/oleidl/ns-oleidl-oleinplaceframeinfo) в Windows SDK.

## <a name="coleipframewndoncreatecontrolbars"></a><a name="oncreatecontrolbars"></a>ColeIPFrameWnd::OnCreateControlBars

Фрейм `OnCreateControlBars` вызывает функцию при активации элемента для редактирования на месте.

```
virtual BOOL OnCreateControlBars(
    CWnd* pWndFrame,
    CWnd* pWndDoc);

virtual BOOL OnCreateControlBars(
    CFrameWnd* pWndFrame,
    CFrameWnd* pWndDoc);
```

### <a name="parameters"></a>Параметры

*pWndFrame*<br/>
Указатель на окно рамы контейнерного приложения.

*pWndDoc*<br/>
Указатель на окно уровня документа контейнера. Может быть NULL, если контейнер является приложением SDI.

### <a name="return-value"></a>Возвращаемое значение

Nonzero на успех; в противном случае, 0.

### <a name="remarks"></a>Примечания

Реализация по умолчанию не выполняет никаких действий. Переопределить эту функцию для выполнения любой специальной обработки, необходимой при создании баров управления.

## <a name="coleipframewndrepositionframe"></a><a name="repositionframe"></a>ColeIPFrameWnd::RepositionFrame

Платформа вызывает `RepositionFrame` функцию элемента для выкладывания баров управления и перепозиционирования окна редактирования на месте, чтобы все это было видно.

```
virtual void RepositionFrame(
    LPCRECT lpPosRect,
    LPCRECT lpClipRect);
```

### <a name="parameters"></a>Параметры

*lpPosRect*<br/>
Указатель на `RECT` структуру `CRect` или объект, содержащий текущие координаты текущего положения окна кадров, в пикселях относительно области клиента.

*lpClipRect*<br/>
Указатель на `RECT` структуру `CRect` или объект, содержащий текущие координаты отсечения-прямоугольника окна в месте, в пикселях относительно области клиента.

### <a name="remarks"></a>Примечания

Расположение контрольных баров в окне контейнера отличается от того, что выполняется окном кадра, не относящееся к OLE. Окно кадра, не отчаиваемые для OLE, вычисляет положения баров управления и других объектов от данного размера окна кадра, как в вызове на [CFrameWnd::RecalcLayout](../../mfc/reference/cframewnd-class.md#recalclayout). Область клиента — это то, что остается после вычитания пространства для контрольных баров и других объектов. Окно, `COleIPFrameWnd` с другой стороны, позиционирует панели инструментов в соответствии с данной областью клиента. Другими словами, `CFrameWnd::RecalcLayout` работает "снаружи в", в то время как `COleIPFrameWnd::RepositionFrame` работает "изнутри".

## <a name="see-also"></a>См. также раздел

[MFC Образец HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)
