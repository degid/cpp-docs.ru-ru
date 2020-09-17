---
title: Класс Коледатетимеспан
ms.date: 03/27/2019
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
ms.openlocfilehash: 746cfdce3265dff7e5b20a5135aa026aca9facdf
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832104"
---
# <a name="coledatetimespan-class"></a>Класс Коледатетимеспан

Представляет относительное время, интервал времени.

## <a name="syntax"></a>Синтаксис

```
class COleDateTimeSpan
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Коледатетимеспан:: Коледатетимеспан](#coledatetimespan)|Формирует объект `COleDateTimeSpan`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Коледатетимеспан::Format](#format)|Формирует форматированное строковое представление `COleDateTimeSpan` объекта.|
|[Коледатетимеспан:: @ Days](#getdays)|Возвращает часть дня диапазона, который представляет этот `COleDateTimeSpan` объект.|
|[Коледатетимеспан:: ч](#gethours)|Возвращает часть часа в диапазоне, `COleDateTimeSpan` представляемом этим объектом.|
|[Коледатетимеспан:: полчаса](#getminutes)|Возвращает часть минуты в диапазоне, `COleDateTimeSpan` представляемом этим объектом.|
|[Коледатетимеспан:: в секунду](#getseconds)|Возвращает вторую часть диапазона, `COleDateTimeSpan` представляемого этим объектом.|
|[Коледатетимеспан::/Status](#getstatus)|Возвращает состояние (допустимость) данного `COleDateTimeSpan` объекта.|
|[Коледатетимеспан:: Жеттоталдайс](#gettotaldays)|Возвращает число дней, которое `COleDateTimeSpan` представляет этот объект.|
|[Коледатетимеспан:: Жеттоталхаурс](#gettotalhours)|Возвращает число часов, которое `COleDateTimeSpan` представляет этот объект.|
|[Коледатетимеспан:: Жеттоталминутес](#gettotalminutes)|Возвращает количество минут, которое `COleDateTimeSpan` представляет этот объект.|
|[Коледатетимеспан:: Жеттоталсекондс](#gettotalseconds)|Возвращает число секунд, которое `COleDateTimeSpan` представляет этот объект.|
|[Коледатетимеспан:: Сетдатетимеспан](#setdatetimespan)|Задает значение этого `COleDateTimeSpan` объекта.|
|[Коледатетимеспан:: SetStatus](#setstatus)|Задает состояние (допустимость) этого `COleDateTimeSpan` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|-|-|
|[operator +,-](#operator_add_-)|Добавление, вычитание и изменение знака для `COleDateTimeSpan` значений.|
|[operator + =,-=](#operator_add_eq_-_eq)|Добавьте и вычтите `COleDateTimeSpan` значение из этого `COleDateTimeSpan` значения.|
|[operator=](#operator_eq)|Копирует `COleDateTimeSpan` значение.|
|[operator = =, <, <=](#coledatetimespan_relational_operators)|Сравните два `COleDateTimeSpan` значения.|
|[double - оператор](#operator_double)|Преобразует это `COleDateTimeSpan` значение в **`double`** .|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Коледатетимеспан:: m_span](#m_span)|Содержит базовый **`double`** для этого `COleDateTimeSpan` объекта.|
|[Коледатетимеспан:: m_status](#m_status)|Содержит состояние этого `COleDateTimeSpan` объекта.|

## <a name="remarks"></a>Примечания

`COleDateTimeSpan` не имеет базового класса.

`COleDateTimeSpan`Время сохраняется в днях.

`COleDateTimeSpan` используется со своим сопутствующим классом [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime` Инкапсулирует `DATE` тип данных OLE Automation. `COleDateTime` Представляет абсолютные значения времени. Все `COleDateTime` вычисления подразумевают `COleDateTimeSpan` значения. Отношение между этими классами аналогично отношению к одному между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).

Дополнительные сведения о `COleDateTime` `COleDateTimeSpan` классах и см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="requirements"></a>Требования

**Заголовок:** ATLComTime.h

## <a name="coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a> Операторы отношения Коледатетимеспан

Операторы сравнения.

```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```

### <a name="parameters"></a>Параметры

