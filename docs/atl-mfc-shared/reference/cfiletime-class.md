---
title: Класс CFileTime
ms.date: 10/18/2018
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
ms.openlocfilehash: fd19d941365c7772363417ce3e9225bd9b0300b2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748837"
---
# <a name="cfiletime-class"></a>Класс CFileTime

Этот класс предоставляет методы управления значениями даты и времени, связанными с файлом.

## <a name="syntax"></a>Синтаксис

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFileTime::CFileTime](#cfiletime)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFileTime::GetCurrentTime](#getcurrenttime)|Вызовите эту статическую `CFileTime` функцию, чтобы получить объект, представляющий текущую дату и время системы.|
|[CFileTime::GetTime](#gettime)|Вызовите этот метод, чтобы `CFileTime` получить время от объекта.|
|[CFileTime:LocalToUTC](#localtoutc)|Вызовите этот метод для преобразования локального времени файла в время файла на основе скоординированного универсального времени (UTC).|
|[CFileTime::SetTime](#settime)|Вызовите этот метод, чтобы установить дату и время, хранящееся объектом. `CFileTime`|
|[CFileTime::UTCtoLocal](#utctolocal)|Вызовите этот метод для преобразования времени на основе скоординированного универсального времени (UTC) в локальное время файла.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CFileTime::оператор -](#operator_-)|Этот оператор используется для выполнения вычитания объекта `CFileTime` или `CFileTimeSpan` объекта.|
|[CFileTime::оператор !](#operator_neq)|Этот оператор сравнивает два `CFileTime` объекта для неравенства.|
|[CFileTime::оператор](#operator_add)|Этот оператор используется для сложения объекта `CFileTimeSpan`.|
|[CFileTime::оператор](#operator_add_eq)|Этот оператор используется для сложения объекта `CFileTimeSpan` и назначения ему результата.|
|[CFileTime::оператор&lt;](#operator_lt)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить меньший из них.|
|[CFileTime::оператор&lt;=](#operator_lt_eq)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или меньший из них.|
|[CFileTime::оператор](#operator_eq)|Оператор назначения.|
|[CFileTime:оператор -](#operator_-_eq)|Этот оператор используется для выполнения вычитания `CFileTimeSpan` объекта и присваивая результат текущему объекту.|
|[CFileTime::оператор](#operator_eq_eq)|Этот оператор сравнивает два объекта `CFileTime` на равенство.|
|[CFileTime::оператор&gt;](#operator_gt)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить больший из них.|
|[CFileTime::оператор&gt;=](#operator_gt_eq)|Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или больший из них.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[CFileTime::Day](#day)|Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют один день.|
|[CFileTime::Hour](#hour)|Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют один час.|
|[CFileTime:: Миллисекунда](#millisecond)|Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют одну миллисекунду.|
|[CFileTime::Минута](#minute)|Статический участник данных, храпротивший число 100-наносекундных интервалов, которые составляют одну минуту.|
|[CFileTime::Второй](#second)|Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют одну секунду.|
|[CFileTime::Неделя](#week)|Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют одну неделю.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет методы управления значениями даты и времени, связанными с созданием, доступом и модификацией файлов. Методы и данные этого класса часто `CFileTimeSpan` используются в сочетании с объектами, которые имеют дело с относительными значениями времени.

Значение даты и времени сохраняется в виде 64-битного значения, представляющего число интервалов в 100 наносекунд с 1 января 1601 года. Это координированный универсальный формат времени (UTC).

Для упрощения расчетов предоставляются следующие статические переменные Const member:

|Переменная-член|Количество 100-наносекундных интервалов|
|---------------------|-----------------------------------------|
|Миллисекунда|10 000|
|Секунда|Миллисекунда \* 1000|
|Минута|Второй \* 60|
|Час|Минута \* 60|
|День|Час \* 24|
|Неделя|День \* 7|

**Заметка** Не все файловые системы могут записывать создание и последнее время доступа, и не все файловые системы записывают их одинаково. Например, в файловой системе Windows NT FAT время создания имеет разрешение 10 миллисекунд, время записи имеет разрешение 2 секунды, а время доступа имеет разрешение 1 день (дата доступа). На NTFS время доступа имеет разрешение 1 час. Кроме того, FAT записывает время на диске по местному времени, но NTFS записывает время на диске в UTC. Для получения дополнительной информации [см.](/windows/win32/SysInfo/file-times)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`FILETIME`

`CFileTime`

## <a name="requirements"></a>Требования

**Заголовок:** atltime.h

## <a name="cfiletimecfiletime"></a><a name="cfiletime"></a>CFileTime::CFileTime

Конструктор.

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Параметры

*Метрах*<br/>
Структура [FILETIME.](/windows/win32/api/minwinbase/ns-minwinbase-filetime)

*nВремя*<br/>
Дата и время, выраженные как 64-битное значение.

### <a name="remarks"></a>Примечания

Объект `CFileTime` может быть создан с использованием `FILETIME` существующей даты и времени из структуры или выражен как 64-битное значение (в локальных или скоординированных форматах времени Universal Time (UTC). Конструктор по умолчанию устанавливает время до 0.

## <a name="cfiletimeday"></a><a name="day"></a>CFileTime::Day

Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют один день.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>Пример

Смотрите пример [Для CFileTime::Millisecond](#millisecond).

## <a name="cfiletimegetcurrenttime"></a><a name="getcurrenttime"></a>CFileTime::GetCurrentTime

Вызовите эту статическую `CFileTime` функцию, чтобы получить объект, представляющий текущую дату и время системы.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущую дату и время системы в формате Скоординированное универсальное время (UTC).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

## <a name="cfiletimegettime"></a><a name="gettime"></a>CFileTime::GetTime

Вызовите этот метод, чтобы `CFileTime` получить время от объекта.

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дату и время в виде 64-битного номера, которое может быть в локальном или скоординированном формате Universal Time (UTC).

## <a name="cfiletimehour"></a><a name="hour"></a>CFileTime::Hour

Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют один час.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>Пример

Смотрите пример [Для CFileTime::Millisecond](#millisecond).

## <a name="cfiletimelocaltoutc"></a><a name="localtoutc"></a>CFileTime:LocalToUTC

Вызовите этот метод для преобразования локального времени файла в время файла на основе скоординированного универсального времени (UTC).

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTime` объект, содержащий время в формате UTC.

### <a name="example"></a>Пример

Смотрите пример [Для CFileTime::UTCToLocal](#utctolocal).

## <a name="cfiletimemillisecond"></a><a name="millisecond"></a>CFileTime:: Миллисекунда

Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют одну миллисекунду.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

## <a name="cfiletimeminute"></a><a name="minute"></a>CFileTime::Минута

Статический участник данных, храпротивший число 100-наносекундных интервалов, которые составляют одну минуту.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>Пример

Смотрите пример [Для CFileTime::Millisecond](#millisecond).

## <a name="cfiletimeoperator--"></a><a name="operator_-"></a>CFileTime::оператор -

Этот оператор используется для выполнения вычитания объекта `CFileTime` или `CFileTimeSpan` объекта.

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*<br/>
Объект `CFileTimeSpan` .

*Метрах*<br/>
Объект `CFileTime` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTime` объект или `CFileTimeSpan` объект, представляющий результат разницы во времени между двумя объектами.

## <a name="cfiletimeoperator-"></a><a name="operator_neq"></a>CFileTime::оператор !

Этот оператор сравнивает два `CFileTime` объекта для неравенства.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*Метрах*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если сравниваемый `CFileTime` элемент не равен объекту, в противном случае FALSE.

## <a name="cfiletimeoperator-"></a><a name="operator_add"></a>CFileTime::оператор

Этот оператор используется для сложения объекта `CFileTimeSpan`.

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*<br/>
Объект `CFileTimeSpan` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTime` объект, представляющий результат исходного времени плюс относительное время.

## <a name="cfiletimeoperator-"></a><a name="operator_add_eq"></a>CFileTime::оператор

Этот оператор используется для сложения объекта `CFileTimeSpan` и назначения ему результата.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*Пролета*<br/>
Объект `CFileTimeSpan` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTime` объект, представляющий результат исходного времени плюс относительное время.

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt"></a>CFileTime::оператор&lt;

Этот оператор сравнивает два объекта `CFileTime`, чтобы определить меньший из них.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*Метрах*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект меньше (раньше во времени), чем второй, FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt_eq"></a>CFileTime::оператор&lt;=

Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или меньший из них.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*Метрах*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект меньше (раньше во времени) или равен второму, в противном случае FALSE.

## <a name="cfiletimeoperator-"></a><a name="operator_eq"></a>CFileTime::оператор

Оператор назначения.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>Параметры

*Метрах*<br/>
Объект, `CFileTime` содержащий новое время и дату.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTime` объект.

## <a name="cfiletimeoperator--"></a><a name="operator_-_eq"></a>CFileTime:оператор -

Этот оператор используется для выполнения вычитания `CFileTimeSpan` объекта и присваивая результат текущему объекту.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*Пролета*<br/>
Объект, `CFileTimeSpan` содержащий относительное время для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTime` объект.

## <a name="cfiletimeoperator-"></a><a name="operator_eq_eq"></a>CFileTime::оператор

Этот оператор сравнивает два объекта `CFileTime` на равенство.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*Метрах*<br/>
Объект `CFileTime`, подлежащий сравнению.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если объекты равны, в противном случае FALSE.

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt"></a>CFileTime::оператор&gt;

Этот оператор сравнивает два объекта `CFileTime`, чтобы определить больший из них.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*Метрах*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект больше, чем (позже во времени), чем второй, в противном случае FALSE.

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt_eq"></a>CFileTime::оператор&gt;=

Этот оператор сравнивает два объекта `CFileTime`, чтобы определить равенство или больший из них.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Параметры

*Метрах*<br/>
Сравниваемый объект `CFileTime`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект больше (позже во времени) или равен второму, в противном случае FALSE.

## <a name="cfiletimesecond"></a><a name="second"></a>CFileTime::Второй

Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют один день.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>Пример

Смотрите пример [Для CFileTime::Millisecond](#millisecond).

## <a name="cfiletimesettime"></a><a name="settime"></a>CFileTime::SetTime

Вызовите этот метод, чтобы установить дату и время, хранящееся объектом. `CFileTime`

```cpp
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Параметры

*nВремя*<br/>
64-битное значение, представляющее дату и время, в локальном или скоординированном формате Universal Time (UTC).

## <a name="cfiletimeutctolocal"></a><a name="utctolocal"></a>CFileTime::UTCtoLocal

Вызовите этот метод для преобразования времени на основе скоординированного универсального времени (UTC) в локальное время файла.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTime` объект, содержащий время в локальном формате времени файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

## <a name="cfiletimeweek"></a><a name="week"></a>CFileTime::Неделя

Статический участник данных, храпротягивающих число 100-наносекундных интервалов, которые составляют одну неделю.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>Пример

Смотрите пример [Для CFileTime::Millisecond](#millisecond).

## <a name="see-also"></a>См. также раздел

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[Класс CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
