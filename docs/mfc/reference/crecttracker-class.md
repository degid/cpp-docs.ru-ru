---
title: Класс CRectTracker
ms.date: 11/19/2018
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
ms.openlocfilehash: c3600bc5a945c24e91269bc280b4b8e99c54d4c8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750454"
---
# <a name="crecttracker-class"></a>Класс CRectTracker

Позволяет отображать элемент, перемещать и переделывать сяризбить по-разному.

## <a name="syntax"></a>Синтаксис

```
class CRectTracker
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRectTracker::CRectTracker](#crecttracker)|Формирует объект `CRectTracker`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRectTracker::AdjustRect](#adjustrect)|Вызывается при повторном размере прямоугольника.|
|[CRectTracker::Draw](#draw)|Рендерс прямоугольник.|
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|Вызывается при рисовании границы `CRectTracker` объекта.|
|[CRectTracker::GetHandleMask](#gethandlemask)|Вызывается, чтобы получить `CRectTracker` маску из реразмерных ручек предмета.|
|[CRectTracker::GetTrueRect](#gettruerect)|Возвращает ширину и высоту прямоугольника, включая реразмерные ручки.|
|[CRectTracker::HitTest](#hittest)|Возвращает текущее положение курсора, `CRectTracker` связанного с объектом.|
|[CRectTracker::NormalizeHit](#normalizehit)|Нормализует код хит-теста.|
|[CRectTracker::OnChangedRect](#onchangedrect)|Вызывается, когда прямоугольник был уменьшен или перемещен.|
|[CRectTracker::SetCursor](#setcursor)|Устанавливает курсор, в зависимости от его положения над прямоугольником.|
|[CRectTracker::Track](#track)|Позволяет пользователю манипулировать прямоугольником.|
|[CRectTracker:TrackRubberBand](#trackrubberband)|Позволяет пользователю "резиновой полосой" выбора.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|Определяет размер реразмерных ручек.|
|[CRectTracker:::m_nStyle](#m_nstyle)|Текущий стиль (ы) трекера.|
|[CRectTracker:::m_rect](#m_rect)|Текущее положение (в пикселях) прямоугольника.|
|[CRectTracker::m_sizeMin](#m_sizemin)|Определяет минимальную ширину прямоугольника и высоту.|

## <a name="remarks"></a>Примечания

`CRectTracker`не имеет базового класса.

Хотя `CRectTracker` класс предназначен для того, чтобы позволить пользователю взаимодействовать с элементами OLE с помощью графического интерфейса, его использование не ограничивается приложениями с поддержкой OLE. Он может быть использован в любом месте такой пользовательский интерфейс не требуется.

`CRectTracker`границы могут быть сплошными или пунктирными линиями. Элементу может быть предоставлена вылупиваяся граница или наложена вылупиваяся узор, обозначить различные состояния элемента. Вы можете разместить восемь реразмерных ручек либо на внешней или внутренней границе элемента. (Для объяснения реразмерных ручек см. [GetHandleMask.)](#gethandlemask) Наконец, `CRectTracker` позволяет изменить ориентацию элемента во время изменения размера.

Для `CRectTracker`использования, `CRectTracker` построить объект и указать, какие состояния отображения инициализированы. Затем можно использовать этот интерфейс, чтобы дать пользователю визуальную `CRectTracker` обратную связь о текущем состоянии элемента OLE, связанного с объектом.

Для получения дополнительной `CRectTracker`информации об использовании , см. [Trackers](../../mfc/trackers.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CRectTracker`

## <a name="requirements"></a>Требования

**Заголовок:** afxext.h

## <a name="crecttrackeradjustrect"></a><a name="adjustrect"></a>CRectTracker::AdjustRect

Вызывается фреймворком при повторном размере прямоугольника с помощью реразмерной ручки.

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*nХРукт*<br/>
Индекс используемой ручки.

*lpRect*<br/>
Указатель на текущий размер прямоугольника. (Размер прямоугольника дается его высотой и шириной.)

### <a name="remarks"></a>Примечания

Поведение этой функции по умолчанию позволяет ориентации прямоугольника изменяться только тогда, когда `Track` и `TrackRubberBand` вызывается с разрешенной инвертированием.

