---
title: SQL. Настройка инструкции SQL набора записей (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- recordsets, SQL statements
- ODBC recordsets, SQL statements
- SQL statements, customizing
- SQL statements, recordset
- customizing SQL statements
- overriding, SQL statements
- SQL, opening recordsets
ms.assetid: 72293a08-cef2-4be2-aa1c-30565fcfbaf9
ms.openlocfilehash: 083d268d2b2f2eef072809b1afde9d6ea34f6996
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374516"
---
# <a name="sql-customizing-your-recordsets-sql-statement-odbc"></a>SQL. Настройка инструкции SQL набора записей (ODBC)

В этом разделе рассматриваются следующие вопросы.

- Как фреймворк строит заявление S'L

- Как переопределить выписку по S'L

> [!NOTE]
> Эта информация относится к классам ODBC библиотеки MFC. Если вы работаете с классами MFC DAO, см.

## <a name="sql-statement-construction"></a>Строительство заявления S'L

Ваш рекордный набор записей в первую очередь на выписке S'L **SELECT.** Когда вы объявляете свой класс с мастером, `GetDefaultSQL` он пишет передний вариант функции участника, которая выглядит примерно так (для класса recordset называется). `CAuthors`

```cpp
CString CAuthors::GetDefaultSQL()
{
    return "AUTHORS";
}
```

По умолчанию этот переопределение возвращает имя таблицы, указанное мастером. В примере имя таблицы — AUTHORS. При дальнейшем вызове функции `Open` участника `Open` записи строится окончательное заявление **SELECT** формы:

```
SELECT rfx-field-list FROM table-name [WHERE m_strFilter]
       [ORDER BY m_strSort]
```

где `table-name` получено путем вызова `GetDefaultSQL` и `rfx-field-list` получено от `DoFieldExchange`rfX функции звонки в . Это то, что вы получаете для оператора **SELECT,** если вы не замените его главной версией во время выполнения, хотя вы также можете изменить заявление по умолчанию с параметрами или фильтром.

> [!NOTE]
> Если вы указываете имя столбца, содержащее (или может содержать) пробелы, необходимо приложить имя в квадратные скобки. Например, название «Имя» должно быть «Первое имя».

Чтобы переопределить выписку **SELECT** по умолчанию, передай `Open`строку, содержащую полное заявление **SELECT** при вызове. Вместо того, чтобы строить собственную строку по умолчанию, в наборе рекордов используется строка, поставляемая. Если выписка о замене содержит оговорку `m_strFilter` **WHERE,** не укажите фильтр, так как у вас будет две оператора фильтра. Аналогичным образом, если в вашей заменяющей выписке `m_strSort` содержится оговорка **ORDER BY,** не укажите сортировку, чтобы у вас не было двух сортированных инструкций.

> [!NOTE]
> Если вы используете буквальные строки в фильтрах (или других частях оператора S'L), возможно, вам придется "цитировать" (приложить в указанные делимитемы) такие строки с DBMS-специфический буквальный приставку и буквальный символ суффикса (или символы).

Вы также можете столкнуться со специальными синтаксических требований для операций, таких как внешние соединения, в зависимости от вашего DBMS. Используйте функции ODBC для получения этой информации от драйвера для DBMS. Например, `::SQLGetTypeInfo` вызов для определенного типа `SQL_VARCHAR`данных, например, запрос агнизируете LITERAL_PREFIX и LITERAL_SUFFIX символов. Если вы пишете независимый код базы данных, [ODBC Programmer's Reference](/sql/odbc/reference/odbc-programmer-s-reference) [см.](/sql/odbc/reference/appendixes/appendix-c-sql-grammar)

Объект звукозаписи строит заявление S'L, которое он использует для выбора записей, если вы не проходите пользовательскую выписку s'L. Как это делается, зависит главным образом от значения, который `Open` вы проходите в параметре *lpszS'L* функции члена.

Общая форма выписки s'L **SELECT:**

```
SELECT [ALL | DISTINCT] column-list FROM table-list
    [WHERE search-condition][ORDER BY column-list [ASC | DESC]]
```

Один из способов добавить ключевое слово **DISTINCT** в заявление вашего рекордсета — вставить `DoFieldExchange`ключевое слово в первый вызов функции RFX. Пример:

```
...
    RFX_Text(pFX, "DISTINCT CourseID", m_strCourseID);
...
```

> [!NOTE]
> Используйте эту технику только с рекордным набором, открытым как только для чтения.

## <a name="overriding-the-sql-statement"></a>Отмена заявления СЗЛ

В следующей таблице показаны возможности для параметра *lpszS'L.* `Open` Случаи в таблице объясняются после таблицы.

**Параметр lpszS-L и результирующая строка S'L**

|Случай|Что вы проходите в lpszS'L|Полученная выписка SELECT|
|----------|------------------------------|------------------------------------|
|1|NULL|**Выберите** *RFX-поле-список* **из** названия *таблицы*<br /><br /> `CRecordset::Open`звонки, `GetDefaultSQL` чтобы получить имя стола. Результирующая строка является одним из `GetDefaultSQL` случаев 2 до 5, в зависимости от того, что возвращается.|
|2|Имя таблицы|**Выберите** *RFX-поле-список* **из** названия *таблицы*<br /><br /> Список полей взят из заявлений RFX в `DoFieldExchange`. Если `m_strFilter` `m_strSort` и не пусты, добавляет сярвые положения **WHERE** and/or **ORDER BY.**|
|3\*|Полное заявление **SELECT,** но без положения **WHERE** или **ORDER BY**|Как прошло. Если `m_strFilter` `m_strSort` и не пусты, добавляет сярвые положения **WHERE** and/or **ORDER BY.**|
|4\*|Полное заявление **SELECT** с оговоркой **WHERE** and/or **ORDER BY**|Как прошло. `m_strFilter`и/или `m_strSort` должны оставаться пустыми, или производятся два фильтра и/или сортировки.|
|5\*|Вызов на сохраненную процедуру|Как прошло.|

\*`m_nFields` должно быть меньше или равно числу столбцов, указанным в заявлении **SELECT.** Тип данных каждого столбца, указанный в отчете **SELECT,** должен быть таким же, как и тип данных соответствующего выходного столбца RFX.

### <a name="case-1---lpszsql--null"></a>Дело 1 lpszS'L - NULL

Выбор набора записей `GetDefaultSQL` зависит `CRecordset::Open` от того, что возвращается при вызове. Случаи 2 по 5 описывают возможные строки.

### <a name="case-2---lpszsql--a-table-name"></a>Дело 2 lpszS'L - Название таблицы

Запись использует обмен поля записи (RFX) для создания списка столбцов из имен столбцов, предоставленных в `DoFieldExchange`функциях RFX, в переопределение класса recordset. Если вы использовали мастер для объявления класса записей, этот случай имеет тот же результат, что и случай 1 (при условии, что вы передаете то же имя таблицы, указанное в мастере). Если вы не используете мастера для написания вашего класса, случай 2 — это самый простой способ построения оператора S'L.

В следующем примере построена выписка по S'L, которая выбирает записи из приложения базы данных MFC. Когда фреймворк вызывает функцию `GetDefaultSQL` участника, функция `SECTION`возвращает имя таблицы.

```cpp
CString CEnrollSet::GetDefaultSQL()
{
    return "SECTION";
}
```

Для получения имен столбцов для оператора S'L **SELECT** `DoFieldExchange` платформа вызывает функцию участника.

```cpp
void CEnrollSet::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Text(pFX, "CourseID", m_strCourseID);
    RFX_Text(pFX, "InstructorID", m_strInstructorID);
    RFX_Text(pFX, "RoomNo", m_strRoomNo);
    RFX_Text(pFX, "Schedule", m_strSchedule);
    RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

По завершении, выписка по S'L выглядит следующим образом:

```sql
SELECT CourseID, InstructorID, RoomNo, Schedule, SectionNo
    FROM SECTION
```

### <a name="case-3---lpszsql--a-selectfrom-statement"></a>Дело 3 lpszS'L - заявление SELECT/FROM

Вы указываете список столбцов вручную, а не полагаетесь на RFX, чтобы построить его автоматически. Вы можете сделать это, когда:

- Вы хотите указать ключевое слово **DISTINCT,** следующее за **SELECT.**

   Список столбцов должен соответствовать именам и типам `DoFieldExchange`столбцов в том же порядке, в каком они перечислены в.

- У вас есть основания вручную извлекать значения `::SQLGetData` столбца с помощью функции ODBC, а не полагаться на RFX для связывания и извлечения столбцов для вас.

   Например, может потребоваться разместить новые столбцы, добавленные клиентом приложения в таблицы баз данных после распространения приложения. Необходимо добавить дополнительные полевые данные, которые не были известны в то время, когда вы объявили класс с мастером.

   Список столбцов должен соответствовать именам и типам `DoFieldExchange`столбцов в том же порядке, в каком они перечислены в, а затем имена колонн, связанных вручную. Для получения дополнительной информации [см. Recordset: Динамически связывающие столбцы данных (ODBC).](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

- Вы хотите присоединиться к таблицам, указав несколько таблиц в пункте **FROM.**

   Для получения информации [Recordset: Performing a Join (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)и примера см.

### <a name="case-4---lpszsql--selectfrom-plus-where-andor-order-by"></a>Дело 4 lpszS'L - SELECT/FROM Plus WHERE and/or ORDER BY

Вы указываете все: список столбцов (на основе звонков `DoFieldExchange`RFX), список таблиц и содержимое пункта **WHERE** and/or ORDER **BY.** Если вы укажете свои положения **WHERE** and/or `m_strFilter` ORDER **BY** таким образом, не используйте и/или `m_strSort`.

### <a name="case-5---lpszsql--a-stored-procedure-call"></a>Дело 5 lpszS'L - Сохраненный вызов процедуры

Если вам необходимо вызвать заранее определенный запрос (например, сохраненную процедуру в базе данных Microsoft S'L Server), необходимо написать выписку **CALL** в строке, которая перешвеляется *в lpszS'L.* Мастера не поддерживают объявление класса записей для вызова заданного запроса. Не все предопределенные записи возврата запросов.

Если предопределенный запрос не возвращает записи, `CDatabase` можно `ExecuteSQL` использовать функцию участника напрямую. Для заданного запроса, который возвращает записи, необходимо также вручную написать вызовы RFX `DoFieldExchange` для любых столбцов, возвращающие процедуру. Вызовы RFX должны быть в том же порядке и возвращать те же типы, что и предопределенный запрос. Для получения дополнительной информации [см. Recordset: Объявление класса для предопределенного запроса (ODBC).](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)

## <a name="see-also"></a>См. также раздел

[SQL. Типы данных SQL и C++ (ODBC)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)<br/>
[SQL. Выполнение прямых вызовов SQL (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)
