---
title: Класс CDateTimeCtrl
ms.date: 11/04/2016
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
helpviewer_keywords:
- CDateTimeCtrl [MFC], CDateTimeCtrl
- CDateTimeCtrl [MFC], CloseMonthCal
- CDateTimeCtrl [MFC], Create
- CDateTimeCtrl [MFC], GetDateTimePickerInfo
- CDateTimeCtrl [MFC], GetIdealSize
- CDateTimeCtrl [MFC], GetMonthCalColor
- CDateTimeCtrl [MFC], GetMonthCalCtrl
- CDateTimeCtrl [MFC], GetMonthCalFont
- CDateTimeCtrl [MFC], GetMonthCalStyle
- CDateTimeCtrl [MFC], GetRange
- CDateTimeCtrl [MFC], GetTime
- CDateTimeCtrl [MFC], SetFormat
- CDateTimeCtrl [MFC], SetMonthCalColor
- CDateTimeCtrl [MFC], SetMonthCalFont
- CDateTimeCtrl [MFC], SetMonthCalStyle
- CDateTimeCtrl [MFC], SetRange
- CDateTimeCtrl [MFC], SetTime
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
ms.openlocfilehash: f04cce93aa6a86d11c2d9ec953992a0f90f635c5
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561951"
---
# <a name="cdatetimectrl-class"></a>Класс CDateTimeCtrl

Инкапсулирует функциональность элемента управления "выбор даты и времени".

## <a name="syntax"></a>Синтаксис

```
class CDateTimeCtrl : public CWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDateTimeCtrl:: CDateTimeCtrl](#cdatetimectrl)|Формирует объект `CDateTimeCtrl`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDateTimeCtrl:: Клосемонскал](#closemonthcal)|Закрывает текущий элемент управления выбор даты и времени.|
|[CDateTimeCtrl:: Create](#create)|Создает элемент управления выбора даты и времени и прикрепляет его к `CDateTimeCtrl` объекту.|
|[CDateTimeCtrl:: Жетдатетимепиккеринфо](#getdatetimepickerinfo)|Извлекает сведения о текущем элементе управления средства выбора даты и времени.|
|[CDateTimeCtrl:: Жетидеалсизе](#getidealsize)|Возвращает идеальный размер элемента управления "Выбор даты и времени", необходимого для вывода текущей даты или времени.|
|[CDateTimeCtrl:: Жетмонскалколор](#getmonthcalcolor)|Извлекает цвет для заданной части месячного календаря в элементе управления выбора даты и времени.|
|[CDateTimeCtrl:: Жетмонскалктрл](#getmonthcalctrl)|Извлекает `CMonthCalCtrl` объект, связанный с элементом управления "Выбор даты и времени".|
|[CDateTimeCtrl:: Жетмонскалфонт](#getmonthcalfont)|Извлекает шрифт, который в настоящее время используется элементом управления "Календарь" элемента управления "Выбор даты и времени".|
|[CDateTimeCtrl:: Жетмонскалстиле](#getmonthcalstyle)|Возвращает стиль текущего элемента управления "Выбор даты и времени".|
|[CDateTimeCtrl:: Range](#getrange)|Извлекает текущее минимальное и максимальное разрешенное системное время для элемента управления выбора даты и времени.|
|[CDateTimeCtrl:: во время](#gettime)|Извлекает текущее выбранное время из элемента управления "Выбор даты и времени" и помещает его в указанную `SYSTEMTIME` структуру.|
|[CDateTimeCtrl:: Сетформат](#setformat)|Задает отображение элемента управления "Выбор даты и времени" в соответствии с заданной строкой формата.|
|[CDateTimeCtrl:: Сетмонскалколор](#setmonthcalcolor)|Задает цвет для заданной части месячного календаря в элементе управления выбора даты и времени.|
|[CDateTimeCtrl:: Сетмонскалфонт](#setmonthcalfont)|Задает шрифт, который будет использоваться элементом управления "Календарь дочернего месяца" элемента управления "Выбор даты и времени".|
|[CDateTimeCtrl:: Сетмонскалстиле](#setmonthcalstyle)|Задает стиль текущего элемента управления "Выбор даты и времени".|
|[CDateTimeCtrl:: SetRange](#setrange)|Задает минимальное и максимально допустимое системное время для элемента управления выбора даты и времени.|
|[CDateTimeCtrl:: SetTime](#settime)|Задает время в элементе управления выбора даты и времени.|

## <a name="remarks"></a>Примечания

Элемент управления "Выбор даты и времени" (DTP Control) предоставляет простой интерфейс для обмена данными о дате и времени с пользователем. Этот интерфейс содержит поля, каждый из которых отображает часть сведений о дате и времени, хранящихся в элементе управления. Пользователь может изменить сведения, хранящиеся в элементе управления, изменив содержимое строки в заданном поле. Пользователь может перейти от поля к полю с помощью мыши или клавиатуры.

Элемент управления выбора даты и времени можно настроить, применяя разнообразные стили к объекту при его создании. Дополнительные сведения о стилях, относящихся к элементу управления "Выбор даты и времени", см. в разделе [стили элементов управления "Выбор даты и времени](/windows/win32/Controls/date-and-time-picker-control-styles) " в Windows SDK. Формат вывода элемента управления DTP можно задать с помощью стилей форматирования. Эти стили форматирования описаны в разделе "стили форматирования" в Windows SDK разделе [стили элемента управления "Выбор даты и времени](/windows/win32/Controls/date-and-time-picker-control-styles)".

Элемент управления "Выбор даты и времени" также использует уведомления и обратные вызовы, описанные в разделе [Использование CDateTimeCtrl](../../mfc/using-cdatetimectrl.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDateTimeCtrl`

