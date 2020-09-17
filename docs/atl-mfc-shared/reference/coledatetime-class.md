---
title: Класс COleDateTime
description: Справочник по API для класса MFC COleDateTime, который инкапсулирует `DATE` тип данных, используемый в OLE-автоматизации.
ms.date: 08/27/2020
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
ms.openlocfilehash: 9ebbab02860daaeb57c24d3e0901666861adfc2b
ms.sourcegitcommit: c8f1605354724a13566bc3b0fac3c5d98265f1d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2020
ms.locfileid: "89062162"
---
# <a name="coledatetime-class"></a>Класс COleDateTime

Инкапсулирует `DATE` тип данных, используемый в OLE-автоматизации.

## <a name="syntax"></a>Синтаксис

```
class COleDateTime
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[COleDateTime:: COleDateTime](#coledatetime)|Формирует объект `COleDateTime`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[COleDateTime::Format](#format)|Формирует форматированное строковое представление `COleDateTime` объекта.|
|[COleDateTime:: Жетасдбтиместамп](#getasdbtimestamp)|Вызовите этот метод, чтобы получить время в `COleDateTime` объекте в виде `DBTIMESTAMP` структуры данных.|
|[COleDateTime:: Жетассистемтиме](#getassystemtime)|Вызовите этот метод, чтобы получить время в `COleDateTime` объекте в виде структуры данных [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) .|
|[COleDateTime:: Жетасудате](#getasudate)|Вызовите этот метод, чтобы получить время в `COleDateTime` виде `UDATE` структуры данных.|
|[COleDateTime:: Жеткурренттиме](#getcurrenttime)|Создает `COleDateTime` объект, представляющий текущее время (статическую функцию-член).|
|[COleDateTime:: GetDay](#getday)|Возвращает день, который `COleDateTime` представляет этот объект (1-31).|
|[COleDateTime:: Жетдайофвик](#getdayofweek)|Возвращает день недели, который представляет этот `COleDateTime` объект (воскресенье = 1).|
|[COleDateTime:: Жетдайофеар](#getdayofyear)|Возвращает день года, который представляет этот `COleDateTime` объект (1 января = 1).|
|[COleDateTime:: в час](#gethour)|Возвращает час, который `COleDateTime` представляет этот объект (0-23).|
|[COleDateTime:: Minute](#getminute)|Возвращает значение минуты, которую `COleDateTime` представляет этот объект (0-59).|
|[COleDateTime:: в месяц](#getmonth)|Возвращает месяц, который `COleDateTime` представляет этот объект (1-12).|
|[COleDateTime:: в секунду](#getsecond)|Возвращает второй объект, `COleDateTime` представленный этим объектом (0-59).|
|[COleDateTime::/Status](#getstatus)|Возвращает состояние (допустимость) данного `COleDateTime` объекта.|
|[COleDateTime:: в г.](#getyear)|Возвращает год, который `COleDateTime` представляет этот объект.|
|[COleDateTime::P Арседатетиме](#parsedatetime)|Считывает значение даты и времени из строки и задает значение `COleDateTime` .|
|[COleDateTime:: SetDate](#setdate)|Устанавливает значение этого `COleDateTime` объекта в указанное значение только для даты.|
|[COleDateTime:: Сетдатетиме](#setdatetime)|Устанавливает значение этого `COleDateTime` объекта в указанное значение даты и времени.|
|[COleDateTime:: SetStatus](#setstatus)|Задает состояние (допустимость) этого `COleDateTime` объекта.|
|[COleDateTime:: SetTime](#settime)|Задает `COleDateTime` для этого объекта указанное значение времени.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[COleDateTime::operator==, COleDateTime::operator< и т. д.](#coledatetime_relational_operators)|Сравните два `COleDateTime` значения.|
|[COleDateTime::operator+, COleDateTime::operator-](#operator_add_-)|Добавление и вычитание `COleDateTime` значений.|
|[COleDateTime::operator+=, COleDateTime::operator-=](#operator_add_eq_-_eq)|Добавление и вычитание `COleDateTime` значения из этого `COleDateTime` объекта.|
|[COleDateTime::operator=](#operator_eq)|Копирует `COleDateTime` значение.|
|[COleDateTime::operator Дата, COleDateTime::operator Дата *](#operator_date)|Преобразует `COleDateTime` значение в `DATE` или `DATE*` .|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[COleDateTime:: m_dt](#m_dt)|Содержит базовый `DATE` для этого `COleDateTime` объекта.|
|[COleDateTime:: m_status](#m_status)|Содержит состояние этого `COleDateTime` объекта.|

## <a name="remarks"></a>Примечания

`COleDateTime` не имеет базового класса.

Это один из возможных типов для типа данных [Variant](/windows/win32/api/oaidl/ns-oaidl-variant) OLE Automation. `COleDateTime`Значение представляет собой абсолютное значение даты и времени.

`DATE`Тип реализуется как значение с плавающей запятой. Дни измеряются 30 декабря 1899 в полночь. В следующей таблице показаны некоторые даты и связанные с ними значения.

|Дата|Значение|
|----------|-----------|
|29 декабря 1899 г., полночь|-1.0|
|29 декабря 1899 г., 6 A. м|-1.25|
|30 декабря 1899 г., полночь|0,0|
|31 декабря 1899 г., полночь|1.0|
|1 января 1900 г., 6 часов утра|2.25|

> [!CAUTION]
> В приведенной выше таблице, несмотря на то, что значения дня становятся отрицательными до полуночи 30 декабря 1899 г., значения времени суток не используются. Например, 6:00 AM всегда представляется десятичным значением 0,25 независимо от того, является ли целое число, представляющее день, положительным (после 30 декабря 1899) или отрицательным (до 30 декабря 1899 г.). Это означает, что простое сравнение с плавающей точкой будет ошибочно сортировать значение, `COleDateTime` представляющее 6:00 AM 12/29/1899, как показано **выше** , чем значение, представляющее 7:00 в один день.

`COleDateTime`Класс обрабатывает даты с 1 января 100 до 31 декабря 9999. `COleDateTime`Класс использует григорианский календарь; он не поддерживает Юлианские даты. `COleDateTime` игнорирует летнее время. (См. раздел [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).)

> [!NOTE]
> Можно использовать `%y` Формат для получения двузначного года только для дат, начиная с 1900. Если вы используете `%y` Формат на дату до 1900, код создает ошибку Assert.

Этот тип также используется для представления значений только даты или времени. По соглашению дата 0 (30 декабря 1899) используется только для значений времени, а время 00:00 (полночь) используется только для значений даты.

Если `COleDateTime` объект создается с датой меньше 100, то дата принимается, но последующие вызовы функций `GetYear` , `GetMonth` ,,, `GetDay` `GetHour` `GetMinute` и `GetSecond` возвращают значение-1. Ранее можно было использовать даты, состоящих из двух цифр, но в MFC 4,2 и более поздних версиях даты должны быть 100 или больше.

Чтобы избежать проблем, укажите 4-значную дату. Пример:

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

Базовые арифметические операции для `COleDateTime` значений используют сопутствующий класс [коледатетимеспан](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan` значения определяют интервал времени. Связь между этими классами похожа на одну между [CTime](../../atl-mfc-shared/reference/ctime-class.md) и [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).

