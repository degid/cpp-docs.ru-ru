---
title: Класс CDBException
ms.date: 11/04/2016
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
ms.openlocfilehash: 1ab7daeb3af55c92985c951c632b1d4050681474
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321896"
---
# <a name="cdbexception-class"></a>Класс CDBException

Представляет условие исключения, поступающее от классов базы данных.

## <a name="syntax"></a>Синтаксис

```
class CDBException : public CException
```

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDBException::m_nRetCode](#m_nretcode)|Содержит код возврата Open Database Connectivity (ODBC) типа RETCODE.|
|[CDBException::m_strError](#m_strerror)|Содержит строку, описывающая ошибку в алфавитных терминах.|
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|Содержит строку, описывающую ошибку с точки зрения кодов ошибок, возвращенных ODBC.|

## <a name="remarks"></a>Примечания

Класс включает в себя два открытых члена данных, которые можно использовать для определения причины исключения или отображения текстового сообщения, описывающего исключение. `CDBException`объекты строятся и выбрасываются функциями членов классов баз данных.

> [!NOTE]
> Этот класс является одним из классов MFC Open Database Connectivity (ODBC). Если вместо этого вы используете новые классы доступа к данным (DAO), используйте [CDaoException.](../../mfc/reference/cdaoexception-class.md) Все названия классов DAO имеют "CDao" в качестве приставки. Для получения дополнительной информации смотрите статью [Обзор: Программирование базы данных](../../data/data-access-programming-mfc-atl.md).

Исключение составляют случаи ненормального выполнения, включающие условия вне контроля программы, такие как источник данных или ошибки ввихателей/осе. Ошибки, которые можно ожидать увидеть в обычном процессе выполнения программы, обычно не считаются исключениями.

Эти объекты можно получить в рамках выражения **CATCH.** Вы также `CDBException` можете бросать объекты `AfxThrowDBException` из собственного кода с глобальной функцией.

Для получения дополнительной информации об `CDBException` обработке исключений в целом или [Exceptions: Database Exceptions](../../mfc/exceptions-database-exceptions.md)об объектах см. [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="cdbexceptionm_nretcode"></a><a name="m_nretcode"></a>CDBException::m_nRetCode

Содержит код ошибки ODBC типа RETCODE, возвращенный функцией интерфейса программирования приложений ODBC (API).

### <a name="remarks"></a>Примечания

Этот тип включает в себя коды, установленные ODBC, и AFX_SQL-фиксированные коды, определенные классами баз данных. Для `CDBException`этого участника будет содержаться одно из следующих значений:

- AFX_SQL_ERROR_API_CONFORMANCE Драйвер для `CDatabase::OpenEx` `CDatabase::Open` вызова или вызова не соответствует требуемому уровню соответствия ODBC API 1 (SQL_OAC_LEVEL1).

- AFX_SQL_ERROR_CONNECT_FAIL подключение к источнику данных не удалось. Вы передали`CDatabase` указатель NULL конструктору записей и последующую `GetDefaultConnect` попытку создать соединение на основе неудачного.

- AFX_SQL_ERROR_DATA_TRUNCATED Вы запросили больше данных, чем предоставили для хранения. Для получения информации об `CString` увеличении предоставляемого хранилища данных для типов или `CByteArray` типов данных `nMaxLength` [RFX_Binary](record-field-exchange-functions.md#rfx_binary) [RFX_Text,](record-field-exchange-functions.md#rfx_text) см.

- AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED Звонок `CRecordset::Open` на запрос динасета не удалось. Dynasets не поддерживаются водителем.

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST Вы пытались открыть таблицу (или то, что вы дали, не может быть идентифицировано как вызов процедуры или `DoFieldExchange` заявление **SELECT),** но в переопределениех нет столбцов, идентифицированных в вызовах функции обмена полями записи (RFX).

- AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH Тип функции RFX `DoFieldExchange` в переопределениене не совместим с типом данных столбца в наборе записей.

- AFX_SQL_ERROR_ILLEGAL_MODE Вы `CRecordset::Update` позвонили `CRecordset::AddNew` `CRecordset::Edit`без предварительного вызова или .

- AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED Ваш запрос на блокировку записей для обновления не может быть выполнен, поскольку ваш драйвер ODBC не поддерживает блокировку.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED Вы `CRecordset::Update` `Delete` позвонили или для таблицы без уникального ключа и изменили несколько записей.

- AFX_SQL_ERROR_NO_CURRENT_RECORD Вы пытались отсеить или удалить ранее удаленную запись. Вы должны прокрутить новую текущую запись после удаления.

- AFX_SQL_ERROR_NO_POSITIONED_UPDATES Ваш запрос на dynaset не может быть выполнен, потому что ваш драйвер ODBC не поддерживает позиционированные обновления.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED Вы `CRecordset::Update` `Delete`позвонили или , но когда операция началась запись больше не может быть найдено.

- AFX_SQL_ERROR_ODBC_LOAD_FAILED Попытка загрузить ODBC. DLL не удалось; Windows не могла найти или не могла загрузить этот DLL. Эта ошибка является фатальной.

- AFX_SQL_ERROR_ODBC_V2_REQUIRED Ваш запрос на dynaset не может быть выполнен, потому что требуется драйвер ODBC уровня 2.

- AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY Попытка прокрутки не увенчалась успехом, поскольку источник данных не поддерживает обратную прокрутку.

- AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED вызов `CRecordset::Open` запроса моментального снимка не удалось. Снимки не поддерживаются драйвером. (Это должно произойти только тогда, когда библиотека курсора ODBC ODBCCURS. DLL нет.)

- AFX_SQL_ERROR_SQL_CONFORMANCE Драйвер для `CDatabase::OpenEx` `CDatabase::Open` вызова или вызова не соответствует требуемому уровню соответствия ODBC S'L "Минимальное" (SQL_OSC_MINIMUM).

- AFX_SQL_ERROR_SQL_NO_TOTAL драйвер ODBC не смог указать `CLongBinary` общий размер значения данных. Операция, вероятно, не удалось, потому что глобальный блок памяти не может быть предварительно распределены.

- AFX_SQL_ERROR_RECORDSET_READONLY Вы пытались обновить набор записей только для чтения, или источник данных читается только для чтения. Операции обновления не могут выполняться с `CDatabase` помощью набора записей или объекта, с ним он связан.

- SQL_ERROR функция не сработала. Сообщение об ошибке, возвращенное функцией `SQLError` ODBC, хранится в члене `m_strError` данных.

- SQL_INVALID_HANDLE функция не сработала из-за недействительной ручки среды, ручки соединения или ручки оператора. Это указывает на ошибку программирования. Дополнительная информация от функции `SQLError`ODBC отсутствует.

Коды, закрепленные на sL,s, определяются ODBC. Коды AFX-фиксированные определены в AFXDB. H, найдено в МФЦ-БИТЕ.

## <a name="cdbexceptionm_strerror"></a><a name="m_strerror"></a>CDBException::m_strError

Содержит строку, описывающую ошибку, вызвавшие исключение.

### <a name="remarks"></a>Примечания

Строка описывает ошибку в алфавитных терминах. Для получения более подробной `m_strStateNativeOrigin`информации и примера см.

## <a name="cdbexceptionm_strstatenativeorigin"></a><a name="m_strstatenativeorigin"></a>CDBException::m_strStateNativeOrigin

Содержит строку, описывающую ошибку, вызвавшие исключение.

### <a name="remarks"></a>Примечания

Строка имеет форму "State:%s,Native:%ld,Origin:%s", где коды формата, в порядке, заменяются значениями, которые описывают:

- Строка с нулевой завершенной строкой, содержащей код ошибки из пяти символов, возвращенный в параметре *szSqlState* функции `SQLError`ODBC. Значения S'LSTATE перечислены в приложении A, [коды ошибок ODBC](/sql/odbc/reference/appendixes/appendix-a-odbc-error-codes), в *Справке программиста ODBC*. Пример: "S0022".

- Исходный код ошибки, специфичный для источника данных, возвращается в параметр *pfNativeError* функции. `SQLError` Пример: 207.

- Текст сообщения об ошибке вернулся в параметр *szErrorMsg* функции. `SQLError` Это сообщение состоит из нескольких имен в скобках. Поскольку ошибка передается от источника пользователю, каждый компонент ODBC (источник данных, драйвер, менеджер драйвера) придает свое собственное имя. Эта информация помогает определить происхождение ошибки. Пример: «Майкрософт» (Водитель сервера ODBC S'L) (S'L Server)

Рамка интерпретирует строку ошибки и помещает ее компоненты в; `m_strStateNativeOrigin` если `m_strStateNativeOrigin` содержит информацию для более чем одной ошибки, ошибки разделены новыми строками. Платформа помещает алфавитный текст ошибки в `m_strError`.

Для получения дополнительной информации о кодах, используемых для создания *ODBC Programmer's Reference*этой строки, см. [SQLError](/sql/odbc/reference/syntax/sqlerror-function)

### <a name="example"></a>Пример

От ODBC: "State:S0022,Родной:207,Origin:\[Microsoft"\[ODBC\[S'L Драйвер сервера S'L Server " Недействительный столбец "ColName""

В `m_strStateNativeOrigin`: "Государство:S0022,Родной:207,Происхождение:\[Microsoft"\[ODBC\[S'L Драйвер сервера S'L "

В `m_strError`: "Недействительный столбец имя 'ColName'"

## <a name="see-also"></a>См. также раздел

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Класс CFieldExchange](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::Обновление](../../mfc/reference/crecordset-class.md#update)<br/>
[CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)