## <a name="requirements"></a>Требования

**Заголовок:** афксдтктл.h

## <a name="cdatetimectrlcdatetimectrl"></a><a name="cdatetimectrl"></a> CDateTimeCtrl:: CDateTimeCtrl

Формирует объект `CDateTimeCtrl`.

```
CDateTimeCtrl();
```

## <a name="cdatetimectrlclosemonthcal"></a><a name="closemonthcal"></a> CDateTimeCtrl:: Клосемонскал

Закрывает текущий элемент управления выбор даты и времени.

```cpp
void CloseMonthCal() const;
```

### <a name="remarks"></a>Примечания

Этот метод отправляет [DTM_CLOSEMONTHCAL](/windows/win32/Controls/dtm-closemonthcal) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, *m_dateTimeCtrl*, которая используется для программного доступа к элементу выбора даты и времени. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Пример

В следующем примере кода закрывается раскрывающийся календарь для текущего элемента управления выбор даты и времени.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]

## <a name="cdatetimectrlcreate"></a><a name="create"></a> CDateTimeCtrl:: Create

Создает элемент управления выбора даты и времени и прикрепляет его к `CDateTimeCtrl` объекту.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Параметры

*двстиле*<br/>
Задает сочетание стилей управления датой и временем. Дополнительные сведения о стилях выбора даты и времени см. в разделе [стили элементов управления выбор даты и времени](/windows/win32/Controls/date-and-time-picker-control-styles) в Windows SDK.

*rect*<br/>
Ссылка на структуру [Rect](/windows/win32/api/windef/ns-windef-rect) , которая является позицией и размером элемента управления выбора даты и времени.

*ппарентвнд*<br/>
Указатель на объект [CWnd](../../mfc/reference/cwnd-class.md) , который является родительским окном элемента управления выбора даты и времени. Оно не должно иметь значение NULL.

*nID*<br/>
Задает идентификатор элемента управления средства выбора даты и времени.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если создание прошло успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

##### <a name="to-create-a-date-and-time-picker-control"></a>Создание элемента управления "Выбор даты и времени"

