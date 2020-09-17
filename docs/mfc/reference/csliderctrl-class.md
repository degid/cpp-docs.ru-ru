---
title: Класс CSliderCtrl
ms.date: 11/04/2016
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
ms.openlocfilehash: 8dfdcf34474027180708045131a19bf6f7e14512
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562536"
---
# <a name="csliderctrl-class"></a>Класс CSliderCtrl

Предоставляет функциональные возможности стандартного элемента управления "ползунок" Windows.

## <a name="syntax"></a>Синтаксис

```
class CSliderCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSliderCtrl:: CSliderCtrl](#csliderctrl)|Формирует объект `CSliderCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSliderCtrl:: Клеарсел](#clearsel)|Очищает текущий выделенный фрагмент в элементе управления "ползунок".|
|[CSliderCtrl:: Клеартикс](#cleartics)|Удаляет текущие деления из элемента управления "ползунок".|
|[CSliderCtrl:: Create](#create)|Создает элемент управления "ползунок" и прикрепляет его к `CSliderCtrl` объекту.|
|[CSliderCtrl:: Креатикс](#createex)|Создает элемент управления "ползунок" с заданными расширенными стилями Windows и присоединяет его к `CSliderCtrl` объекту.|
|[CSliderCtrl:: приятель](#getbuddy)|Получает маркер для элемента управления "ползунок" в заданном месте.|
|[CSliderCtrl:: Жетчаннелрект](#getchannelrect)|Возвращает размер канала элемента управления ползунка.|
|[CSliderCtrl:: Жетлинесизе](#getlinesize)|Получает размер строки элемента управления "ползунок".|
|[CSliderCtrl:: Жетнумтикс](#getnumtics)|Возвращает число делений в элементе управления "ползунок".|
|[CSliderCtrl:: PageSize](#getpagesize)|Получает размер страницы элемента управления "ползунок".|
|[CSliderCtrl:: Жетпос](#getpos)|Извлекает текущее положение ползунка.|
|[CSliderCtrl:: Range](#getrange)|Возвращает минимальное и максимальное положение ползунка.|
|[CSliderCtrl:: Жетранжемакс](#getrangemax)|Возвращает максимальное положение для ползунка.|
|[CSliderCtrl:: Жетранжемин](#getrangemin)|Возвращает минимальное положение для ползунка.|
|[CSliderCtrl:: выделять](#getselection)|Извлекает диапазон текущего выделения.|
|[CSliderCtrl:: Жетсумбленгс](#getthumblength)|Получает длину ползунка в текущем элементе управления TrackBar.|
|[CSliderCtrl:: Жетсумбрект](#getthumbrect)|Возвращает размер бегунка элемента управления ползунка.|
|[CSliderCtrl:: Жеттик](#gettic)|Извлекает расположение указанного деления.|
|[CSliderCtrl:: Жеттикаррай](#getticarray)|Извлекает массив позиций делений для элемента управления "ползунок".|
|[CSliderCtrl:: Жеттикпос](#getticpos)|Извлекает расположение указанного деления в клиентских координатах.|
|[CSliderCtrl:: подсказки](#gettooltips)|Получает маркер для элемента управления ToolTip, назначенного элементу управления Slider (при его наличии).|
|[CSliderCtrl:: Сетбудди](#setbuddy)|Назначает окно в качестве окна собеседника для элемента управления "ползунок".|
|[CSliderCtrl:: Сетлинесизе](#setlinesize)|Задает размер линии для элемента управления "ползунок".|
|[CSliderCtrl:: SetPageSize](#setpagesize)|Задает размер страницы для элемента управления "ползунок".|
|[CSliderCtrl:: Сетпос](#setpos)|Задает текущее положение ползунка.|
|[CSliderCtrl:: SetRange](#setrange)|Задает минимальное и максимальное положение ползунка.|
|[CSliderCtrl:: Сетранжемакс](#setrangemax)|Задает максимальное положение для ползунка.|
|[CSliderCtrl:: Сетранжемин](#setrangemin)|Задает минимальное положение для ползунка.|
|[CSliderCtrl:: Сетселектион](#setselection)|Задает диапазон текущего выделения.|
|[CSliderCtrl:: Сетсумбленгс](#setthumblength)|Задает длину ползунка в текущем элементе управления TrackBar.|
|[CSliderCtrl:: Set](#settic)|Задает расположение указанного деления.|
|[CSliderCtrl:: Сеттикфрек](#setticfreq)|Задает частоту деления на шаг ползунка шкалы.|
|[CSliderCtrl:: Сеттипсиде](#settipside)|Размещает элемент управления ToolTip, используемый элементом управления TrackBar.|
|[CSliderCtrl:: Сеттултипс](#settooltips)|Назначает элемент управления ToolTip элементу управления "ползунок".|

## <a name="remarks"></a>Примечания

Элемент управления "ползунок" (также известный как TrackBar) — это окно, содержащее ползунок и необязательные деления. Когда пользователь перемещает ползунок с помощью мыши или клавиш направления, элемент управления отправляет сообщения уведомления для указания на изменение.

Элементы управления "ползунок" полезны, когда нужно, чтобы пользователь выберет дискретное значение или набор последовательных значений в диапазоне. Например, можно использовать элемент управления "ползунок", чтобы разрешить пользователю задавать скорость повтора для клавиатуры, перемещая ползунок на заданный знак деления.

Этот элемент управления (и, следовательно, `CSliderCtrl` класс) доступен только для программ, работающих под управлением windows 95/98 и Windows NT версии 3,51 и более поздних версий.

Ползунок перемещается по шагам, указанным при создании. Например, если указать, что ползунок должен иметь диапазон из пяти, то ползунок может занимать только шесть позиций: положение с левой стороны элемента управления Slider и одну позицию для каждого приращения в диапазоне. Как правило, каждая из этих позиций обозначается делением галочки.

Вы создаете ползунок с помощью конструктора и `Create` функции-члена класса `CSliderCtrl` . После создания элемента управления "ползунок" `CSliderCtrl` для изменения многих его свойств можно использовать функции-члены в. Изменения, которые можно внести, включают задание минимальных и максимальных позиций для ползунка, рисование делений, задание диапазона выбора и изменение положения ползунка.

Дополнительные сведения об использовании см `CSliderCtrl` . в разделе [элементы управления](../../mfc/controls-mfc.md) и [Использование CSliderCtrl](../../mfc/using-csliderctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSliderCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="csliderctrlclearsel"></a><a name="clearsel"></a> CSliderCtrl:: Клеарсел

Очищает текущий выделенный фрагмент в элементе управления "ползунок".

```cpp
void ClearSel(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*bRedraw*<br/>
Флаг перерисовки. Если этот параметр имеет значение TRUE, ползунок перерисовывается после очистки выделения. в противном случае ползунок не перерисовывается.

## <a name="csliderctrlcleartics"></a><a name="cleartics"></a> CSliderCtrl:: Клеартикс

Удаляет текущие деления из элемента управления "ползунок".

```cpp
void ClearTics(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*bRedraw*<br/>
Флаг перерисовки. Если этот параметр имеет значение TRUE, ползунок перерисовывается после очистки делений. в противном случае ползунок не перерисовывается.

## <a name="csliderctrlcreate"></a><a name="create"></a> CSliderCtrl:: Create

Создает элемент управления "ползунок" и прикрепляет его к `CSliderCtrl` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает стиль элемента управления "ползунок". Примените любое сочетание [стилей элементов управления Slider](/windows/win32/Controls/trackbar-control-styles), описанных в Windows SDK, к элементу управления.

*rect*<br/>
Задает размер и положение элемента управления ползунка. Это может быть либо объект [крект](../../atl-mfc-shared/reference/crect-class.md) , либо структура [Rect](/windows/win32/api/windef/ns-windef-rect) .

*ппарентвнд*<br/>
Задает родительское окно элемента управления ползунка, обычно `CDialog` . Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления ползунка.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Построение создается `CSliderCtrl` в два этапа. Сначала вызовите конструктор, а затем вызовите метод `Create` , который создает элемент управления Slider и присоединяет его к `CSliderCtrl` объекту.

В зависимости от значений, заданных для *двстиле*, элемент управления "ползунок" может иметь вертикальную или горизонтальную ориентацию. Он может иметь деления на обеих сторонах, обе стороны или ни одно из них. Он также может использоваться для указания диапазона последовательных значений.

Чтобы применить расширенные стили окна к элементу управления "ползунок", вызовите [креатикс](#createex) вместо `Create` .

## <a name="csliderctrlcreateex"></a><a name="createex"></a> CSliderCtrl:: Креатикс

Создает элемент управления (дочернее окно) и связывает его с `CSliderCtrl` объектом.

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
Задает стиль элемента управления "ползунок". Примените любое сочетание [стилей элементов управления Slider](/windows/win32/Controls/trackbar-control-styles), описанных в Windows SDK, к элементу управления.

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

## <a name="csliderctrlcsliderctrl"></a><a name="csliderctrl"></a> CSliderCtrl:: CSliderCtrl

Формирует объект `CSliderCtrl`.

```
CSliderCtrl();
```

## <a name="csliderctrlgetbuddy"></a><a name="getbuddy"></a> CSliderCtrl:: приятель

Получает маркер для элемента управления "ползунок" в заданном месте.

```
CWnd* GetBuddy(BOOL fLocation = TRUE) const;
```

### <a name="parameters"></a>Параметры

*fLocation*<br/>
Логическое значение, указывающее, какой из двух дескрипторов окна собеседников следует извлечь. Может иметь одно из следующих значений:

- Значение TRUE Получает маркер для собеседника слева от ползунка. Если элемент управления "ползунок" использует стиль TBS_VERT, сообщение будет извлекать собеседника над ползунком.

- FALSE — Получает маркер, расположенный справа от ползунка. Если элемент управления "ползунок" использует стиль TBS_VERT, сообщение будет извлекать собеседника под ползунком.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является дружественным окном в расположении, заданном параметром *fLocation*, или значение null, если в этом расположении не существует дружественного окна.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TBM_GETBUDDY](/windows/win32/Controls/tbm-getbuddy), как описано в Windows SDK. Описание стилей элемента управления "ползунок" см. в разделе [стили элементов управления TrackBar](/windows/win32/Controls/trackbar-control-styles) в Windows SDK.

## <a name="csliderctrlgetchannelrect"></a><a name="getchannelrect"></a> CSliderCtrl:: Жетчаннелрект

Получает размер и положение ограничивающего прямоугольника для канала элемента управления ползунка.

```cpp
void GetChannelRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Параметры

*лпрк*<br/>
Указатель на объект [крект](../../atl-mfc-shared/reference/crect-class.md) , который содержит размер и расположение ограничивающего прямоугольника канала при возврате функции.

### <a name="remarks"></a>Примечания

Канал — это область, в которую перемещается ползунок, который содержит выделение при выборе диапазона.

## <a name="csliderctrlgetlinesize"></a><a name="getlinesize"></a> CSliderCtrl:: Жетлинесизе

Возвращает размер линии для элемента управления "ползунок".

```
int GetLineSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер линии для элемента управления "ползунок".

### <a name="remarks"></a>Примечания

Размер линии влияет на то, сколько ползунков перемещается для TB_LINEUP и TB_LINEDOWNных уведомлений. Значение по умолчанию для параметра Размер линии равно 1.

## <a name="csliderctrlgetnumtics"></a><a name="getnumtics"></a> CSliderCtrl:: Жетнумтикс

Возвращает число делений в элементе управления "ползунок".

```
UINT GetNumTics() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число делений в элементе управления "ползунок".

## <a name="csliderctrlgetpagesize"></a><a name="getpagesize"></a> CSliderCtrl:: PageSize

Получает размер страницы для элемента управления "ползунок".

```
int GetPageSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер страницы для элемента управления "ползунок".

### <a name="remarks"></a>Примечания

Размер страницы влияет на то, сколько ползунков перемещается для TB_PAGEUP и TB_PAGEDOWN уведомлений.

## <a name="csliderctrlgetpos"></a><a name="getpos"></a> CSliderCtrl:: Жетпос

Извлекает текущее положение ползунка в элементе управления "ползунок".

```
int GetPos() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущая позиция.

## <a name="csliderctrlgetrange"></a><a name="getrange"></a> CSliderCtrl:: Range

Извлекает максимальное и минимальное положение ползунка в элементе управления "ползунок".

```cpp
void GetRange(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Параметры

*Nмин.*<br/>
Ссылка на целое число, принимающее минимальную точку.

*Nмакс.*<br/>
Ссылка на целое число, которое получает максимальную точку.

### <a name="remarks"></a>Примечания

Эта функция копирует значения в целые числа, на которые ссылаются *nмин.* и *nмакс.*.

## <a name="csliderctrlgetrangemax"></a><a name="getrangemax"></a> CSliderCtrl:: Жетранжемакс

Получает максимальную положение ползунка в элементе управления "ползунок".

```
int GetRangeMax() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное расположение элемента управления.

## <a name="csliderctrlgetrangemin"></a><a name="getrangemin"></a> CSliderCtrl:: Жетранжемин

Возвращает минимальное положение ползунка в элементе управления "ползунок".

```
int GetRangeMin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Минимальная заданная позицией элемента управления.

## <a name="csliderctrlgetselection"></a><a name="getselection"></a> CSliderCtrl:: выделять

Получает начальные и конечные позиции текущего выделения в элементе управления "ползунок".

```cpp
void GetSelection(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>Параметры

*Nмин.*<br/>
Ссылка на целое число, получающее начальную точку текущего выделения.

*Nмакс.*<br/>
Ссылка на целое число, получающее конечное расположение текущего выделения.

## <a name="csliderctrlgetthumblength"></a><a name="getthumblength"></a> CSliderCtrl:: Жетсумбленгс

Получает длину ползунка в текущем элементе управления TrackBar.

```
int GetThumbLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина ползунка в пикселях.

### <a name="remarks"></a>Примечания

Этот метод отправляет [TBM_GETTHUMBLENGTH](/windows/win32/Controls/tbm-getthumblength) сообщение, описанное в Windows SDK.

## <a name="csliderctrlgetthumbrect"></a><a name="getthumbrect"></a> CSliderCtrl:: Жетсумбрект

Получает размер и положение ограничивающего прямоугольника для ползунка (бегунка) в элементе управления "ползунок".

```cpp
void GetThumbRect(LPRECT lprc) const;
```

### <a name="parameters"></a>Параметры

*лпрк*<br/>
Указатель на `CRect` объект, содержащий ограничивающий прямоугольник для ползунка при возврате функции.

## <a name="csliderctrlgettic"></a><a name="gettic"></a> CSliderCtrl:: Жеттик

Получает положение деления в элементе управления "ползунок".

```
int GetTic(int nTic) const;
```

### <a name="parameters"></a>Параметры

*нтик*<br/>
Отсчитываемый от нуля индекс, указывающий деление.

### <a name="return-value"></a>Возвращаемое значение

Позиция указанного деления или-1, если *НТИК* не указывает допустимый индекс.

## <a name="csliderctrlgetticarray"></a><a name="getticarray"></a> CSliderCtrl:: Жеттикаррай

Извлекает адрес массива, содержащего позиции делений для элемента управления "ползунок".

```
DWORD* GetTicArray() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес массива, содержащего позиции делений для элемента управления "ползунок".

## <a name="csliderctrlgetticpos"></a><a name="getticpos"></a> CSliderCtrl:: Жеттикпос

Извлекает текущее физическое положение деления в элементе управления "ползунок".

```
int GetTicPos(int nTic) const;
```

### <a name="parameters"></a>Параметры

*нтик*<br/>
Отсчитываемый от нуля индекс, указывающий деление.

### <a name="return-value"></a>Возвращаемое значение

Физическая позиция в клиентских координатах указанного деления или-1, если *НТИК* не указывает допустимый индекс.

## <a name="csliderctrlgettooltips"></a><a name="gettooltips"></a> CSliderCtrl:: подсказки

Получает маркер для элемента управления ToolTip, назначенного элементу управления Slider (при его наличии).

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) или значение null, если подсказки не используются. Если элемент управления "ползунок" не использует стиль TBS_TOOLTIPS, возвращается значение NULL.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TBM_GETTOOLTIPS](/windows/win32/Controls/tbm-gettooltips), как описано в Windows SDK. Обратите внимание, что эта функция-член возвращает `CToolTipCtrl` объект, а не обработчик элемента управления.

Описание стилей элемента управления "ползунок" см. в разделе [стили элементов управления TrackBar](/windows/win32/Controls/trackbar-control-styles) в Windows SDK.

## <a name="csliderctrlsetbuddy"></a><a name="setbuddy"></a> CSliderCtrl:: Сетбудди

Назначает окно в качестве окна собеседника для элемента управления "ползунок".

```
CWnd* SetBuddy(
    CWnd* pWndBuddy,
    BOOL fLocation = TRUE);
```

### <a name="parameters"></a>Параметры

*пвндбудди*<br/>
Указатель на `CWnd` объект, который будет установлен в качестве собеседника элемента управления Slider.

*fLocation*<br/>
Значение, указывающее расположение, в котором будет отображаться окно собеседника. Значение может быть одним из следующих.

- Значение TRUE, если элемент управления TrackBar использует стиль TBS_HORZ, в левой части ползунка будет отображаться друг. Если значение TrackBar использует стиль TBS_VERT, то он отображается над элементом управления TrackBar.

- Значение FALSE, если элемент управления TrackBar использует стиль TBS_HORZ, то справа от TrackBar появится значок. Если значение TrackBar использует стиль TBS_VERT, то он отображается под элементом управления TrackBar.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , который ранее был назначен элементу управления Slider в этом расположении.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TBM_SETBUDDY](/windows/win32/Controls/tbm-setbuddy), как описано в Windows SDK. Обратите внимание, что эта функция члена использует указатели на `CWnd` объекты, а не на дескрипторы окон как для возвращаемого значения, так и для параметра.

Описание стилей элемента управления "ползунок" см. в разделе [стили элементов управления TrackBar](/windows/win32/Controls/trackbar-control-styles) в Windows SDK.

## <a name="csliderctrlsetlinesize"></a><a name="setlinesize"></a> CSliderCtrl:: Сетлинесизе

Задает размер линии для элемента управления "ползунок".

```
int SetLineSize(int nSize);
```

### <a name="parameters"></a>Параметры

*нсизе*<br/>
Новый размер строки элемента управления "ползунок".

### <a name="return-value"></a>Возвращаемое значение

Размер предыдущей строки.

### <a name="remarks"></a>Примечания

Размер линии влияет на то, сколько ползунков перемещается для TB_LINEUP и TB_LINEDOWNных уведомлений.

## <a name="csliderctrlsetpagesize"></a><a name="setpagesize"></a> CSliderCtrl:: SetPageSize

Задает размер страницы для элемента управления "ползунок".

```
int SetPageSize(int nSize);
```

### <a name="parameters"></a>Параметры

*нсизе*<br/>
Новый размер страницы элемента управления "ползунок".

### <a name="return-value"></a>Возвращаемое значение

Предыдущий размер страницы.

### <a name="remarks"></a>Примечания

Размер страницы влияет на то, сколько ползунков перемещается для TB_PAGEUP и TB_PAGEDOWN уведомлений.

## <a name="csliderctrlsetpos"></a><a name="setpos"></a> CSliderCtrl:: Сетпос

Задает текущую положение ползунка в элементе управления "ползунок".

```cpp
void SetPos(int nPos);
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Указывает новую положение ползунка.

## <a name="csliderctrlsetrange"></a><a name="setrange"></a> CSliderCtrl:: SetRange

Задает диапазон (минимальное и максимальное позиции) для ползунка в элементе управления "ползунок".

```cpp
void SetRange(
    int nMin,
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*Nмин.*<br/>
Минимальная позиция ползунка.

*Nмакс.*<br/>
Максимальное положение ползунка.

*bRedraw*<br/>
Флаг перерисовки. Если этот параметр имеет значение TRUE, ползунок перерисовывается после установки диапазона. в противном случае ползунок не перерисовывается.

## <a name="csliderctrlsetrangemax"></a><a name="setrangemax"></a> CSliderCtrl:: Сетранжемакс

Задает максимальный диапазон для ползунка в элементе управления "ползунок".

```cpp
void SetRangeMax(
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*Nмакс.*<br/>
Максимальное положение ползунка.

*bRedraw*<br/>
Флаг перерисовки. Если этот параметр имеет значение TRUE, ползунок перерисовывается после установки диапазона. в противном случае ползунок не перерисовывается.

## <a name="csliderctrlsetrangemin"></a><a name="setrangemin"></a> CSliderCtrl:: Сетранжемин

Задает минимальный диапазон для ползунка в элементе управления "ползунок".

```cpp
void SetRangeMin(
    int nMin,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>Параметры

*Nмин.*<br/>
Минимальная позиция ползунка.

*bRedraw*<br/>
Флаг перерисовки. Если этот параметр имеет значение TRUE, ползунок перерисовывается после установки диапазона. в противном случае ползунок не перерисовывается.

## <a name="csliderctrlsetselection"></a><a name="setselection"></a> CSliderCtrl:: Сетселектион

Задает начальные и конечные позиции для текущего выделения в элементе управления "ползунок".

```cpp
void SetSelection(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Параметры

*Nмин.*<br/>
Начальная позиция ползунка.

*Nмакс.*<br/>
Конечное положение для ползунка.

## <a name="csliderctrlsetthumblength"></a><a name="setthumblength"></a> CSliderCtrl:: Сетсумбленгс

Задает длину ползунка в текущем элементе управления TrackBar.

```cpp
void SetThumbLength(int nLength);
```

### <a name="parameters"></a>Параметры

*нленгс*\
окне Длина ползунка в пикселях.

### <a name="remarks"></a>Примечания

Для этого метода необходимо, чтобы для элемента управления TrackBar было задано значение [TBS_FIXEDLENGTH](/windows/win32/Controls/trackbar-control-styles) Style.

Этот метод отправляет [TBM_SETTHUMBLENGTH](/windows/win32/Controls/tbm-setthumblength) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_sliderCtrl` которая используется для доступа к текущему элементу управления TrackBar. В примере также определяется переменная, `thumbLength` которая используется для хранения длины по умолчанию компонента Thumb элемента управления TrackBar. Эти переменные используются в следующем примере.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]

### <a name="example"></a>Пример

В следующем примере кода компоненту Thumb элемента управления TrackBar присваивается значение удвоенной длины по умолчанию.

[!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]

## <a name="csliderctrlsettic"></a><a name="settic"></a> CSliderCtrl:: Set

Задает положение деления в элементе управления "ползунок".

```
BOOL SetTic(int nTic);
```

### <a name="parameters"></a>Параметры

*нтик*<br/>
Расположение деления. Этот параметр должен задавать положительное значение.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если установлен флажок деления; в противном случае — 0.

## <a name="csliderctrlsetticfreq"></a><a name="setticfreq"></a> CSliderCtrl:: Сеттикфрек

Задает частоту, с которой деления отображаются на ползунке.

```cpp
void SetTicFreq(int nFreq);
```

### <a name="parameters"></a>Параметры

*нфрек*<br/>
Частота делений.

### <a name="remarks"></a>Примечания

Например, если для периодичности задано значение 2, то для каждого второго шага в диапазоне ползунка отображается деление. Значение по умолчанию для периодичности равно 1 (то есть каждый инкремент в диапазоне связан с делениями).

Для использования этой функции необходимо создать элемент управления с TBS_AUTOTICKS стилем. Дополнительные сведения см. в разделе [CSliderCtrl:: Create](#create).

## <a name="csliderctrlsettipside"></a><a name="settipside"></a> CSliderCtrl:: Сеттипсиде

Размещает элемент управления ToolTip, используемый элементом управления TrackBar.

```
int SetTipSide(int nLocation);
```

### <a name="parameters"></a>Параметры

*Nрасположение*<br/>
Значение, представляющее расположение, в котором отображается элемент управления ToolTip. Список возможных значений см. в [TBM_SETTIPSIDE](/windows/win32/Controls/tbm-settipside)сообщения Win32, как описано в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Значение, представляющее предыдущее расположение элемента управления ToolTip. Возвращаемое значение равно одному из возможных значений для *nрасположение*.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 TBM_SETTIPSIDE, как описано в Windows SDK. Элементы управления "ползунок", использующие отображение подсказок TBS_TOOLTIPS стиля. Описание стилей элемента управления "ползунок" см. в разделе [стили элементов управления TrackBar](/windows/win32/Controls/trackbar-control-styles) в Windows SDK.

## <a name="csliderctrlsettooltips"></a><a name="settooltips"></a> CSliderCtrl:: Сеттултипс

Назначает элемент управления ToolTip элементу управления "ползунок".

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>Параметры

*пвндтип*<br/>
Указатель на объект [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) , содержащий подсказки для использования с элементом управления "ползунок".

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [TBM_SETTOOLTIPS](/windows/win32/Controls/tbm-settooltips), как описано в Windows SDK. При создании элемента управления "ползунок" с TBS_TOOLTIPS стилем он создает элемент управления ToolTip по умолчанию, который отображается рядом с ползунком, отображая текущую положение ползунка. Описание стилей элемента управления "ползунок" см. в разделе [стили элементов управления TrackBar](/windows/win32/Controls/trackbar-control-styles) в Windows SDK.

## <a name="see-also"></a>См. также

[Пример CMNCTRL2 для MFC](../../overview/visual-cpp-samples.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CProgressCtrl](../../mfc/reference/cprogressctrl-class.md)
