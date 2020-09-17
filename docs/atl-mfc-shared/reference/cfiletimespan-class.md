---
title: Класс CFileTimeSpan
description: Класс «Активный шаблон» (ATL) и Microsoft Foundation Classes (MFC) CFileTimeSpan управляет временными интервалами в единицах FILETIME.
ms.date: 01/10/2020
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
ms.openlocfilehash: 87737ea1c778660a68510b484bcdfa3a4670e8ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317856"
---
# <a name="cfiletimespan-class"></a>Класс CFileTimeSpan

Этот класс предоставляет методы управления относительными значениями даты и времени, связанными с файлом.

## <a name="syntax"></a>Синтаксис

```cpp
class CFileTimeSpan
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Вызовите этот метод, чтобы `CFileTimeSpan` получить промежуток времени от объекта.|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Вызовите этот метод, чтобы `CFileTimeSpan` установить промежуток времени объекта.|

### <a name="public-operators"></a>Публичные операторы

|Имя|Описание|
|----------|-----------------|
|[CFileTimeSpan:оператор -](#operator_-)|Выполняет вычитание `CFileTimeSpan` объекта.|
|[CFileTimeSpan::оператор !](#operator_neq)|Проверяет неравенство двух объектов `CFileTimeSpan`.|
|[CFileTimeSpan::оператор](#operator_add)|Выполняет добавление на `CFileTimeSpan` объекте.|
|[CFileTimeSpan::оператор](#operator_add_eq)|Выполняет добавление на `CFileTimeSpan` объекте и присваивает результат текущему объекту.|
|[CFileTimeSpan::оператор&lt;](#operator_lt)|Сравнивает `CFileTimeSpan` два объекта, чтобы определить меньший.|
|[CFileTimeSpan::оператор&lt;=](#operator_lt_eq)|Сравнивает `CFileTimeSpan` два объекта для определения равенства или меньшего.|
|[CFileTimeSpan::оператор](#operator_eq)|Оператор назначения.|
|[CFileTimeSpan:оператор -](#operator_-_eq)|Выполняет вычитание `CFileTimeSpan` объекта и присваивает результат текущему объекту.|
|[CFileTimeSpan::оператор](#operator_eq_eq)|Сравнивает два объекта `CFileTimeSpan` на равенство.|
|[CFileTimeSpan::оператор&gt;](#operator_gt)|Сравнивает `CFileTimeSpan` два объекта для определения большего размера.|
|[CFileTimeSpan::оператор&gt;=](#operator_gt_eq)|Сравнивает `CFileTimeSpan` два объекта для определения равенства или большего.|

## <a name="remarks"></a>Примечания

Класс `CFileTimeSpan` предоставляет методы обработки относительных периодов времени в единицах, используемых файловой системой. Эти единицы часто используются в файловых операциях, например, когда файл был создан, последний доступ или последний измененный. Методы этого класса часто используются в сочетании с объектами [класса CFileTime.](../../atl-mfc-shared/reference/cfiletime-class.md)

## <a name="example"></a>Пример

Смотрите пример [Для CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).

## <a name="requirements"></a>Требования

**Заголовок:** atltime.h

## <a name="cfiletimespancfiletimespan"></a><a name="cfiletimespan"></a>CFileTimeSpan::CFileTimeSpan

Конструктор.

```cpp
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Существующий объект `CFileTimeSpan`.

*nSpan*\
Период времени в единицах FILETIME.

### <a name="remarks"></a>Примечания

Объект `CFileTimeSpan` может быть создан `CFileTimeSpan` с помощью существующего объекта или выражен в виде 64-битного значения в 100-наносекундных единицах FILETIME. Для получения дополнительной информации [см.](cfiletime-class.md) Конструктор по умолчанию устанавливает временной промежуток до 0.

## <a name="cfiletimespangettimespan"></a><a name="gettimespan"></a>CFileTimeSpan::GetTimeSpan

Вызовите этот метод, чтобы `CFileTimeSpan` получить промежуток времени от объекта.