*датеспан*<br/>
Сравниваемый шаблон `COleDateTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Эти операторы сравнивают два значения даты и времени и возвращают значение TRUE, если условие истинно. в противном случае — FALSE.

### <a name="remarks"></a>Примечания

> [!NOTE]
> Если один из операндов является недопустимым, возникнет исключение АТЛАССЕРТ.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]

[!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]

## <a name="coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a> Коледатетимеспан:: Коледатетимеспан

Формирует объект `COleDateTimeSpan`.

```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Параметры

*дблспансрк*<br/>
Число дней, которое должно быть скопировано в новый `COleDateTimeSpan` объект.

*лдайс*, *нхаурс*, *нминс*, *нсекс*<br/>
Укажите значения дня и времени, которые должны быть скопированы в новый `COleDateTimeSpan` объект.

### <a name="remarks"></a>Примечания

Все эти конструкторы создают новые `COleDateTimeSpan` объекты, инициализированные с указанным значением. Ниже приведено краткое описание каждого из этих конструкторов.

- **Коледатетимеспан ()** Конструирует объект, `COleDateTimeSpan` инициализированный значением 0.

- **Коледатетимеспан (** `dblSpanSrc` **)** конструирует `COleDateTimeSpan` объект из значения с плавающей запятой.

- **Коледатетимеспан (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)** конструирует объект, `COleDateTimeSpan` инициализируемый на указанные числовые значения.

`COleDateTimeSpan`Для нового объекта задано допустимое состояние.

Дополнительные сведения о границах для `COleDateTimeSpan` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]

## <a name="coledatetimespanformat"></a><a name="format"></a> Коледатетимеспан::Format

Формирует форматированное строковое представление `COleDateTimeSpan` объекта.

```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Параметры

*пформат*<br/>
Строка форматирования, аналогичная `printf` строке форматирования. Коды форматирования, перед которыми стоит знак процента ( `%` ), заменяются соответствующим `COleDateTimeSpan` компонентом. Другие символы в строке форматирования копируются без изменений в возвращаемую строку. Значение и значения кодов форматирования для `Format` приведены ниже.

- **% H** Часов в текущем дне

- **% M** Минут за текущий час

- **% S** Секунд в текущей минуте

- **%%** Знак процента

Приведенные выше четыре кода формата являются единственными кодами, которые будут приниматься в формате.

-

*nID*<br/>
Идентификатор ресурса для строки управления форматированием.

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащий форматированное значение даты и времени.

### <a name="remarks"></a>Примечания

Вызывайте эти функции, чтобы создать форматированное представление значения интервала времени. Если состояние этого `COleDateTimeSpan` объекта равно null, то возвращаемое значение является пустой строкой. Если состояние является недопустимым, возвращаемая строка указывается строковым ресурсом IDS_INVALID_DATETIMESPAN.

Краткое описание форм для этой функции приведено ниже.

**Формат (** *пформат* **)**<br/>
Эта форма форматирует значение с помощью строки формата, содержащей специальные коды форматирования, которые предшествуют знаку процента (%), как в `printf` . Строка форматирования передается в функцию в качестве параметра.

**Формат (** *NID* **)**<br/>
Эта форма форматирует значение с помощью строки формата, содержащей специальные коды форматирования, которые предшествуют знаку процента (%), как в `printf` . Строка форматирования является ресурсом. ИДЕНТИФИКАТОР этого строкового ресурса передается в качестве параметра.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]

## <a name="coledatetimespangetdays"></a><a name="getdays"></a> Коледатетимеспан:: @ Days

Извлекает день этого значения даты и времени.

```
LONG GetDays() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Часть дня этого значения даты и времени.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этой функции находятся в диапазоне от приблизительно 3 615 000 до 3 615 000.