Переопределить эту функцию для управления регулировкой прямоугольника слежения во время операции перетаскивания. Один из методов заключается в регулировке координат, указанных *lpRect* перед возвращением.

Специальные функции, которые `CRectTracker`не поддерживаются напрямую, такие как snap-to-grid или keep-aspect-ratio, могут быть реализованы путем переопределения этой функции.

## <a name="crecttrackercrecttracker"></a><a name="crecttracker"></a>CRectTracker::CRectTracker

Создает и инициализирует объект `CRectTracker`.

```
CRectTracker();

CRectTracker(
    LPCRECT lpSrcRect,
    UINT nStyle);
```

### <a name="parameters"></a>Параметры

*lpSrcRect*<br/>
Координаты объекта прямоугольника.

*nStyle*<br/>
Определяет стиль `CRectTracker` объекта. Поддерживаются следующие стили:

- `CRectTracker::solidLine`Используйте сплошную линию для прямоугольной границы.

- `CRectTracker::dottedLine`Используйте пунктирную линию для прямоугольной границы.

- `CRectTracker::hatchedBorder`Используйте вылупившийся узор для прямоугольной границы.

- `CRectTracker::resizeInside`Реразмерные ручки, расположенные внутри прямоугольника.

- `CRectTracker::resizeOutside`Реразмерные ручки, расположенные за пределами прямоугольника.

- `CRectTracker::hatchInside`Вылупившийся узор покрывает весь прямоугольник.

### <a name="remarks"></a>Примечания

Конструктор по умолчанию инициализирует `CRectTracker` объект с значениями от *lpSrcRect* и инициализирует другие размеры для системных по умолчанию. Если объект создается без каких-либо параметров, `m_rect` то и члены `m_nStyle` данных не являются первоначальными.

## <a name="crecttrackerdraw"></a><a name="draw"></a>CRectTracker::Draw

Назовите эту функцию, чтобы нарисовать внешние линии прямоугольника и внутреннюю область.

```cpp
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>Параметры

*pDC*<br/>
Указатель на контекст устройства, на котором можно рисовать.

### <a name="remarks"></a>Примечания

Стиль трекера определяет, как делается рисунок. `CRectTracker` Дополнительную информацию о доступных стилях можно найти на конструкторе.

## <a name="crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a>CRectTracker::DrawTrackerRect

Вызывается по системе всякий раз, когда положение `Track` `TrackRubberBand` трекера изменилось в то время как внутри или функции члена.

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*lpRect*<br/>
Указатель на `RECT` то, что содержит прямоугольник для рисования.

*pWndClipTo*<br/>
Указатель на окно для использования в отсечении прямоугольника.

*pDC*<br/>
Указатель на контекст устройства, на котором можно рисовать.

*pWnd*<br/>
Указатель на окно, на котором будет происходить рисунок.

### <a name="remarks"></a>Примечания

Реализация по умолчанию `CDC::DrawFocusRect`делает вызов, который рисует пунктирный прямоугольник.

Переопределить эту функцию, чтобы обеспечить различную обратную связь во время операции отслеживания.

## <a name="crecttrackergethandlemask"></a><a name="gethandlemask"></a>CRectTracker::GetHandleMask

Платформа вызывает эту функцию члена для извлечения маски для реразмерных декейок прямоугольника.

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>Возвращаемое значение

Маска реразмерных ручек `CRectTracker` предмета.

### <a name="remarks"></a>Примечания

Ручки изменения размера отображаются по бокам и углам прямоугольника и позволяют пользователю контролировать форму и размер прямоугольника.

Прямоугольник имеет 8 реразмерных ручек с номерами 0-7. Каждая ручка из яснейки представлена немного в маске; значение этого бита составляет 2 *"n*, где *n* является номером реразмерной ручки. Биты 0-3 соответствуют угловым релевпробиваемым ручкам, начиная с верхнего левого движения по часовой стрелке. Биты 4-7 соответствуют боковым реразмерным ручкам, начиная с верхней части движения по часовой стрелке. На следующей иллюстрации показаны реуверенные ручки прямоугольника и соответствующие номера и значения реразмерной ручки:

![Номера регулируели](../../mfc/reference/media/vc35dp1.gif "Числа маркера изменения размера")

Реализация по `GetHandleMask` умолчанию возвращает маску битов так, чтобы появляются рефигурные ручки. Если один бит горит, соответствующая ручка повторного размера будет нарисована.

Переопределить эту функцию участника, чтобы скрыть или показать указанные ручки повторного размера.

## <a name="crecttrackergettruerect"></a><a name="gettruerect"></a>CRectTracker::GetTrueRect

Вызовите эту функцию, чтобы получить координаты прямоугольника.

```cpp
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>Параметры