Дополнительные сведения о `COleDateTime` `COleDateTimeSpan` классах и см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="requirements"></a>Требования

**Заголовок:** ATLComTime.h

## <a name="coledatetime-relational-operators"></a><a name="coledatetime_relational_operators"></a> Операторы отношения COleDateTime

Операторы сравнения.

```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```

### <a name="parameters"></a>Параметры

*date*<br/>
Сравниваемый объект `COleDateTime`.

### <a name="remarks"></a>Примечания

> [!NOTE]
> Если один из двух операндов является недопустимым, возникнет исключение АТЛАССЕРТ.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>Пример

Операторы, **>=** **\<=**, **>** и **<** , будут утверждать, если `COleDateTime` объект имеет значение null.

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

## <a name="coledatetimecoledatetime"></a><a name="coledatetime"></a> COleDateTime:: COleDateTime

Формирует объект `COleDateTime`.

```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& timeStamp) throw();
```

### <a name="parameters"></a>Параметры

*датесрк*<br/>
Существующий `COleDateTime` объект, который будет скопирован в новый `COleDateTime` объект.

*varSrc*<br/>
Существующая `VARIANT` Структура данных (возможно, `COleVariant` объект) будет преобразована в значение даты и времени (VT_DATE) и скопирована в новый `COleDateTime` объект.

*дтсрк*<br/>
Значение даты и времени ( `DATE` ), которое должно быть скопировано в новый `COleDateTime` объект.

*тимесрк*<br/>
`time_t`Значение или, `__time64_t` которое необходимо преобразовать в значение даты и времени и скопировать в новый `COleDateTime` объект.

*систимесрк*<br/>
`SYSTEMTIME`Структура, которую необходимо преобразовать в значение даты и времени и скопировать в новый `COleDateTime` объект.

*филетимесрк*<br/>
`FILETIME`Структура, которую необходимо преобразовать в значение даты и времени и скопировать в новый `COleDateTime` объект. В `FILETIME` используется Универсальное координированное время (UTC), поэтому при передаче в структуру местного времени результаты будут неправильными. Дополнительные сведения см. в разделе [время файла](/windows/win32/SysInfo/file-times) в Windows SDK.

*НЕАР*, *нмонс*, *nОшибка дня*, *nчас суток*, *nмин.*, *NSEC*<br/>
Указывает значения даты и времени, которые должны быть скопированы в новый `COleDateTime` объект.

*вдосдате*, *вдостиме*<br/>
Значения даты и времени MS-DOS, которые должны быть преобразованы в значение даты и времени и скопированы в новый `COleDateTime` объект.

*timeStamp*<br/>
Ссылка на структуру [DBTIMESTAMP](/dotnet/api/system.data.oledb.oledbtype) , содержащую текущее местное время.

### <a name="remarks"></a>Примечания

Все эти конструкторы создают новые `COleDateTime` объекты, инициализированные с указанным значением. В следующей таблице показаны допустимые диапазоны для каждого компонента даты и времени.

|Компонент даты и времени|Допустимый диапазон|
|--------------------------|-----------------|
|year|100-9999|
|month|0 - 12|
|day|0 - 31|
|hour|0 - 23|
|minute|0 - 59|
|second|0 - 59|

Обратите внимание, что фактическая верхняя граница для компонента Day зависит от компонентов «месяц» и «год». Дополнительные сведения см. в `SetDate` разделе `SetDateTime` функции элементов или.

Ниже приведено краткое описание каждого конструктора.

- `COleDateTime(`**)** Конструирует объект, `COleDateTime` инициализируемый в 0 (полночь, 30 декабря 1899).

