---
title: Класс CTimeSpan
ms.date: 10/18/2018
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
ms.openlocfilehash: 0c13aa0d8f6c46db3b018283ab2a408a3f9531e1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832026"
---
# <a name="ctimespan-class"></a>Класс CTimeSpan

Количество времени, которое внутренне хранится как количество секунд в интервале времени.

## <a name="syntax"></a>Синтаксис

```
class CTimeSpan
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CTimeSpan:: CTimeSpan](#ctimespan)|Конструирует `CTimeSpan` объекты различными способами.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTimeSpan::Format](#format)|Преобразует `CTimeSpan` в отформатированную строку.|
|[CTimeSpan:: @ Days](#getdays)|Возвращает значение, представляющее количество полных дней в этом `CTimeSpan` .|
|[CTimeSpan:: ч](#gethours)|Возвращает значение, представляющее число часов в текущем дне (от-23 до 23).|
|[CTimeSpan:: полчаса](#getminutes)|Возвращает значение, представляющее количество минут в текущем часе (от-59 до 59).|
|[CTimeSpan:: в секунду](#getseconds)|Возвращает значение, представляющее количество секунд в текущей минуте (от-59 до 59).|
|[CTimeSpan:: TimeSpan](#gettimespan)|Возвращает значение `CTimeSpan` объекта.|
|[CTimeSpan:: Жеттоталхаурс](#gettotalhours)|Возвращает значение, представляющее общее количество полных часов в этом `CTimeSpan` .|
|[CTimeSpan:: Жеттоталминутес](#gettotalminutes)|Возвращает значение, представляющее общее количество полных минут в этом `CTimeSpan` .|
|[CTimeSpan:: Жеттоталсекондс](#gettotalseconds)|Возвращает значение, представляющее общее число полных секунд в этом `CTimeSpan` .|
|[CTimeSpan:: Serialize64](#serialize64)|Сериализует данные в архив или из него.|

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator +-](#operator_add_-)|Добавляет и вычитает `CTimeSpan` объекты.|
|[operator + =-=](#operator_add_eq_-_eq)|Добавляет и вычитает `CTimeSpan` объект из этого объекта `CTimeSpan` .|
|[operator = = < и т. д.](#ctimespan_comparison_operators)|Сравнивает два значения относительного времени.|

## <a name="remarks"></a>Примечания

`CTimeSpan` не имеет базового класса.

`CTimeSpan` функции преобразуют секунды в различные сочетания дней, часов, минут и секунд.

`CTimeSpan`Объект хранится в структуре **__time64_t** , которая составляет 8 байт.

Сопутствующий класс, [CTime](../../atl-mfc-shared/reference/ctime-class.md), представляет абсолютное время.

`CTime`Классы и `CTimeSpan` не предназначены для наследования. Поскольку нет виртуальных функций, размер обоих `CTime` `CTimeSpan` объектов и равен 8 байтам. Большинство функций членов являются встроенными.

Дополнительные сведения об использовании см `CTimeSpan` . в статьях [Дата и время](../../atl-mfc-shared/date-and-time.md), а также [Управление временем](../../c-runtime-library/time-management.md) в *справочнике по библиотеке времени выполнения*.

## <a name="requirements"></a>Требования

**Заголовок:** атлтиме.h

## <a name="ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a> Операторы сравнения CTimeSpan

Операторы сравнения.

```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Объект для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Эти операторы сравнивают два значения относительного времени. Они возвращают значение TRUE, если условие истинно; в противном случае — FALSE.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

## <a name="ctimespanctimespan"></a><a name="ctimespan"></a> CTimeSpan:: CTimeSpan

Конструирует `CTimeSpan` объекты различными способами.

```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(
    LONG lDays,
    int nHours,
    int nMins,
    int nSecs) throw();
```

### <a name="parameters"></a>Параметры

*тимеспансрк*<br/>
`CTimeSpan`Объект, который уже существует.

*time*<br/>
Значение времени **__time64_t** , представляющее количество секунд в интервале времени.

*лдайс*, *нхаурс*, *нминс*, *нсекс*<br/>
Дни, часы, минуты и секунды соответственно.

### <a name="remarks"></a>Примечания

Все эти конструкторы создают новый `CTimeSpan` объект, инициализируемый с указанным относительное время. Каждый конструктор описан ниже.

- `CTimeSpan( );` Конструирует неинициализированный `CTimeSpan` объект.

- `CTimeSpan( const CTimeSpan& );` Конструирует `CTimeSpan` объект из другого `CTimeSpan` значения.

- `CTimeSpan( __time64_t );` Конструирует `CTimeSpan` объект из типа **__time64_t** .

- `CTimeSpan( LONG, int, int, int );` Создает `CTimeSpan` объект из компонентов с каждым компонентом, ограниченным следующими диапазонами:

   |Компонент|Диапазон|
   |---------------|-----------|
   |*лдайс*|0 — 25 000 (приблизительно)|
   |*нхаурс*|0-23|
   |*нминс*|0-59|
   |*нсекс*|0-59|

Обратите внимание, что отладочная версия библиотека Microsoft Foundation Class утверждает, если один или несколько компонентов времени выходит за пределы диапазона. Перед вызовом вы обязаны проверить аргументы.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

## <a name="ctimespanformat"></a><a name="format"></a> CTimeSpan::Format

