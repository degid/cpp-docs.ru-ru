---
title: Класс CSpinButtonCtrl
ms.date: 11/04/2016
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
ms.openlocfilehash: cedfe16a6870bc779121e8e864866cfcb711b148
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753104"
---
# <a name="cspinbuttonctrl-class"></a>Класс CSpinButtonCtrl

Предоставляет функциональные возможности стандартного элемента управления "счетчик" Windows.

## <a name="syntax"></a>Синтаксис

```
class CSpinButtonCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Формирует объект `CSpinButtonCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSpinButtonCtrl::Создание](#create)|Создает управление кнопкой вращения и `CSpinButtonCtrl` прикрепляет его к объекту.|
|[CSpinButtonCtrl::CreateEx](#createex)|Создает управление кнопкой спина с указанными расширенными `CSpinButtonCtrl` стилями Windows и прикрепляет его к объекту.|
|[CSpinButtonCtrl::GetAccel](#getaccel)|Извлекает информацию об ускорении для управления кнопкой вращения.|
|[CSpinButtonCtrl::GetBase](#getbase)|Получает текущую базу для управления кнопкой спина.|
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Извлекает указатель на текущее окно приятеля.|
|[CSpinButtonCtrl::GetPos](#getpos)|Извлекает текущее положение управления кнопкой вращения.|
|[CSpinButtonCtrl::GetRange](#getrange)|Получает верхние и нижние пределы (диапазон) для управления кнопкой спина.|
|[CSpinButtonCtrl::SetAccel](#setaccel)|Устанавливает ускорение для управления кнопкой спина.|
|[CSpinButtonCtrl:SetBase](#setbase)|Устанавливает основу для управления кнопкой спина.|
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Устанавливает окно приятеля для управления кнопкой спина.|
|[CSpinButtonCtrl::SetPos](#setpos)|Устанавливает текущее положение для элемента управления.|
|[CSpinButtonCtrl::SetRange](#setrange)|Устанавливает верхние и нижние пределы (диапазон) для управления кнопкой спина.|

## <a name="remarks"></a>Примечания

"Управление кнопками спина" (также известный как вверх-вниз управления) представляет собой пару кнопок стрелки, что пользователь может нажать на приращение или decrement значение, например, положение прокрутки или номер отображается в компаньон управления. Значение, связанное с управлением кнопкой вращения, называется его текущее положение. Управление кнопкой вращения чаще всего используется с управлением компаньона, называемым «окном приятеля».

Этот элемент управления `CSpinButtonCtrl` (и, следовательно, класс) доступен только для программ, работающих под Windows 95/98 и Windows NT версии 3.51 и позже.

Для пользователя управление кнопкой вращения и его окно приятеля часто выглядят как один элемент управления. Можно указать, что управление кнопкой вращения автоматически позиционирует себя рядом с окном приятеля и автоматически устанавливает заголовок окна приятеля в его текущее положение. Вы можете использовать управление кнопкой спина с управлением правкой для отвода, чтобы подсказать пользователю для численного ввода.

Нажатие стрелки вверх перемещает текущее положение к максимуму, а нажатие вниз стрелка перемещает текущее положение к минимуму. По умолчанию минимум 100, а максимум 0. Каждый раз, когда минимальная настройка больше, чем максимальная настройка (например, при использовании параметров по умолчанию), нажатие на стрелку вверх уменьшает значение позиции и нажатие вниз стрелка увеличивает его.

Управление кнопкой спина без окна приятеля функционирует как своего рода упрощенный бар прокрутки. Например, управление вкладками иногда отображает управление кнопкой вращения, чтобы пользователь мог прокрутить дополнительные вкладки в поле зрения.

Для получения дополнительной `CSpinButtonCtrl`информации об использовании, см. [Управление](../../mfc/controls-mfc.md) и [использование CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** afxcmn.h

## <a name="cspinbuttonctrlcreate"></a><a name="create"></a>CSpinButtonCtrl::Создание

Создает управление кнопкой вращения и `CSpinButtonCtrl` прикрепляет его к объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwStyle*<br/>
Определяет стиль управления кнопкой вращения. Примените к управлению любую комбинацию стилей управления кнопками спина. Эти стили описаны в [стилях управления Up-Down](/windows/win32/Controls/up-down-control-styles) в Windows SDK.

*rect*<br/>
Определяет размер и положение управления кнопкой вращения. Это может быть либо объект [CRect,](../../atl-mfc-shared/reference/crect-class.md) либо структура [RECT](/windows/win32/api/windef/ns-windef-rect)

*pParentWnd*<br/>
Указатель на родительское окно управления кнопкой `CDialog`спина, как правило, . Она не должна быть NULL.

*nID*<br/>
Упоняет идентификатор управления кнопкой вращения.

### <a name="return-value"></a>Возвращаемое значение

Незерно, если инициализация была успешной; в противном случае 0.

### <a name="remarks"></a>Примечания

Сначала вы `CSpinButtonCtrl` строите объект в два этапа, вызываете конструктор, а затем вызываете, `Create` `CSpinButtonCtrl` что создает управление кнопкой вращения и прикрепляет его к объекту.

Чтобы создать управление кнопкой спина с расширенными стилями окон, позвоните [CSpinButtonCtrl::CreateEx](#createex) вместо `Create`.

## <a name="cspinbuttonctrlcreateex"></a><a name="createex"></a>CSpinButtonCtrl::CreateEx

Создает элемент управления (детское окно) и `CSpinButtonCtrl` связывает его с объектом.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*dwExStyle*<br/>
Определяет расширенный стиль создаваемого элемента управления. Список расширенных стилей окон можно узнать [в](/windows/win32/api/winuser/nf-winuser-createwindowexw) *SDK* Windows см.

*dwStyle*<br/>
Определяет стиль управления кнопкой вращения. Примените к управлению любую комбинацию стилей управления кнопками спина. Эти стили описаны в [стилях управления Up-Down](/windows/win32/Controls/up-down-control-styles) в Windows SDK.

*rect*<br/>
Ссылка на структуру [RECT,](/windows/win32/api/windef/ns-windef-rect) описывающую размер и положение создаваемого окна, в клиентских координатах *pParentWnd*.

*pParentWnd*<br/>
Указатель на окно, которое является родителем элемента управления.

*nID*<br/>
Идентификатор окна ребенка элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Используйте `CreateEx` вместо [Create](#create) для применения расширенных стилей Windows, указанных в предисловии расширенного стиля Windows WS_EX_.

## <a name="cspinbuttonctrlcspinbuttonctrl"></a><a name="cspinbuttonctrl"></a>CSpinButtonCtrl::CSpinButtonCtrl

Формирует объект `CSpinButtonCtrl`.

```
CSpinButtonCtrl();
```

## <a name="cspinbuttonctrlgetaccel"></a><a name="getaccel"></a>CSpinButtonCtrl::GetAccel

Извлекает информацию об ускорении для управления кнопкой вращения.

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>Параметры

*nAccel*<br/>
Количество элементов в массиве, указанном *pAccel.*

*pAccel*<br/>
Указатель на массив структур [UDACCEL,](/windows/win32/api/commctrl/ns-commctrl-udaccel) который получает информацию об ускорении.

### <a name="return-value"></a>Возвращаемое значение

Количество извлеченных конструкций ускорителя.

## <a name="cspinbuttonctrlgetbase"></a><a name="getbase"></a>CSpinButtonCtrl::GetBase

Получает текущую базу для управления кнопкой спина.

```
UINT GetBase() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее базовое значение.

## <a name="cspinbuttonctrlgetbuddy"></a><a name="getbuddy"></a>CSpinButtonCtrl::GetBuddy

Извлекает указатель на текущее окно приятеля.

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущее окно приятеля.

## <a name="cspinbuttonctrlgetpos"></a><a name="getpos"></a>CSpinButtonCtrl::GetPos

Извлекает текущее положение управления кнопкой вращения.

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>Параметры

*lpbОшибка*<br/>
Указатель на значение boolean, которое устанавливается до нуля, если значение успешно извлечено или не нулевое, если происходит ошибка. Если этот параметр установлен на NULL, ошибки не сообщаются.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает 16-битное текущее положение в слове с низким заказом. Слово высокого порядка является ненулевым, если произошла ошибка.

Вторая версия возвращает 32-битную позицию.

### <a name="remarks"></a>Примечания

Когда он обрабатывает возвращенное значение, элемент управления обновляет свое текущее положение на основе подписи окна приятель. Элемент управления возвращает ошибку, если нет окна приятеля или если заголовок указывает недействительное или вне диапазона значение.

## <a name="cspinbuttonctrlgetrange"></a><a name="getrange"></a>CSpinButtonCtrl::GetRange

Получает верхние и нижние пределы (диапазон) для управления кнопкой спина.

```
DWORD GetRange() const;

void GetRange(
    int& lower,
    int& upper) const;

void GetRange32(
    int& lower,
    int &upper) const;
```

### <a name="parameters"></a>Параметры

*Ниже*<br/>
Ссылка на несколько, которая получает нижний предел для управления.

*Верхней*<br/>
Ссылка на несколько, который получает верхний предел для управления.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает 32-битное значение, содержащее верхние и нижние пределы. Слово низкого порядка является верхним пределом для управления, а слово высокого порядка — нижним пределом.

### <a name="remarks"></a>Примечания

Функция `GetRange32` члена получает диапазон управления кнопкой спина в виде 32-битного целого.

## <a name="cspinbuttonctrlsetaccel"></a><a name="setaccel"></a>CSpinButtonCtrl::SetAccel

Устанавливает ускорение для управления кнопкой спина.

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>Параметры

*nAccel*<br/>
Количество структур [UDACCEL,](/windows/win32/api/commctrl/ns-commctrl-udaccel) указанных *pAccel*.

*pAccel*<br/>
Указатель на массив структур UDACCEL, которые содержат информацию об ускорении. Элементы должны быть отсортированы `nSec` в порядке возрастания на основе члена.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

## <a name="cspinbuttonctrlsetbase"></a><a name="setbase"></a>CSpinButtonCtrl:SetBase

Устанавливает основу для управления кнопкой спина.

```
int SetBase(int nBase);
```

### <a name="parameters"></a>Параметры

*nБаза*<br/>
Новое базовое значение для управления. Это может быть 10 для десятичной или 16 для гексадецимного.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее базовое значение в случае успеха или ноль, если предоставлена недействительная база.

### <a name="remarks"></a>Примечания

Базовое значение определяет, отображает ли окно приятель числа десятичных или гексадецичных цифр. Гексадецимальные числа всегда не подписаны; десятичные номера подписаны.

## <a name="cspinbuttonctrlsetbuddy"></a><a name="setbuddy"></a>CSpinButtonCtrl::SetBuddy

Устанавливает окно приятеля для управления кнопкой спина.

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>Параметры

*pWndBuddy*<br/>
Указатель на новое окно приятеля.

### <a name="return-value"></a>Возвращаемое значение

Указатель на предыдущее окно приятеля.

### <a name="remarks"></a>Примечания

Контроль спина почти всегда связан с другим окном, например элементом управления дейтом, которое отображает некоторое содержимое. Это другое окно называется "приятель" спин-контроля.

## <a name="cspinbuttonctrlsetpos"></a><a name="setpos"></a>CSpinButtonCtrl::SetPos

Устанавливает текущее положение для управления кнопкой вращения.

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>Параметры

*Npos*<br/>
Новая позиция для управления. Это значение должно находиться в диапазоне, указанном верхними и нижними границами для управления.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая позиция (16-битная точность для `SetPos`32-битной точности для). `SetPos32`

### <a name="remarks"></a>Примечания

`SetPos32`устанавливает 32-битную позицию.

## <a name="cspinbuttonctrlsetrange"></a><a name="setrange"></a>CSpinButtonCtrl::SetRange

Устанавливает верхние и нижние пределы (диапазон) для управления кнопкой спина.

```cpp
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Параметры

*nLower* и *nUpper*<br/>
Верхние и нижние пределы для управления. Для `SetRange`, ни один предел не может быть больше, чем UD_MAXVAL или менее UD_MINVAL; кроме того, разница между этими двумя лимитами не может превышать UD_MAXVAL. `SetRange32`не ограничивает лимиты; использовать любые несколько.

### <a name="remarks"></a>Примечания

Функция `SetRange32` члена устанавливает диапазон 32-битной для управления кнопкой спина.

> [!NOTE]
> Диапазон по умолчанию для кнопки спина имеет максимальный набор до нуля (0) и минимальный набор до 100. Поскольку максимальное значение меньше минимального значения, нажатие на стрелку вверх уменьшит положение и нажатие вниз стрелка увеличит его. Используйте `CSpinButtonCtrl::SetRange` для настройки этих значений.

## <a name="see-also"></a>См. также раздел

[MFC Образец CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CSliderCtrl](../../mfc/reference/csliderctrl-class.md)