1. Вызовите [CDateTimeCtrl](#cdatetimectrl) для создания `CDateTimeCtrl` объекта.

1. Вызовите эту функцию члена, которая создает элемент управления выбора даты и времени Windows и присоединяет его к `CDateTimeCtrl` объекту.

При вызове метода `Create` инициализируются стандартные элементы управления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]

## <a name="cdatetimectrlgetdatetimepickerinfo"></a><a name="getdatetimepickerinfo"></a> CDateTimeCtrl:: Жетдатетимепиккеринфо

Извлекает сведения о текущем элементе управления средства выбора даты и времени.

```
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;
```

### <a name="parameters"></a>Параметры

*пдатетимепиккеринфо*\
заполняет Указатель на структуру [датетимепиккеринфо](/windows/win32/api/commctrl/ns-commctrl-datetimepickerinfo) , которая получает описание текущего элемента управления "Выбор даты и времени". Вызывающий объект отвечает за выделение этой структуры. Однако этот метод инициализирует элемент *кбсизе* структуры.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если этот метод успешно выполнен; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [DTM_GETDATETIMEPICKERINFO](/windows/win32/Controls/dtm-getdatetimepickerinfo) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, *m_dateTimeCtrl*, которая используется для программного доступа к элементу выбора даты и времени. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Пример

В следующем примере кода показано, возвращает ли он сведения о текущем элементе управления "Выбор даты и времени".

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]

## <a name="cdatetimectrlgetmonthcalcolor"></a><a name="getmonthcalcolor"></a> CDateTimeCtrl:: Жетмонскалколор

Извлекает цвет для заданной части месячного календаря в элементе управления выбора даты и времени.

```
COLORREF GetMonthCalColor(int iColor) const;
```

### <a name="parameters"></a>Параметры

*иколор*<br/>
**`int`** Значение, указывающее цветовую область календаря месяца для извлечения. Список значений см. в описании параметра *иколор* для [сетмонскалколор](#setmonthcalcolor).

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее параметр цвета для указанной части элемента управления "месячный календарь" в случае успешного выполнения. Функция возвращает значение-1 в случае неудачи.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [DTM_GETMCCOLOR](/windows/win32/Controls/dtm-getmccolor), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]

## <a name="cdatetimectrlgetmonthcalctrl"></a><a name="getmonthcalctrl"></a> CDateTimeCtrl:: Жетмонскалктрл

Извлекает `CMonthCalCtrl` объект, связанный с элементом управления "Выбор даты и времени".

```
CMonthCalCtrl* GetMonthCalCtrl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md) или значение NULL в случае неудачи или, если окно не отображается.

### <a name="remarks"></a>Примечания

Элементы управления "Выбор даты и времени" создают элемент управления "календарь за дочерний месяц", когда пользователь щелкает стрелку раскрывающегося списка. Если `CMonthCalCtrl` объект больше не нужен, он уничтожается, поэтому приложение не должно полагаться на хранение объекта, представляющего дочерний календарь месяца элемента управления "Выбор даты и времени".

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]

## <a name="cdatetimectrlgetmonthcalfont"></a><a name="getmonthcalfont"></a> CDateTimeCtrl:: Жетмонскалфонт

Возвращает шрифт, используемый в настоящее время элементом управления "календарь месяца" элемента управления "Выбор даты и времени".

```
CFont* GetMonthCalFont() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [кфонт](../../mfc/reference/cfont-class.md) или значение NULL в случае неудачи.

### <a name="remarks"></a>Примечания

`CFont`Объект, на который указывает возвращаемое значение, является временным объектом и уничтожается во время следующего времени обработки простоя.

## <a name="cdatetimectrlgetmonthcalstyle"></a><a name="getmonthcalstyle"></a> CDateTimeCtrl:: Жетмонскалстиле

Возвращает стиль элемента управления "месячный календарь", связанный с текущим элементом управления "Выбор даты и времени".