Другие функции, которые запрашивают значение `COleDateTimeSpan` объекта, см. в следующих функциях-членах:

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [жеттоталдайс](#gettotaldays)

- [жеттоталхаурс](#gettotalhours)

- [жеттоталминутес](#gettotalminutes)

- [жеттоталсекондс](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]

## <a name="coledatetimespangethours"></a><a name="gethours"></a> Коледатетимеспан:: ч

Получает часть часа этого значения даты и времени.

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Часть часов в этом значении даты и времени.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этой функции находятся в диапазоне от-23 до 23.

Другие функции, которые запрашивают значение `COleDateTimeSpan` объекта, см. в следующих функциях-членах:

- [Число дней](#getdays)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [жеттоталдайс](#gettotaldays)

- [жеттоталхаурс](#gettotalhours)

- [жеттоталминутес](#gettotalminutes)

- [жеттоталсекондс](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]

## <a name="coledatetimespangetminutes"></a><a name="getminutes"></a> Коледатетимеспан:: полчаса

Получает часть минуты этого значения даты и времени.

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Часть минуты этого значения даты и времени.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этой функции находятся в диапазоне от-59 до 59.

Другие функции, которые запрашивают значение `COleDateTimeSpan` объекта, см. в следующих функциях-членах:

- [Число дней](#getdays)

- [GetHours](#gethours)

- [GetSeconds](#getseconds)

- [жеттоталдайс](#gettotaldays)

- [жеттоталхаурс](#gettotalhours)

- [жеттоталминутес](#gettotalminutes)

- [жеттоталсекондс](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]

## <a name="coledatetimespangetseconds"></a><a name="getseconds"></a> Коледатетимеспан:: в секунду

Извлекает вторую часть этого значения даты и времени.

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Часть секунд этого значения даты и времени.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этой функции находятся в диапазоне от-59 до 59.

Другие функции, которые запрашивают значение `COleDateTimeSpan` объекта, см. в следующих функциях-членах:

- [Число дней](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [жеттоталдайс](#gettotaldays)

- [жеттоталхаурс](#gettotalhours)

- [жеттоталминутес](#gettotalminutes)

- [жеттоталсекондс](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]

## <a name="coledatetimespangetstatus"></a><a name="getstatus"></a> Коледатетимеспан::/Status

Возвращает состояние (допустимость) данного `COleDateTimeSpan` объекта.

```
DateTimeSpanStatus GetStatus() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Состояние этого `COleDateTimeSpan` значения.

### <a name="remarks"></a>Примечания

Возвращаемое значение определяется `DateTimeSpanStatus` перечисляемым типом, который определен в `COleDateTimeSpan` классе.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
};
```

Краткое описание этих значений состояния см. в следующем списке:

- `COleDateTimeSpan::valid` Указывает, что этот `COleDateTimeSpan` объект является допустимым.

- `COleDateTimeSpan::invalid` Указывает, что этот `COleDateTimeSpan` объект является недопустимым; его значение может быть неправильным.

- `COleDateTimeSpan::null` Указывает, что этот `COleDateTimeSpan` объект имеет значение null, то есть что для этого объекта не было предоставлено значение. (Это "null" в смысле базы данных "без значения", а не на C++ NULL.)

Состояние `COleDateTimeSpan` объекта недопустимо в следующих случаях:

- Значение, если во время операции арифметического присваивания этот объект вызвал переполнение или потерю точности, а именно `+=` или `-=` .

- Если этому объекту было присвоено недопустимое значение.

- Значение, если состояние этого объекта было явно задано как недопустимое с помощью `SetStatus` .

Дополнительные сведения об операциях, для которых может быть задано состояние "недопустимо", см. в разделе [коледатетимеспан::operator+,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) and [коледатетимеспан::operator+=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

Дополнительные сведения о границах для `COleDateTimeSpan` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="coledatetimespangettotaldays"></a><a name="gettotaldays"></a> Коледатетимеспан:: Жеттоталдайс

Извлекает это значение даты и времени, выраженное в днях.

```
double GetTotalDays() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Это значение даты и времени, выраженное в днях. Хотя эта функция является прототипом для возврата Double, она всегда будет возвращать целочисленное значение.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этой функции находятся в диапазоне от приблизительно-3.65 E6 до 3.65 E6.

Другие функции, которые запрашивают значение `COleDateTimeSpan` объекта, см. в следующих функциях-членах:

- [Число дней](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [жеттоталхаурс](#gettotalhours)

- [жеттоталминутес](#gettotalminutes)

- [жеттоталсекондс](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]

## <a name="coledatetimespangettotalhours"></a><a name="gettotalhours"></a> Коледатетимеспан:: Жеттоталхаурс

Получает значение даты и времени, выраженное в часах.

```
double GetTotalHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Это значение даты и времени, выраженное в часах. Хотя эта функция является прототипом для возврата Double, она всегда будет возвращать целочисленное значение.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этой функции находятся в диапазоне от приблизительно-8.77 E7 до 8.77 E7.

Другие функции, которые запрашивают значение `COleDateTimeSpan` объекта, см. в следующих функциях-членах:

- [Число дней](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [жеттоталдайс](#gettotaldays)

- [жеттоталминутес](#gettotalminutes)

- [жеттоталсекондс](#gettotalseconds)

### <a name="example"></a>Пример

См. пример для [жеттоталдайс](#gettotaldays).

## <a name="coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a> Коледатетимеспан:: Жеттоталминутес

Получает значение даты и времени, выраженное в минутах.

```
double GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Это значение даты и времени, выраженное в минутах. Хотя эта функция является прототипом для возврата Double, она всегда будет возвращать целочисленное значение.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этой функции находятся в диапазоне от приблизительно-5.26 E9 до 5.26 E9.

Другие функции, которые запрашивают значение `COleDateTimeSpan` объекта, см. в следующих функциях-членах:

- [Число дней](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [жеттоталдайс](#gettotaldays)

- [жеттоталхаурс](#gettotalhours)

- [жеттоталсекондс](#gettotalseconds)

### <a name="example"></a>Пример

См. пример для [жеттоталдайс](#gettotaldays).

## <a name="coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a> Коледатетимеспан:: Жеттоталсекондс

Получает значение даты и времени, выраженное в секундах.

```
double GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Это значение даты и времени, выраженное в секундах. Хотя эта функция является прототипом для возврата Double, она всегда будет возвращать целочисленное значение.

### <a name="remarks"></a>Примечания

Возвращаемые значения из этой функции находятся в диапазоне от приблизительно-3.16 E11 до 3.16 E11.

Другие функции, которые запрашивают значение `COleDateTimeSpan` объекта, см. в следующих функциях-членах:

- [Число дней](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [жеттоталдайс](#gettotaldays)

- [жеттоталхаурс](#gettotalhours)

- [жеттоталминутес](#gettotalminutes)

### <a name="example"></a>Пример

См. пример для [жеттоталдайс](#gettotaldays).

## <a name="coledatetimespanm_span"></a><a name="m_span"></a> Коледатетимеспан:: m_span

Базовое **`double`** значение для этого `COleDateTime` объекта.

```
double m_span;
```

### <a name="remarks"></a>Примечания

Это значение выражает дату и время в днях.

> [!CAUTION]
> Изменение значения в **`double`** элементе данных приведет к изменению значения этого `COleDateTimeSpan` объекта. Он не изменяет состояние этого `COleDateTimeSpan` объекта.

## <a name="coledatetimespanm_status"></a><a name="m_status"></a> Коледатетимеспан:: m_status

Тип для этого элемента данных — перечислимый тип `DateTimeSpanStatus` , который определен в `COleDateTimeSpan` классе.

```
DateTimeSpanStatus m_status;
```

### <a name="remarks"></a>Примечания

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

Краткое описание этих значений состояния см. в следующем списке:

- `COleDateTimeSpan::valid` Указывает, что этот `COleDateTimeSpan` объект является допустимым.

- `COleDateTimeSpan::invalid` Указывает, что этот `COleDateTimeSpan` объект является недопустимым; его значение может быть неправильным.

- `COleDateTimeSpan::null` Указывает, что этот `COleDateTimeSpan` объект имеет значение null, то есть что для этого объекта не было предоставлено значение. (Это "null" в смысле базы данных "без значения", а не на C++ NULL.)

Состояние `COleDateTimeSpan` объекта недопустимо в следующих случаях:

- Значение, если во время операции арифметического присваивания этот объект вызвал переполнение или потерю точности, а именно `+=` или `-=` .

- Если этому объекту было присвоено недопустимое значение.

- Значение, если состояние этого объекта было явно задано как недопустимое с помощью [SetStatus](#setstatus).

Дополнительные сведения об операциях, для которых может быть задано состояние "недопустимо", см. в разделе [коледатетимеспан::operator+,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) and [коледатетимеспан::operator+=,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).

> [!CAUTION]
> Этот элемент данных предназначен для более сложных сценариев программирования. Следует использовать встроенные функции элементов с параметром " [Status](#getstatus) " и [SetStatus](#setstatus). Дополнительные `SetStatus` предостережения относительно явного задания этого элемента данных см. в разделе.

Дополнительные сведения о границах для `COleDateTimeSpan` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="coledatetimespanoperator-"></a><a name="operator_eq"></a> Коледатетимеспан::operator=

Копирует `COleDateTimeSpan` значение.

```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```

### <a name="remarks"></a>Примечания

Этот перегруженный оператор присваивания копирует значение даты и времени исходного диапазона в этот `COleDateTimeSpan` объект.

## <a name="coledatetimespanoperator---"></a><a name="operator_add_-"></a> Коледатетимеспан::operator+,-

Добавление, вычитание и изменение знака для `COleDateTimeSpan` значений.

```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```

### <a name="remarks"></a>Примечания

Первые два оператора позволяют добавлять и вычитать значения даты и времени. Третья позволяет изменить знак значения даты и времени.

Если любой из операндов имеет значение null, состояние результирующего `COleDateTimeSpan` значения равно null.

Если один из операндов является недопустимым и второй не равен null, состояние результирующего `COleDateTimeSpan` значения является недопустимым.

Дополнительные сведения о допустимых, недопустимых и нулевых значениях состояния см. в разделе переменная члена [M_STATUS](#m_status) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]

## <a name="coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a> Коледатетимеспан::operator+=,-=

Добавьте и вычтите `COleDateTimeSpan` значение из этого `COleDateTimeSpan` значения.

```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Примечания

Эти операторы позволяют добавлять и вычитать значения даты и времени из этого `COleDateTimeSpan` объекта. Если любой из операндов имеет значение null, состояние результирующего `COleDateTimeSpan` значения равно null.

Если один из операндов является недопустимым и второй не равен null, состояние результирующего `COleDateTimeSpan` значения является недопустимым.

Дополнительные сведения о допустимых, недопустимых и нулевых значениях состояния см. в разделе переменная члена [M_STATUS](#m_status) .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]

## <a name="coledatetimespanoperator-double"></a><a name="operator_double"></a> Коледатетимеспан::operator, двойной

Преобразует это `COleDateTimeSpan` значение в **`double`** .

```
operator double() const throw();
```

### <a name="remarks"></a>Примечания

Этот оператор возвращает значение этого `COleDateTimeSpan` значения в виде числа дней с плавающей запятой.

## <a name="coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a> Коледатетимеспан:: Сетдатетимеспан

Задает значение этого значения даты и времени.

```cpp
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```

### <a name="parameters"></a>Параметры

*лдайс*, *нхаурс*, *нминс*, *нсекс*<br/>
Укажите значения диапазона даты и времени, которые должны быть скопированы в этот `COleDateTimeSpan` объект.

### <a name="remarks"></a>Примечания

Сведения о функциях, которые запрашивают значение `COleDateTimeSpan` объекта, см. в следующих функциях-членах:

- [Число дней](#getdays)

- [GetHours](#gethours)

- [GetMinutes](#getminutes)

- [GetSeconds](#getseconds)

- [жеттоталдайс](#gettotaldays)

- [жеттоталхаурс](#gettotalhours)

- [жеттоталминутес](#gettotalminutes)

- [жеттоталсекондс](#gettotalseconds)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]

## <a name="coledatetimespansetstatus"></a><a name="setstatus"></a> Коледатетимеспан:: SetStatus

Задает состояние (допустимость) этого `COleDateTimeSpan` объекта.

```cpp
void SetStatus(DateTimeSpanStatus status) throw();
```

### <a name="parameters"></a>Параметры

*status*<br/>
Новое значение состояния для этого `COleDateTimeSpan` объекта.

### <a name="remarks"></a>Примечания

Значение параметра *Status* определяется `DateTimeSpanStatus` перечисляемым типом, который определен в `COleDateTimeSpan` классе.

```
enum DateTimeSpanStatus{
   valid = 0,
   invalid = 1,
   null = 2,
   };
```

Краткое описание этих значений состояния см. в следующем списке:

- `COleDateTimeSpan::valid` Указывает, что этот `COleDateTimeSpan` объект является допустимым.

- `COleDateTimeSpan::invalid` Указывает, что этот `COleDateTimeSpan` объект является недопустимым; его значение может быть неправильным.

- `COleDateTimeSpan::null` Указывает, что этот `COleDateTimeSpan` объект имеет значение null, то есть что для этого объекта не было предоставлено значение. (Это "null" в смысле базы данных "без значения", а не на C++ NULL.)

   > [!CAUTION]
   > Эта функция предназначена для расширенных ситуаций программирования. Эта функция не изменяет данные в этом объекте. Чаще всего он используется для установки состояния в **значение NULL** или **недопустимо**. Обратите внимание, что оператор присваивания ([operator =](#operator_eq)) и [сетдатетимеспан](#setdatetimespan) устанавливают состояние объекта на основе исходных значений.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)<br/>
[Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