- `COleDateTime(``dateSrc` **)** Конструирует `COleDateTime` объект на основе существующего `COleDateTime` объекта.

- `COleDateTime(`*варсрк* **)** конструирует `COleDateTime` объект. Пытается преобразовать `VARIANT` структуру или объект [COleVariant](../../mfc/reference/colevariant-class.md) в значение даты и времени ( `VT_DATE` ). Если это преобразование выполнено успешно, преобразованное значение копируется в новый `COleDateTime` объект. Если это не так, значение `COleDateTime` объекта задается равным 0 (полночь, 30 декабря 1899), а его состояние — недопустимо.

- `COleDateTime(``dtSrc` **)** Конструирует `COleDateTime` объект из `DATE` значения.

- `COleDateTime(``timeSrc` **)** Конструирует `COleDateTime` объект из `time_t` значения.

- `COleDateTime(`*систимесрк* **)** конструирует `COleDateTime` объект из `SYSTEMTIME` значения.

- `COleDateTime(``filetimeSrc` **)** Конструирует `COleDateTime` объект из `FILETIME` значения. . В `FILETIME` используется Универсальное координированное время (UTC), поэтому при передаче в структуру местного времени результаты будут неправильными. Дополнительные сведения см. в разделе [время файла](/windows/win32/SysInfo/file-times) в Windows SDK.

- `COleDateTime(``nYear`,,, `nMonth` `nDay` `nHour` , `nMin` , `nSec` **)** Конструирует `COleDateTime` объект из указанных числовых значений.

- `COleDateTime(``wDosDate`, `wDosTime` **)** Конструирует `COleDateTime` объект на основе указанных значений даты и времени MS-DOS.

Дополнительные сведения о `time_t` типе данных см. в описании функции [time](../../c-runtime-library/reference/time-time32-time64.md) в *справочнике по библиотеке времени выполнения*.

Дополнительные сведения см. в разделе структуры [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) и [fileTime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) в Windows SDK.

Дополнительные сведения о границах для `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

> [!NOTE]
> Конструктор, использующий `DBTIMESTAMP` параметр, доступен только при включении OLEDB.h.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

## <a name="coledatetimeformat"></a><a name="format"></a> COleDateTime::Format

Создает форматированное представление значения даты и времени.

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Указывает один из следующих флагов языкового стандарта:

- LOCALE_NOUSEROVERRIDE использовать системные параметры по умолчанию, а не пользовательские параметры пользователя.

- VAR_TIMEVALUEONLY не учитывать часть даты во время синтаксического анализа.

- VAR_DATEVALUEONLY пропустить часть времени во время синтаксического анализа.

*lcid*<br/>
Указывает код локали, используемый для преобразования. Дополнительные сведения об идентификаторах языков см. в разделе [идентификаторы языков](/windows/win32/Intl/language-identifiers).

*лпсзформат*<br/>
Строка форматирования, аналогичная `printf` строке форматирования. Каждый код форматирования, которому предшествует знак процента ( `%` ), заменяется соответствующим `COleDateTime` компонентом. Другие символы в строке форматирования копируются без изменений в возвращаемую строку. Дополнительные сведения см. в описании функции времени выполнения [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md). Значение и смысл кодов форматирования для `Format` :

- `%H` Часов в текущем дне

- `%M` Минут за текущий час

- `%S` Секунд в текущей минуте

- `%%` Знак процента

*нформатид*<br/>
Идентификатор ресурса для строки управления форматированием.

### <a name="return-value"></a>Возвращаемое значение

Значение типа `CString` , содержащее форматированное значение даты и времени.

### <a name="remarks"></a>Примечания

Если состояние этого `COleDateTime` объекта равно null, то возвращаемое значение является пустой строкой. Если состояние является недопустимым, возвращаемая строка указывается строковым ресурсом ATL_IDS_DATETIME_INVALID.

Краткое описание трех форм для этой функции приведено ниже.

`Format`( *dwFlags*, *LCID*)<br/>
Эта форма форматирует значение с помощью языковых спецификаций (идентификаторов локали) для даты и времени. Используя параметры по умолчанию, эта форма выводит дату и время, если только часть времени не равна 0 (полночь). в этом случае выводится только дата или часть даты — 0 (30 декабря 1899). в этом случае будет распечатано только время. Если значение даты и времени равно 0 (30 декабря 1899, полночь), то эта форма с параметрами по умолчанию будет выводит полночь.

`Format`( *лпсзформат*)<br/>
Эта форма форматирует значение с помощью строки формата, содержащей специальные коды форматирования, которые предшествуют знаку процента (%), как в `printf` . Строка форматирования передается в функцию в качестве параметра. Дополнительные сведения о кодах форматирования см. в разделе [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) в справочнике по библиотеке времени выполнения.

`Format`( *нформатид*)<br/>
Эта форма форматирует значение с помощью строки формата, содержащей специальные коды форматирования, которые предшествуют знаку процента (%), как в `printf` . Строка форматирования является ресурсом. ИДЕНТИФИКАТОР этого строкового ресурса передается в качестве параметра. Дополнительные сведения о кодах форматирования см. в разделе [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) в *справочнике по библиотеке времени выполнения*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

## <a name="coledatetimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a> COleDateTime:: Жетасдбтиместамп

Вызовите этот метод, чтобы получить время в `COleDateTime` объекте в виде `DBTIMESTAMP` структуры данных.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& timeStamp) const throw();
```

