---
title: Класс CProgressCtrl
ms.date: 11/04/2016
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
ms.openlocfilehash: eda19ca2b94978201806e60d2ae8399e00e13f1f
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561522"
---
# <a name="cprogressctrl-class"></a>Класс CProgressCtrl

Предоставляет функциональные возможности стандартного элемента управления "индикатор выполнения" Windows.

## <a name="syntax"></a>Синтаксис

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CProgressCtrl:: CProgressCtrl](#cprogressctrl)|Формирует объект `CProgressCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CProgressCtrl:: Create](#create)|Создает элемент управления "индикатор выполнения" и прикрепляет его к `CProgressCtrl` объекту.|
|[CProgressCtrl:: Креатикс](#createex)|Создает элемент управления хода выполнения с указанными расширенными стилями Windows и прикрепляет его к `CProgressCtrl` объекту.|
|[CProgressCtrl:: Жетбарколор](#getbarcolor)|Возвращает цвет индикатора хода выполнения для текущего элемента управления "индикатор выполнения".|
|[CProgressCtrl:: Жетбкколор](#getbkcolor)|Возвращает цвет фона текущего индикатора выполнения.|
|[CProgressCtrl:: Жетпос](#getpos)|Возвращает текущее расположение индикатора выполнения.|
|[CProgressCtrl:: Range](#getrange)|Возвращает нижний и верхний пределы диапазона элемента управления "индикатор выполнения".|
|[CProgressCtrl:: State](#getstate)|Возвращает состояние текущего элемента управления "индикатор выполнения".|
|[CProgressCtrl:: onstep](#getstep)|Возвращает шаг приращения для индикатора выполнения текущего элемента управления "индикатор выполнения".|
|[CProgressCtrl:: Оффсетпос](#offsetpos)|Изменяет текущую позицию элемента управления "индикатор выполнения" на заданное приращение и перерисовывает линию, чтобы отразить новую позицию.|
|[CProgressCtrl:: Сетбарколор](#setbarcolor)|Задает цвет индикатора хода выполнения в текущем элементе управления "индикатор выполнения".|
|[CProgressCtrl:: Сетбкколор](#setbkcolor)|Задает цвет фона для индикатора выполнения.|
|[CProgressCtrl:: Сетмаркуи](#setmarquee)|Включение или выключение режима бегущей строки для текущего элемента управления "индикатор выполнения".|
|[CProgressCtrl:: Сетпос](#setpos)|Задает текущую точку для элемента управления "индикатор выполнения" и перерисовывает линию для отражения новой должности.|
|[CProgressCtrl:: SetRange](#setrange)|Задает минимальный и максимальный диапазоны для элемента управления "индикатор выполнения" и перерисовывает линию для отражения новых диапазонов.|
|[CProgressCtrl:: SetState](#setstate)|Задает состояние текущего элемента управления "Индикатор выполнения".|
|[CProgressCtrl:: Сетстеп](#setstep)|Задает шаг приращения для элемента управления "индикатор выполнения".|
|[CProgressCtrl:: Степит](#stepit)|Изменяет текущую позицию элемента управления "индикатор выполнения" на шаг шага (см. [сетстеп](#setstep)) и перерисовывает линию, чтобы отразить новую позицию.|

## <a name="remarks"></a>Примечания

Элемент управления "индикатор выполнения" — это окно, которое приложение может использовать для указания хода выполнения длительной операции. Он состоит из прямоугольника, который постепенно заполняется слева направо, с цветом выделения системы в ходе выполнения операции.

Элемент управления "индикатор выполнения" имеет диапазон и текущую точку. Диапазон представляет общую длительность операции, а текущая — ход выполнения, выполненный приложением для завершения операции. В процедуре окна используется диапазон и текущая координата для определения процента индикатора выполнения для заполнения цветом выделения. Так как значения диапазона и текущего расположения выражаются как целые числа со знаком, возможный диапазон значений текущей позицией составляет от-2 147 483 648 до 2 147 483 647 включительно.

Дополнительные сведения об использовании см `CProgressCtrl` . в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CProgressCtrl](../../mfc/using-cprogressctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cprogressctrlcprogressctrl"></a><a name="cprogressctrl"></a> CProgressCtrl:: CProgressCtrl

Формирует объект `CProgressCtrl`.

```
CProgressCtrl();
```

### <a name="remarks"></a>Примечания

После создания `CProgressCtrl` объекта вызовите метод, `CProgressCtrl::Create` чтобы создать элемент управления "индикатор выполнения".

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

## <a name="cprogressctrlcreate"></a><a name="create"></a> CProgressCtrl:: Create

Создает элемент управления "индикатор выполнения" и прикрепляет его к `CProgressCtrl` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает стиль элемента управления "индикатор выполнения". Примените любое сочетание окна стилесдескрибед в [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) в Windows SDK, помимо следующих стилей элемента управления индикатором выполнения, к элементу управления:

- PBS_VERTICAL отображает сведения о ходе выполнения по вертикали сверху вниз. Без этого флага элемент управления "индикатор выполнения" отображается горизонтально, слева направо.

- PBS_SMOOTH отображает постепенное, гладкое заполнение элемента управления "индикатор выполнения". Без этого флага элемент управления будет заполняться блоками.

*rect*<br/>
Задает размер и расположение элемента управления "индикатор выполнения". Это может быть либо объект [крект](../../atl-mfc-shared/reference/crect-class.md) , либо структура [Rect](/windows/win32/api/windef/ns-windef-rect) . Поскольку элемент управления должен быть дочерним окном, указанные координаты зависят от клиентской области *ппарентвнд*.

*ппарентвнд*<br/>
Задает родительское окно элемента управления "индикатор выполнения", обычно `CDialog` . Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления индикатора выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если `CProgressCtrl` объект успешно создан; в противном случае — значение false.

### <a name="remarks"></a>Примечания

`CProgressCtrl`Объект создается в два этапа. Сначала вызовите конструктор, который создает `CProgressCtrl` объект, а затем вызовите `Create` , который создает элемент управления "индикатор выполнения".

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

## <a name="cprogressctrlcreateex"></a><a name="createex"></a> CProgressCtrl:: Креатикс

Создает элемент управления (дочернее окно) и связывает его с `CProgressCtrl` объектом.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двексстиле*<br/>
Задает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе параметр *двексстиле* для [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) в Windows SDK.

*двстиле*<br/>
Задает стиль элемента управления "индикатор выполнения". Примените любое сочетание стилей окон, описанное в [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) , в Windows SDK.

*rect*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , описывающую размер и расположение создаваемого окна в клиентских координатах *ппарентвнд*.

*ппарентвнд*<br/>
Указатель на окно, которое является родительским элементом управления.

*nID*<br/>
Идентификатор дочернего окна элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [CREATE](#create) , чтобы применить расширенные стили Windows, заданные **WS_EX_** в расширенном стиле Windows.

## <a name="cprogressctrlgetbarcolor"></a><a name="getbarcolor"></a> CProgressCtrl:: Жетбарколор

Возвращает цвет индикатора хода выполнения для текущего элемента управления "индикатор выполнения".

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет текущего индикатора выполнения, представленный в виде значения [COLORREF](/windows/win32/gdi/colorref) , или CLR_DEFAULT, если цвет панели индикаторов выполнения является цветом по умолчанию.

### <a name="remarks"></a>Примечания

Этот метод отправляет [PBM_GETBARCOLOR](/windows/win32/Controls/pbm-getbarcolor) сообщение, описанное в Windows SDK.

## <a name="cprogressctrlgetbkcolor"></a><a name="getbkcolor"></a> CProgressCtrl:: Жетбкколор

Возвращает цвет фона текущего индикатора выполнения.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Цвет фона текущего индикатора выполнения, представленный в виде значения [COLORREF](/windows/win32/gdi/colorref) .

### <a name="remarks"></a>Примечания

Этот метод отправляет [PBM_GETBKCOLOR](/windows/win32/Controls/pbm-getbkcolor) сообщение, описанное в Windows SDK.

## <a name="cprogressctrlgetpos"></a><a name="getpos"></a> CProgressCtrl:: Жетпос

Извлекает текущее расположение индикатора выполнения.

```
int GetPos();
```

### <a name="return-value"></a>Возвращаемое значение

Расположение элемента управления "индикатор выполнения".

### <a name="remarks"></a>Примечания

Положение элемента управления "индикатор выполнения" не является физическим расположением на экране, а находится между верхним и нижним диапазонами, указанными в [SetRange](#setrange).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

## <a name="cprogressctrlgetrange"></a><a name="getrange"></a> CProgressCtrl:: Range

Возвращает текущие нижний и верхний пределы (или диапазон) элемента управления "индикатор выполнения".

```cpp
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>Параметры

*нловер*<br/>
Ссылка на целое число, получающее нижнюю границу элемента управления "индикатор выполнения".

*нуппер*<br/>
Ссылка на целое число, получающее верхний предел элемента управления "индикатор выполнения".

### <a name="remarks"></a>Примечания

Эта функция копирует значения нижнего и верхнего пределов в целые числа, на которые ссылаются *нловер* и *нуппер*соответственно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

## <a name="cprogressctrlgetstate"></a><a name="getstate"></a> CProgressCtrl:: State

Возвращает состояние текущего элемента управления "индикатор выполнения".

```
int GetState() const;
```

### <a name="return-value"></a>Возвращаемое значение

Состояние текущего элемента управления "индикатор выполнения", которое является одним из следующих значений:

|Значение|Состояние|
|-----------|-----------|
|PBST_NORMAL|Выполняется|
|PBST_ERROR|Error|
|PBST_PAUSED|Пауза|

### <a name="remarks"></a>Примечания

Этот метод отправляет [PBM_GETSTATE](/windows/win32/Controls/pbm-getstate) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

В следующем примере кода извлекается состояние текущего элемента управления "индикатор выполнения".

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

## <a name="cprogressctrlgetstep"></a><a name="getstep"></a> CProgressCtrl:: onstep

Возвращает шаг приращения для индикатора выполнения текущего элемента управления "индикатор выполнения".

```
int GetStep() const;
```

### <a name="return-value"></a>Возвращаемое значение

Шаг приращения индикатора выполнения.

### <a name="remarks"></a>Примечания

Шаг приращения — это величина, на которую вызов [CProgressCtrl:: степит](#stepit) увеличивает текущее расположение индикатора выполнения.

Этот метод отправляет [PBM_GETSTEP](/windows/win32/Controls/pbm-getstep) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

В следующем примере кода извлекается шаг приращения текущего элемента управления "индикатор выполнения".

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

## <a name="cprogressctrloffsetpos"></a><a name="offsetpos"></a> CProgressCtrl:: Оффсетпос

Изменяет текущую позицию элемента управления "индикатор выполнения" на шаг приращения, заданный параметром *npos* , и перерисовывает линию, чтобы отразить новую позицию.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Величина, на которую должно быть перемещено расположение.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее расположение элемента управления "индикатор выполнения".

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

## <a name="cprogressctrlsetbarcolor"></a><a name="setbarcolor"></a> CProgressCtrl:: Сетбарколор

Задает цвет индикатора хода выполнения в текущем элементе управления "индикатор выполнения".

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>Параметры

*клрбар*\
окне Значение [COLORREF](/windows/win32/gdi/colorref) , указывающее новый цвет индикатора хода выполнения. Укажите CLR_DEFAULT, чтобы в индикаторе выполнения использовался цвет по умолчанию.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий цвет индикатора хода выполнения, представленный в виде значения [COLORREF](/windows/win32/gdi/colorref) , или CLR_DEFAULT, если цвет индикатора выполнения является цветом по умолчанию.

### <a name="remarks"></a>Примечания

`SetBarColor`Метод задает цвет индикатора выполнения только в том случае, если [Тема](/windows/win32/Controls/visual-styles-overview) Windows Vista не действует.

Этот метод отправляет [PBM_SETBARCOLOR](/windows/win32/Controls/pbm-setbarcolor) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

В следующем примере кода цвет индикатора выполнения изменяется на красный, зеленый, синий или по умолчанию.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

## <a name="cprogressctrlsetbkcolor"></a><a name="setbkcolor"></a> CProgressCtrl:: Сетбкколор

Задает цвет фона для индикатора выполнения.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>Параметры

*клрнев*<br/>
Значение COLORREF, указывающее новый цвет фона. Укажите CLR_DEFAULT значение, чтобы использовать цвет фона по умолчанию для индикатора выполнения.

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , указывающее предыдущий цвет фона, или CLR_DEFAULT, если цвет фона является цветом по умолчанию.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

## <a name="cprogressctrlsetmarquee"></a><a name="setmarquee"></a> CProgressCtrl:: Сетмаркуи

Включение или выключение режима бегущей строки для текущего элемента управления "индикатор выполнения".

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>Параметры

*фмаркуимоде*\
окне Значение TRUE, чтобы включить режим бегущей строки или значение FALSE, чтобы отключить режим бегущей строки.

*Nинтервал*\
окне Время в миллисекундах между обновлениями анимации бегущей строки.

### <a name="return-value"></a>Возвращаемое значение

Этот метод всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Если включен режим "бегущая строка", индикатор выполнения анимируется и прокручивается как знак в области театра.

Этот метод отправляет [PBM_SETMARQUEE](/windows/win32/Controls/pbm-setmarquee) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

Следующий пример кода запускает и останавливает анимацию с бегущей полосой.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

## <a name="cprogressctrlsetpos"></a><a name="setpos"></a> CProgressCtrl:: Сетпос

Задает текущую точку элемента управления "индикатор выполнения" в соответствии с *npos* и перерисовывает линию для отражения новой должности.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Новое расположение элемента управления "индикатор выполнения".

### <a name="return-value"></a>Возвращаемое значение

Предыдущее расположение элемента управления "индикатор выполнения".

### <a name="remarks"></a>Примечания

Положение элемента управления "индикатор выполнения" не является физическим расположением на экране, а находится между верхним и нижним диапазонами, указанными в [SetRange](#setrange).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

## <a name="cprogressctrlsetrange"></a><a name="setrange"></a> CProgressCtrl:: SetRange

Задает верхний и нижний пределы диапазона элемента управления "индикатор выполнения" и перерисовывает линию для отражения новых диапазонов.

```cpp
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Параметры

*нловер*<br/>
Задает нижнюю границу диапазона (по умолчанию равен нулю).

*нуппер*<br/>
Задает верхний предел диапазона (по умолчанию — 100).

### <a name="remarks"></a>Примечания

Функция-член `SetRange32` задает 32-разрядный диапазон для элемента управления progress.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

## <a name="cprogressctrlsetstate"></a><a name="setstate"></a> CProgressCtrl:: SetState

Задает состояние текущего элемента управления "Индикатор выполнения".

```
int SetState(int iState);
```

### <a name="parameters"></a>Параметры

*татэ*\
окне Состояние для задания индикатора выполнения. Используйте одно из следующих значений:

- `PBST_NORMAL` -Выполняется
- `PBST_ERROR` -Ошибка
- `PBST_PAUSED` — приостановлено.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее состояние текущего элемента управления "Индикатор выполнения".

### <a name="remarks"></a>Примечания

Этот метод отправляет [PBM_SETSTATE](/windows/win32/Controls/pbm-setstate) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная `m_progressCtrl`, используемая для программного доступа к элементу управления "Индикатор выполнения". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Пример

Следующий пример кода позволяет задать состояние текущего индикатора выполнения: "Приостановлено" или "Выполняется".

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

## <a name="cprogressctrlsetstep"></a><a name="setstep"></a> CProgressCtrl:: Сетстеп

Задает шаг приращения для элемента управления "индикатор выполнения".

```
int SetStep(int nStep);
```

### <a name="parameters"></a>Параметры

*нстеп*<br/>
Шаг приращения нового шага.

### <a name="return-value"></a>Возвращаемое значение

Шаг приращения предыдущего шага.

### <a name="remarks"></a>Примечания

Шаг приращения — это величина, на которую вызов `CProgressCtrl::StepIt` увеличивает текущее расположение индикатора выполнения.

По умолчанию шаг шага равен 10.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

## <a name="cprogressctrlstepit"></a><a name="stepit"></a> CProgressCtrl:: Степит

Изменяет текущую позицию элемента управления "индикатор выполнения" на шаг приращения шага и перерисовывает линию, чтобы отразить новую позицию.

```
int StepIt();
```

### <a name="return-value"></a>Возвращаемое значение

Предыдущее расположение элемента управления "индикатор выполнения".

### <a name="remarks"></a>Примечания

Шаг приращения задается `CProgressCtrl::SetStep` функцией-членом.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>См. также

[Пример CMNCTRL2 для MFC](../../overview/visual-cpp-samples.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)