```
DWORD GetMonthCalStyle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Стиль элемента управления календаря в виде раскрывающегося списка, который является побитовым сочетанием (или) стилей элемента управления "Выбор даты и времени". Дополнительные сведения см. в разделе [стили элементов управления "месячный календарь](/windows/win32/Controls/month-calendar-control-styles)".

### <a name="remarks"></a>Примечания

Этот метод отправляет [DTM_GETMCSTYLE](/windows/win32/Controls/dtm-getmcstyle) сообщение, описанное в Windows SDK.

## <a name="cdatetimectrlgetrange"></a><a name="getrange"></a> CDateTimeCtrl:: Range

Извлекает текущее минимальное и максимальное разрешенное системное время для элемента управления выбора даты и времени.

```
DWORD GetRange(
    COleDateTime* pMinRange,
    COleDateTime* pMaxRange) const;

DWORD GetRange(
    CTime* pMinRange,
    CTime* pMaxRange) const;
```

### <a name="parameters"></a>Параметры

*пминранже*<br/>
Указатель на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) , содержащий самое раннее время, допустимое в `CDateTimeCtrl` объекте.

*пмаксранже*<br/>
Указатель на `COleDateTime` объект или `CTime` объект, содержащий Последнее разрешенное время в `CDateTimeCtrl` объекте.

### <a name="return-value"></a>Возвращаемое значение

Значение типа DWORD, содержащее флаги, указывающие, какие диапазоны задаются. If

`return value & GDTR_MAX` == 0

Второй параметр является допустимым. Аналогично, если

`return value & GDTR_MIN` == 0

Первый параметр является допустимым.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [DTM_GETRANGE](/windows/win32/Controls/dtm-getrange), как описано в Windows SDK. В реализации MFC можно указать значение `COleDateTime` или `CTime` использование.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#4](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]

## <a name="cdatetimectrlgettime"></a><a name="gettime"></a> CDateTimeCtrl:: во время

Извлекает текущее выбранное время из элемента управления "Выбор даты и времени" и помещает его в указанную `SYSTEMTIME` структуру.

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>Параметры

*тимедест*<br/>
В первой версии — ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , который будет принимать сведения о системном времени. Во второй версии — ссылка на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) , который будет принимать сведения о системном времени.

*птимедест*<br/>
Указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) для получения сведений о системном времени. Не может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

В первой версии ненулевое значение, если время успешно записано в `COleDateTime` объект; в противном случае — 0. Во второй и третьей версиях значение DWORD, равное набору элементов *dwFlag* в структуре [нмдатетимечанже](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) . Дополнительные сведения см. в разделе **"Примечания"** ниже.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [DTM_GETSYSTEMTIME](/windows/win32/Controls/dtm-getsystemtime), как описано в Windows SDK. В реализации MFC `GetTime` можно использовать `COleDateTime` `CTime` классы или, а также использовать `SYSTEMTIME` структуру для хранения сведений о времени.

Возвращаемое значение DWORD во второй и третьей версиях, приведенном выше, указывает, установлен ли элемент управления "Выбор даты и времени" в состояние "без даты", как указано в *dwFlagsе*элемента структуры [нмдатетимечанже](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange) . Если возвращенное значение равно GDT_NONE, то элементу управления присваивается состояние "нет даты" и используется стиль DTS_SHOWNONE. Если возвращенное значение равно GDT_VALID, системное время успешно хранится в целевом расположении.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]

## <a name="cdatetimectrlgetidealsize"></a><a name="getidealsize"></a> CDateTimeCtrl:: Жетидеалсизе

Возвращает идеальный размер элемента управления "Выбор даты и времени", необходимого для вывода текущей даты или времени.

```
BOOL GetIdealSize(LPSIZE psize) const;
```

### <a name="parameters"></a>Параметры

*псизе*\
заполняет Указатель на структуру [размера](/windows/win32/api/windef/ns-windef-size) , которая содержит идеальный размер элемента управления.

### <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение всегда равно TRUE.

### <a name="remarks"></a>Примечания

Этот метод отправляет [DTM_GETIDEALSIZE](/windows/win32/Controls/dtm-getidealsize) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, *m_dateTimeCtrl*, которая используется для программного доступа к элементу выбора даты и времени. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Пример

Следующий пример кода извлекает идеальный размер для вывода элемента управления выбора даты и времени.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]

## <a name="cdatetimectrlsetformat"></a><a name="setformat"></a> CDateTimeCtrl:: Сетформат

Задает отображение элемента управления "Выбор даты и времени" в соответствии с заданной строкой формата.

```
BOOL SetFormat(LPCTSTR pstrFormat);
```

### <a name="parameters"></a>Параметры

*пстрформат*<br/>
Указатель на строку формата с нулевым нулем, которая определяет требуемый вид. Если задать для этого параметра значение NULL, элемент управления будет сброшен в строку форматирования по умолчанию для текущего стиля.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

> [!NOTE]
> Ввод данных пользователем не определяет успешность или неудачу для этого вызова.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [DTM_SETFORMAT](/windows/win32/Controls/dtm-setformat), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#6](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]

## <a name="cdatetimectrlsetmonthcalcolor"></a><a name="setmonthcalcolor"></a> CDateTimeCtrl:: Сетмонскалколор

Задает цвет для заданной части месячного календаря в элементе управления выбора даты и времени.

```
COLORREF SetMonthCalColor(
    int iColor,
    COLORREF ref);