### <a name="parameters"></a>Параметры

*timeStamp*<br/>
Ссылка на структуру [DBTIMESTAMP](/dotnet/api/system.data.oledb.oledbtype) .

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Сохраняет результирующее время в указанной структуре *метки времени* . `DBTIMESTAMP`Для структуры данных, инициализированной этой функцией, член будет иметь `fraction` значение 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

## <a name="coledatetimegetassystemtime"></a><a name="getassystemtime"></a> COleDateTime:: Жетассистемтиме

Вызовите этот метод, чтобы получить время в `COleDateTime` объекте в виде `SYSTEMTIME` структуры данных.

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>Параметры

*систиме*<br/>
Ссылка на структуру [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) для получения преобразованного значения даты и времени из `COleDateTime` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения. Значение FALSE, если преобразование завершается неудачно или если `COleDateTime` объект имеет значение null или является недопустимым.

### <a name="remarks"></a>Примечания

`GetAsSystemTime` сохраняет результирующее время в упоминаемом объекте *систиме* . `SYSTEMTIME`Для структуры данных, инициализированной этой функцией, член будет иметь `wMilliseconds` значение 0.

Дополнительные сведения о сведениях о состоянии, хранящихся в `COleDateTime` объекте, см. в разделе о [состоянии](#getstatus).

## <a name="coledatetimegetasudate"></a><a name="getasudate"></a> COleDateTime:: Жетасудате

Вызовите этот метод, чтобы получить время в `COleDateTime` объекте в виде `UDATE` структуры данных.

```
bool GetAsUDATE(UDATE& uDate) const throw();
```

### <a name="parameters"></a>Параметры

*удате*<br/>
Ссылка на `UDATE` структуру, которая получает преобразованное значение даты и времени из `COleDateTime` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успешного выполнения. Значение FALSE, если преобразование завершается неудачно или если `COleDateTime` объект имеет значение null или является недопустимым.

### <a name="remarks"></a>Примечания

`UDATE`Структура представляет "распакованную" дату.

## <a name="coledatetimegetcurrenttime"></a><a name="getcurrenttime"></a> COleDateTime:: Жеткурренттиме

Вызовите эту статическую функцию-член, чтобы вернуть текущее значение даты и времени.

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

## <a name="coledatetimegetday"></a><a name="getday"></a> COleDateTime:: GetDay

Возвращает день месяца, представленный этим значением даты и времени.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

День месяца, представленный значением этого объекта, или значение `COleDateTime` `COleDateTime::error` , если день не может быть получен.

### <a name="remarks"></a>Примечания

Допустимые возвращаемые значения находятся в диапазоне от 1 до 31.

Сведения о других функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [В час](#gethour)

- [GetMinute —](#getminute)

- [В секунду](#getsecond)

- [жетдайофвик](#getdayofweek)

- [жетдайофеар](#getdayofyear)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

## <a name="coledatetimegetdayofweek"></a><a name="getdayofweek"></a> COleDateTime:: Жетдайофвик

Возвращает день недели, представленный этим значением даты и времени.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

День недели, представленный значением этого объекта, или значение `COleDateTime` `COleDateTime::error` , если не удалось получить день недели.

### <a name="remarks"></a>Примечания

Допустимые возвращаемые значения находятся в диапазоне от 1 до 7, где 1 = воскресенье, 2 = понедельник и т. д.

Сведения о других функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [В час](#gethour)

- [GetMinute —](#getminute)

- [В секунду](#getsecond)

- [жетдайофеар](#getdayofyear)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

## <a name="coledatetimegetdayofyear"></a><a name="getdayofyear"></a> COleDateTime:: Жетдайофеар

Возвращает день года, представленный этим значением даты и времени.

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

День года, представленный значением этого объекта, или значение `COleDateTime` `COleDateTime::error` , если не удалось получить день года.

### <a name="remarks"></a>Примечания

Допустимые возвращаемые значения находятся в диапазоне от 1 до 366, где 1 января = 1.

Сведения о других функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [В час](#gethour)

- [GetMinute —](#getminute)

- [В секунду](#getsecond)

- [жетдайофвик](#getdayofweek)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

## <a name="coledatetimegethour"></a><a name="gethour"></a> COleDateTime:: в час

Возвращает час, представленный этим значением даты и времени.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Час, представленный значением этого объекта, `COleDateTime` или значение `COleDateTime::error` , если не удалось получить час.

### <a name="remarks"></a>Примечания

Допустимые значения в диапазоне от 0 до 23.

Сведения о других функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetMinute —](#getminute)

- [В секунду](#getsecond)

- [жетдайофвик](#getdayofweek)

- [жетдайофеар](#getdayofyear)

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

## <a name="coledatetimegetminute"></a><a name="getminute"></a> COleDateTime:: Minute

Возвращает значение минуты, представленное этим значением даты и времени.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Минуты, представленные значением этого объекта, `COleDateTime` или значение `COleDateTime::error` , если значение минуты не может быть получено.

### <a name="remarks"></a>Примечания

Допустимые значения в диапазоне от 0 до 59.

Сведения о других функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [В час](#gethour)

- [В секунду](#getsecond)

- [жетдайофвик](#getdayofweek)

- [жетдайофеар](#getdayofyear)

### <a name="example"></a>Пример

См. пример для в течение [часа](#gethour).

## <a name="coledatetimegetmonth"></a><a name="getmonth"></a> COleDateTime:: в месяц

Возвращает месяц, представленный этим значением даты и времени.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Месяц, представленный значением этого объекта, `COleDateTime` или значение `COleDateTime::error` , если месяц не удалось получить.

### <a name="remarks"></a>Примечания

Допустимые возвращаемые значения находятся в диапазоне от 1 до 12.

Сведения о других функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetYear](#getyear)

- [В час](#gethour)

- [GetMinute —](#getminute)

- [В секунду](#getsecond)

- [жетдайофвик](#getdayofweek)

- [жетдайофеар](#getdayofyear)

### <a name="example"></a>Пример

См. пример для [GetDay](#getday).

## <a name="coledatetimegetsecond"></a><a name="getsecond"></a> COleDateTime:: в секунду

Возвращает второй объект, представленный этим значением даты и времени.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Второй объект, представленный значением данного `COleDateTime` объекта, или `COleDateTime::error` значение, если второе значение не может быть получено.

### <a name="remarks"></a>Примечания

Допустимые значения в диапазоне от 0 до 59.

> [!NOTE]
> `COleDateTime`Класс не поддерживает високосные секунды.

Дополнительные сведения о реализации `COleDateTime` см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

Сведения о других функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [В час](#gethour)

- [GetMinute —](#getminute)

- [жетдайофвик](#getdayofweek)

- [жетдайофеар](#getdayofyear)

### <a name="example"></a>Пример

См. пример для в течение [часа](#gethour).

## <a name="coledatetimegetstatus"></a><a name="getstatus"></a> COleDateTime::/Status

Возвращает состояние (допустимость) заданного `COleDateTime` объекта.

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает состояние этого `COleDateTime` значения. При вызове `GetStatus` для `COleDateTime` объекта, созданного с использованием значения по умолчанию, он возвратит допустимое значение. При вызове `GetStatus` для `COleDateTime` объекта, инициализированного с помощью конструктора со значением NULL, `GetStatus` будет возвращено значение null.

### <a name="remarks"></a>Примечания

Возвращаемое значение определяется `DateTimeStatus` перечисляемым типом, который определен в `COleDateTime` классе.

```
enum DateTimeStatus
{
   error = -1,
   valid = 0,
   invalid = 1,    // Invalid date (out of range, etc.)
   null = 2,       // Literally has no value
};
```

Краткое описание этих значений состояния см. в следующем списке:

- `COleDateTime::error` Указывает, что при попытке получить часть значения даты и времени произошла ошибка.

- `COleDateTime::valid` Указывает, что этот `COleDateTime` объект является допустимым.

- `COleDateTime::invalid` Указывает, что этот `COleDateTime` объект является недопустимым; его значение может быть неправильным.

- `COleDateTime::null` Указывает, что этот `COleDateTime` объект имеет значение null, то есть что для этого объекта не было предоставлено значение. (Это "null" в смысле базы данных "без значения", а не на C++ NULL.)

Состояние `COleDateTime` объекта недопустимо в следующих случаях:

- Значение, если для параметра задано значение `VARIANT` или `COleVariant` , которое не может быть преобразовано в значение даты и времени.

- Значение, если для параметра задано значение `time_t` , `SYSTEMTIME` или `FILETIME` , которое не может быть преобразовано в допустимое значение даты и времени.

- Если его значение задано `SetDateTime` с помощью недопустимых значений параметров.

- Значение, если во время операции арифметического присваивания этот объект вызвал переполнение или потерю точности, а именно `+=` или `-=` .

- Если этому объекту было присвоено недопустимое значение.

- Значение, если состояние этого объекта было явно задано как недопустимое с помощью `SetStatus` .

Дополнительные сведения об операциях, для которых может быть задано состояние "недопустимо", см. в следующих функциях элементов:

- [COleDateTime](#coledatetime)

- [сетдатетиме](#setdatetime)

- [operator +,-](#operator_add_-)

- [operator + =,-=](#operator_add_eq_-_eq)

Дополнительные сведения о границах для `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

## <a name="coledatetimegetyear"></a><a name="getyear"></a> COleDateTime:: в г.

Возвращает год, представленный этим значением даты и времени.

```
int GetYear() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Год, представленный значением этого объекта, `COleDateTime` или значение `COleDateTime::error` , если год не может быть получен.

### <a name="remarks"></a>Примечания

Диапазон допустимых возвращаемых значений — от 100 до 9999, включая век.

Сведения о других функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [В час](#gethour)

- [GetMinute —](#getminute)

- [В секунду](#getsecond)

- [жетдайофвик](#getdayofweek)

- [жетдайофеар](#getdayofyear)

Дополнительные сведения о границах для `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Пример

См. пример для [GetDay](#getday).

## <a name="coledatetimem_dt"></a><a name="m_dt"></a> COleDateTime:: m_dt

Базовая `DATE` структура для этого `COleDateTime` объекта.

```
DATE m_dt;
```

### <a name="remarks"></a>Примечания

> [!CAUTION]
> Изменение значения `DATE` объекта, к которому обращается указатель, возвращаемый этой функцией, приведет к изменению значения этого `COleDateTime` объекта. Он не изменяет состояние этого `COleDateTime` объекта.

Дополнительные сведения о реализации `DATE` объекта см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="coledatetimem_status"></a><a name="m_status"></a> COleDateTime:: m_status

Содержит состояние этого `COleDateTime` объекта.

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>Примечания

Тип этого элемента данных — перечислимый тип `DateTimeStatus` , который определен в `COleDateTime` классе. Дополнительные сведения см. в разделе [COleDateTime:: Status](#getstatus).

> [!CAUTION]
> Этот элемент данных предназначен для более сложных сценариев программирования. Следует использовать встроенные функции элементов с параметром " [Status](#getstatus) " и [SetStatus](#setstatus). Дополнительные `SetStatus` предостережения относительно явного задания этого элемента данных см. в разделе.

## <a name="coledatetimeoperator-"></a><a name="operator_eq"></a> COleDateTime::operator=

Копирует `COleDateTime` значение.

```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& uDate) throw();
```

### <a name="remarks"></a>Примечания

Эти перегруженные операторы присваивания копируют исходное значение даты и времени в этот `COleDateTime` объект. Ниже приведено краткое описание каждого перегруженного оператора присваивания.

- **operator = (** `dateSrc` **)** значение и состояние операнда копируются в этот `COleDateTime` объект.

- **operator = (** *варсрк* **)** Если преобразование значения [типа Variant](/windows/win32/api/oaidl/ns-oaidl-variant) (или объекта [COleVariant](../../mfc/reference/colevariant-class.md) ) в дату и время (VT_DATE) выполнено успешно, преобразованное значение копируется в этот `COleDateTime` объект, а его состояние устанавливается в допустимое. Если преобразование завершилось неудачно, значение этого объекта устанавливается равным нулю (30 декабря 1899, полночь), а его состояние — недопустимо.

- **operator = (** `dtSrc` **)** `DATE` значение копируется в этот `COleDateTime` объект, а его состояние имеет значение Valid.

- **operator = (** `timeSrc` **)** `time_t` значение или `__time64_t` преобразуется и копируется в этот `COleDateTime` объект. Если преобразование прошло успешно, состояние этого объекта устанавливается в допустимое значение; в случае неудачи задано недопустимое значение.

- **operator = (** *систимесрк* **)** Значение [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) преобразуется и копируется в этот `COleDateTime` объект. Если преобразование прошло успешно, состояние этого объекта устанавливается в допустимое значение; в случае неудачи задано недопустимое значение.

- **operator = (** `uDate` **)** `UDATE` значение преобразуется и копируется в этот `COleDateTime` объект. Если преобразование прошло успешно, состояние этого объекта устанавливается в допустимое значение; в случае неудачи задано недопустимое значение. `UDATE`Структура представляет "распакованную" дату. Дополнительные сведения см. в описании функции [вардатефромудате](/windows/win32/api/oleauto/nf-oleauto-vardatefromudate).

- **operator = (** `filetimeSrc` **)** значение [fileTime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) преобразуется и копируется в этот `COleDateTime` объект. Если преобразование прошло успешно, состояние этого объекта устанавливается в допустимое значение; в противном случае задано недопустимое значение. `FILETIME` использует время в формате UTC, поэтому при передаче в структуру времени в формате UTC результаты будут преобразованы из времени UTC в местное время и будут храниться как вариантное время. Такое поведение аналогично поведению в Visual C++ 6,0 и Visual C++ .NET 2003 с пакетом обновления 2 (SP2). Дополнительные сведения см. в разделе [время файла](/windows/win32/SysInfo/file-times) в Windows SDK.

Дополнительные сведения см. в записи [типа Variant](/windows/win32/api/oaidl/ns-oaidl-variant) в Windows SDK.

Дополнительные сведения о `time_t` типе данных см. в описании функции [time](../../c-runtime-library/reference/time-time32-time64.md) в *справочнике по библиотеке времени выполнения*.

Дополнительные сведения см. в разделе структуры [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) и [fileTime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) в Windows SDK.

Дополнительные сведения о границах для `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="coledatetimeoperator---"></a><a name="operator_add_-"></a> COleDateTime::operator+,-

Добавление и вычитание `ColeDateTime` значений.

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>Примечания

`COleDateTime` объекты представляют абсолютное время. Объекты [коледатетимеспан](../../atl-mfc-shared/reference/coledatetimespan-class.md) представляют относительные значения времени. Первые два оператора позволяют добавлять и вычитать `COleDateTimeSpan` значение из `COleDateTime` значения. Третий оператор позволяет вычесть одно `COleDateTime` значение из другого, чтобы получить `COleDateTimeSpan` значение.

Если любой из операндов имеет значение null, состояние результирующего `COleDateTime` значения равно null.

Если результирующее `COleDateTime` значение выходит за пределы допустимых значений, состояние этого `COleDateTime` значения является недопустимым.

Если один из операндов является недопустимым и второй не равен null, состояние результирующего `COleDateTime` значения является недопустимым.

**+** Операторы и **-** будут утверждать, если `COleDateTime` объект имеет значение null. Пример см. в разделе [реляционные операторы COleDateTime](#coledatetime_relational_operators) .

Дополнительные сведения о допустимых, недопустимых и нулевых значениях состояния см. в разделе переменная члена [M_STATUS](#m_status) .

Дополнительные сведения о границах для `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

## <a name="coledatetimeoperator---"></a><a name="operator_add_eq_-_eq"></a> COleDateTime::operator+=,-=

Добавление и вычитание `ColeDateTime` значения из этого `COleDateTime` объекта.

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Примечания

Эти операторы позволяют добавлять и вычитать `COleDateTimeSpan` значения из этого `COleDateTime` . Если любой из операндов имеет значение null, состояние результирующего `COleDateTime` значения равно null.

Если результирующее `COleDateTime` значение выходит за пределы допустимых значений, то состояние этого `COleDateTime` параметра будет равно "недопустимо".

Если один из операндов является недопустимым и другое не равно null, состояние результирующего `COleDateTime` значения является недопустимым.

Дополнительные сведения о допустимых, недопустимых и нулевых значениях состояния см. в разделе переменная члена [M_STATUS](#m_status) .

**+=** Операторы и **-=** будут утверждать, если `COleDateTime` объект имеет значение null. Пример см. в разделе [реляционные операторы COleDateTime](#coledatetime_relational_operators) .

Дополнительные сведения о границах для `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="coledatetimeoperator-date"></a><a name="operator_date"></a> COleDateTime:: Оператор DATE

Преобразует `ColeDateTime` значение в `DATE` .

```
operator DATE() const throw();
```

### <a name="remarks"></a>Примечания

Этот оператор возвращает `DATE` объект, значение которого копируется из этого `COleDateTime` объекта. Дополнительные сведения о реализации `DATE` объекта см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

`DATE`Оператор будет утверждать, если `COleDateTime` объект имеет значение null. Пример см. в разделе [реляционные операторы COleDateTime](#coledatetime_relational_operators) .

## <a name="coledatetimeparsedatetime"></a><a name="parsedatetime"></a> COleDateTime::P Арседатетиме

Анализирует строку для считывания значения даты-времени.

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>Параметры

*лпсздате*<br/>
Указатель на строку, завершающуюся нулем, которая должна быть проанализирована. Дополнительные сведения см. в разделе "Заметки".

*dwFlags*<br/>
Указывает флаги для параметров языкового стандарта и анализа. Один или несколько следующих флагов:

- LOCALE_NOUSEROVERRIDE использовать системные параметры по умолчанию, а не пользовательские параметры пользователя.

- VAR_TIMEVALUEONLY не учитывать часть даты во время синтаксического анализа.

- VAR_DATEVALUEONLY пропустить часть времени во время синтаксического анализа.

*lcid*<br/>
Указывает код локали, используемый для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если строка была успешно преобразована в значение даты и времени; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если строка была успешно преобразована в значение даты и времени, то этому объекту присваивается значение `COleDateTime` , а его состояние — Valid.

> [!NOTE]
> Значения года должны находиться в диапазоне от 100 до 9999 включительно.

Параметр *лпсздате* может иметь различные форматы. Например, следующие строки содержат допустимые форматы даты и времени:

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

КОД локали также влияет на то, допустим ли формат строки для преобразования в значение даты и времени.

В случае VAR_DATEVALUEONLY значение времени задается как время 0 или полночь. В случае VAR_TIMEVALUEONLY значение даты устанавливается равным 0, то есть 30 декабря 1899.

Если строку не удалось преобразовать в значение даты-времени или произошло числовое переполнение, то состояние этого `COleDateTime` объекта недопустимо.

Дополнительные сведения о границах и реализации `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="coledatetimesetdate"></a><a name="setdate"></a> COleDateTime:: SetDate

Задает дату этого `COleDateTime` объекта.

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>Параметры

*неар*\
Указывает год для копирования в этот `COleDateTime` объект.

*нмонс*\
Указывает месяц для копирования в этот `COleDateTime` объект.

*nОшибка дня*\
Указывает день для копирования в этот `COleDateTime` объект.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если значение этого `COleDateTime` объекта успешно задано; в противном случае — 1. Это возвращаемое значение основано на `DateTimeStatus` типе перечисления. Дополнительные сведения см. в описании функции элемента [SetStatus](#setstatus) .

### <a name="remarks"></a>Примечания

Для даты заданы указанные значения. Время задано как время 0, полночь.

В следующей таблице приведены границы для значений параметров.

|Параметр|Bounds|
|---------------|------------|
|*неар*|100-9999|
|*нмонс*|1 - 12|
|*nОшибка дня*|0 - 31|

Если переполняется день месяца, он преобразуется в правильный день следующего месяца, а месяц и (или) год увеличивается соответственно. Значение дня, равное нулю, указывает последний день предыдущего месяца. Поведение аналогично поведению `SystemTimeToVariantTime` .

Если значение даты, заданное параметрами, недопустимо, состояние этого объекта равно `COleDateTime::invalid` . Чтобы проверить допустимость значения, следует использовать параметр "с [состоянием](#getstatus) " `DATE` и не следует рассчитывать на то, что значение [m_dt](#m_dt) останется неизменным.

Ниже приведены некоторые примеры значений дат.

|*неар*|*нмонс*|*nОшибка дня*|Значение|
|-------------|--------------|------------|-----------|
|2000|2|29|29 февраля 2000|
|1776|7|4|4 июля 1776|
|1925|4|35|35 апреля 1925 (Недопустимая дата)|
|10000|1|1|1 января 10000 (Недопустимая дата)|

Сведения о задании даты и времени см. в разделе [COleDateTime:: сетдатетиме](#setdatetime).

Сведения о функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [В час](#gethour)

- [GetMinute —](#getminute)

- [В секунду](#getsecond)

- [жетдайофвик](#getdayofweek)

- [жетдайофеар](#getdayofyear)

Дополнительные сведения о границах для `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

## <a name="coledatetimesetdatetime"></a><a name="setdatetime"></a> COleDateTime:: Сетдатетиме

Задает дату и время для этого `COleDateTime` объекта.

```
int SetDateTime(
    int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Параметры

*НЕАР*, *нмонс*, *nОшибка дня*, *nчас суток*, *nмин.*, *NSEC*<br/>
Указывает компоненты даты и времени, которые должны быть скопированы в этот `COleDateTime` объект.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если значение этого `COleDateTime` объекта успешно задано; в противном случае — 1. Это возвращаемое значение основано на `DateTimeStatus` типе перечисления. Дополнительные сведения см. в описании функции элемента [SetStatus](#setstatus) .

### <a name="remarks"></a>Примечания

В следующей таблице приведены границы для значений параметров.

|Параметр|Bounds|
|---------------|------------|
|*неар*|100-9999|
|*нмонс*|1 - 12|
|*nОшибка дня*|0 - 31|
|*Nчас суток*|0 - 23|
|*Nмин.*|0 - 59|
|*nSec*|0 - 59|

Если переполняется день месяца, он преобразуется в правильный день следующего месяца, а месяц и (или) год увеличивается соответственно. Значение дня, равное нулю, указывает последний день предыдущего месяца. Поведение аналогично [системтиметоварианттиме](/windows/win32/api/oleauto/nf-oleauto-systemtimetovarianttime).

Если значение даты или времени, указанное в параметрах, является недопустимым, состояние этого объекта задается как недопустимое, а значение этого объекта не изменяется.

Ниже приведены некоторые примеры значений времени.

|*Nчас суток*|*Nмин.*|*nSec*|Значение|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Недопустимо|
|9|60|0|Недопустимо|

Ниже приведены некоторые примеры значений дат.

|*неар*|*нмонс*|*nОшибка дня*|Значение|
|-------------|--------------|------------|-----------|
|1995|4|15|15 апреля 1995|
|1789|7|14|17 июля 1789|
|1925|2|30|Недопустимо|
|10000|1|1|Недопустимо|

Чтобы установить только дату, см. раздел [COleDateTime:: setDate](#setdate). Сведения о задании только времени см. в разделе [COleDateTime:: setTime](#settime).

Сведения о функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [В час](#gethour)

- [GetMinute —](#getminute)

- [В секунду](#getsecond)

- [жетдайофвик](#getdayofweek)

- [жетдайофеар](#getdayofyear)

Дополнительные сведения о границах для `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Пример

См. пример для получения [состояния](#getstatus).

## <a name="coledatetimesetstatus"></a><a name="setstatus"></a> COleDateTime:: SetStatus

Задает состояние этого `COleDateTime` объекта.

```cpp
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>Параметры

*status*<br/>
Новое значение состояния для этого `COleDateTime` объекта.

### <a name="remarks"></a>Примечания

Значение параметра *Status* определяется `DateTimeStatus` перечисляемым типом, который определен в `COleDateTime` классе. Дополнительные сведения см. в разделе [COleDateTime:: Status](#getstatus) .

> [!CAUTION]
> Эта функция предназначена для расширенных ситуаций программирования. Эта функция не изменяет данные в этом объекте. Чаще всего он используется для установки состояния в **значение NULL** или **недопустимо**. Оператор присваивания ([operator =](#operator_eq)) и [сетдатетиме](#setdatetime) устанавливают состояние объекта на основе исходных значений.

### <a name="example"></a>Пример

См. пример для получения [состояния](#getstatus).

## <a name="coledatetimesettime"></a><a name="settime"></a> COleDateTime:: SetTime

Задает время для этого `COleDateTime` объекта.

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Параметры

*nчас суток*, *nмин.*, *NSEC*<br/>
Указывает компоненты времени, которые должны быть скопированы в этот `COleDateTime` объект.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если значение этого `COleDateTime` объекта успешно задано; в противном случае — 1. Это возвращаемое значение основано на `DateTimeStatus` типе перечисления. Дополнительные сведения см. в описании функции элемента [SetStatus](#setstatus) .

### <a name="remarks"></a>Примечания

Для времени задаются указанные значения. Для даты задано значение Date 0, то есть 30 декабря 1899.

В следующей таблице приведены границы для значений параметров.

|Параметр|Bounds|
|---------------|------------|
|*Nчас суток*|0 - 23|
|*Nмин.*|0 - 59|
|*nSec*|0 - 59|

Если значение времени, заданное параметрами, является недопустимым, состояние этого объекта задается как недопустимое, а значение этого объекта не изменяется.

Ниже приведены некоторые примеры значений времени.

|*Nчас суток*|*Nмин.*|*nSec*|Значение|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Недопустимо|
|9|60|0|Недопустимо|

Сведения о задании даты и времени см. в разделе [COleDateTime:: сетдатетиме](#setdatetime).

Сведения о функциях элементов, которые запрашивают значение этого `COleDateTime` объекта, см. в следующих функциях элементов:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [В час](#gethour)

- [GetMinute —](#getminute)

- [В секунду](#getsecond)

- [жетдайофвик](#getdayofweek)

- [жетдайофеар](#getdayofyear)

Дополнительные сведения о границах для `COleDateTime` значений см. в статье [Дата и время: Поддержка автоматизации](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Пример

См. пример для [setDate](#setdate).

## <a name="see-also"></a>См. также раздел

[Класс COleVariant](../../mfc/reference/colevariant-class.md)<br/>
[Класс CTime](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[Класс CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