Формирует отформатированную строку, соответствующую этому `CTimeSpan` .

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>Параметры

*пформат*, *псзформат*<br/>
Строка форматирования, аналогичная `printf` строке форматирования. Коды форматирования, перед которыми стоит знак процента ( `%` ), заменяются соответствующим `CTimeSpan` компонентом. Другие символы в строке форматирования копируются без изменений в возвращаемую строку. Значение и значения кодов форматирования для `Format` приведены ниже.

- **% D** Всего дней в этом `CTimeSpan`

- **% H** Часов в текущем дне

- **% M** Минут за текущий час

- **% S** Секунд в текущей минуте

- **%%** Знак процента

*nID*<br/>
Идентификатор строки, определяющей этот формат.

### <a name="return-value"></a>Возвращаемое значение

`CString`Объект, содержащий отформатированное время.

### <a name="remarks"></a>Примечания

Отладочная версия библиотеки проверяет коды форматирования и утверждает, если код отсутствует в списке выше.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

## <a name="ctimespangetdays"></a><a name="getdays"></a> CTimeSpan:: @ Days

Возвращает значение, представляющее количество полных дней в этом `CTimeSpan` .

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число полных 24-часовых дней в интервале времени. Это значение может быть отрицательным, если временной диапазон является отрицательным.

### <a name="remarks"></a>Примечания

Обратите внимание, что переход на летнее время может привести `GetDays` к возврату потенциально неудивительного результата. Например, если действует ЛЕТНее время, `GetDays` выводится число дней между 1 апреля и 1 мая как 29, а не 30, поскольку один день в апреле сокращается на час и поэтому не считается полным днем.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

## <a name="ctimespangethours"></a><a name="gethours"></a> CTimeSpan:: ч

Возвращает значение, представляющее число часов в текущем дне (от-23 до 23).

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество часов в текущем дне. Диапазон — от-23 до 23.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

## <a name="ctimespangetminutes"></a><a name="getminutes"></a> CTimeSpan:: полчаса

Возвращает значение, представляющее количество минут в текущем часе (от-59 до 59).

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество минут в текущем часе. Диапазон значений — от-59 до 59.

### <a name="example"></a>Пример

См. пример для [работы с часами](#gethours).

## <a name="ctimespangetseconds"></a><a name="getseconds"></a> CTimeSpan:: в секунду

Возвращает значение, представляющее количество секунд в текущей минуте (от-59 до 59).

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество секунд в текущей минуте. Диапазон значений — от-59 до 59.

### <a name="example"></a>Пример

См. пример для [работы с часами](#gethours).

## <a name="ctimespangettimespan"></a><a name="gettimespan"></a> CTimeSpan:: TimeSpan

Возвращает значение `CTimeSpan` объекта.

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущее значение `CTimeSpan` объекта.

## <a name="ctimespangettotalhours"></a><a name="gettotalhours"></a> CTimeSpan:: Жеттоталхаурс

Возвращает значение, представляющее общее количество полных часов в этом `CTimeSpan` .

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает общее количество полных часов в этом `CTimeSpan` .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

## <a name="ctimespangettotalminutes"></a><a name="gettotalminutes"></a> CTimeSpan:: Жеттоталминутес

Возвращает значение, представляющее общее количество полных минут в этом `CTimeSpan` .

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает общее количество полных минут в этом `CTimeSpan` .

### <a name="example"></a>Пример

См. пример для [жеттоталхаурс](#gettotalhours).

## <a name="ctimespangettotalseconds"></a><a name="gettotalseconds"></a> CTimeSpan:: Жеттоталсекондс

Возвращает значение, представляющее общее число полных секунд в этом `CTimeSpan` .

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает общее число полных секунд в этом `CTimeSpan` .

### <a name="example"></a>Пример

См. пример для [жеттоталхаурс](#gettotalhours).

## <a name="ctimespanoperator---"></a><a name="operator_add_-"></a> CTimeSpan::operator+,-

Добавляет и вычитает `CTimeSpan` объекты.

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Значение, добавляемое в `CTimeSpan` объект.

### <a name="return-value"></a>Возвращаемое значение

`CTimeSpan`Объект, представляющий результат операции.

### <a name="remarks"></a>Примечания

Эти два оператора позволяют добавлять и вычитать `CTimeSpan` объекты друг за другом.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

## <a name="ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a> CTimeSpan::operator+=,-=

Добавляет и вычитает `CTimeSpan` объект из этого объекта `CTimeSpan` .

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*размещать*<br/>
Значение, добавляемое в `CTimeSpan` объект.

### <a name="return-value"></a>Возвращаемое значение

Обновленный `CTimeSpan` объект.

### <a name="remarks"></a>Примечания

Эти операторы позволяют добавлять и вычитать `CTimeSpan` объект из этого объекта `CTimeSpan` .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

## <a name="ctimespanserialize64"></a><a name="serialize64"></a> CTimeSpan:: Serialize64

> [!NOTE]
> Этот метод доступен только в проектах MFC.

Сериализует данные, связанные с переменной члена, в архив или из архива.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Параметры

*AR*<br/>
`CArchive`Объект, который требуется обновить.

### <a name="return-value"></a>Возвращаемое значение

Обновленный `CArchive` объект.

## <a name="see-also"></a>См. также раздел

[asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)<br/>
[_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)<br/>
[localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
