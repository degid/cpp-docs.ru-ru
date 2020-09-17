---
title: Класс CMonthCalCtrl
ms.date: 11/04/2016
f1_keywords:
- CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::CMonthCalCtrl
- AFXDTCTL/CMonthCalCtrl::Create
- AFXDTCTL/CMonthCalCtrl::GetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::GetCalendarCount
- AFXDTCTL/CMonthCalCtrl::GetCalendarGridInfo
- AFXDTCTL/CMonthCalCtrl::GetCalID
- AFXDTCTL/CMonthCalCtrl::GetColor
- AFXDTCTL/CMonthCalCtrl::GetCurrentView
- AFXDTCTL/CMonthCalCtrl::GetCurSel
- AFXDTCTL/CMonthCalCtrl::GetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::GetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::GetMaxTodayWidth
- AFXDTCTL/CMonthCalCtrl::GetMinReqRect
- AFXDTCTL/CMonthCalCtrl::GetMonthDelta
- AFXDTCTL/CMonthCalCtrl::GetMonthRange
- AFXDTCTL/CMonthCalCtrl::GetRange
- AFXDTCTL/CMonthCalCtrl::GetSelRange
- AFXDTCTL/CMonthCalCtrl::GetToday
- AFXDTCTL/CMonthCalCtrl::HitTest
- AFXDTCTL/CMonthCalCtrl::IsCenturyView
- AFXDTCTL/CMonthCalCtrl::IsDecadeView
- AFXDTCTL/CMonthCalCtrl::IsMonthView
- AFXDTCTL/CMonthCalCtrl::IsYearView
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorder
- AFXDTCTL/CMonthCalCtrl::SetCalendarBorderDefault
- AFXDTCTL/CMonthCalCtrl::SetCalID
- AFXDTCTL/CMonthCalCtrl::SetCenturyView
- AFXDTCTL/CMonthCalCtrl::SetColor
- AFXDTCTL/CMonthCalCtrl::SetCurrentView
- AFXDTCTL/CMonthCalCtrl::SetCurSel
- AFXDTCTL/CMonthCalCtrl::SetDayState
- AFXDTCTL/CMonthCalCtrl::SetDecadeView
- AFXDTCTL/CMonthCalCtrl::SetFirstDayOfWeek
- AFXDTCTL/CMonthCalCtrl::SetMaxSelCount
- AFXDTCTL/CMonthCalCtrl::SetMonthDelta
- AFXDTCTL/CMonthCalCtrl::SetMonthView
- AFXDTCTL/CMonthCalCtrl::SetRange
- AFXDTCTL/CMonthCalCtrl::SetSelRange
- AFXDTCTL/CMonthCalCtrl::SetToday
- AFXDTCTL/CMonthCalCtrl::SetYearView
- AFXDTCTL/CMonthCalCtrl::SizeMinReq
- AFXDTCTL/CMonthCalCtrl::SizeRectToMin
helpviewer_keywords:
- CMonthCalCtrl [MFC], CMonthCalCtrl
- CMonthCalCtrl [MFC], Create
- CMonthCalCtrl [MFC], GetCalendarBorder
- CMonthCalCtrl [MFC], GetCalendarCount
- CMonthCalCtrl [MFC], GetCalendarGridInfo
- CMonthCalCtrl [MFC], GetCalID
- CMonthCalCtrl [MFC], GetColor
- CMonthCalCtrl [MFC], GetCurrentView
- CMonthCalCtrl [MFC], GetCurSel
- CMonthCalCtrl [MFC], GetFirstDayOfWeek
- CMonthCalCtrl [MFC], GetMaxSelCount
- CMonthCalCtrl [MFC], GetMaxTodayWidth
- CMonthCalCtrl [MFC], GetMinReqRect
- CMonthCalCtrl [MFC], GetMonthDelta
- CMonthCalCtrl [MFC], GetMonthRange
- CMonthCalCtrl [MFC], GetRange
- CMonthCalCtrl [MFC], GetSelRange
- CMonthCalCtrl [MFC], GetToday
- CMonthCalCtrl [MFC], HitTest
- CMonthCalCtrl [MFC], IsCenturyView
- CMonthCalCtrl [MFC], IsDecadeView
- CMonthCalCtrl [MFC], IsMonthView
- CMonthCalCtrl [MFC], IsYearView
- CMonthCalCtrl [MFC], SetCalendarBorder
- CMonthCalCtrl [MFC], SetCalendarBorderDefault
- CMonthCalCtrl [MFC], SetCalID
- CMonthCalCtrl [MFC], SetCenturyView
- CMonthCalCtrl [MFC], SetColor
- CMonthCalCtrl [MFC], SetCurrentView
- CMonthCalCtrl [MFC], SetCurSel
- CMonthCalCtrl [MFC], SetDayState
- CMonthCalCtrl [MFC], SetDecadeView
- CMonthCalCtrl [MFC], SetFirstDayOfWeek
- CMonthCalCtrl [MFC], SetMaxSelCount
- CMonthCalCtrl [MFC], SetMonthDelta
- CMonthCalCtrl [MFC], SetMonthView
- CMonthCalCtrl [MFC], SetRange
- CMonthCalCtrl [MFC], SetSelRange
- CMonthCalCtrl [MFC], SetToday
- CMonthCalCtrl [MFC], SetYearView
- CMonthCalCtrl [MFC], SizeMinReq
- CMonthCalCtrl [MFC], SizeRectToMin
ms.assetid: a42f6bd6-ab5c-4335-82f8-839982fc64a2
ms.openlocfilehash: d986aa5f8e232f0ab94858dbdfae5754536ccdb9
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562146"
---
# <a name="cmonthcalctrl-class"></a>Класс CMonthCalCtrl

Инкапсулирует функциональность элемента управления "календарь месяца".

## <a name="syntax"></a>Синтаксис