```

### <a name="parameters"></a>Параметры

*иколор*<br/>
**`int`** значение, указывающее, какую область элемента управления календаря месяца необходимо задать. Это значение может быть одним из следующих.

|Значение|Значение|
|-----------|-------------|
|MCSC_BACKGROUND|Задает цвет фона, отображаемый в интервале между месяцами.|
|MCSC_MONTHBK|Задайте цвет фона, отображаемый в течение месяца.|
|MCSC_TEXT|Задайте цвет, используемый для показа текста в течение месяца.|
|MCSC_TITLEBK|Задайте цвет фона, отображаемый в заголовке календаря.|
|MCSC_TITLETEXT|Задайте цвет, используемый для показа текста в заголовке календаря.|
|MCSC_TRAILINGTEXT|Задает цвет, используемый для вывода текста верхнего и конечного дней. Дни заголовков и конечных дней — это дни предыдущего и следующего месяцев, которые отображаются в текущем календаре.|

*ref*<br/>
Значение COLORREF, представляющее цвет, который будет задан для указанной области в месячном календаре.

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, представляющее предыдущий цвет для указанной части элемента управления "календарь месяца" в случае успеха. В противном случае сообщение возвращает значение-1.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [DTM_SETMCCOLOR](/windows/win32/Controls/dtm-setmccolor), как описано в Windows SDK.

### <a name="example"></a>Пример

  См. пример для [CDateTimeCtrl:: жетмонскалколор](#getmonthcalcolor).

## <a name="cdatetimectrlsetmonthcalfont"></a><a name="setmonthcalfont"></a> CDateTimeCtrl:: Сетмонскалфонт

Задает шрифт, который будет использоваться элементом управления "Календарь дочернего месяца" элемента управления "Выбор даты и времени".

```cpp
void SetMonthCalFont(
    HFONT hFont,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Параметры

*хфонт*<br/>
Обработано шрифтом, который будет установлен.

*bRedraw*<br/>
Указывает, должен ли элемент управления перерисоваться сразу после установки шрифта. Если задать для этого параметра значение TRUE, элемент управления будет перерисовываться самим собой.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [DTM_SETMCFONT](/windows/win32/Controls/dtm-setmcfont), как описано в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#7](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]

> [!NOTE]
> При использовании этого кода необходимо сделать член класса, производного от, с `CDialog` именем *m_MonthFont* типа `CFont` .

## <a name="cdatetimectrlsetmonthcalstyle"></a><a name="setmonthcalstyle"></a> CDateTimeCtrl:: Сетмонскалстиле

Задает стиль элемента управления "месячный календарь", связанный с текущим элементом управления "Выбор даты и времени".

```
DWORD SetMonthCalStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Параметры

*двстиле*\
окне Новый месячный стиль элемента управления Calendar, который представляет собой побитовое сочетание (или) стилей элемента управления "месячный календарь". Дополнительные сведения см. в разделе [стили элементов управления "месячный календарь](/windows/win32/Controls/month-calendar-control-styles)".

### <a name="return-value"></a>Возвращаемое значение

Предыдущий стиль элемента управления "месячный календарь".

### <a name="remarks"></a>Примечания

Этот метод отправляет [DTM_SETMCSTYLE](/windows/win32/Controls/dtm-setmcstyle) сообщение, описанное в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода определяется переменная, *m_dateTimeCtrl*, которая используется для программного доступа к элементу выбора даты и времени. Эта переменная используется в следующем примере.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]

### <a name="example"></a>Пример

В следующем примере кода элемент управления выбор даты и времени задается для отображения номеров недель, сокращенных названий дней недели и отсутствия текущего индикатора.

[!code-cpp[NVC_MFC_CDateTimeCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]

## <a name="cdatetimectrlsetrange"></a><a name="setrange"></a> CDateTimeCtrl:: SetRange

Задает минимальное и максимально допустимое системное время для элемента управления выбора даты и времени.

```
BOOL SetRange(
    const COleDateTime* pMinRange,
    const COleDateTime* pMaxRange);

BOOL SetRange(
    const CTime* pMinRange,
    const CTime* pMaxRange);
```

### <a name="parameters"></a>Параметры

*пминранже*<br/>
Указатель на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) или объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) , содержащий самое раннее время, допустимое в `CDateTimeCtrl` объекте.

*пмаксранже*<br/>
Указатель на `COleDateTime` объект или `CTime` объект, содержащий Последнее разрешенное время в `CDateTimeCtrl` объекте.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [DTM_SETRANGE](/windows/win32/Controls/dtm-setrange), как описано в Windows SDK. В реализации MFC можно указать значение `COleDateTime` или `CTime` использование. Если `COleDateTime` объект имеет состояние null, диапазон будет удален. Если `CTime` указатель или `COleDateTime` указатель имеет значение null, диапазон будет удален.

### <a name="example"></a>Пример

  См. пример для [CDateTimeCtrl::/Range](#getrange).

## <a name="cdatetimectrlsettime"></a><a name="settime"></a> CDateTimeCtrl:: SetTime

Задает время в элементе управления выбора даты и времени.

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* pTimeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```

### <a name="parameters"></a>Параметры

*тименев*<br/>
Ссылка на объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий элемент, для которого будет установлен элемент управления.

*птименев*<br/>
Во второй версии, приведенной выше, указатель на объект [CTime](../../atl-mfc-shared/reference/ctime-class.md) , содержащий время, в которое будет задаваться элемент управления. В третьей версии, приведенной выше, указатель на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) , содержащую время, в которое будет задаваться элемент управления.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Эта функция члена реализует поведение сообщения Win32 [DTM_SETSYSTEMTIME](/windows/win32/Controls/dtm-setsystemtime), как описано в Windows SDK. В реализации MFC `SetTime` можно использовать `COleDateTime` `CTime` классы или, а `SYSTEMTIME` для задания сведений о времени можно использовать структуру.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFC_CDateTimeCtrl#8](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]

## <a name="see-also"></a>См. также

[Пример CMNCTRL1 для MFC](../../overview/visual-cpp-samples.md)<br/>
[CWnd, класс](../../mfc/reference/cwnd-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)