*lpTrueRect*<br/>
Указатель на `RECT` структуру, которая будет содержать `CRectTracker` координаты устройства объекта.

### <a name="remarks"></a>Примечания

Размеры прямоугольника включают высоту и ширину любых решеток, расположенных на внешней границе. По *возвращении lpTrueRect* всегда является нормализованным прямоугольником в координатах устройства.

## <a name="crecttrackerhittest"></a><a name="hittest"></a>CRectTracker::HitTest

Позвоните в эту функцию, чтобы узнать, схватил ли пользователь ручку повторного размера.

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>Параметры

*Точки*<br/>
Точка, в координатах устройства, для тестирования.

### <a name="return-value"></a>Возвращаемое значение

Возврат значения основан на перечисленном типе `CRectTracker::TrackerHit` и может иметь одно из следующих значений:

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 0

- `CRectTracker::hitTopRight`1

- `CRectTracker::hitBottomRight`2

- `CRectTracker::hitBottomLeft`3

- `CRectTracker::hitTop` 4

- `CRectTracker::hitRight`5

- `CRectTracker::hitBottom`6

- `CRectTracker::hitLeft`7

- `CRectTracker::hitMiddle`8

## <a name="crecttrackerm_nhandlesize"></a><a name="m_nhandlesize"></a>CRectTracker::m_nHandleSize

Размер, в пикселях, `CRectTracker` реразмерных ручек.

```
int m_nHandleSize;
```

### <a name="remarks"></a>Примечания

Инициализировано со значением системы по умолчанию.

## <a name="crecttrackerm_rect"></a><a name="m_rect"></a>CRectTracker:::m_rect

Текущее положение прямоугольника в координатах клиента (пикселей).

```
CRect m_rect;
```

## <a name="crecttrackerm_sizemin"></a><a name="m_sizemin"></a>CRectTracker::m_sizeMin

Минимальный размер прямоугольника.

```
CSize m_sizeMin;
```

### <a name="remarks"></a>Примечания

Значения по `cx` умолчанию `cy`и, рассчитываются из значения системы по умолчанию для ширины границы. Этот член данных используется `AdjustRect` только функцией участника.

## <a name="crecttrackerm_nstyle"></a><a name="m_nstyle"></a>CRectTracker:::m_nStyle

Текущий стиль прямоугольника.

```
UINT m_nStyle;
```

### <a name="remarks"></a>Примечания