```
class CMonthCalCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMonthCalCtrl:: CMonthCalCtrl](#cmonthcalctrl)|Формирует объект `CMonthCalCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMonthCalCtrl:: Create](#create)|Создает месячный элемент управления Calendar и прикрепляет его к `CMonthCalCtrl` объекту.|
|[CMonthCalCtrl:: Жеткалендарбордер](#getcalendarborder)|Получает ширину границы элемента управления Calendar в текущем месяце.|
|[CMonthCalCtrl:: Жеткалендаркаунт](#getcalendarcount)|Извлекает число календарей, отображаемых в элементе управления Calendar за текущий месяц.|
|[CMonthCalCtrl:: Жеткалендаргридинфо](#getcalendargridinfo)|Извлекает сведения об элементе управления Calendar в текущем месяце.|
|[CMonthCalCtrl:: Жеткалид](#getcalid)|Возвращает идентификатор календаря для элемента управления "Календарь текущего месяца".|
|[CMonthCalCtrl:: "Color"](#getcolor)|Возвращает цвет указанной области элемента управления календаря на месяц.|
|[CMonthCalCtrl:: Жеткуррентвиев](#getcurrentview)|Извлекает представление, отображаемое в данный момент элементом управления "Календарь текущего месяца".|
|[CMonthCalCtrl:: рекурсивно](#getcursel)|Возвращает системное время, указанное в выбранной дате.|
|[CMonthCalCtrl:: Жетфирстдайофвик](#getfirstdayofweek)|Возвращает первый день недели, отображаемый в крайнем левом столбце календаря.|
|[CMonthCalCtrl:: Жетмаксселкаунт](#getmaxselcount)|Возвращает текущее максимальное число дней, которое может быть выбрано в элементе управления ' календарь на месяц '.|
|[CMonthCalCtrl:: Жетмакстодайвидс](#getmaxtodaywidth)|Возвращает максимальную ширину строки "сегодня" для элемента управления "Календарь текущего месяца".|
|[CMonthCalCtrl:: Жетминрекрект](#getminreqrect)|Возвращает минимальный размер, необходимый для отображения полного месяца в элементе управления ' календарь на месяц '.|
|[CMonthCalCtrl:: Жетмонсделта](#getmonthdelta)|Возвращает скорость прокрутки для элемента управления "месячный календарь".|
|[CMonthCalCtrl:: Жетмонсранже](#getmonthrange)|Извлекает сведения о датах, представляющие верхний и нижний пределы отображаемого элемента управления календаря.|
|[CMonthCalCtrl:: Range](#getrange)|Извлекает текущие минимальные и максимальные даты, заданные в элементе управления ' календарь на месяц '.|
|[CMonthCalCtrl:: Жетселранже](#getselrange)|Извлекает сведения о дате, представляющие верхний и нижний пределы диапазона дат, выбранного пользователем в текущий момент.|
|[CMonthCalCtrl:: ontoday](#gettoday)|Извлекает сведения о дате для даты, указанной в поле "сегодня", для элемента управления "месячный календарь".|
|[CMonthCalCtrl:: HitTest](#hittest)|Определяет, какой раздел элемента управления "календарь месяца" находится в заданной точке экрана.|
|[CMonthCalCtrl:: Исцентуривиев](#iscenturyview)|Указывает, является ли текущее представление элемента управления Calendar текущего месяца представлением века.|
|[CMonthCalCtrl:: Исдекадевиев](#isdecadeview)|Указывает, является ли текущее представление элемента управления "Календарь текущего месяца" представлением десятилетия.|
|[CMonthCalCtrl:: Исмонсвиев](#ismonthview)|Указывает, является ли текущее представление элемента управления "Календарь текущего месяца" представлением "месяц".|
|[CMonthCalCtrl:: Исеарвиев](#isyearview)|Указывает, является ли текущее представление элемента управления "Календарь текущего месяца" представлением "год".|
|[CMonthCalCtrl:: Сеткалендарбордер](#setcalendarborder)|Задает ширину границы элемента управления "Календарь текущего месяца".|
|[CMonthCalCtrl:: Сеткалендарбордердефаулт](#setcalendarborderdefault)|Задает ширину по умолчанию для границы элемента управления "Календарь текущего месяца".|
|[CMonthCalCtrl:: Сеткалид](#setcalid)|Задает идентификатор календаря для элемента управления "Календарь текущего месяца".|
|[CMonthCalCtrl:: Сетцентуривиев](#setcenturyview)|Задает текущий элемент управления "календарь месяца" для отображения представления "век".|
|[CMonthCalCtrl:: Сетколор](#setcolor)|Задает цвет указанной области элемента управления календаря на месяц.|
|[CMonthCalCtrl:: Сеткуррентвиев](#setcurrentview)|Задает текущий элемент управления "календарь месяца" для отображения указанного представления.|
|[CMonthCalCtrl:: Сеткурсел](#setcursel)|Задает текущую выбранную дату для элемента управления "месячный календарь".|
|[CMonthCalCtrl:: Сетдайстате](#setdaystate)|Задает отображение для дней в элементе управления "месячный календарь".|
|[CMonthCalCtrl:: Сетдекадевиев](#setdecadeview)|Устанавливает элемент управления "Календарь на текущий месяц" в представление "десятилетие".|
|[CMonthCalCtrl:: Сетфирстдайофвик](#setfirstdayofweek)|Задает день недели, который будет отображаться в крайнем левом столбце календаря.|
|[CMonthCalCtrl:: Сетмаксселкаунт](#setmaxselcount)|Задает максимальное число дней, которое может быть выбрано в элементе управления ' календарь на месяц '.|
|[CMonthCalCtrl:: Сетмонсделта](#setmonthdelta)|Задает скорость прокрутки для элемента управления "месячный календарь".|
|[CMonthCalCtrl:: Сетмонсвиев](#setmonthview)|Задает текущий элемент управления "календарь месяца" для отображения представления "месяц".|
|[CMonthCalCtrl:: SetRange](#setrange)|Задает минимальную и максимальную допустимые даты для элемента управления "месячный календарь".|
|[CMonthCalCtrl:: Сетселранже](#setselrange)|Задает для элемента управления "месячный календарь" определенный диапазон дат.|
|[CMonthCalCtrl:: Сеттодай](#settoday)|Задает элемент управления Calendar за текущий день.|
|[CMonthCalCtrl:: Сетеарвиев](#setyearview)|Устанавливает для элемента управления "Календарь на текущий месяц" представление "год".|
|[CMonthCalCtrl:: Сиземинрек](#sizeminreq)|Перерисовывает элемент управления "календарь месяца" до минимального размера в один месяц.|
|[CMonthCalCtrl:: Сизеректтомин](#sizerecttomin)|Для элемента управления "Календарь текущего месяца" вычисляет наименьший прямоугольник, который может содержать все календари, попадающие в указанный прямоугольник.|

## <a name="remarks"></a>Примечания

Элемент управления "календарь месяца" предоставляет пользователю простой интерфейс календаря, с помощью которого пользователь может выбрать дату. Пользователь может изменить отображение следующим образом:

- Прокрутка назад и вперед, начиная с месяца и до месяца.

- Щелкните текст "сегодня", чтобы отобразить текущий день (если стиль MCS_NOTODAY не используется).

- Выбор месяца или года из всплывающего меню.

Вы можете настроить элемент управления "месячный календарь", применяя разнообразные стили к объекту при его создании. Эти стили описаны в [статье стили управления календарем](/windows/win32/Controls/month-calendar-control-styles) в Windows SDK.

Элемент управления "календарь месяца" может отображать более одного месяца и может указывать специальные дни (например, праздники), выделять дату.

Дополнительные сведения об использовании элемента управления "Календарь на месяц" см. в разделе [using CMonthCalCtrl](../../mfc/using-cmonthcalctrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CMonthCalCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** афксдтктл.h

## <a name="cmonthcalctrlcmonthcalctrl"></a><a name="cmonthcalctrl"></a> CMonthCalCtrl:: CMonthCalCtrl

Формирует объект `CMonthCalCtrl`.

```
CMonthCalCtrl();
```

### <a name="remarks"></a>Примечания

`Create`После создания объекта необходимо вызвать метод.

## <a name="cmonthcalctrlcreate"></a><a name="create"></a> CMonthCalCtrl:: Create

Создает месячный элемент управления Calendar и прикрепляет его к `CMonthCalCtrl` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(
    DWORD dwStyle,
    const POINT& pt,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает сочетание стилей Windows, применяемых к элементу управления "месячный календарь". Дополнительные сведения о стилях см. в разделе [месячные стили элемента управления Calendar](/windows/win32/Controls/month-calendar-control-styles) в Windows SDK.

*rect*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) . Содержит расположение и размер элемента управления "Календарь на месяц".

*пт*<br/>
Ссылка на структуру [Point](/windows/win32/api/windef/ns-windef-point) , определяющую расположение элемента управления "месячный календарь".

*ппарентвнд*<br/>
Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является родительским окном элемента управления "календарь месяца". Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления "месячный календарь".

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если инициализация прошла успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Создание элемента управления "месячный календарь" в два этапа:

1. Вызовите [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) для создания `CMonthCalCtrl` объекта.

1. Вызовите эту функцию-член, которая создает месячный элемент управления Calendar и прикрепляет его к `CMonthCalCtrl` объекту.

При вызове метода `Create` инициализируются стандартные элементы управления. `Create`Вызываемая версия определяет его размер:

- Чтобы обеспечить автоматическое изменение размера элемента управления MFC на один месяц, вызовите переопределение, которое использует параметр *PT* .

- Чтобы задать размер элемента управления самостоятельно, вызовите переопределение этой функции, которая использует параметр *Rect* .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_1.cpp)]

## <a name="cmonthcalctrlgetcalendarborder"></a><a name="getcalendarborder"></a> CMonthCalCtrl:: Жеткалендарбордер

Получает ширину границы элемента управления Calendar в текущем месяце.

```
int GetCalendarBorder() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина границы элемента управления в пикселях.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCALENDARBORDER](/windows/win32/Controls/mcm-getcalendarborder) сообщение, описанное в Windows SDK.

## <a name="cmonthcalctrlgetcalendarcount"></a><a name="getcalendarcount"></a> CMonthCalCtrl:: Жеткалендаркаунт

Извлекает число календарей, отображаемых в элементе управления Calendar за текущий месяц.

```
int GetCalendarCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число календарей, отображаемых в данный момент в элементе управления "месячный календарь". Максимально допустимое число календарей — 12.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCALENDARCOUNT](/windows/win32/Controls/mcm-getcalendarcount) сообщение, описанное в Windows SDK.

## <a name="cmonthcalctrlgetcalendargridinfo"></a><a name="getcalendargridinfo"></a> CMonthCalCtrl:: Жеткалендаргридинфо

Извлекает сведения об элементе управления Calendar в текущем месяце.

```
BOOL GetCalendarGridInfo(PMCGRIDINFO pmcGridInfo) const;
```

### <a name="parameters"></a>Параметры

*пмкгридинфо*\
заполняет Указатель на структуру [мкгридинфо](/windows/win32/api/commctrl/ns-commctrl-mcgridinfo) , которая получает сведения об элементе управления "Календарь текущего месяца". Вызывающий объект отвечает за выделение и инициализацию этой структуры.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCALENDARGRIDINFO](/windows/win32/Controls/mcm-getcalendargridinfo) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_monthCalCtrl` , которая используется для программного доступа к элементу управления "месячный календарь". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода метод используется `GetCalendarGridInfo` для получения календарной даты, которую отображает элемент управления Calendar в текущем месяце.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_3.cpp)]

## <a name="cmonthcalctrlgetcalid"></a><a name="getcalid"></a> CMonthCalCtrl:: Жеткалид

Возвращает идентификатор календаря для элемента управления "Календарь текущего месяца".

```
CALID GetCalID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Одна из констант [идентификатора календаря](/windows/win32/Intl/calendar-identifiers) .

### <a name="remarks"></a>Примечания

Идентификатор календаря обозначает календарь определенного региона, например григорианский (локализованный), японский или летоисчисление по хиджре календари. Приложение может использовать идентификатор календаря с различными функциями языковой поддержки.

Этот метод отправляет [MCM_GETCALID](/windows/win32/Controls/mcm-getcalid) сообщение, описанное в Windows SDK.

## <a name="cmonthcalctrlgetcolor"></a><a name="getcolor"></a> CMonthCalCtrl:: "Color"

Извлекает цвет области элемента управления календаря месяца, заданного параметром *нрегион*.

```
COLORREF GetColor(int nRegion) const;
```

### <a name="parameters"></a>Параметры

*нрегион*<br/>
Регион элемента управления "календарь месяца", из которого извлекается цвет. Список значений см. в описании параметра *нрегион* объекта [сетколор](#setcolor).

### <a name="return-value"></a>Возвращаемое значение

Значение [COLORREF](/windows/win32/gdi/colorref) , указывающее цвет, связанный с частью элемента управления "календарь месяца", в случае успеха. В противном случае эта функция-член возвращает значение – 1.

## <a name="cmonthcalctrlgetcurrentview"></a><a name="getcurrentview"></a> CMonthCalCtrl:: Жеткуррентвиев

Извлекает представление, отображаемое в данный момент элементом управления "Календарь текущего месяца".

```
DWORD GetCurrentView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее представление, на которое указывает одно из следующих значений:

|Значение|Значение|
|-----------|-------------|
|MCMV_MONTH|Представление за месяц|
|MCMV_YEAR|Ежегодное представление|
|MCMV_DECADE|Представление десятилетия|
|MCMV_CENTURY|Представление "век"|

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_monthCalCtrl` , которая используется для программного доступа к элементу управления "месячный календарь". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода указывается, какие представления отображаются в элементе управления "месячный календарь".

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_4.cpp)]

## <a name="cmonthcalctrlgetcursel"></a><a name="getcursel"></a> CMonthCalCtrl:: рекурсивно

Возвращает системное время, указанное в выбранной дате.

```
BOOL GetCurSel(COleDateTime& refDateTime) const;  BOOL GetCurSel(CTime& refDateTime) const;

BOOL GetCurSel(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Параметры

*рефдатетиме*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) . Получает текущее время.

*пдатетиме*<br/>
Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , которая будет принимать текущие выбранные сведения о дате. Этот параметр должен быть допустимым адресом и не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение в случае успешного выполнения; осервизе 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_GETCURSEL](/windows/win32/Controls/mcm-getcursel), как описано в Windows SDK.

> [!NOTE]
> Эта функция-член завершается ошибкой, если задан стиль MCS_MULTISELECT.

В реализации MFC `GetCurSel` можно указать использование `COleDateTime` , `CTime` использование или `SYSTEMTIME` использование структуры.

## <a name="cmonthcalctrlgetfirstdayofweek"></a><a name="getfirstdayofweek"></a> CMonthCalCtrl:: Жетфирстдайофвик

Возвращает первый день недели, отображаемый в крайнем левом столбце календаря.

```
int GetFirstDayOfWeek(BOOL* pbLocal = NULL) const;
```

### <a name="parameters"></a>Параметры

*пблокал*<br/>
Указатель на логическое значение. Если значение не равно нулю, то параметр элемента управления не соответствует параметру на панели управления.

### <a name="return-value"></a>Возвращаемое значение

Целочисленное значение, представляющее первый день недели. Дополнительные сведения о том, что представляют эти целые числа, см. в разделе **Примечания** .

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_GETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-getfirstdayofweek), как описано в Windows SDK. Дни недели представлены в виде целых чисел, как показано ниже.

|Значение|День недели.|
|-----------|---------------------|
|0|Понедельник|
|1|Вторник|
|2|Среда|
|3|Четверг|
|4|Пятница|
|5|Суббота|
|6|Воскресенье|

### <a name="example"></a>Пример

  См. пример для [CMonthCalCtrl:: сетфирстдайофвик](#setfirstdayofweek).

## <a name="cmonthcalctrlgetmaxselcount"></a><a name="getmaxselcount"></a> CMonthCalCtrl:: Жетмаксселкаунт

Возвращает текущее максимальное число дней, которое может быть выбрано в элементе управления ' календарь на месяц '.

```
int GetMaxSelCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Целочисленное значение, представляющее общее число дней, которое может быть выбрано для элемента управления.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_GETMAXSELCOUNT](/windows/win32/Controls/mcm-getmaxselcount), как описано в Windows SDK. Используйте эту функцию элемента для элементов управления с набором стилей MCS_MULTISELECT.

### <a name="example"></a>Пример

  См. пример для [CMonthCalCtrl:: сетмаксселкаунт](#setmaxselcount).

## <a name="cmonthcalctrlgetmaxtodaywidth"></a><a name="getmaxtodaywidth"></a> CMonthCalCtrl:: Жетмакстодайвидс

Возвращает максимальную ширину строки "сегодня" для элемента управления "Календарь текущего месяца".

```
DWORD GetMaxTodayWidth() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ширина строки "сегодня" в пикселях.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_monthCalCtrl` , которая используется для программного доступа к элементу управления "месячный календарь". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода демонстрируется `GetMaxTodayWidth` метод.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_5.cpp)]

### <a name="remarks"></a>Примечания

Пользователь может вернуться к текущей дате, щелкнув строку "Today", которая отображается в нижней части элемента управления "Календарь на месяц". Строка "Today" включает текст метки и текст даты.

Этот метод отправляет [MCM_GETMAXTODAYWIDTH](/windows/win32/Controls/mcm-getmaxtodaywidth) сообщение, описанное в Windows SDK.

## <a name="cmonthcalctrlgetminreqrect"></a><a name="getminreqrect"></a> CMonthCalCtrl:: Жетминрекрект

Возвращает минимальный размер, необходимый для отображения полного месяца в элементе управления ' календарь на месяц '.

```
BOOL GetMinReqRect(RECT* pRect) const;
```

### <a name="parameters"></a>Параметры

*прект*<br/>
Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , которая будет принимать сведения об ограничивающем прямоугольнике. Этот параметр должен быть допустимым адресом и не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

В случае успеха эта функция члена возвращает ненулевое значение и `lpRect` получает применимые сведения о границах. В случае неудачи функция члена возвращает значение 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_GETMINREQRECT](/windows/win32/Controls/mcm-getminreqrect), как описано в Windows SDK.

## <a name="cmonthcalctrlgetmonthdelta"></a><a name="getmonthdelta"></a> CMonthCalCtrl:: Жетмонсделта

Возвращает скорость прокрутки для элемента управления "месячный календарь".

```
int GetMonthDelta() const;
```

### <a name="return-value"></a>Возвращаемое значение

Скорость прокрутки для элемента управления "месячный календарь". Скорость прокрутки — это число месяцев, в течение которых элемент управления перемещает свое отображение, когда пользователь нажимает кнопку прокрутки один раз.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_GETMONTHDELTA](/windows/win32/Controls/mcm-getmonthdelta), как описано в Windows SDK.

## <a name="cmonthcalctrlgetmonthrange"></a><a name="getmonthrange"></a> CMonthCalCtrl:: Жетмонсранже

Извлекает сведения о датах, представляющие верхний и нижний пределы отображаемого элемента управления календаря.

```
int GetMonthRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    CTime& refMinRange,
    CTime& refMaxRange,
    DWORD dwFlags) const;

int GetMonthRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange,
    DWORD dwFlags) const;
```

### <a name="parameters"></a>Параметры

*рефминранже*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , который содержит минимально допустимую дату.

*рефмаксранже*<br/>
Ссылка на `COleDateTime` объект или, `CTime` содержащий максимально допустимую дату.

*пминранже*<br/>
Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , содержащую дату в наименьшем конце диапазона.

*пмаксранже*<br/>
Указатель на структуру, `SYSTEMTIME` содержащую дату в самом верхнем конце диапазона.

*dwFlags*<br/>
Значение, указывающее область возвращаемых пределов диапазона. Это значение должно быть одним из следующих.

|Значение|Значение|
|-----------|-------------|
|GMR_DAYSTATE|Включить предыдущие и конечные месяцы видимого диапазона, которые отображаются только частично.|
|GMR_VISIBLE|Включить только те месяцы, которые отображаются полностью.|

### <a name="return-value"></a>Возвращаемое значение

Целое число, представляющее диапазон в месяцах, охватываемый двумя ограничениями, указанными в *рефминранже* и *рефмаксранже* в первой и второй версиях, а также *пминранже* и *пмаксранже* в третьей версии.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_GETMONTHRANGE](/windows/win32/Controls/mcm-getmonthrange), как описано в Windows SDK. В реализации MFC `GetMonthRange` можно указать использование `COleDateTime` , `CTime` использование или `SYSTEMTIME` использование структуры.

### <a name="example"></a>Пример

  См. пример для [CMonthCalCtrl:: сетдайстате](#setdaystate).

## <a name="cmonthcalctrlgetrange"></a><a name="getrange"></a> CMonthCalCtrl:: Range

Извлекает текущие минимальные и максимальные даты, заданные в элементе управления ' календарь на месяц '.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;

DWORD GetRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Параметры

*пминранже*<br/>
Указатель на `COleDateTime` объект, `CTime` объект или структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , содержащую дату в наименьшем конце диапазона.

*пмаксранже*<br/>
Указатель на `COleDateTime` объект, `CTime` объект или структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , содержащую дату в самом верхнем конце диапазона.

### <a name="return-value"></a>Возвращаемое значение

Значение типа DWORD, которое может равняться нулю (никакие ограничения не заданы), или сочетание следующих значений, задающих сведения об ограничении.

|Значение|Значение|
|-----------|-------------|
|GDTR_MAX|Для элемента управления задано ограничение максимального значения; *пмаксранже* является допустимым и содержит применимые сведения о датах.|
|GDTR_MIN|Для элемента управления задано минимальное ограничение; *пминранже* является допустимым и содержит применимые сведения о датах.|

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_GETRANGE](/windows/win32/Controls/mcm-getrange), как описано в Windows SDK. В реализации MFC `GetRange` можно указать использование `COleDateTime` , `CTime` использование или `SYSTEMTIME` использование структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_6.cpp)]

## <a name="cmonthcalctrlgetselrange"></a><a name="getselrange"></a> CMonthCalCtrl:: Жетселранже

Извлекает сведения о дате, представляющие верхний и нижний пределы диапазона дат, выбранного пользователем в текущий момент.

```
BOOL GetSelRange(
    COleDateTime& refMinRange,
    COleDateTime& refMaxRange) const;

BOOL GetSelRange(
    CTime& refMinRange,
    CTime& refMaxRange) const;

BOOL GetSelRange(
    LPSYSTEMTIME pMinRange,
    LPSYSTEMTIME pMaxRange) const;
```

### <a name="parameters"></a>Параметры

*рефминранже*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , который содержит минимально допустимую дату.

*рефмаксранже*<br/>
Ссылка на `COleDateTime` объект или, `CTime` содержащий максимально допустимую дату.

*пминранже*<br/>
Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , содержащую дату в наименьшем конце диапазона.

*пмаксранже*<br/>
Указатель на структуру, `SYSTEMTIME` содержащую дату в самом верхнем конце диапазона.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_GETSELRANGE](/windows/win32/Controls/mcm-getselrange), как описано в Windows SDK. `GetSelRange` завершится ошибкой, если применяется к элементу управления "месячный календарь", который не использует стиль MCS_MULTISELECT.

В реализации MFC `GetSelRange` можно указать использование `COleDateTime` , `CTime` использование или `SYSTEMTIME` использование структуры.

## <a name="cmonthcalctrlgettoday"></a><a name="gettoday"></a> CMonthCalCtrl:: ontoday

Извлекает сведения о дате для даты, указанной в поле "сегодня", для элемента управления "месячный календарь".

```
BOOL GetToday(COleDateTime& refDateTime) const;  BOOL GetToday(COleDateTime& refDateTime) const;

BOOL GetToday(LPSYSTEMTIME pDateTime) const;
```

### <a name="parameters"></a>Параметры

*рефдатетиме*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , указывающий текущий день.

*пдатетиме*<br/>
Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , которая получит сведения о дате. Этот параметр должен быть допустимым адресом и не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_GETTODAY](/windows/win32/Controls/mcm-gettoday), как описано в Windows SDK. В реализации MFC `GetToday` можно указать использование `COleDateTime` , `CTime` использование или `SYSTEMTIME` использование структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#3](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_7.cpp)]

## <a name="cmonthcalctrlhittest"></a><a name="hittest"></a> CMonthCalCtrl:: HitTest

Определяет, какой элемент управления календаря месяца, если он имеется, находится в указанной позиции.

```
DWORD HitTest(PMCHITTESTINFO pMCHitTest);
```

### <a name="parameters"></a>Параметры

*пмчиттест*<br/>
Указатель на структуру [мчиттестинфо](/windows/win32/api/commctrl/ns-commctrl-mchittestinfo) , содержащую точки проверки попадания для элемента управления "месячный календарь".

### <a name="return-value"></a>Возвращаемое значение

Значение типа DWORD. Значение, равное **ухит** элементу `MCHITTESTINFO` структуры.

### <a name="remarks"></a>Примечания

`HitTest` использует `MCHITTESTINFO` структуру, которая содержит сведения о проверке попадания.

## <a name="cmonthcalctrliscenturyview"></a><a name="iscenturyview"></a> CMonthCalCtrl:: Исцентуривиев

Указывает, является ли текущее представление элемента управления Calendar текущего месяца представлением века.

```
BOOL IsCenturyView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущее представление является представлением века; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, описанное в Windows SDK. Если это сообщение возвращает MCMV_CENTURY, этот метод возвращает значение TRUE.

## <a name="cmonthcalctrlisdecadeview"></a><a name="isdecadeview"></a> CMonthCalCtrl:: Исдекадевиев

Указывает, является ли текущее представление элемента управления "Календарь текущего месяца" представлением десятилетия.

```
BOOL IsDecadeView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущее представление является представлением десятилетия; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, описанное в Windows SDK. Если это сообщение возвращает MCMV_DECADE, этот метод возвращает значение TRUE.

## <a name="cmonthcalctrlismonthview"></a><a name="ismonthview"></a> CMonthCalCtrl:: Исмонсвиев

Указывает, является ли текущее представление элемента управления "Календарь текущего месяца" представлением "месяц".

```
BOOL IsMonthView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущее представление является представлением месяца; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, описанное в Windows SDK. Если это сообщение возвращает MCMV_MONTH, этот метод возвращает значение TRUE.

## <a name="cmonthcalctrlisyearview"></a><a name="isyearview"></a> CMonthCalCtrl:: Исеарвиев

Указывает, является ли текущее представление элемента управления "Календарь текущего месяца" представлением "год".

```
BOOL IsYearView() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если текущее представление является представлением года; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_GETCURRENTVIEW](/windows/win32/Controls/mcm-getcurrentview) сообщение, описанное в Windows SDK. Если это сообщение возвращает MCMV_YEAR, этот метод возвращает значение TRUE.

## <a name="cmonthcalctrlsetcalendarborder"></a><a name="setcalendarborder"></a> CMonthCalCtrl:: Сеткалендарбордер

Задает ширину границы элемента управления "Календарь текущего месяца".

```cpp
void SetCalendarBorder(int cxyBorder);
```

### <a name="parameters"></a>Параметры

*кксибордер*\
окне Ширина границы в пикселях.

### <a name="remarks"></a>Примечания

Если этот метод завершился с ошибкой, то ширина границы устанавливается в параметр *кксибордер* . В противном случае ширина границы сбрасывается до значения по умолчанию, заданного текущей [темой](/windows/win32/Controls/visual-styles-overview), или нуль, если темы не используются.

Этот метод отправляет [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_monthCalCtrl` , которая используется для программного доступа к элементу управления "месячный календарь". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода ширина границы элемента управления "календарь месяца" устанавливается равна 8 пикселям. Для определения успешности этого метода используйте метод [CMonthCalCtrl:: жеткалендарбордер](#getcalendarborder) .

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_8.cpp)]

## <a name="cmonthcalctrlsetcalendarborderdefault"></a><a name="setcalendarborderdefault"></a> CMonthCalCtrl:: Сеткалендарбордердефаулт

Задает ширину по умолчанию для границы элемента управления "Календарь текущего месяца".

```cpp
void SetCalendarBorderDefault();
```

### <a name="remarks"></a>Примечания

Ширина границы устанавливается равным значению по умолчанию, заданному текущей [темой](/windows/win32/Controls/visual-styles-overview), или нуль, если темы не используются.

Этот метод отправляет [MCM_SETCALENDARBORDER](/windows/win32/Controls/mcm-setcalendarborder) сообщение, описанное в Windows SDK.

## <a name="cmonthcalctrlsetcalid"></a><a name="setcalid"></a> CMonthCalCtrl:: Сеткалид

Задает идентификатор календаря для элемента управления "Календарь текущего месяца".

```
BOOL SetCalID(CALID calid);
```

### <a name="parameters"></a>Параметры

*калид*\
окне Одна из констант [идентификатора календаря](/windows/win32/Intl/calendar-identifiers) .

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Идентификатор календаря указывает календарь определенного региона, например григорианский (локализованный), японский или летоисчисление по хиджре календари. Используйте `SetCalID` метод для вывода календаря, указанного параметром *Калид* , если на компьютере установлен языковой стандарт, содержащий календарь.

Этот метод отправляет [MCM_SETCALID](/windows/win32/Controls/mcm-setcalid) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_monthCalCtrl` , которая используется для программного доступа к элементу управления "месячный календарь". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода элемент управления "календарь месяца" задается для показа японского календаря императора эры. `SetCalID`Метод будет выполнен, только если этот календарь установлен на компьютере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_9.cpp)]

## <a name="cmonthcalctrlsetcenturyview"></a><a name="setcenturyview"></a> CMonthCalCtrl:: Сетцентуривиев

Задает текущий элемент управления "календарь месяца" для отображения представления "век".

```
BOOL SetCenturyView();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует метод [CMonthCalCtrl:: сеткуррентвиев](#setcurrentview) , чтобы задать представление `MCMV_CENTURY` , которое представляет представление века.

## <a name="cmonthcalctrlsetcolor"></a><a name="setcolor"></a> CMonthCalCtrl:: Сетколор

Задает цвет указанной области элемента управления календаря на месяц.

```
COLORREF SetColor(
    int nRegion,
    COLORREF ref);
```

### <a name="parameters"></a>Параметры

*нрегион*<br/>
Целочисленное значение, указывающее, какой цвет календаря месяца нужно задать. Это значение может быть одним из следующих.

|Значение|Значение|
|-----------|-------------|
|MCSC_BACKGROUND|Цвет фона, отображаемый в интервале между месяцами.|
|MCSC_MONTHBK|Цвет фона, отображаемый в течение месяца.|
|MCSC_TEXT|Цвет, используемый для показа текста в пределах месяца.|
|MCSC_TITLEBK|Цвет фона, отображаемый в заголовке календаря.|
|MCSC_TITLETEXT|Цвет, используемый для показа текста в заголовке календаря.|
|MCSC_TRAILINGTEXT|Цвет, используемый для вывода текста верхнего и конечного дней. Дни заголовков и конечных дней — это дни предыдущего и следующего месяцев, которые отображаются в текущем календаре.|

*ref*<br/>
Значение COLORREF для нового параметра цвета для указанной части элемента управления "месячный календарь".

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее предыдущий цвет для указанного фрагмента элемента управления "месячный календарь" в случае успеха. В противном случае это сообщение возвращает значение-1.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_SETCOLOR](/windows/win32/Controls/mcm-setcolor), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#4](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_10.cpp)]

## <a name="cmonthcalctrlsetcurrentview"></a><a name="setcurrentview"></a> CMonthCalCtrl:: Сеткуррентвиев

Задает текущий элемент управления "календарь месяца" для отображения указанного представления.

```
BOOL SetCurrentView(DWORD dwNewView);
```

### <a name="parameters"></a>Параметры

*двневвиев*\
окне Одно из следующих значений, которое указывает представление месяца, ежегодного, десятилетия или века.

- `MCMV_MONTH`: Представление за месяц
- `MCMV_YEAR`: Ежегодное представление
- `MCMV_DECADE`: Представление десятилетия
- `MCMV_CENTURY`: Век, представление

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [MCM_SETCURRENTVIEW](/windows/win32/Controls/mcm-setcurrentview) сообщение, описанное в Windows SDK.

## <a name="cmonthcalctrlsetcursel"></a><a name="setcursel"></a> CMonthCalCtrl:: Сеткурсел

Задает текущую выбранную дату для элемента управления "месячный календарь".

```
BOOL SetCurSel(const COleDateTime& refDateTime);
BOOL SetCurSel(const CTime& refDateTime);
BOOL SetCurSel(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Параметры

*рефдатетиме*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или [CTime](../../atl-mfc-shared/reference/ctime-class.md) , указывающий на текущий выбранный элемент управления календаря в месяц.

*пдатетиме*<br/>
Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , содержащую дату, которая должна быть выбрана в качестве текущего выделения.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_SETCURSEL](/windows/win32/Controls/mcm-setcursel), как описано в Windows SDK. В реализации MFC `SetCurSel` можно указать использование `COleDateTime` , `CTime` использование или `SYSTEMTIME` использование структуры.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#5](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_11.cpp)]

## <a name="cmonthcalctrlsetdaystate"></a><a name="setdaystate"></a> CMonthCalCtrl:: Сетдайстате

Задает отображение для дней в элементе управления "месячный календарь".

```
BOOL SetDayState(
    int nMonths,
    LPMONTHDAYSTATE pStates);
```

### <a name="parameters"></a>Параметры

*нмонсс*<br/>
Значение, указывающее, сколько элементов находится в массиве, на который *пстатес* указывает.

*пстатес*<br/>
Указатель на массив значений [монсдайстате](/windows/win32/Controls/monthdaystate) , определяющий, как календарь месяца будет рисовать каждый день в его дисплее. Тип данных МОНСДАЙСТАТЕ является битовым полем, где каждый бит (от 1 до 31) представляет состояние дня в месяце. Если бит включен, соответствующий день будет отображаться полужирным шрифтом; в противном случае он будет отображаться без каких бы то ни было внимания.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_SETDAYSTATE](/windows/win32/Controls/mcm-setdaystate), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#6](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_12.cpp)]

## <a name="cmonthcalctrlsetdecadeview"></a><a name="setdecadeview"></a> CMonthCalCtrl:: Сетдекадевиев

Устанавливает элемент управления "Календарь на текущий месяц" в представление "десятилетие".

```
BOOL SetDecadeView();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует метод [CMonthCalCtrl:: сеткуррентвиев](#setcurrentview) , чтобы задать для представления значение `MCMV_DECADE` , представляющее представление десятилетия.

## <a name="cmonthcalctrlsetfirstdayofweek"></a><a name="setfirstdayofweek"></a> CMonthCalCtrl:: Сетфирстдайофвик

Задает день недели, который будет отображаться в крайнем левом столбце календаря.

```
BOOL SetFirstDayOfWeek(
    int iDay,
    int* lpnOld = NULL);
```

### <a name="parameters"></a>Параметры

*идай*<br/>
Целочисленное значение, представляющее день, который должен быть установлен в качестве первого дня недели. Это значение должно быть одним из номеров дней. Описание номеров дней см. в разделе [жетфирстдайофвик](#getfirstdayofweek) .

*лпнолд*<br/>
Указатель на целое число, обозначающее первый день ранее заданной недели.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если предыдущим первым днем недели присвоено отличное от LOCALE_IFIRSTDAYOFWEEK, то есть день, указанный в параметре панели управления. В противном случае эта функция возвращает 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_SETFIRSTDAYOFWEEK](/windows/win32/Controls/mcm-setfirstdayofweek), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#7](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_13.cpp)]

## <a name="cmonthcalctrlsetmaxselcount"></a><a name="setmaxselcount"></a> CMonthCalCtrl:: Сетмаксселкаунт

Задает максимальное число дней, которое может быть выбрано в элементе управления ' календарь на месяц '.

```
BOOL SetMaxSelCount(int nMax);
```

### <a name="parameters"></a>Параметры

*Nмакс.*<br/>
Значение, которое будет задаваться для представления максимального числа выбираемых дней.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_SETMAXSELCOUNT](/windows/win32/Controls/mcm-setmaxselcount), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CMonthCalCtrl#8](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_14.cpp)]

## <a name="cmonthcalctrlsetmonthdelta"></a><a name="setmonthdelta"></a> CMonthCalCtrl:: Сетмонсделта

Задает скорость прокрутки для элемента управления "месячный календарь".

```
int SetMonthDelta(int iDelta);
```

### <a name="parameters"></a>Параметры

*Класса idelta*<br/>
Число месяцев, которое должно быть задано в качестве скорости прокрутки элемента управления. Если это значение равно нулю, то дельта по месяцам сбрасывается до значения по умолчанию, которое равно количеству месяцев, отображаемых в элементе управления.

### <a name="return-value"></a>Возвращаемое значение

Предыдущая скорость прокрутки. Если скорость прокрутки не была задана ранее, возвращаемое значение равно 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_SETMONTHDELTA](/windows/win32/Controls/mcm-setmonthdelta), как описано в Windows SDK.

## <a name="cmonthcalctrlsetmonthview"></a><a name="setmonthview"></a> CMonthCalCtrl:: Сетмонсвиев

Задает текущий элемент управления "календарь месяца" для отображения представления "месяц".

```
BOOL SetMonthView();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует метод [CMonthCalCtrl:: сеткуррентвиев](#setcurrentview) , чтобы установить представление в MCMV_MONTH, представляющее представление месяца.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, `m_monthCalCtrl` , которая используется для программного доступа к элементу управления "месячный календарь". Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_2.h)]

### <a name="example"></a>Пример

В следующем примере кода элемент управления "Календарь на месяц" задает отображение представлений "месяц", "год", "десятилетие" и "столетие".

[!code-cpp[NVC_MFC_CMonthCalCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cmonthcalctrl-class_15.cpp)]

## <a name="cmonthcalctrlsetrange"></a><a name="setrange"></a> CMonthCalCtrl:: SetRange

Задает минимальную и максимальную допустимые даты для элемента управления "месячный календарь".

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);

BOOL SetRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Параметры

*пминранже*<br/>
Указатель на `COleDateTime` объект, `CTime` объект или структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , содержащую дату в наименьшем конце диапазона.

*пмаксранже*<br/>
Указатель на `COleDateTime` объект, `CTime` объект или `SYSTEMTIME` структуру, содержащую дату в самом верхнем конце диапазона.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_SETRANGE](/windows/win32/Controls/mcm-setrange), как описано в Windows SDK. В реализации MFC `SetRange` можно указать использование `COleDateTime` , `CTime` использование или `SYSTEMTIME` использование структуры.

### <a name="example"></a>Пример

  См. пример для [CMonthCalCtrl::/Range](#getrange).

## <a name="cmonthcalctrlsetselrange"></a><a name="setselrange"></a> CMonthCalCtrl:: Сетселранже

Задает для элемента управления "месячный календарь" определенный диапазон дат.

```
BOOL SetSelRange(
    const COleDateTime& pMinRange,
    const COleDateTime& pMaxRange);

BOOL SetSelRange(
    const CTime& pMinRange,
    const CTime& pMaxRange);

BOOL SetSelRange(
    const LPSYSTEMTIME pMinRange,
    const LPSYSTEMTIME pMaxRange);
```

### <a name="parameters"></a>Параметры

*пминранже*<br/>
Указатель на `COleDateTime` объект, `CTime` объект или структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , содержащую дату в наименьшем конце диапазона.

*пмаксранже*<br/>
Указатель на `COleDateTime` объект, `CTime` объект или `SYSTEMTIME` структуру, содержащую дату в самом верхнем конце диапазона.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_SETSELRANGE](/windows/win32/Controls/mcm-setselrange), как описано в Windows SDK. В реализации MFC `SetSelRange` можно указать использование `COleDateTime` , `CTime` использование или `SYSTEMTIME` использование структуры.

## <a name="cmonthcalctrlsettoday"></a><a name="settoday"></a> CMonthCalCtrl:: Сеттодай

Задает элемент управления Calendar за текущий день.

```cpp
void SetToday(const COleDateTime& refDateTime);
void SetToday(const CTime* pDateTime);
void SetToday(const LPSYSTEMTIME pDateTime);
```

### <a name="parameters"></a>Параметры

*рефдатетиме*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , который содержит текущую дату.

*пдатетиме*<br/>
Во второй версии — указатель на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) , содержащий сведения о текущей дате. В третьей версии — указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , содержащую сведения о текущей дате.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [MCM_SETTODAY](/windows/win32/Controls/mcm-settoday), как описано в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [CMonthCalCtrl:: ontoday](#gettoday).

## <a name="cmonthcalctrlsetyearview"></a><a name="setyearview"></a> CMonthCalCtrl:: Сетеарвиев

Устанавливает для элемента управления "Календарь на текущий месяц" представление "год".

```
BOOL SetYearView();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод использует метод [CMonthCalCtrl:: сеткуррентвиев](#setcurrentview) , чтобы задать для представления значение MCMV_YEAR, представляющее годовое представление.

## <a name="cmonthcalctrlsizeminreq"></a><a name="sizeminreq"></a> CMonthCalCtrl:: Сиземинрек

Отображает элемент управления "месячный календарь" до минимального размера, отображающего один месяц.

```
BOOL SizeMinReq(BOOL bRepaint = TRUE);
```

### <a name="parameters"></a>Параметры

*bRepaint*<br/>
Указывает, следует ли перерисовать элемент управления. По умолчанию значение TRUE. Если задано значение FALSE, перерисовка не выполняется.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент управления "календарь месяца" имеет размер до минимального. в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызов `SizeMinReq` успешно отображает элемент управления "Календарь на весь месяц" для календаря в один месяц.

## <a name="cmonthcalctrlsizerecttomin"></a><a name="sizerecttomin"></a> CMonthCalCtrl:: Сизеректтомин

Для элемента управления "Календарь текущего месяца" вычисляет наименьший прямоугольник, который может содержать все календари, попадающие в указанный прямоугольник.

```
LPRECT SizeRectToMin(LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*лпрект*\
окне Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , определяющую прямоугольник, который содержит необходимое количество календарей.

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , определяющую прямоугольник, размер которого меньше или равен прямоугольнику, определенному параметром *лпрект* .

### <a name="remarks"></a>Примечания

Этот метод вычисляет, сколько календарей может уместиться в прямоугольнике, указанном параметром *лпрект* , а затем возвращает наименьший прямоугольник, который может содержать это количество календарей. Фактически этот метод сжимает указанный прямоугольник в точном соответствии с требуемым количеством календарей.

Этот метод отправляет [MCM_SIZERECTTOMIN](/windows/win32/Controls/mcm-sizerecttomin) сообщение, описанное в Windows SDK.

## <a name="see-also"></a>См. также

[Пример CMNCTRL1 для MFC](../../overview/visual-cpp-samples.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)