```cpp
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает промежуток времени в 100-наносекундных единицАХ FILETIME. Для получения дополнительной информации [см.](cfiletime-class.md)

## <a name="cfiletimespanoperator--"></a><a name="operator_-"></a>CFileTimeSpan:оператор -

Выполняет вычитание `CFileTimeSpan` объекта.

```cpp
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Объект `CFileTimeSpan` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTimeSpan` объект, представляющий результат разницы между двумя промежутками времени.

## <a name="cfiletimespanoperator-"></a><a name="operator_neq"></a>CFileTimeSpan::оператор !

Проверяет неравенство двух объектов `CFileTimeSpan`.

```cpp
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если сравниваемый элемент `CFileTimeSpan` не равен объекту; в противном случае FALSE.

## <a name="cfiletimespanoperator-"></a><a name="operator_add"></a>CFileTimeSpan::оператор

Выполняет добавление на `CFileTimeSpan` объекте.

```cpp
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Объект `CFileTimeSpan` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает `CFileTimeSpan` объект, содержащий сумму двух промежутков времени.

## <a name="cfiletimespanoperator-"></a><a name="operator_add_eq"></a>CFileTimeSpan::оператор

Выполняет добавление на `CFileTimeSpan` объекте и присваивает результат текущему объекту.

```cpp
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Объект `CFileTimeSpan` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTimeSpan` объект, содержащий сумму двух промежутков времени.

## <a name="cfiletimespanoperator-lt"></a><a name="operator_lt"></a>CFileTimeSpan::оператор&lt;

Сравнивает `CFileTimeSpan` два объекта, чтобы определить меньший.

```cpp
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект меньше (т.е. представляет собой более короткий период времени), чем второй, в противном случае FALSE.

## <a name="cfiletimespanoperator-lt"></a><a name="operator_lt_eq"></a>CFileTimeSpan::оператор&lt;=

Сравнивает `CFileTimeSpan` два объекта для определения равенства или меньшего.

```cpp
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект меньше (т.е. представляет собой более короткий период времени) или равен второму, в противном случае FALSE.

## <a name="cfiletimespanoperator-"></a><a name="operator_eq"></a>CFileTimeSpan::оператор

Оператор назначения.

```cpp
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Объект `CFileTimeSpan` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTimeSpan` объект.

## <a name="cfiletimespanoperator--"></a><a name="operator_-_eq"></a>CFileTimeSpan:оператор -

Выполняет вычитание `CFileTimeSpan` объекта и присваивает результат текущему объекту.

```cpp
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Объект `CFileTimeSpan` .

### <a name="return-value"></a>Возвращаемое значение

Возвращает обновленный `CFileTimeSpan` объект.

## <a name="cfiletimespanoperator-"></a><a name="operator_eq_eq"></a>CFileTimeSpan::оператор

Сравнивает два объекта `CFileTimeSpan` на равенство.

```cpp
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если объекты равны, в противном случае FALSE.

## <a name="cfiletimespanoperator-gt"></a><a name="operator_gt"></a>CFileTimeSpan::оператор&gt;

Сравнивает `CFileTimeSpan` два объекта для определения большего размера.

```cpp
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект больше, чем (т.е. представляет собой более длительный период времени), чем второй, в противном случае FALSE.

## <a name="cfiletimespanoperator-gt"></a><a name="operator_gt_eq"></a>CFileTimeSpan::оператор&gt;=

Сравнивает `CFileTimeSpan` два объекта для определения равенства или большего.

```cpp
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Параметры

*Пролета*\
Сравниваемый объект `CFileTimeSpan`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если первый объект больше( то есть представляет собой более длительный период времени) или равен второму, в противном случае FALSE.

## <a name="cfiletimespansettimespan"></a><a name="settimespan"></a>CFileTimeSpan::SetTimeSpan

Вызовите этот метод, чтобы `CFileTimeSpan` установить промежуток времени объекта.

```cpp
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Параметры

*nSpan*\
Новое значение для промежуток времени в 100-наносекундных единицFILETIME. Для получения дополнительной информации [см.](cfiletime-class.md)

## <a name="see-also"></a>См. также раздел

[Filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime)\
[Класс CFileTime](cfiletime-class.md)\
[Иерархия диаграммы](../../mfc/hierarchy-chart.md)\
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