Смотрите [CRectTracker::CRectTracker](#crecttracker) для списка возможных стилей.

## <a name="crecttrackernormalizehit"></a><a name="normalizehit"></a>CRectTracker::NormalizeHit

Вызов ими функции для преобразования потенциально перевернутой ручки.

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>Параметры

*nХРукт*<br/>
Ручка, выбранная пользователем.

### <a name="return-value"></a>Возвращаемое значение

Индекс нормализованной ручки.

### <a name="remarks"></a>Примечания

Когда `CRectTracker::Track` `CRectTracker::TrackRubberBand` или называется с инвертированиеразрешено, прямоугольник может быть перевернут на оси x, y-оси, или оба. Когда это `HitTest` произойдет, будет возвращаться ручки, которые также перевернуты в отношении прямоугольника. Это не подходит для обработки отзывов курсора, поскольку обратная связь зависит от положения прямоугольника экрана, а не от той части структуры данных прямоугольника, которая будет изменена.

## <a name="crecttrackeronchangedrect"></a><a name="onchangedrect"></a>CRectTracker::OnChangedRect

Вызывается по рамкам всякий раз, когда прямоугольник трекера изменился `Track`во время вызова.

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>Параметры

*rectOld*<br/>
Содержит старые координаты `CRectTracker` устройства объекта.

### <a name="remarks"></a>Примечания

В момент вызова этой функции все `DrawTrackerRect` отзывы, нарисованные с помощью, были удалены. Реализация по умолчанию этой функции не выполняет никаких действий.

Переизобить эту функцию, когда вы хотите выполнить какие-либо действия после изменения размера прямоугольника.

## <a name="crecttrackersetcursor"></a><a name="setcursor"></a>CRectTracker::SetCursor

Вызовите эту функцию, чтобы изменить форму `CRectTracker` курсора, пока она находится над областью объекта.

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на окно, которое в настоящее время содержит курсор.

*nHitTest*<br/>
Результаты предыдущего теста хита, из сообщения WM_SETCURSOR.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если предыдущий удар был над прямоугольником трекера; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов этой функции изнутри функции окна, которая `OnSetCursor`обрабатывает WM_SETCURSOR сообщение (обычно).

## <a name="crecttrackertrack"></a><a name="track"></a>CRectTracker::Track

Вызовите эту функцию для отображения пользовательского интерфейса для изменения размера прямоугольника.

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Объект окна, содержащий прямоугольник.

*Точки*<br/>
Координаты устройства текущего положения мыши относительно области клиента.

*ballowInvert*<br/>
Если правда, прямоугольник может быть перевернут вдоль x-оси или y-оси; в противном случае FALSE.

*pWndClipTo*<br/>
Окно, к которому будут обрезаны операции рисования. Если NULL, *pWnd* используется в качестве прямоугольника отсечения.

### <a name="return-value"></a>Возвращаемое значение

При нажатии ключа ESC процесс отслеживания прекращается, прямоугольник, хранящийся в трекере, не изменяется, а 0 возвращается. Если изменение зафиксировано, путем перемещения мыши и выпуска левой кнопки мыши, новое положение и/или размер записываются в прямоугольник трекера и ненулевой возвращается.

### <a name="remarks"></a>Примечания

Это обычно вызывается изнутри функции приложения, `WM_LBUTTONDOWN` которое `OnLButtonDown`обрабатывает сообщение (обычно).

Эта функция будет захватывать мышь до тех пор, пока пользователь не выпустит левую кнопку мыши, не нажмет клавишу ESC или не нажмет правую кнопку мыши. Как пользователь перемещает курсор мыши, обратная связь `DrawTrackerRect` `OnChangedRect`обновляется путем вызова и .

Если *bAllowInvert* является правдой, прямоугольник отслеживания может быть перевернут на обеих x-оси или у-оси.

## <a name="crecttrackertrackrubberband"></a><a name="trackrubberband"></a>CRectTracker:TrackRubberBand

Вызовите эту функцию, чтобы сделать выбор резиновой полосы.

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Объект окна, содержащий прямоугольник.

*Точки*<br/>
Координаты устройства текущего положения мыши относительно области клиента.

*ballowInvert*<br/>
Если правда, прямоугольник может быть перевернут вдоль x-оси или y-оси; в противном случае FALSE.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если мышь переехала и прямоугольник не пуст; в противном случае 0.

### <a name="remarks"></a>Примечания

Обычно он вызывается изнутри функции приложения, которое `OnLButtonDown`обрабатывает WM_LBUTTONDOWN сообщение (обычно).

Эта функция будет захватывать мышь до тех пор, пока пользователь не выпустит левую кнопку мыши, не нажмет клавишу ESC или не нажмет правую кнопку мыши. Как пользователь перемещает курсор мыши, обратная связь `DrawTrackerRect` `OnChangedRect`обновляется путем вызова и .

Отслеживание выполняется с помощью выбора типа резиновой полосы с нижней правой ручки. Если инвертирование разрешено, прямоугольник может быть размером, перетащив либо вверх и влево или вниз и вправо.

## <a name="see-also"></a>См. также раздел

[MFC Образец TRACKER](../../overview/visual-cpp-samples.md)<br/>
[MFC Образец DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс ColeReReresizebar](../../mfc/reference/coleresizebar-class.md)<br/>
[Класс CRect](../../atl-mfc-shared/reference/crect-class.md)
