---
title: Класс CRecordset
ms.date: 11/04/2016
f1_keywords:
- CRecordset
- AFXDB/CRecordset
- AFXDB/CRecordset::CRecordset
- AFXDB/CRecordset::AddNew
- AFXDB/CRecordset::CanAppend
- AFXDB/CRecordset::CanBookmark
- AFXDB/CRecordset::Cancel
- AFXDB/CRecordset::CancelUpdate
- AFXDB/CRecordset::CanRestart
- AFXDB/CRecordset::CanScroll
- AFXDB/CRecordset::CanTransact
- AFXDB/CRecordset::CanUpdate
- AFXDB/CRecordset::CheckRowsetError
- AFXDB/CRecordset::Close
- AFXDB/CRecordset::Delete
- AFXDB/CRecordset::DoBulkFieldExchange
- AFXDB/CRecordset::DoFieldExchange
- AFXDB/CRecordset::Edit
- AFXDB/CRecordset::FlushResultSet
- AFXDB/CRecordset::GetBookmark
- AFXDB/CRecordset::GetDefaultConnect
- AFXDB/CRecordset::GetDefaultSQL
- AFXDB/CRecordset::GetFieldValue
- AFXDB/CRecordset::GetODBCFieldCount
- AFXDB/CRecordset::GetODBCFieldInfo
- AFXDB/CRecordset::GetRecordCount
- AFXDB/CRecordset::GetRowsetSize
- AFXDB/CRecordset::GetRowsFetched
- AFXDB/CRecordset::GetRowStatus
- AFXDB/CRecordset::GetSQL
- AFXDB/CRecordset::GetStatus
- AFXDB/CRecordset::GetTableName
- AFXDB/CRecordset::IsBOF
- AFXDB/CRecordset::IsDeleted
- AFXDB/CRecordset::IsEOF
- AFXDB/CRecordset::IsFieldDirty
- AFXDB/CRecordset::IsFieldNull
- AFXDB/CRecordset::IsFieldNullable
- AFXDB/CRecordset::IsOpen
- AFXDB/CRecordset::Move
- AFXDB/CRecordset::MoveFirst
- AFXDB/CRecordset::MoveLast
- AFXDB/CRecordset::MoveNext
- AFXDB/CRecordset::MovePrev
- AFXDB/CRecordset::OnSetOptions
- AFXDB/CRecordset::OnSetUpdateOptions
- AFXDB/CRecordset::Open
- AFXDB/CRecordset::RefreshRowset
- AFXDB/CRecordset::Requery
- AFXDB/CRecordset::SetAbsolutePosition
- AFXDB/CRecordset::SetBookmark
- AFXDB/CRecordset::SetFieldDirty
- AFXDB/CRecordset::SetFieldNull
- AFXDB/CRecordset::SetLockingMode
- AFXDB/CRecordset::SetParamNull
- AFXDB/CRecordset::SetRowsetCursorPosition
- AFXDB/CRecordset::SetRowsetSize
- AFXDB/CRecordset::Update
- AFXDB/CRecordset::m_hstmt
- AFXDB/CRecordset::m_nFields
- AFXDB/CRecordset::m_nParams
- AFXDB/CRecordset::m_pDatabase
- AFXDB/CRecordset::m_strFilter
- AFXDB/CRecordset::m_strSort
helpviewer_keywords:
- CRecordset [MFC], CRecordset
- CRecordset [MFC], AddNew
- CRecordset [MFC], CanAppend
- CRecordset [MFC], CanBookmark
- CRecordset [MFC], Cancel
- CRecordset [MFC], CancelUpdate
- CRecordset [MFC], CanRestart
- CRecordset [MFC], CanScroll
- CRecordset [MFC], CanTransact
- CRecordset [MFC], CanUpdate
- CRecordset [MFC], CheckRowsetError
- CRecordset [MFC], Close
- CRecordset [MFC], Delete
- CRecordset [MFC], DoBulkFieldExchange
- CRecordset [MFC], DoFieldExchange
- CRecordset [MFC], Edit
- CRecordset [MFC], FlushResultSet
- CRecordset [MFC], GetBookmark
- CRecordset [MFC], GetDefaultConnect
- CRecordset [MFC], GetDefaultSQL
- CRecordset [MFC], GetFieldValue
- CRecordset [MFC], GetODBCFieldCount
- CRecordset [MFC], GetODBCFieldInfo
- CRecordset [MFC], GetRecordCount
- CRecordset [MFC], GetRowsetSize
- CRecordset [MFC], GetRowsFetched
- CRecordset [MFC], GetRowStatus
- CRecordset [MFC], GetSQL
- CRecordset [MFC], GetStatus
- CRecordset [MFC], GetTableName
- CRecordset [MFC], IsBOF
- CRecordset [MFC], IsDeleted
- CRecordset [MFC], IsEOF
- CRecordset [MFC], IsFieldDirty
- CRecordset [MFC], IsFieldNull
- CRecordset [MFC], IsFieldNullable
- CRecordset [MFC], IsOpen
- CRecordset [MFC], Move
- CRecordset [MFC], MoveFirst
- CRecordset [MFC], MoveLast
- CRecordset [MFC], MoveNext
- CRecordset [MFC], MovePrev
- CRecordset [MFC], OnSetOptions
- CRecordset [MFC], OnSetUpdateOptions
- CRecordset [MFC], Open
- CRecordset [MFC], RefreshRowset
- CRecordset [MFC], Requery
- CRecordset [MFC], SetAbsolutePosition
- CRecordset [MFC], SetBookmark
- CRecordset [MFC], SetFieldDirty
- CRecordset [MFC], SetFieldNull
- CRecordset [MFC], SetLockingMode
- CRecordset [MFC], SetParamNull
- CRecordset [MFC], SetRowsetCursorPosition
- CRecordset [MFC], SetRowsetSize
- CRecordset [MFC], Update
- CRecordset [MFC], m_hstmt
- CRecordset [MFC], m_nFields
- CRecordset [MFC], m_nParams
- CRecordset [MFC], m_pDatabase
- CRecordset [MFC], m_strFilter
- CRecordset [MFC], m_strSort
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
ms.openlocfilehash: d00764205b3b81e9f01dbe53d0c67372ebb2532e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219629"
---
# <a name="crecordset-class"></a>Класс CRecordset

Представляет набор записей, выбранных из источника данных.

## <a name="syntax"></a>Синтаксис

```
class CRecordset : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRecordset:: CRecordset](#crecordset)|Формирует объект `CRecordset`. Производный класс должен предоставить конструктор, который вызывает этот метод.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRecordset:: AddNew](#addnew)|Подготовка к добавлению новой записи. Вызовите метод, `Update` чтобы завершить добавление.|
|[CRecordset:: Канаппенд](#canappend)|Возвращает ненулевое значение, если новые записи можно добавить в набор записей с помощью `AddNew` функции члена.|
|[CRecordset:: Канбукмарк](#canbookmark)|Возвращает ненулевое значение, если набор записей поддерживает закладки.|
|[CRecordset:: Cancel](#cancel)|Отменяет асинхронную операцию или процесс из второго потока.|
|[CRecordset:: CancelUpdate](#cancelupdate)|Отменяет все ожидающие обновления из-за `AddNew` `Edit` операции или.|
|[CRecordset:: Канрестарт](#canrestart)|Возвращает ненулевое значение `Requery` , если метод может быть вызван для повторного выполнения запроса набора записей.|
|[CRecordset:: Канскролл](#canscroll)|Возвращает ненулевое значение, если можно выполнить прокрутку записей.|
|[CRecordset:: Кантрансакт](#cantransact)|Возвращает ненулевое значение, если источник данных поддерживает транзакции.|
|[CRecordset:: Канупдате](#canupdate)|Возвращает ненулевое значение, если набор записей может быть обновлен (можно добавлять, обновлять или удалять записи).|
|[CRecordset:: Чеккровсетеррор](#checkrowseterror)|Вызывается для обработке ошибок, созданных во время выборки записей.|
|[CRecordset:: Close](#close)|Закрывает набор записей и связанный с ним ХСТМТ ODBC.|
|[CRecordset::D удалить](#delete)|Удаляет текущую запись из набора записей. После удаления необходимо явно прокрутить на другую запись.|
|[CRecordset::D Обулкфиелдексчанже](#dobulkfieldexchange)|Вызывается для обмена массовыми строками данных из источника данных с набором записей. Реализует блочный обмен полей записей (групповой RFX).|
|[CRecordset::D Офиелдексчанже](#dofieldexchange)|Вызывается для обмена данными (в обоих направлениях) между элементами данных поля набора записей и соответствующей записью в источнике данных. Реализует обмен полями записей (RFX).|
|[CRecordset:: Edit](#edit)|Подготавливает изменения к текущей записи. Вызовите, `Update` чтобы завершить изменение.|
|[CRecordset:: Флушресултсет](#flushresultset)|Возвращает ненулевое значение, если для получения другого результирующего набора используется предопределенный запрос.|
|[CRecordset:: onbookmark](#getbookmark)|Присваивает значение закладки записи объекту параметра.|
|[CRecordset:: Жетдефаултконнект](#getdefaultconnect)|Вызывается для получения строки подключения по умолчанию.|
|[CRecordset:: GetDefaultSQL](#getdefaultsql)|Вызывается для получения строки SQL по умолчанию для выполнения.|
|[CRecordset:: GetFieldValue](#getfieldvalue)|Возвращает значение поля в наборе записей.|
|[CRecordset:: Жетодбкфиелдкаунт](#getodbcfieldcount)|Возвращает количество полей в наборе записей.|
|[CRecordset:: Жетодбкфиелдинфо](#getodbcfieldinfo)|Возвращает определенные виды информации о полях в наборе записей.|
|[CRecordset:: Жетрекордкаунт](#getrecordcount)|Возвращает количество записей в наборе записей.|
|[CRecordset:: Жетровсетсизе](#getrowsetsize)|Возвращает количество записей, которые требуется получить во время одной выборки.|
|[CRecordset:: Жетровсфетчед](#getrowsfetched)|Возвращает фактическое число строк, полученных во время выборки.|
|[CRecordset:: Жетровстатус](#getrowstatus)|Возвращает состояние строки после выборки.|
|[CRecordset:: Жетскл](#getsql)|Возвращает строку SQL, используемую для выбора записей для набора записей.|
|[CRecordset::/Status](#getstatus)|Возвращает состояние набора записей: индекс текущей записи и значение, указывающее, получено ли конечное количество записей.|
|[CRecordset:: имя_таблицы](#gettablename)|Возвращает имя таблицы, на которой основан набор записей.|
|[CRecordset:: Исбоф](#isbof)|Возвращает ненулевое значение, если набор записей был помещен перед первой записью. Отсутствует текущая запись.|
|[CRecordset:: isDeleted](#isdeleted)|Возвращает ненулевое значение, если набор записей расположен на удаленной записи.|
|[CRecordset:: Исеоф](#iseof)|Возвращает ненулевое значение, если набор записей был помещен после последней записи. Отсутствует текущая запись.|
|[CRecordset:: Исфиелддирти](#isfielddirty)|Возвращает ненулевое значение, если указанное поле в текущей записи было изменено.|
|[CRecordset:: Исфиелднулл](#isfieldnull)|Возвращает ненулевое значение, если указанное поле в текущей записи имеет значение null (не имеет значения).|
|[CRecordset:: Исфиелднуллабле](#isfieldnullable)|Возвращает ненулевое значение, если указанное поле в текущей записи может быть установлено в NULL (без значения).|
|[CRecordset:: OnOpen](#isopen)|Возвращает ненулевое значение `Open` , если метод был вызван ранее.|
|[CRecordset:: Move](#move)|Размещает набор записей по заданному числу записей из текущей записи в любом направлении.|
|[CRecordset:: MoveFirst](#movefirst)|Позиционирует текущую запись в первой записи в наборе записей. Проверьте `IsBOF` сначала.|
|[CRecordset:: MoveLast](#movelast)|Позиционирует текущую запись по последней записи или последнему набору строк. Проверьте `IsEOF` сначала.|
|[Метод CRecordset:: MoveNext](#movenext)|Позиционирует текущую запись на следующую запись или на следующий набор строк. Проверьте `IsEOF` сначала.|
|[CRecordset:: Мовепрев](#moveprev)|Позиционирует текущую запись по предыдущей записи или к предыдущему набору строк. Проверьте `IsBOF` сначала.|
|[CRecordset:: Онсетоптионс](#onsetoptions)|Вызывается для задания параметров (используемых в выделении) для указанной инструкции ODBC.|
|[CRecordset:: Онсетупдатеоптионс](#onsetupdateoptions)|Вызывается для задания параметров (используемых при обновлении) для указанной инструкции ODBC.|
|[CRecordset:: Open](#open)|Открывает набор записей, получая таблицу или выполняя запрос, представляемый набором записей.|
|[CRecordset:: Рефрешровсет](#refreshrowset)|Обновляет данные и состояние указанных строк.|
|[CRecordset:: Requery](#requery)|Повторно выполняет запрос набора записей, чтобы обновить выбранные записи.|
|[CRecordset:: Сетабсолутепоситион](#setabsoluteposition)|Размещает набор записей для записи, соответствующей указанному номеру записи.|
|[CRecordset:: Сетбукмарк](#setbookmark)|Размещает набор записей для записи, заданной закладкой.|
|[CRecordset:: Сетфиелддирти](#setfielddirty)|Помечает указанное поле в текущей записи как измененное.|
|[CRecordset:: Сетфиелднулл](#setfieldnull)|Устанавливает значение указанного поля в текущей записи в значение null (без значения).|
|[CRecordset:: Сетлоккингмоде](#setlockingmode)|Устанавливает режим блокировки «Оптимистическая» блокировка (по умолчанию) или «пессимистическая» блокировка. Определяет, как записи блокируются для обновлений.|
|[CRecordset:: Сетпарамнулл](#setparamnull)|Присваивает указанному параметру значение null (без значения).|
|[CRecordset:: Сетровсеткурсорпоситион](#setrowsetcursorposition)|Позиционирует курсор на указанную строку в наборе строк.|
|[CRecordset:: Сетровсетсизе](#setrowsetsize)|Указывает количество записей, которые необходимо получить во время выборки.|
|[CRecordset:: Update](#update)|Завершает `AddNew` `Edit` операцию или, сохраняя новые или измененные данные в источнике данных.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CRecordset:: m_hstmt](#m_hstmt)|Содержит маркер инструкции ODBC для набора записей. Введите `HSTMT`.|
|[CRecordset:: m_nFields](#m_nfields)|Содержит количество элементов данных полей в наборе записей. Введите `UINT`.|
|[CRecordset:: m_nParams](#m_nparams)|Содержит число элементов данных параметров в наборе записей. Введите `UINT`.|
|[CRecordset:: m_pDatabase](#m_pdatabase)|Содержит указатель на объект, `CDatabase` через который набор записей подключен к источнику данных.|
|[CRecordset:: m_strFilter](#m_strfilter)|Содержит объект `CString` , задающий предложение язык SQL (SQL) `WHERE` . Используется в качестве фильтра для выбора только тех записей, которые удовлетворяют определенным условиям.|
|[CRecordset:: m_strSort](#m_strsort)|Содержит объект `CString` , указывающий `ORDER BY` предложение SQL. Используется для управления порядком сортировки записей.|

## <a name="remarks"></a><a name="remarks"></a> Замечания

Объекты, известные как "наборы записей", `CRecordset` обычно используются в двух формах: динамических подмножеств данных и моментальных снимках. Динамический набор синхронизируется с обновлениями данных, сделанными другими пользователями. Моментальный снимок является статическим представлением данных. Каждая форма представляет набор записей, фиксированных во время открытия набора записей, но при прокрутке к записи в динамическом наборе он отражает изменения, внесенные в запись другими пользователями или другими наборами записей в приложении.

> [!NOTE]
> Если вы работаете с классами объектов доступа к данным (DAO), а не с классами ODBC, используйте вместо этого класс [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) . Дополнительные сведения см. в статье [Общие сведения о программировании баз данных](../../data/data-access-programming-mfc-atl.md).

Для работы с любым типом набора записей обычно необходимо, чтобы класс набора записей, зависящий от приложения, наследовался от `CRecordset` . Наборы записей выбирают записи из источника данных, а затем можно:

- Прокрутите записи.

- Обновите записи и укажите режим блокировки.

- Отфильтруйте набор записей, чтобы ограничить выбор выбираемых записей из доступных в источнике данных.

- Сортировка набора записей.

- Параметризация набора записей для настройки его выбора со сведениями, неизвестными до времени выполнения.

Чтобы использовать класс, откройте базу данных и создайте объект набора записей, передав конструктору указатель на ваш `CDatabase` объект. Затем вызовите `Open` функцию-член набора записей, где можно указать, является ли объект динамическим или моментальным снимком. Вызов `Open` выбирает данные из источника данных. После открытия объекта Recordset используйте его функции-члены и элементы данных для прокрутки записей и работы с ними. Доступные операции зависят от того, является ли объект динамическим или моментальным снимком, является ли он обновляемым или доступным только для чтения (это зависит от возможностей источника данных ODBC) и от того, реализована ли многострочная выборка строк. Чтобы обновить записи, которые могли быть изменены или добавлены с момента `Open` вызова, вызовите `Requery` функцию члена объекта. Вызовите `Close` функцию члена объекта и уничтожайте объект после завершения работы с ним.

В производном `CRecordset` классе для поддержки чтения и обновления полей записи используется операция обмена полями записей (RFX) или обмен полями групповой записи (групповой RFX).

Дополнительные сведения о наборах записей и обмене полями записей см. в статье [Общие сведения о программировании баз данных](../../data/data-access-programming-mfc-atl.md), [наборе записей (ODBC)](../../data/odbc/recordset-odbc.md), [наборе](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)записей и [обмене полями записей (RFX)](../../data/odbc/record-field-exchange-rfx.md). Дополнительные сведения о динамических подмножествах и моментальных снимках см. [в статье динамические](../../data/odbc/dynaset.md) наборы [и моментальные](../../data/odbc/snapshot.md)снимки.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>Требования

**Заголовок:** афксдб.h

## <a name="crecordsetaddnew"></a><a name="addnew"></a>CRecordset:: AddNew

Готовится к добавлению новой записи в таблицу.

```
virtual void AddNew();
```

### <a name="remarks"></a>Примечания

Чтобы увидеть только что добавленную запись, необходимо вызвать функцию " [Обновление](#requery) члена". Поля записи изначально имеют значение null. (В терминологии базы данных значение NULL означает, что значение не имеет значения и не совпадает со значением NULL в C++.) Чтобы завершить операцию, необходимо вызвать функцию [обновления](#update) члена. `Update`сохраняет изменения в источнике данных.

> [!NOTE]
> При реализации групповой выборки строк нельзя вызвать `AddNew` . Это приведет к неудачному утверждению. Хотя класс не `CRecordset` предоставляет механизм для обновления строк данных, можно написать собственные функции с помощью функции API ODBC `SQLSetPos` . Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`AddNew`подготавливает новую пустую запись с помощью элементов данных поля набора записей. После вызова задайте нужные `AddNew` значения в элементах данных поля набора записей. (Для этой цели нет необходимости вызывать функцию-член [Edit](#edit) ; используйте `Edit` только для существующих записей.) При последующем вызове `Update` измененные значения в элементах данных поля сохраняются в источнике данных.

> [!CAUTION]
> При прокрутке до новой записи перед вызовом `Update` Новая запись теряется и предупреждение не выдается.

Если источник данных поддерживает транзакции, можно сделать `AddNew` часть вызова транзакции. Дополнительные сведения о транзакциях см. в разделе класс [CDatabase](../../mfc/reference/cdatabase-class.md). Обратите внимание, что перед вызовом следует вызвать метод [CDatabase:: примеры BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) `AddNew` .

> [!NOTE]
> Для динамических подмножеств данных новые записи добавляются в набор записей в качестве последней записи. Добавленные записи не добавляются в моментальные снимки. `Requery`чтобы обновить набор записей, необходимо вызвать метод.

Не допускается вызов `AddNew` для набора записей, функция- `Open` член которой не была вызвана. `CDBException`Исключение создается при вызове `AddNew` для набора записей, к которому нельзя добавить к. Чтобы определить, можно ли обновить набор записей путем вызова [канаппенд](#canappend).

Дополнительные сведения см. в следующих статьях: [набор записей: принцип обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [набор записей: Добавление, обновление и удаление записей (](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)ODBC) и [транзакция (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Пример

См. статью [транзакция: выполнение транзакции в наборе записей (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

## <a name="crecordsetcanappend"></a><a name="canappend"></a>CRecordset:: Канаппенд

Определяет, позволяет ли ранее открытый набор записей добавлять новые записи.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей допускает добавление новых записей; в противном случае — 0. `CanAppend`Возвращает 0, если набор записей открыт только для чтения.

## <a name="crecordsetcanbookmark"></a><a name="canbookmark"></a>CRecordset:: Канбукмарк

Определяет, позволяет ли набор записей помечать записи с помощью закладок.

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей поддерживает закладки. в противном случае — 0.

### <a name="remarks"></a>Примечания

Эта функция не зависит от `CRecordset::useBookmarks` параметра в параметре *Двоптионс* функции [Open](#open) Member. `CanBookmark`Указывает, поддерживаются ли закладки для данного драйвера ODBC и типа курсора. `CRecordset::useBookmarks`Указывает, будут ли доступны закладки при условии, что они поддерживаются.

> [!NOTE]
> Закладки не поддерживаются для наборов записей с последовательным входом.

Дополнительные сведения о закладках и навигации по наборам записей см. в статьях [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [Recordset: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="crecordsetcancel"></a><a name="cancel"></a>CRecordset:: Cancel

Запрашивает, что источник данных отменяет выполняющуюся асинхронную операцию или процесс из второго потока.

```cpp
void Cancel();
```

### <a name="remarks"></a>Примечания

Обратите внимание, что классы ODBC MFC больше не используют асинхронную обработку. для выполнения операции асинхронного необходимо напрямую вызвать функцию API ODBC `SQLSetConnectOption` . Дополнительные сведения см. в разделе "асинхронное выполнение функций в *руководстве программиста по ODBC SDK*".

## <a name="crecordsetcancelupdate"></a><a name="cancelupdate"></a>CRecordset:: CancelUpdate

Отменяет все ожидающие обновления, вызванные операцией [Edit](#edit) или [AddNew](#addnew) , перед вызовом метода [Update](#update) .

```cpp
void CancelUpdate();
```

### <a name="remarks"></a>Примечания

> [!NOTE]
> Эта функция-член неприменима к наборам записей, использующим многострочную выборку строк, так как такие наборы записей не могут вызывать `Edit` , `AddNew` или `Update` . Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Если включена автоматическая проверка "грязных" полей, `CancelUpdate` переменные-члены будут восстановлены до или после `Edit` `AddNew` вызова значений. в противном случае любые изменения значений останутся. По умолчанию автоматическая проверка полей включается при открытии набора записей. Чтобы отключить его, необходимо указать `CRecordset::noDirtyFieldCheck` в параметре *Двоптионс* функции [Open](#open) Member.

Дополнительные сведения об обновлении данных см. в статье [набор записей: Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).

## <a name="crecordsetcanrestart"></a><a name="canrestart"></a>CRecordset:: Канрестарт

Определяет, допускает ли набор записей перезапуск запроса (для обновления записей), вызывая функцию- `Requery` член.

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если разрешено повторное обновление; в противном случае — 0.

## <a name="crecordsetcanscroll"></a><a name="canscroll"></a>CRecordset:: Канскролл

Определяет, допускает ли набор записей прокрутку.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей допускает прокрутку; в противном случае — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения о прокрутке см. в статье [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="crecordsetcantransact"></a><a name="cantransact"></a>CRecordset:: Кантрансакт

Определяет, допускает ли набор записей транзакции.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей допускает транзакции; в противном случае — 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в описании [транзакции статьи (ODBC)](../../data/odbc/transaction-odbc.md).

## <a name="crecordsetcanupdate"></a><a name="canupdate"></a>CRecordset:: Канупдате

Определяет, можно ли обновить набор записей.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей может быть обновлен; в противном случае — 0.

### <a name="remarks"></a>Примечания

Набор записей может быть доступен только для чтения, если базовый источник данных доступен только для чтения или указан `CRecordset::readOnly` в параметре *двоптионс* при открытии набора записей.

## <a name="crecordsetcheckrowseterror"></a><a name="checkrowseterror"></a>CRecordset:: Чеккровсетеррор

Вызывается для обработке ошибок, созданных во время выборки записей.

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>Параметры

*нреткоде*<br/>
Код возврата функции API ODBC. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

Эта виртуальная функция-член обрабатывает ошибки, происходящие при выборке записей, и полезна при выполнении групповой выборки строк. Может потребоваться переопределение `CheckRowsetError` для реализации собственной обработки ошибок.

`CheckRowsetError`вызывается автоматически в операции перехода по курсору, например `Open` , `Requery` или любой `Move` операции. Ему передается возвращаемое значение функции API ODBC `SQLExtendedFetch` . В следующей таблице перечислены возможные значения для параметра *нреткоде* .

|нреткоде|Описание|
|--------------|-----------------|
|SQL_SUCCESS|Функция успешно выполнена; Дополнительные сведения недоступны.|
|SQL_SUCCESS_WITH_INFO|Функция успешно выполнена, возможно, произошла неустранимая ошибка. Дополнительные сведения можно получить, вызвав `SQLError` .|
|SQL_NO_DATA_FOUND|Все строки из результирующего набора получены.|
|SQL_ERROR|Сбой функции. Дополнительные сведения можно получить, вызвав `SQLError` .|
|SQL_INVALID_HANDLE|Сбой функции из-за недопустимого обработчика среды, маркера соединения или маркера инструкции. Это указывает на ошибку программирования. Дополнительные сведения не доступны в `SQLError` .|
|SQL_STILL_EXECUTING|Функция, которая была запущена асинхронно, по-прежнему выполняется. Обратите внимание, что по умолчанию MFC никогда не передает это значение в `CheckRowsetError` ; MFC будет продолжать вызов `SQLExtendedFetch` до тех пор, пока он больше не возвратит SQL_STILL_EXECUTING.|

Дополнительные сведения о `SQLError` см. в Windows SDK. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetclose"></a><a name="close"></a>CRecordset:: Close

Закрывает набор записей.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

ХСТМТ ODBC и вся память, выделенная для набора записей, освобождается. Обычно после вызова `Close` удаляется объект набора записей C++, если он был выделен с помощью **`new`** .

После вызова метод можно вызвать `Open` снова `Close` . Это позволяет повторно использовать объект Recordset. Альтернативой является вызов `Requery` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

## <a name="crecordsetcrecordset"></a><a name="crecordset"></a>CRecordset:: CRecordset

Формирует объект `CRecordset`.

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Параметры

*пдатабасе*<br/>
Содержит указатель на `CDatabase` объект или значение null. Если не равно NULL и `CDatabase` `Open` функция члена объекта не была вызвана для подключения к источнику данных, набор записей пытается открыть его для вас во время собственного `Open` вызова. Если передать значение NULL, `CDatabase` объект будет создан и подключен для вас с помощью сведений об источнике данных, указанных при наследовании класса Recordset с помощью ClassWizard.

### <a name="remarks"></a>Примечания

Можно либо напрямую использовать, `CRecordset` либо создать производный от приложения класс от `CRecordset` . ClassWizard можно использовать для получения классов набора записей.

> [!NOTE]
> Производный класс *должен* предоставить собственный конструктор. В конструкторе производного класса вызовите конструктор `CRecordset::CRecordset` , передав ему соответствующие параметры.

Передайте значение NULL конструктору набора записей, чтобы `CDatabase` объект был автоматически создан и подключен. Это полезная Краткая форма, которая не требует создания и подключения `CDatabase` объекта перед созданием набора записей.

### <a name="example"></a>Пример

Дополнительные сведения см. в статье [набор записей: объявление класса для таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

## <a name="crecordsetdelete"></a><a name="delete"></a>CRecordset::D удалить

Удаляет текущую запись.

```
virtual void Delete();
```

### <a name="remarks"></a>Примечания

После успешного удаления элементы данных поля набора записей устанавливаются в значение null, и для перемещения удаленной записи необходимо явно вызвать одну из `Move` функций. После перемещения удаленной записи к ней невозможно вернуться. Если источник данных поддерживает транзакции, можно сделать `Delete` часть вызова транзакции. Дополнительные сведения см. в описании [транзакции статьи (ODBC)](../../data/odbc/transaction-odbc.md).

> [!NOTE]
> При реализации групповой выборки строк нельзя вызвать `Delete` . Это приведет к неудачному утверждению. Хотя класс не `CRecordset` предоставляет механизм для обновления строк данных, можно написать собственные функции с помощью функции API ODBC `SQLSetPos` . Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!CAUTION]
> Набор записей должен быть обновляемым, и при вызове в наборе записей должна быть действительная запись, в `Delete` противном случае возникнет ошибка. Например, если удалить запись, но не прокручивать до новой записи перед `Delete` повторным вызовом, `Delete` создает исключение [кдбексцептион](../../mfc/reference/cdbexception-class.md).

В отличие от [AddNew](#addnew) и [Edit](#edit), вызов метода `Delete` не должен сопровождаться вызовом [Update](#update). Если `Delete` вызов завершается неудачно, элементы данных поля остаются без изменений.

### <a name="example"></a>Пример

В этом примере показан набор записей, созданный на кадре функции. В примере предполагается существование `m_dbCust` , переменная-член типа, `CDatabase` уже подключенная к источнику данных.

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

## <a name="crecordsetdobulkfieldexchange"></a><a name="dobulkfieldexchange"></a>CRecordset::D Обулкфиелдексчанже

Вызывается для обмена массовыми строками данных из источника данных с набором записей. Реализует блочный обмен полей записей (групповой RFX).

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Параметры

*Сохраняется*<br/>
Указатель на объект [кфиелдексчанже](../../mfc/reference/cfieldexchange-class.md) . Платформа уже настроит этот объект, чтобы указать контекст для операции обмена полями.

### <a name="remarks"></a>Примечания

При реализации групповой выборки строк платформа вызывает эту функцию-член для автоматической пересылки данных из источника данных в объект набора записей. `DoBulkFieldExchange`также привязывает элементы данных параметров, если таковые имеются, к заполнителям параметров в строке инструкции SQL для выбора набора записей.

Если многострочная выборка строк не реализована, платформа вызывает функцию [DoFieldExchange](#dofieldexchange). Для реализации групповой выборки строк необходимо указать `CRecordset::useMultiRowFetch` параметр *двоптионс* в функции [Open](#open) Member.

> [!NOTE]
> `DoBulkFieldExchange`доступен только при использовании класса, производного от `CRecordset` . Если вы создали объект набора записей непосредственно из `CRecordset` , необходимо вызвать функцию-член [GetFieldValue](#getfieldvalue) для получения данных.

Блочный обмен полями записей (групповой RFX) аналогичен обмену полями записей (RFX). Данные автоматически передаются из источника данных в объект набора записей. Однако нельзя вызвать метод `AddNew` , `Edit` , `Delete` или `Update` для передачи изменений обратно в источник данных. `CRecordset`В настоящее время класс не предоставляет механизм обновления строк данных. Однако можно написать собственные функции с помощью функции API ODBC `SQLSetPos` .

Обратите внимание, что ClassWizard не поддерживает обмен полями с массовыми записями. Таким образом, необходимо `DoBulkFieldExchange` вручную переопределить, написав вызовы функций функции "массовый RFX". Дополнительные сведения об этих функциях см. в разделе [функции обмена полями записи](../../mfc/reference/record-field-exchange-functions.md).

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Дополнительные сведения см. в статье [Обмен полями записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).

## <a name="crecordsetdofieldexchange"></a><a name="dofieldexchange"></a>CRecordset::D Офиелдексчанже

Вызывается для обмена данными (в обоих направлениях) между элементами данных поля набора записей и соответствующей записью в источнике данных. Реализует обмен полями записей (RFX).

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Параметры

*Сохраняется*<br/>
Указатель на объект [кфиелдексчанже](../../mfc/reference/cfieldexchange-class.md) . Платформа уже настроит этот объект, чтобы указать контекст для операции обмена полями.

### <a name="remarks"></a>Примечания

Если многострочная выборка строк не реализована, платформа вызывает эту функцию-член для автоматического обмена данными между элементами данных поля объекта Recordset и соответствующими столбцами текущей записи в источнике данных. `DoFieldExchange`также привязывает элементы данных параметров, если таковые имеются, к заполнителям параметров в строке инструкции SQL для выбора набора записей.

Если реализуется групповая выборка строк, платформа вызывает [добулкфиелдексчанже](#dobulkfieldexchange). Для реализации групповой выборки строк необходимо указать `CRecordset::useMultiRowFetch` параметр *двоптионс* в функции [Open](#open) Member.

> [!NOTE]
> `DoFieldExchange`доступен только при использовании класса, производного от `CRecordset` . Если вы создали объект набора записей непосредственно из `CRecordset` , необходимо вызвать функцию-член [GetFieldValue](#getfieldvalue) для получения данных.

Обмен данными полей, называемый обмен полями записей (RFX), работает в обоих направлениях: от элементов данных поля объекта набора записей к полям записи в источнике данных и от записи в источнике данных к объекту набора записей.

Единственное действие, которое необходимо выполнить для реализации в `DoFieldExchange` производном классе набора записей, — это создать класс с ClassWizard и указать имена и типы данных для элементов данных поля. Вы также можете добавить код в запись ClassWizard для указания элементов данных параметров или для работы с любыми динамически связываемыми столбцами. Дополнительные сведения см. в статье [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

При объявлении производного класса набора записей с помощью ClassWizard мастер записывает переопределение `DoFieldExchange` , которое напоминает следующий пример:

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

Дополнительные сведения о функциях RFX см. в разделе [функции обмена полями записи](../../mfc/reference/record-field-exchange-functions.md).

Дополнительные примеры и подробные сведения см `DoFieldExchange` . в статье [Обмен данными с полями статей: принципы работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Общие сведения о RFX см. в статье об [обмене данными с полем записи](../../data/odbc/record-field-exchange-rfx.md).

## <a name="crecordsetedit"></a><a name="edit"></a>CRecordset:: Edit

Позволяет вносить изменения в текущую запись.

```
virtual void Edit();
```

### <a name="remarks"></a>Примечания

После вызова `Edit` можно изменить элементы данных поля путем прямого сброса их значений. Операция завершается при последующем вызове функции-члена [обновления](#update) для сохранения изменений в источнике данных.

> [!NOTE]
> При реализации групповой выборки строк нельзя вызвать `Edit` . Это приведет к неудачному утверждению. Хотя класс не `CRecordset` предоставляет механизм для обновления строк данных, можно написать собственные функции с помощью функции API ODBC `SQLSetPos` . Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`Edit`сохраняет значения элементов данных набора записей. При вызове `Edit` , внесении изменений и `Edit` повторном вызове значения записи восстанавливаются до первого `Edit` вызова.

В некоторых случаях может потребоваться обновить столбец, сделав его нулевым (не содержащим данные). Для этого вызовите [сетфиелднулл](#setfieldnull) с ПАРАМЕТРом true, чтобы пометить поле как null; Это также приводит к обновлению столбца. Если необходимо, чтобы поле было записано в источник данных, даже если его значение не изменилось, вызовите [сетфиелддирти](#setfielddirty) с параметром true. Это работает, даже если поле имеет значение null.

Если источник данных поддерживает транзакции, можно сделать `Edit` часть вызова транзакции. Обратите внимание, что перед вызовом и после открытия набора записей следует вызвать метод [CDatabase:: примеры BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) `Edit` . Также обратите внимание, что вызов метода [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) не является заменой вызову `Update` для завершения `Edit` операции. Дополнительные сведения о транзакциях см. в разделе класс [CDatabase](../../mfc/reference/cdatabase-class.md).

В зависимости от текущего режима блокировки обновляемая запись может быть заблокирована `Edit` до тех пор, пока не будет вызвана `Update` или прокрутка к другой записи или она будет заблокирована только во время `Edit` вызова. Режим блокировки можно изменить с помощью [сетлоккингмоде](#setlockingmode).

Предыдущее значение текущей записи восстанавливается при прокрутке до новой записи перед вызовом `Update` . `CDBException`Исключение возникает при вызове `Edit` для набора записей, который не может быть обновлен, или в случае отсутствия текущей записи.

Дополнительные сведения см. в статьях [транзакции (ODBC)](../../data/odbc/transaction-odbc.md) и [набор записей: Блокировка записей (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

## <a name="crecordsetflushresultset"></a><a name="flushresultset"></a>CRecordset:: Флушресултсет

Извлекает следующий результирующий набор предопределенного запроса (хранимой процедуры), если имеется несколько результирующих наборов.

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если требуется получить дополнительные результирующие наборы. в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызов следует выполнять `FlushResultSet` только после завершения работы с курсором на текущем результирующем наборе. Обратите внимание, что при извлечении следующего результирующего набора с помощью метода `FlushResultSet` курсор не является допустимым для этого результирующего набора. необходимо вызвать функцию-член [MoveNext](#movenext) после вызова метода `FlushResultSet` .

Если в предопределенном запросе используется выходной параметр или параметры ввода-вывода, необходимо вызвать метод, `FlushResultSet` пока он не возвратит `FALSE` (значение 0), чтобы получить эти значения параметров.

`FlushResultSet`вызывает функцию API ODBC `SQLMoreResults` . Если функция `SQLMoreResults` возвращает SQL_ERROR или SQL_INVALID_HANDLE, то выдаст `FlushResultSet` исключение. Дополнительные сведения о `SQLMoreResults` см. в Windows SDK.

Если требуется вызвать, хранимая процедура должна иметь привязанные поля `FlushResultSet` .

### <a name="example"></a>Пример

В следующем коде предполагается, что `COutParamRecordset` является `CRecordset` производным объектом на основе предопределенного запроса с входным параметром и выходным параметром и наличием нескольких результирующих наборов. Обратите внимание на структуру переопределения [DoFieldExchange](#dofieldexchange) .

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

## <a name="crecordsetgetbookmark"></a><a name="getbookmark"></a>CRecordset:: onbookmark

Получает значение закладки для текущей записи.

```cpp
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>Параметры

*варбукмарк*<br/>
Ссылка на объект [кдбвариант](../../mfc/reference/cdbvariant-class.md) , представляющий закладку для текущей записи.

### <a name="remarks"></a>Примечания

Чтобы определить, поддерживаются ли закладки в наборе записей, вызовите [канбукмарк](#canbookmark). Чтобы сделать закладки доступными, если они поддерживаются, необходимо задать `CRecordset::useBookmarks` параметр в параметре *Двоптионс* функции [Open](#open) Member.

> [!NOTE]
> Если закладки не поддерживаются или недоступны, вызов `GetBookmark` приводит к возникновению исключения. Закладки не поддерживаются для наборов записей с последовательным входом.

`GetBookmark`присваивает значение закладки для текущей записи `CDBVariant` объекту. Чтобы вернуться к этой записи в любое время после перехода на другую запись, вызовите [сетбукмарк](#setbookmark) с соответствующим `CDBVariant` объектом.

> [!NOTE]
> После выполнения определенных операций с набором записей закладки могут стать недействительными. Например, при вызове `GetBookmark` , за которым следует `Requery` , возможно, не удастся вернуться к записи с помощью `SetBookmark` . Вызовите метод [CDatabase:: жетбукмаркперсистенце](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) , чтобы проверить, можно ли безопасно вызвать `SetBookmark` .

Дополнительные сведения о закладках и навигации по наборам записей см. в статьях [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [Recordset: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="crecordsetgetdefaultconnect"></a><a name="getdefaultconnect"></a>CRecordset:: Жетдефаултконнект

Вызывается для получения строки подключения по умолчанию.

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>Возвращаемое значение

Значение типа `CString` , содержащее строку подключения по умолчанию.

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию-член, чтобы получить строку подключения по умолчанию для источника данных, на котором основан набор записей. ClassWizard реализует эту функцию, определяя тот же источник данных, который используется в ClassWizard для получения сведений о таблицах и столбцах. Возможно, вам будет удобно полагаться на это подключение по умолчанию при разработке приложения. Однако подключение по умолчанию может не подойти для пользователей вашего приложения. В этом случае следует повторно реализовать эту функцию, отменяя версию ClassWizard. Дополнительные сведения о строках подключения см. в статье [источник данных (ODBC)](../../data/odbc/data-source-odbc.md).

## <a name="crecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>CRecordset:: GetDefaultSQL

Вызывается для получения строки SQL по умолчанию для выполнения.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Возвращаемое значение

Значение типа `CString` , содержащее инструкцию SQL по умолчанию.

### <a name="remarks"></a>Примечания

Платформа вызывает эту функцию-член для получения инструкции SQL по умолчанию, на которой основан набор записей. Это может быть имя таблицы или инструкция SQL **SELECT** .

Вы косвенно определяете инструкцию SQL по умолчанию, объявляя класс набора записей с помощью ClassWizard, и ClassWizard выполняет эту задачу.

Если требуется строка инструкции SQL для собственного использования, вызовите метод `GetSQL` , который возвращает инструкцию SQL, используемую для выбора записей набора записей при его открытии. Вы можете изменить строку SQL по умолчанию в переопределении класса `GetDefaultSQL` . Например, можно указать вызов предопределенного запроса с помощью инструкции **Call** . (Обратите внимание, что при редактировании `GetDefaultSQL` также необходимо изменить `m_nFields` в соответствии с количеством столбцов в источнике данных.)

Дополнительные сведения см. в статье [набор записей: объявление класса для таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

> [!CAUTION]
> Имя таблицы будет пустым, если платформе не удалось определить имя таблицы, если было указано несколько имен таблиц или если инструкция **Call** не может быть интерпретирована. Обратите внимание, что при использовании оператора **Call** не следует вставлять пробелы между фигурными скобками и ключевым словом **Call** , а также вставлять пробелы перед фигурными скобками или перед ключевым словом **SELECT** в инструкции **SELECT** .

## <a name="crecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>CRecordset:: GetFieldValue

Извлекает данные поля в текущей записи.

```cpp
void GetFieldValue(
    LPCTSTR lpszName,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CStringA& strValue);

void GetFieldValue(
    short nIndex,
    CStringW& strValue);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
Имя поля.

*варвалу*ссылку на объект [кдбвариант](../../mfc/reference/cdbvariant-class.md) , в котором будет храниться значение поля.

*нфиелдтипе*<br/>
Тип данных ODBC C для поля. Использование значения по умолчанию, DEFAULT_FIELD_TYPE, заставляет `GetFieldValue` определить тип данных C на основе типа данных SQL, исходя из следующей таблицы. В противном случае можно указать тип данных напрямую или выбрать совместимый тип данных. Например, можно сохранить любой тип данных в SQL_C_CHAR.

|Тип данных C|Тип данных SQL|
|-----------------|-------------------|
|SQL_C_BIT|SQL_BIT|
|SQL_C_UTINYINT|SQL_TINYINT|
|SQL_C_SSHORT|SQL_SMALLINT|
|SQL_C_SLONG|SQL_INTEGER|
|SQL_C_FLOAT|SQL_REAL|
|SQL_C_DOUBLE|SQL_FLOATSQL_DOUBLE|
|SQL_C_TIMESTAMP|SQL_DATESQL_TIMESQL_TIMESTAMP|
|SQL_C_CHAR|SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR|
|SQL_C_BINARY|SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY|

Дополнительные сведения о типах данных ODBC см. в разделах «типы данных SQL» и «типы данных C» в приложении г Windows SDK.

*ниндекс*<br/>
Отсчитываемый от нуля индекс поля.

*strValue*<br/>
Ссылка на объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) , который будет хранить значение поля, преобразованное в текст, независимо от типа данных поля.

### <a name="remarks"></a>Примечания

Можно найти поле по имени или по индексу. Значение поля можно сохранить как в `CDBVariant` объекте, так и в `CString` объекте.

При реализации групповой выборки строк текущая запись всегда размещается на первой записи набора строк. Чтобы использовать для `GetFieldValue` записи в заданном наборе строк, необходимо сначала вызвать функцию-член [сетровсеткурсорпоситион](#setrowsetcursorposition) , чтобы переместить курсор в нужную строку в этом наборе строк. Затем вызовите `GetFieldValue` для этой строки. Для реализации групповой выборки строк необходимо указать `CRecordset::useMultiRowFetch` параметр *двоптионс* в функции [Open](#open) Member.

Можно использовать `GetFieldValue` для динамической выборки полей во время выполнения, а не для их статической привязки во время разработки. Например, если объект набора записей был объявлен непосредственно из `CRecordset` , необходимо использовать `GetFieldValue` для извлечения данных поля, обмена полями записей (RFX) или блочного обмена полями записей (групповой RFX), не реализован.

> [!NOTE]
> Если объект набора записей объявляется без наследования от `CRecordset` , не следует загружать библиотеку курсоров ODBC. Библиотека курсоров требует, чтобы набор записей имел по крайней мере один привязанный столбец. Однако при `CRecordset` непосредственном использовании ни один из столбцов не привязан. Функции члена [CDatabase:: опенекс](../../mfc/reference/cdatabase-class.md#openex) и [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) контролируют, будет ли загружена библиотека курсоров.

`GetFieldValue`вызывает функцию API ODBC `SQLGetData` . Если драйвер выводит значение SQL_NO_TOTAL фактической длины значения поля, `GetFieldValue` создает исключение. Дополнительные сведения о `SQLGetData` см. в Windows SDK.

### <a name="example"></a>Пример

В следующем образце кода показаны вызовы для `GetFieldValue` объекта Recordset, объявленного непосредственно из `CRecordset` .

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
> В отличие от класса DAO `CDaoRecordset` , не `CRecordset` имеет функции- `SetFieldValue` члена. Если объект создается непосредственно из `CRecordset` , он фактически доступен только для чтения.

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetgetodbcfieldcount"></a><a name="getodbcfieldcount"></a>CRecordset:: Жетодбкфиелдкаунт

Извлекает общее число полей в объекте набора записей.

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число полей в наборе записей.

### <a name="remarks"></a>Примечания

Дополнительные сведения о создании наборов записей см. в статье [набор записей: создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

## <a name="crecordsetgetodbcfieldinfo"></a><a name="getodbcfieldinfo"></a>CRecordset:: Жетодбкфиелдинфо

Получает сведения о полях в наборе записей.

```cpp
void GetODBCFieldInfo(
    LPCTSTR lpszName,
    CODBCFieldInfo& fieldinfo);

void GetODBCFieldInfo(
    short nIndex,
    CODBCFieldInfo& fieldinfo);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
Имя поля.

*FieldInfo*<br/>
Ссылка на `CODBCFieldInfo` структуру.

*ниндекс*<br/>
Отсчитываемый от нуля индекс поля.

### <a name="remarks"></a>Примечания

Одна версия функции позволяет искать поле по имени. Другая версия позволяет найти поле по индексу.

Описание возвращаемых сведений см. в разделе Структура [кодбкфиелдинфо](../../mfc/reference/codbcfieldinfo-structure.md) .

Дополнительные сведения о создании наборов записей см. в статье [набор записей: создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

## <a name="crecordsetgetrecordcount"></a><a name="getrecordcount"></a>CRecordset:: Жетрекордкаунт

Определяет размер набора записей.

```
long GetRecordCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число записей в наборе записей; 0, если набор записей не содержит записей; значение-1, если невозможно определить счетчик записей.

### <a name="remarks"></a>Примечания

> [!CAUTION]
> Число записей сохраняется как «высокий знак воды», а самая старшая запись, еще не отображаемая при перемещении по записям. Общее число записей известно только после того, как пользователь переместился за последнюю запись. По соображениям производительности число не обновляется при вызове метода `MoveLast` . Чтобы самостоятельно подсчитать записи, вызывайте их `MoveNext` повторно, пока не `IsEOF` вернет ненулевое значение. Добавление записи с помощью `CRecordset:AddNew` и `Update` увеличение числа; удаление записи с помощью `CRecordset::Delete` уменьшает число.

## <a name="crecordsetgetrowsetsize"></a><a name="getrowsetsize"></a>CRecordset:: Жетровсетсизе

Получает текущее значение для числа строк, которые необходимо получить во время данной выборки.

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число строк, извлекаемых во время данной выборки.

### <a name="remarks"></a>Примечания

При использовании групповой выборки строк размер набора строк по умолчанию при открытии набора записей составляет 25; в противном случае — 1.

Для реализации групповой выборки строк необходимо указать `CRecordset::useMultiRowFetch` параметр в параметре *Двоптионс* функции [Open](#open) Member. Чтобы изменить параметр для размера набора строк, вызовите [сетровсетсизе](#setrowsetsize).

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetgetrowsfetched"></a><a name="getrowsfetched"></a>CRecordset:: Жетровсфетчед

Определяет, сколько записей было фактически извлечено после выборки.

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число строк, полученных из источника данных после заданной выборки.

### <a name="remarks"></a>Примечания

Это полезно при реализации групповой выборки строк. Размер набора строк обычно указывает, сколько строк будет извлечено из выборки; Однако общее число строк в наборе записей также влияет на количество строк, которые будут извлечены в наборе строк. Например, если набор записей содержит 10 записей с параметром размера набора строк 4, то при циклическом переборе набора записей с помощью вызова `MoveNext` будет создан итоговый набор строк, содержащий только 2 записи.

Для реализации групповой выборки строк необходимо указать `CRecordset::useMultiRowFetch` параметр в параметре *Двоптионс* функции [Open](#open) Member. Чтобы указать размер набора строк, вызовите [сетровсетсизе](#setrowsetsize).

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

## <a name="crecordsetgetrowstatus"></a><a name="getrowstatus"></a>CRecordset:: Жетровстатус

Получает состояние для строки в текущем наборе строк.

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>Параметры

*вров*<br/>
Порядковый номер строки в текущем наборе строк, отсчитываемый от единицы. Это значение может находиться в диапазоне от 1 до размера набора строк.

### <a name="return-value"></a>Возвращаемое значение

Значение состояния для строки. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

`GetRowStatus`Возвращает значение, которое указывает любое изменение состояния строки с момента последнего извлечения из источника данных или не удалось получить строку, соответствующую *вров* . В следующей таблице перечислены возможные возвращаемые значения.

|Значение состояния|Описание|
|------------------|-----------------|
|SQL_ROW_SUCCESS|Строка не изменяется.|
|SQL_ROW_UPDATED|Строка была обновлена.|
|SQL_ROW_DELETED|Строка была удалена.|
|SQL_ROW_ADDED|Строка была добавлена.|
|SQL_ROW_ERROR|Строка не может быть извлечена из-за ошибки.|
|SQL_ROW_NOROW|Нет строки, соответствующей *вров*.|

Дополнительные сведения см. в описании функции ODBC API `SQLExtendedFetch` в Windows SDK.

## <a name="crecordsetgetstatus"></a><a name="getstatus"></a>CRecordset::/Status

Определяет индекс текущей записи в наборе записей и наличие последней записи.

```cpp
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>Параметры

*рстатус*<br/>
Ссылка на объект `CRecordsetStatus`. Дополнительные сведения см. в разделе «Примечания».

### <a name="remarks"></a>Примечания

`CRecordset`попытается отвестить индекс, но в некоторых обстоятельствах это может оказаться невозможным. Описание см. в разделе [жетрекордкаунт](#getrecordcount) .

`CRecordsetStatus`Структура имеет следующий вид:

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

Два члена `CRecordsetStatus` имеют следующие значения:

- `m_lCurrentRecord`Содержит Отсчитываемый от нуля индекс текущей записи в наборе записей, если он известен. Если индекс не может быть определен, этот элемент содержит AFX_CURRENT_RECORD_UNDEFINED (-2). Если `IsBOF` имеет значение true (пустой набор записей или попытка прокрутки перед первой записью), то `m_lCurrentRecord` устанавливается в AFX_CURRENT_RECORD_BOF (-1). Если используется первая запись, то для нее устанавливается значение 0, вторая запись 1 и т. д.

- `m_bRecordCountFinal`Ненулевое значение, если общее число записей в наборе записей определено. Как правило, это необходимо сделать, начиная с начала набора записей и вызывая метод, `MoveNext` пока не `IsEOF` вернет ненулевое значение. Если этот элемент равен нулю, то счетчик записей, возвращаемый `GetRecordCount` , если он не равен-1, будет считаться количеством записей с высокой назначением.

## <a name="crecordsetgetsql"></a><a name="getsql"></a>CRecordset:: Жетскл

Вызовите эту функцию члена, чтобы получить инструкцию SQL, которая использовалась для выбора записей набора записей при его открытии.

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Ссылка на объект `CString` , содержащий инструкцию SQL.

### <a name="remarks"></a>Примечания

Как правило, это инструкция SQL **SELECT** . Строка, возвращаемая функцией, `GetSQL` доступна только для чтения.

Строка, возвращаемая, `GetSQL` обычно отличается от любой строки, которая могла быть передана набору записей *lpszSQL* в параметре lpszSQL `Open` функции-члену. Это обусловлено тем, что набор записей формирует полную инструкцию SQL в зависимости от того, что вы передали `Open` , что вы указали с помощью ClassWizard, что вы могли указать в элементах `m_strFilter` `m_strSort` данных и, а также какие параметры, которые могли быть указаны. Дополнительные сведения о том, как набор записей формирует эту инструкцию SQL, см. в статье [набор записей: как наборы записей выбирают записи (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

> [!NOTE]
> Вызывайте эту функцию члена только после вызова [Open](#open).

## <a name="crecordsetgettablename"></a><a name="gettablename"></a>CRecordset:: имя_таблицы

Возвращает имя таблицы SQL, на которой основан запрос набора записей.

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>Возвращаемое значение

**`const`** Ссылка на объект `CString` , содержащий имя таблицы, если набор записей основан на таблице; в противном случае — пустая строка.

### <a name="remarks"></a>Примечания

`GetTableName`параметр допустим только в том случае, если набор записей основан на таблице, а не на соединении нескольких таблиц или в предопределенном запросе (хранимой процедуре). Имя доступно только для чтения.

> [!NOTE]
> Вызывайте эту функцию члена только после вызова [Open](#open).

## <a name="crecordsetisbof"></a><a name="isbof"></a>CRecordset:: Исбоф

Возвращает ненулевое значение, если набор записей был помещен перед первой записью. Отсутствует текущая запись.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей не содержит записей или если вы выполнили прокрутку назад перед первой записью; в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызовите эту функцию члена перед прокруткой от записи к записи, чтобы узнать, исчезли ли вы до первой записи набора записей. Также можно использовать `IsBOF` вместе с `IsEOF` для определения того, содержит ли набор записей какие-либо записи или является пустым. Сразу после вызова `Open` , если набор записей не содержит записей, `IsBOF` возвращает ненулевое значение. При открытии набора записей, имеющего по крайней мере одну запись, первая запись является текущей и `IsBOF` возвращает 0.

Если первая запись является текущей, и вы вызываете `MovePrev` , то `IsBOF` впоследствии вернет ненулевое значение. Если функция `IsBOF` возвращает ненулевое значение и вызывается `MovePrev` , возникает ошибка. Если `IsBOF` возвращает ненулевое значение, текущая запись не определена, и любое действие, требующее текущей записи, приведет к ошибке.

### <a name="example"></a>Пример

В этом примере используется `IsBOF` и `IsEOF` для определения ограничений набора записей по мере прокрутки кода в обоих направлениях.

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

## <a name="crecordsetisdeleted"></a><a name="isdeleted"></a>CRecordset:: isDeleted

Определяет, была ли удалена текущая запись.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей расположен на удаленной записи; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если прокрутить запись к записи и `IsDeleted` возвращает значение true (отличное от нуля), то перед выполнением других операций с набором записей необходимо прокрутить на другую запись.

Результат зависит от `IsDeleted` многих факторов, например от типа набора записей, от того, является ли набор записей обновляемым, определен ли `CRecordset::skipDeletedRecords` параметр при открытии набора записей, были ли пакеты драйверов удалены, а также существует ли несколько пользователей.

Дополнительные сведения о `CRecordset::skipDeletedRecords` и упаковке драйверов см. в разделе Функция [Open](#open) Member.

> [!NOTE]
> При реализации групповой выборки строк не следует вызывать метод `IsDeleted` . Вместо этого вызовите функцию члена [жетровстатус](#getrowstatus) . Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetiseof"></a><a name="iseof"></a>CRecordset:: Исеоф

Возвращает ненулевое значение, если набор записей был помещен после последней записи. Отсутствует текущая запись.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей не содержит записей или прокручивается за последнюю запись; в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию члена при прокрутке записи до записи, чтобы узнать, не выходит ли вы за последнюю запись набора записей. Также можно использовать `IsEOF` , чтобы определить, содержит ли набор записей какие-либо записи или пуст. Сразу после вызова `Open` , если набор записей не содержит записей, `IsEOF` возвращает ненулевое значение. При открытии набора записей, имеющего по крайней мере одну запись, первая запись является текущей и `IsEOF` возвращает 0.

Если последняя запись является текущей записью при вызове `MoveNext` , в `IsEOF` дальнейшем будет возвращаться ненулевое значение. Если функция `IsEOF` возвращает ненулевое значение и вызывается `MoveNext` , возникает ошибка. Если `IsEOF` возвращает ненулевое значение, текущая запись не определена, и любое действие, требующее текущей записи, приведет к ошибке.

### <a name="example"></a>Пример

См. пример для [исбоф](#isbof).

## <a name="crecordsetisfielddirty"></a><a name="isfielddirty"></a>CRecordset:: Исфиелддирти

Определяет, изменился ли указанный элемент данных поля с момента вызова метода [Edit](#edit) или [AddNew](#addnew) .

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на элемент данных поля, состояние которого необходимо проверить, или значение NULL, чтобы определить, являются ли какие-либо из полей "грязными".

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если указанный элемент данных поля изменился с момента вызова `AddNew` или `Edit` ; в противном случае — 0.

### <a name="remarks"></a>Примечания

Данные всех элементов данных "грязных" полей будут передаваться в запись источника данных, когда текущая запись обновляется вызовом функции-члена [обновления](#update) метода `CRecordset` (после вызова `Edit` или `AddNew` ).

> [!NOTE]
> Эта функция-член неприменима к наборам записей, использующим групповые выборке строк. Если вы реализовали групповую выборку строк, то `IsFieldDirty` всегда возвратите значение false и приведет к неудачному утверждению. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Вызов `IsFieldDirty` сбрасывает эффекты предыдущих вызовов [сетфиелддирти](#setfielddirty) , так как состояние "грязного" поля повторно вычисляется. В `AddNew` случае, если значение текущего поля отличается от значения псевдо null, поле состояние устанавливается как «грязный». В `Edit` случае, если значение поля отличается от кэшированного значения, поле состояние устанавливается как «грязный».

`IsFieldDirty`реализуется с помощью [DoFieldExchange](#dofieldexchange).

Дополнительные сведения о флаге "грязный" см. в статье [набор записей: выбор записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

## <a name="crecordsetisfieldnull"></a><a name="isfieldnull"></a>CRecordset:: Исфиелднулл

Возвращает ненулевое значение, если указанное поле в текущей записи имеет значение null (не имеет значения).

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на элемент данных поля, состояние которого необходимо проверить, или значение NULL, чтобы определить, имеет ли какое-либо из полей значение null.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если указанный элемент данных поля помечен как null. в противном случае — 0.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член, чтобы определить, помечен ли указанный элемент данных поля набора записей как null. (В терминологии базы данных значение NULL означает, что значение не имеет значения и не совпадает со значением NULL в C++.) Если элемент данных поля помечен как имеющий значение null, он интерпретируется как столбец текущей записи, для которой нет значения.

> [!NOTE]
> Эта функция-член неприменима к наборам записей, использующим групповые выборке строк. Если вы реализовали групповую выборку строк, то `IsFieldNull` всегда возвратите значение false и приведет к неудачному утверждению. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`IsFieldNull`реализуется с помощью [DoFieldExchange](#dofieldexchange).

## <a name="crecordsetisfieldnullable"></a><a name="isfieldnullable"></a>CRecordset:: Исфиелднуллабле

Возвращает ненулевое значение, если указанное поле в текущей записи может быть установлено в NULL (без значения).

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на элемент данных поля, состояние которого необходимо проверить, или значение NULL, чтобы определить, можно ли задать для любого из полей значение null.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член, чтобы определить, является ли указанный элемент данных поля обнуляемым (может быть задано значение null). C++ NULL не совпадает со значением NULL, что в терминологии базы данных означает, что не имеет значения.

> [!NOTE]
> При реализации групповой выборки строк нельзя вызвать `IsFieldNullable` . Вместо этого вызовите функцию-член [жетодбкфиелдинфо](#getodbcfieldinfo) , чтобы определить, можно ли задать для поля значение null. Обратите внимание, что всегда можно вызывать `GetODBCFieldInfo` , независимо от того, реализована ли многострочная выборка строк. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Поле, которое не может быть null, должно иметь значение. При попытке установить такое поле в значение null при добавлении или обновлении записи источник данных отклоняет Добавление или обновление, а [Обновление](#update) выдаст исключение. Исключение возникает при вызове `Update` , а не при вызове [сетфиелднулл](#setfieldnull).

Использование значения NULL для первого аргумента функции приведет к применению функции только к `outputColumn` полям, а не к `param` полям. Например, вызов

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

устанавливает только `outputColumn` поля в значение NULL; `param` поля не затрагиваются.

Для работы с `param` полями необходимо указать фактический адрес человека, с которым `param` вы хотите работать, например:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Это означает, что нельзя задать `param` для всех полей значение null, как это можно сделать с `outputColumn` полями.

`IsFieldNullable`реализуется с помощью [DoFieldExchange](#dofieldexchange).

## <a name="crecordsetisopen"></a><a name="isopen"></a>CRecordset:: OnOpen

Определяет, является ли набор записей уже открытым.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если для объекта набора записей уже был вызван метод [Open](#open) или [Requery](#requery) , а набор записей не закрыт. в противном случае — 0.

## <a name="crecordsetm_hstmt"></a><a name="m_hstmt"></a>CRecordset:: m_hstmt

Содержит маркер структуры данных инструкции ODBC типа ХСТМТ, связанный с набором записей.

### <a name="remarks"></a>Примечания

Каждый запрос к источнику данных ODBC связан с ХСТМТ.

> [!CAUTION]
> Не используйте `m_hstmt` метод перед [открытием](#open) .

Обычно нет необходимости напрямую обращаться к ХСТМТ, но может потребоваться для прямого выполнения инструкций SQL. `ExecuteSQL`Функция члена класса `CDatabase` предоставляет пример использования `m_hstmt` .

## <a name="crecordsetm_nfields"></a><a name="m_nfields"></a>CRecordset:: m_nFields

Содержит количество элементов данных полей в классе набора записей. то есть количество столбцов, выбранных набором записей из источника данных.

### <a name="remarks"></a>Примечания

Конструктор для класса набора записей должен инициализироваться `m_nFields` с правильным числом. Если не реализована многострочная выборка строк, ClassWizard записывает эту инициализацию при ее использовании для объявления класса набора записей. Его также можно записать вручную.

Платформа использует это число для управления взаимодействием между элементами данных поля и соответствующими столбцами текущей записи в источнике данных.

> [!CAUTION]
> Это число должно соответствовать числу выходных столбцов, зарегистрированных в `DoFieldExchange` или `DoBulkFieldExchange` после вызова [сетфиелдтипе](../../mfc/reference/cfieldexchange-class.md#setfieldtype) с параметром `CFieldExchange::outputColumn` .

Столбцы можно привязывать динамически, как описано в статье «набор записей: динамическая привязка столбцов данных». В этом случае необходимо увеличить число в `m_nFields` , чтобы отразить число вызовов функций RFX или МАССОВЫ RFX в `DoFieldExchange` `DoBulkFieldExchange` функции члена или для динамически привязанных столбцов.

Дополнительные сведения см. в статье [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) и [набор записей: некоторая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

См. статью [запись в статье обмен данными: использование RFX](../../data/odbc/record-field-exchange-using-rfx.md).

## <a name="crecordsetm_nparams"></a><a name="m_nparams"></a>CRecordset:: m_nParams

Содержит число элементов данных параметров в классе набора записей. то есть число параметров, передаваемых с помощью запроса набора записей.

### <a name="remarks"></a>Примечания

Если класс набора записей содержит какие – либо элементы данных параметров, конструктор класса должен инициализироваться `m_nParams` с правильным числом. Значение `m_nParams` по умолчанию равно 0. При добавлении элементов данных параметров (которые необходимо выполнить вручную) необходимо также вручную добавить инициализацию в конструктор класса, чтобы отразить количество параметров (которое должно быть не меньше, чем количество заполнителей "" в `m_strFilter` `m_strSort` строке или).

Платформа использует этот номер при параметризации запроса набора записей.

> [!CAUTION]
> Это число должно соответствовать числу параметров "params", зарегистрированных в `DoFieldExchange` или `DoBulkFieldExchange` после вызова [сетфиелдтипе](../../mfc/reference/cfieldexchange-class.md#setfieldtype) со значением параметра `CFieldExchange::inputParam` ,, `CFieldExchange::param` `CFieldExchange::outputParam` или `CFieldExchange::inoutParam` .

### <a name="example"></a>Пример

  См. статьи [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) и [Обмен полями записей: использование RFX](../../data/odbc/record-field-exchange-using-rfx.md).

## <a name="crecordsetm_pdatabase"></a><a name="m_pdatabase"></a>CRecordset:: m_pDatabase

Содержит указатель на объект, `CDatabase` через который набор записей подключен к источнику данных.

### <a name="remarks"></a>Примечания

Эта переменная задается двумя способами. Как правило, `CDatabase` при построении объекта набора записей передается указатель на уже подключенный объект. Если вместо этого вы передаете значение NULL, `CRecordset` создает `CDatabase` объект и подключает его. В любом случае `CRecordset` сохраняет указатель в этой переменной.

Обычно не нужно напрямую использовать указатель, хранящийся в `m_pDatabase` . Однако если вы пишете собственные расширения в `CRecordset` , возможно, потребуется использовать указатель. Например, может потребоваться указатель, если вы создаете собственный объект `CDBException` . Или это может потребоваться, если нужно сделать что-то с помощью того же `CDatabase` объекта, например выполнение транзакций, установка времени ожидания или вызов функции- `ExecuteSQL` члена класса `CDatabase` для непосредственного выполнения инструкций SQL.

## <a name="crecordsetm_strfilter"></a><a name="m_strfilter"></a>CRecordset:: m_strFilter

После создания объекта Recordset, но перед вызовом его `Open` функции-члена используйте этот элемент данных для хранения `CString` содержащего предложение SQL **WHERE** .

### <a name="remarks"></a>Примечания

Набор записей использует эту строку для ограничения (или фильтрации) записей, которые она выбирает во `Open` время `Requery` вызова или. Это полезно для выбора подмножества записей, например "все менеджеры, основанные на Калифорнии" ("штат = CA"). Синтаксис ODBC SQL для предложения **WHERE** :

`WHERE search-condition`

Обратите внимание, что в строке не включено ключевое слово **WHERE** . Платформа предоставляет ее.

Можно также параметризовать строку фильтра, поместив в нее заполнители "", объявляя член данных параметра в классе для каждого заполнителя и передав параметры в набор записей во время выполнения. Это позволяет создать фильтр во время выполнения. Дополнительные сведения см. в статье [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

Дополнительные сведения о предложениях SQL **WHERE** см. в статье [SQL](../../data/odbc/sql.md). Дополнительные сведения о выборе и фильтрации записей см. в статье [набор записей: Фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

## <a name="crecordsetm_strsort"></a><a name="m_strsort"></a>CRecordset:: m_strSort

После создания объекта набора записей, но перед вызовом его `Open` функции-члена используйте этот элемент данных для хранения `CString` содержащего предложение SQL **ORDER BY** .

### <a name="remarks"></a>Примечания

Набор записей использует эту строку для сортировки записей, которые она выбирает во `Open` время `Requery` вызова метода или. Эту функцию можно использовать для сортировки набора записей по одному или нескольким столбцам. Синтаксис ODBC SQL для предложения **ORDER BY** :

`ORDER BY sort-specification [, sort-specification]...`

где спецификация Sort — это целое число или имя столбца. Можно также указать порядок по возрастанию или по убыванию (порядок по умолчанию — по возрастанию), добавив "ASC" или "DESC" в список столбцов в строке сортировки. Выбранные записи сортируются сначала по первому указанному столбцу, затем по второму и т. д. Например, можно упорядочить набор записей Customers по фамилии, а затем по имени. Количество столбцов, которые можно перечислить, зависит от источника данных. Дополнительные сведения см. в Windows SDK.

Обратите внимание, что в строке не включено ключевое слово **ORDER BY** . Платформа предоставляет ее.

Дополнительные сведения о предложениях SQL см. в статье [SQL](../../data/odbc/sql.md). Дополнительные сведения о сортировке записей см. в статье [набор записей: Сортировка записей (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

## <a name="crecordsetmove"></a><a name="move"></a>CRecordset:: Move

Перемещает указатель текущей записи в наборе записей вперед или назад.

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>Параметры

*nRows*<br/>
Число строк для перемещения вперед или назад. Положительные значения перемещаются вперед, ближе к концу набора записей. Отрицательные значения перемещаются назад в направлении к началу.

*вфетчтипе*<br/>
Определяет набор строк, который `Move` будет извлекаться. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

Если передать значение 0 для *nrows*, `Move` обновляет текущую запись, завершает `Move` текущий `AddNew` `Edit` режим или и восстанавливает значение текущей записи перед `AddNew` `Edit` вызовом или.

> [!NOTE]
> При перемещении по набору записей удаленные записи не пропускаются. Дополнительные сведения см. в разделе [CRecordset:: IsDeleted](#isdeleted) . Когда вы открываете `CRecordset` с `skipDeletedRecords` параметром, `Move` утверждает, если параметр *nrows* имеет значение 0. Такое поведение предотвращает обновление строк, удаленных другими клиентскими приложениями, использующими одни и те же данные. Описание см. в описании параметра *элемент dwoption* в разделе [Open](#open) `skipDeletedRecords` .

`Move`Перемещает набор записей по наборам строк. В зависимости от значений для *nrows* и *вфетчтипе* `Move` извлекает соответствующий набор строк, а затем делает первую запись в этом наборе строк текущей записью. Если вы не реализовали групповые выборке строк, то размер набора строк всегда равен 1. При изходе выборки набора строк `Move` напрямую вызывает функцию-член [чеккровсетеррор](#checkrowseterror) для выполнения любых ошибок, возникающих в результате выборки.

В зависимости от передаваемых значений значение `Move` эквивалентно другим `CRecordset` функциям-членам. В частности, значение *вфетчтипе* может указывать на функцию-член, которая более интуитивно понятна и часто является предпочтительным методом перемещения текущей записи.

В следующей таблице перечислены возможные значения для *вфетчтипе*, набор строк, который `Move` будет извлекаться на основе *вфетчтипе* и *nrows*, и все эквивалентные функции элементов, соответствующие *вфетчтипе*.

|вфетчтипе|Выборка набора строк|Эквивалентная функция элемента|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (значение по умолчанию)|Набор строк, запускающий строки *nrows* из первой строки текущего набора строк.||
|SQL_FETCH_NEXT|Следующий набор строк; *nrows* игнорируется.|[MoveNext](#movenext)|
|SQL_FETCH_PRIOR|Предыдущий набор строк; *nrows* игнорируется.|[мовепрев](#moveprev)|
|SQL_FETCH_FIRST|Первый набор строк в наборе записей; *nrows* игнорируется.|[MoveFirst](#movefirst)|
|SQL_FETCH_LAST|Последний полный набор строк в наборе записей; *nrows* игнорируется.|[MoveLast](#movelast)|
|SQL_FETCH_ABSOLUTE|Если *nRows* > 0, набор строк начинает *nrows* строки с начала набора записей. Если *nRows* < 0, набор строк начинает *nrows* строки из конца набора записей. Если *nrows* = 0, то возвращается условие начала файла (BOF).|[сетабсолутепоситион](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|Набор строк, начиная с строки, значение закладки которой соответствует *nrows*.|[сетбукмарк](#setbookmark)|

> [!NOTE]
> Для наборов записей только для перенаправления допускается `Move` только значение SQL_FETCH_NEXT для *вфетчтипе*.

> [!CAUTION]
> Вызов `Move` создает исключение, если набор записей не содержит записей. Чтобы определить, имеются ли записи в наборе записей, вызовите [исбоф](#isbof) и [исеоф](#iseof).

> [!NOTE]
> При прокрутке после начала или конца набора записей ( `IsBOF` или `IsEOF` возвращает ненулевое значение) вызов `Move` функции может вызвать исключение `CDBException` . Например, если функция `IsEOF` возвращает ненулевое значение и не `IsBOF` имеет, то выдаст `MoveNext` исключение, но `MovePrev` не будет.

> [!NOTE]
> При вызове `Move` во время обновления или добавления текущей записи обновления теряются без предупреждения.

Дополнительные сведения о переходе по набору записей см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Связанные сведения см. в описании функции API ODBC `SQLExtendedFetch` в Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

## <a name="crecordsetmovefirst"></a><a name="movefirst"></a>CRecordset:: MoveFirst

Делает первую запись в первом наборе строк текущей записью.

```cpp
void MoveFirst();
```

### <a name="remarks"></a>Примечания

Независимо от того, была ли реализована многострочная выборка строк, это всегда будет первой записью в наборе записей.

Не нужно вызывать `MoveFirst` немедленно после открытия набора записей. В этот момент первая запись (если она есть) автоматически становится текущей.

> [!NOTE]
> Эта функция-член недопустима для наборов записей только для последовательного доступа.

> [!NOTE]
> При перемещении по набору записей удаленные записи не пропускаются. Дополнительные сведения см. в функции элемента [IsDeleted](#isdeleted) .

> [!CAUTION]
> Вызов любой из `Move` функций вызывает исключение, если набор записей не содержит записей. Чтобы определить, содержит ли набор записей какие либо записи, вызовите `IsBOF` и `IsEOF` .

> [!NOTE]
> При вызове любой из `Move` функций во время обновления или добавления текущей записи обновления теряются без предупреждения.

Дополнительные сведения о переходе по набору записей см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  См. пример для [исбоф](#isbof).

## <a name="crecordsetmovelast"></a><a name="movelast"></a>CRecordset:: MoveLast

Делает первую запись в последнем наборе строк текущей записью.

```cpp
void MoveLast();
```

### <a name="remarks"></a>Примечания

Если не реализована многострочная выборка строк, то набор записей имеет размер набора строк, равный 1, поэтому `MoveLast` просто переходит к последней записи в наборе записей.

> [!NOTE]
> Эта функция-член недопустима для наборов записей только для последовательного доступа.

> [!NOTE]
> При перемещении по набору записей удаленные записи не пропускаются. Дополнительные сведения см. в функции элемента [IsDeleted](#isdeleted) .

> [!CAUTION]
> Вызов любой из `Move` функций вызывает исключение, если набор записей не содержит записей. Чтобы определить, содержит ли набор записей какие либо записи, вызовите `IsBOF` и `IsEOF` .

> [!NOTE]
> При вызове любой из `Move` функций во время обновления или добавления текущей записи обновления теряются без предупреждения.

Дополнительные сведения о переходе по набору записей см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  См. пример для [исбоф](#isbof).

## <a name="crecordsetmovenext"></a><a name="movenext"></a>Метод CRecordset:: MoveNext

Делает первую запись в следующем наборе строк текущей записью.

```cpp
void MoveNext();
```

### <a name="remarks"></a>Примечания

Если не реализована многострочная выборка строк, то набор записей имеет размер набора строк, равный 1, поэтому `MoveNext` просто переходит к следующей записи.

> [!NOTE]
> При перемещении по набору записей удаленные записи не пропускаются. Дополнительные сведения см. в функции элемента [IsDeleted](#isdeleted) .

> [!CAUTION]
> Вызов любой из `Move` функций вызывает исключение, если набор записей не содержит записей. Чтобы определить, содержит ли набор записей какие либо записи, вызовите `IsBOF` и `IsEOF` .

> [!NOTE]
> Также рекомендуется вызвать метод `IsEOF` перед вызовом метода `MoveNext` . Например, если прокрутить до конца набора записей, вернет `IsEOF` ненулевое значение; при последующем вызове метода будет `MoveNext` создано исключение.

> [!NOTE]
> При вызове любой из `Move` функций во время обновления или добавления текущей записи обновления теряются без предупреждения.

Дополнительные сведения о переходе по набору записей см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  См. пример для [исбоф](#isbof).

## <a name="crecordsetmoveprev"></a><a name="moveprev"></a>CRecordset:: Мовепрев

Делает первую запись в предыдущем наборе строк текущей записью.

```cpp
void MovePrev();
```

### <a name="remarks"></a>Примечания

Если не реализована многострочная выборка строк, то набор записей имеет размер набора строк, равный 1, поэтому `MovePrev` просто переходит к предыдущей записи.

> [!NOTE]
> Эта функция-член недопустима для наборов записей только для последовательного доступа.

> [!NOTE]
> При перемещении по набору записей удаленные записи не пропускаются. Дополнительные сведения см. в функции элемента [IsDeleted](#isdeleted) .

> [!CAUTION]
> Вызов любой из `Move` функций вызывает исключение, если набор записей не содержит записей. Чтобы определить, содержит ли набор записей какие либо записи, вызовите `IsBOF` и `IsEOF` .

> [!NOTE]
> Также рекомендуется вызвать метод `IsBOF` перед вызовом метода `MovePrev` . Например, если вы выполнили прокрутку перед началом набора записей, вернет `IsBOF` ненулевое значение; при последующем вызове метода будет `MovePrev` создано исключение.

> [!NOTE]
> При вызове любой из `Move` функций во время обновления или добавления текущей записи обновления теряются без предупреждения.

Дополнительные сведения о переходе по набору записей см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  См. пример для [исбоф](#isbof).

## <a name="crecordsetonsetoptions"></a><a name="onsetoptions"></a>CRecordset:: Онсетоптионс

Вызывается для задания параметров (используемых в выделении) для указанной инструкции ODBC.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Параметры

*hstmt*<br/>
ХСТМТ инструкции ODBC, параметры которой должны быть заданы.

### <a name="remarks"></a>Примечания

Вызовите метод `OnSetOptions` , чтобы задать параметры (используемые для выбора) для указанной инструкции ODBC. Платформа вызывает эту функцию члена, чтобы задать начальные параметры для набора записей. `OnSetOptions`Определяет поддержку источника данных прокручиваемых курсоров и для параллелизма курсора и задает соответствующие параметры набора записей. (В то время как используется `OnSetOptions` для операций выбора, `OnSetUpdateOptions` используется для операций обновления.)

Переопределите `OnSetOptions` , чтобы задать параметры, относящиеся к драйверу или источнику данных. Например, если источник данных поддерживает открытие для монопольного доступа, вы можете переопределить `OnSetOptions` , чтобы воспользоваться этой возможностью.

Дополнительные сведения о курсорах см. в статье [ODBC](../../data/odbc/odbc-basics.md).

## <a name="crecordsetonsetupdateoptions"></a><a name="onsetupdateoptions"></a>CRecordset:: Онсетупдатеоптионс

Вызывается для задания параметров (используемых при обновлении) для указанной инструкции ODBC.

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Параметры

*hstmt*<br/>
ХСТМТ инструкции ODBC, параметры которой должны быть заданы.

### <a name="remarks"></a>Примечания

Вызовите метод `OnSetUpdateOptions` , чтобы задать параметры (используемые при обновлении) для указанной инструкции ODBC. Платформа вызывает эту функцию-член после того, как создаст ХСТМТ для обновления записей в наборе записей. (В то время как используется `OnSetOptions` для операций выбора, `OnSetUpdateOptions` используется для операций обновления.) `OnSetUpdateOptions` определяет поддержку для прокручиваемых курсоров и для параллелизма курсора и задает соответствующие параметры набора записей.

Переопределите, `OnSetUpdateOptions` чтобы задать параметры инструкции ODBC перед тем, как использовать эту инструкцию для доступа к базе данных.

Дополнительные сведения о курсорах см. в статье [ODBC](../../data/odbc/odbc-basics.md).

## <a name="crecordsetopen"></a><a name="open"></a>CRecordset:: Open

Открывает набор записей, получая таблицу или выполняя запрос, представляемый набором записей.

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>Параметры

*нопентипе*<br/>
Примите значение по умолчанию AFX_DB_USE_DEFAULT_TYPE или используйте одно из следующих значений из `enum OpenType` :

- `CRecordset::dynaset`Набор записей с двунаправленной прокруткой. Членство и порядок записей определяются при открытии набора записей, но изменения, внесенные другими пользователями в значения данных, видимы после операции выборки. Динамические подмножества данных также называются наборами записей, основанными на наборе ключей.

- `CRecordset::snapshot`Статический набор записей с двунаправленной прокруткой. Членство и порядок записей определяются при открытии набора записей. значения данных определяются при выборке записей. Изменения, внесенные другими пользователями, не видны, пока набор записей не будет закрыт и снова открыт.

- `CRecordset::dynamic`Набор записей с двунаправленной прокруткой. Изменения, внесенные другими пользователями в членство, порядок и значения данных, отображаются после операции выборки. Обратите внимание, что многие драйверы ODBC не поддерживают этот тип набора записей.

- `CRecordset::forwardOnly`Набор записей только для чтения с прямой прокруткой.

   Для `CRecordset` значение по умолчанию — `CRecordset::snapshot` . Механизм значения по умолчанию позволяет мастерам Visual C++ взаимодействовать с ODBC `CRecordset` и DAO `CDaoRecordset` , которые имеют разные значения по умолчанию.

Дополнительные сведения об этих типах наборов записей см. в статье [набор записей (ODBC)](../../data/odbc/recordset-odbc.md). Дополнительные сведения см. в статье «Использование блочных и прокручиваемых курсоров» в Windows SDK.

> [!CAUTION]
> Если запрошенный тип не поддерживается, платформа создает исключение.

*lpszSQL*<br/>
Указатель на строку, содержащий один из следующих элементов:

- ПУСТОЙ указатель.

- Имя таблицы.

- Инструкция SQL **SELECT** (при необходимости с предложением SQL **WHERE** или **ORDER BY** ).

- Оператор **Call** , указывающий имя предопределенного запроса (хранимой процедуры). Будьте внимательны, чтобы не вставлять пробел между фигурными скобками и ключевым словом **Call** .

Дополнительные сведения об этой строке см. в таблице и обсуждении роли ClassWizard в разделе ["Примечания"](#remarks) .

> [!NOTE]
> Порядок столбцов в результирующем наборе должен совпадать с порядком вызовов функций RFX или Массовы RFX в переопределении функции [DoFieldExchange](#dofieldexchange) или [добулкфиелдексчанже](#dobulkfieldexchange) .

*двоптионс*<br/>
Битовая маска, которая может задавать сочетание значений, перечисленных ниже. Некоторые из них являются взаимоисключающими. Значение по умолчанию — **None**.

- `CRecordset::none`Параметры не заданы. Значение этого параметра является взаимоисключающим со всеми другими значениями. По умолчанию набор записей может быть обновлен с помощью [Edit](#edit) или [Delete](#delete) и допускает добавление новых записей с помощью [AddNew](#addnew). Возможность обновления зависит от источника данных, а также от указанного параметра *нопентипе* . Оптимизация для небольшого количества добавлений недоступна. Групповая выборка строк не будет реализована. Удаленные записи не будут пропущены во время навигации по набору записей. Закладки недоступны. Реализована автоматическая проверка "грязных" полей.

- `CRecordset::appendOnly`Не разрешать `Edit` или не использовать `Delete` набор записей. Разрешить `AddNew` только. Этот параметр является взаимоисключающим с `CRecordset::readOnly` .

- `CRecordset::readOnly`Откройте набор записей как "только для чтения". Этот параметр является взаимоисключающим с `CRecordset::appendOnly` .

- `CRecordset::optimizeBulkAdd`Используйте подготовленную инструкцию SQL, чтобы оптимизировать Добавление нескольких записей за один раз. Применяется только в том случае, если не используется функция ODBC API `SQLSetPos` для обновления набора записей. Первое обновление определяет, какие поля помечены как "грязные". Этот параметр является взаимоисключающим с `CRecordset::useMultiRowFetch` .

- `CRecordset::useMultiRowFetch`Реализовать групповую выборку строк, чтобы разрешить получение нескольких строк в одной операции выборки. Это расширенная функция, предназначенная для повышения производительности; Однако ClassWizard не поддерживает обмен полями с массовыми записями. Этот параметр является взаимоисключающим с `CRecordset::optimizeBulkAdd` . Обратите внимание, что если указать `CRecordset::useMultiRowFetch` , параметр `CRecordset::noDirtyFieldCheck` будет включен автоматически (двойная буферизация будет недоступна); в наборе записей с последовательным доступом параметр `CRecordset::useExtendedFetch` будет включен автоматически. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

- `CRecordset::skipDeletedRecords`Пропустить все удаленные записи при переходе по набору записей. Это приведет к снижению производительности в определенных относительных выборках. Этот параметр является недопустимым для наборов записей с последовательным входом. При вызове [Move](#move) с параметром *nrows* , установленным в значение 0, и `CRecordset::skipDeletedRecords` набором параметров `Move` будет Assert. Обратите внимание, что `CRecordset::skipDeletedRecords` аналогично *упаковке драйвера*, то есть удаленные строки удаляются из набора записей. Однако если пакеты драйверов записываются, то будут пропущены только те записи, которые вы удалите. записи, удаленные другими пользователями, не будут пропускаться, пока открыт набор записей. `CRecordset::skipDeletedRecords`пропустит строки, удаленные другими пользователями.

- `CRecordset::useBookmarks`Может использовать закладки в наборе записей, если они поддерживаются. Закладки замедляют получение данных, но улучшают производительность при навигации по данным. Недопустимо использовать в наборах записей последовательного доступа. Дополнительные сведения см. в статье [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

- `CRecordset::noDirtyFieldCheck`Отключите автоматическую проверку измененных полей (двойная буферизация). Это повысит производительность. Однако необходимо вручную пометить поля как "грязные", вызвав `SetFieldDirty` `SetFieldNull` функции и. Обратите внимание, что двойная буферизация в классе `CRecordset` аналогична двойной буферизации в классе `CDaoRecordset` . Однако в `CRecordset` нельзя включить двойную буферизацию для отдельных полей, либо включить ее для всех полей, либо отключить для всех полей. Обратите внимание, что если указать параметр `CRecordset::useMultiRowFetch` , `CRecordset::noDirtyFieldCheck` он будет включен автоматически, однако `SetFieldDirty` и `SetFieldNull` не может использоваться для наборов записей, реализующих многострочную выборку строк.

- `CRecordset::executeDirect`Не используйте подготовленную инструкцию SQL. Для повышения производительности укажите этот параметр, если `Requery` функция члена никогда не будет вызываться.

- `CRecordset::useExtendedFetch`Реализуйте `SQLExtendedFetch` вместо `SQLFetch` . Это предназначено для реализации групповой выборки строк для наборов записей с последовательным входом. Если указать параметр `CRecordset::useMultiRowFetch` в наборе записей последовательного доступа, `CRecordset::useExtendedFetch` он будет включен автоматически.

- `CRecordset::userAllocMultiRowBuffers`Пользователь будет выделять буферы хранилища для данных. Используйте этот параметр вместе с `CRecordset::useMultiRowFetch` , если требуется выделить собственное хранилище. в противном случае платформа автоматически выделит необходимое хранилище. Дополнительные сведения см. в статье [набор записей: групповое извлечение записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Обратите внимание, что указание `CRecordset::userAllocMultiRowBuffers` без указания `CRecordset::useMultiRowFetch` приводит к неудачному утверждению.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если `CRecordset` объект был успешно открыт; в противном случае — 0, если метод [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) (если вызывается) возвращает значение 0.

### <a name="remarks"></a>Примечания

Для выполнения запроса, определяемого набором записей, необходимо вызвать эту функцию члена. Перед вызовом `Open` необходимо создать объект набора записей.

Соединение этого набора записей с источником данных зависит от способа создания набора записей перед вызовом метода `Open` . Если передать объект [CDatabase](../../mfc/reference/cdatabase-class.md) в конструктор набора записей, который не был подключен к источнику данных, эта функция-член использует [жетдефаултконнект](#getdefaultconnect) , чтобы попытаться открыть объект базы данных. Если передать значение NULL конструктору набора записей, конструктор создаст `CDatabase` объект и `Open` попытается подключиться к объекту базы данных. Дополнительные сведения о закрытии набора записей и подключении в этих различных обстоятельствах см. в разделе [Close](#close).

> [!NOTE]
> Доступ к источнику данных через `CRecordset` объект всегда является общим. В отличие от `CDaoRecordset` класса, объект нельзя использовать `CRecordset` для открытия источника данных с монопольным доступом.

При вызове `Open` запрос, обычно инструкция SQL **SELECT** , выбирает записи на основе критериев, показанных в следующей таблице.

|Значение параметра lpszSQL|Выбранные записи определяются|Пример|
|------------------------------------|----------------------------------------|-------------|
|NULL|Строка, возвращаемая методом `GetDefaultSQL` .||
|Имя таблицы SQL|Все столбцы списка таблиц в `DoFieldExchange` или `DoBulkFieldExchange` .|`"Customer"`|
|Предопределенное имя запроса (хранимая процедура)|Столбцы, возвращаемые запросом.|`"{call OverDueAccts}"`|
|**Выберите** столбец-список **из** таблицы-список|Указанные столбцы из указанных таблиц.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
> Будьте внимательны, чтобы не вставлять лишние пробелы в строку SQL. Например, если вставить пробел между фигурными скобками и ключевым словом **Call** , MFC будет ошибочно ИНТЕРПРЕТИРОВАТЬ строку SQL как имя таблицы и включить ее в инструкцию **SELECT** , что приведет к возникновению исключения. Аналогично, если в предопределенном запросе используется выходной параметр, не вставляйте пробелы между фигурными скобками и символом "". Наконец, не следует вставлять пробелы перед фигурными скобками в операторе **Call** или перед ключевым словом **SELECT** в инструкции **SELECT** .

Обычная процедура заключается в передаче NULL в `Open` ; в этом случае `Open` вызывает функцию [GetDefaultSQL](#getdefaultsql). При использовании производного `CRecordset` класса `GetDefaultSQL` присваивает имена таблиц, указанных в ClassWizard. Вместо этого можно указать другие сведения в `lpszSQL` параметре.

Все, что вы передали, `Open` конструирует конечную строку SQL для запроса (строка может содержать предложения **WHERE** и **ORDER BY** , добавленные к `lpszSQL` переданной строке), а затем выполняет запрос. Вы можете проверить созданную строку, вызвав [жетскл](#getsql) после вызова метода `Open` . Дополнительные сведения о том, как набор записей формирует инструкцию SQL и выбирает записи, см. в статье [набор записей: как наборы записей выбирают записи (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

Элементы данных поля класса Recordset привязаны к столбцам выбранных данных. Если возвращаются какие бы то ни было записи, первая запись станет текущей.

Если вы хотите задать параметры для набора записей, например фильтр или сортировку, укажите их после создания объекта набора записей, но перед вызовом `Open` . Если необходимо обновить записи в наборе записей после того, как набор записей уже открыт, вызовите метод [Requery](#requery).

Дополнительные сведения, включая дополнительные примеры, см. в статьях [набор записей (ODBC)](../../data/odbc/recordset-odbc.md), [набор записей: как наборы записей выбор записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)и [набор записей: создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

### <a name="example"></a>Пример

В следующих примерах кода показаны различные формы `Open` вызова.

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

## <a name="crecordsetrefreshrowset"></a><a name="refreshrowset"></a>CRecordset:: Рефрешровсет

Обновляет данные и состояние строки в текущем наборе строк.

```cpp
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Параметры

*вров*<br/>
Порядковый номер строки в текущем наборе строк, отсчитываемый от единицы. Это значение может варьироваться от нуля до размера набора строк.

*влокктипе*<br/>
Значение, указывающее, как заблокировать строку после ее обновления. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

Если для *вров*передается нулевое значение, то каждая строка в наборе строк будет обновлена.

Для использования необходимо `RefreshRowset` реализовать многострочную выборку строк, указав `CRecordset::useMulitRowFetch` параметр в функции [Open](#open) Member.

`RefreshRowset`вызывает функцию API ODBC `SQLSetPos` . Параметр *влокктипе* задает состояние блокировки строки после `SQLSetPos` ее выполнения. В следующей таблице описаны возможные значения для *влокктипе*.

|влокктипе|Описание|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (значение по умолчанию)|Драйвер или источник данных гарантирует, что строка находится в том же заблокированном или разблокированном состоянии, как и до `RefreshRowset` вызова метода.|
|SQL_LOCK_EXCLUSIVE|Драйвер или источник данных блокирует строку в монопольном режиме. Не все источники данных поддерживают этот тип блокировки.|
|SQL_LOCK_UNLOCK|Драйвер или источник данных разблокирует строку. Не все источники данных поддерживают этот тип блокировки.|

Дополнительные сведения о `SQLSetPos` см. в Windows SDK. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetrequery"></a><a name="requery"></a>CRecordset:: Requery

Перестраивает (обновляет) набор записей.

```
virtual BOOL Requery();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей был успешно перестроен; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если возвращаются какие бы то ни было записи, первая запись станет текущей.

Чтобы набор записей отражал добавленные и удаляемые вами или другими пользователями данные в источнике данных, необходимо перестроить набор записей путем вызова `Requery` . Если набор записей является динамическим, он автоматически отражает обновления, внесенные вами или другими пользователями в существующие записи (но не дополнения). Если набор записей является моментальным снимком, необходимо вызвать `Requery` , чтобы отразить изменения других пользователей, а также добавления и удаления.

Для динамического или моментального снимка необходимо вызвать `Requery` любое время для перестроения набора записей с помощью нового фильтра или сортировки или новых значений параметров. Задайте новое свойство Filter или Sort, назначив новые значения `m_strFilter` и `m_strSort` перед вызовом `Requery` . Задайте новые параметры, назначив новые значения членам данных параметров перед вызовом `Requery` . Если строки фильтра и сортировки не изменяются, можно повторно использовать запрос, что повышает производительность.

Если попытка перестроения набора записей завершается ошибкой, набор записей закрывается. Перед вызовом `Requery` можно определить, можно ли выполнить повторный запрос к набору записей, вызвав `CanRestart` функцию члена. `CanRestart`не гарантирует, что `Requery` будет выполнена.

> [!CAUTION]
> Вызывайте `Requery` только после вызова [Open](#open).

### <a name="example"></a>Пример

В этом примере выполняется перестроение набора записей для применения другого порядка сортировки.

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

## <a name="crecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>CRecordset:: Сетабсолутепоситион

Размещает набор записей для записи, соответствующей указанному номеру записи.

```cpp
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>Параметры

*nRows*<br/>
Порядковый номер, отсчитываемый от единицы по отношению к текущей записи в наборе записей.

### <a name="remarks"></a>Примечания

`SetAbsolutePosition`Перемещает указатель текущей записи на основе этой позиции.

> [!NOTE]
> Эта функция-член недопустима для наборов записей с последовательным входом.

Для наборов записей ODBC параметр абсолютного позиционирования, равный 1, ссылается на первую запись в наборе записей; значение 0 указывает на расположение начала файла (BOF).

Можно также передать отрицательные значения в `SetAbsolutePosition` . В этом случае расположение набора записей вычисляется с конца набора записей. Например, `SetAbsolutePosition( -1 )` перемещает указатель текущей записи на последнюю запись в наборе записей.

> [!NOTE]
> Абсолютное положение не предназначено для использования в качестве номера записи-заместителя. Закладки по-прежнему являются рекомендуемым способом удержания и возврата в заданную точку, так как при удалении предыдущих записей изменяется ее расположение. Кроме того, нельзя быть уверены, что данная запись будет иметь ту же абсолютное положение, если набор записей снова создается повторно, так как порядок отдельных записей в наборе записей не гарантируется, если он не создан с помощью инструкции SQL с предложением **ORDER BY** .

Дополнительные сведения о переходе по набору записей и закладок см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

## <a name="crecordsetsetbookmark"></a><a name="setbookmark"></a>CRecordset:: Сетбукмарк

Размещает набор записей для записи, содержащей указанную закладку.

```cpp
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>Параметры

*варбукмарк*<br/>
Ссылка на объект [кдбвариант](../../mfc/reference/cdbvariant-class.md) , содержащий значение закладки для конкретной записи.

### <a name="remarks"></a>Примечания

Чтобы определить, поддерживаются ли закладки в наборе записей, вызовите [канбукмарк](#canbookmark). Чтобы сделать закладки доступными, если они поддерживаются, необходимо задать `CRecordset::useBookmarks` параметр в параметре *Двоптионс* функции [Open](#open) Member.

> [!NOTE]
> Если закладки не поддерживаются или недоступны, вызов `SetBookmark` приводит к возникновению исключения. Закладки не поддерживаются для наборов записей с последовательным входом.

Чтобы сначала получить закладку для текущей записи, вызовите метод «@ [Bookmark](#getbookmark)», который сохраняет значение закладки в `CDBVariant` объекте. Позже можно будет вернуться к этой записи, вызвав `SetBookmark` с помощью сохраненного значения закладки.

> [!NOTE]
> После выполнения определенных операций с набором записей следует проверить сохраняемость закладки перед вызовом метода `SetBookmark` . Например, если вы получаете закладку с `GetBookmark` , а затем вызываете `Requery` , закладка может стать недействительной. Вызовите метод [CDatabase:: жетбукмаркперсистенце](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) , чтобы проверить, можно ли безопасно вызвать `SetBookmark` .

Дополнительные сведения о закладках и навигации по наборам записей см. в статьях [набор записей: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [Recordset: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="crecordsetsetfielddirty"></a><a name="setfielddirty"></a>CRecordset:: Сетфиелддирти

Помечает элемент данных поля набора записей как измененный или как неизмененный.

```cpp
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Содержит адрес элемента данных поля в наборе записей или значение NULL. Если значение равно NULL, все элементы данных полей в наборе записей помечаются как помеченные. (C++ NULL не совпадает со значением NULL в терминологии базы данных, что означает отсутствие значения.)

*бдирти*<br/>
Значение TRUE, если элемент данных поля должен быть помечен как "грязный" (измененный). В противном случае FALSE, если элемент данных поля должен быть помечен как "чистый" (без изменений).

### <a name="remarks"></a>Примечания

Пометка полей как неизмененных гарантирует, что поле не будет обновлено и в результате будет меньше трафика SQL.

> [!NOTE]
> Эта функция-член неприменима к наборам записей, использующим групповые выборке строк. Если вы реализовали групповые выборке строк, то `SetFieldDirty` приведет к неудачному утверждению. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Платформа помечает измененные элементы данных поля, чтобы убедиться, что они будут записаны в запись источника данных с помощью механизма обмена полями записей (RFX). Изменение значения поля обычно устанавливает поле как «грязный» автоматически, поэтому вам редко приходится вызывать `SetFieldDirty` себя, но иногда может потребоваться обеспечить явное обновление или вставку столбцов независимо от значения в элементе данных поля.

> [!CAUTION]
> Вызывайте эту функцию члена только после вызова [Edit](#edit) или [AddNew](#addnew).

Использование значения NULL для первого аргумента функции приведет к применению функции только к `outputColumn` полям, а не к `param` полям. Например, вызов

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

устанавливает только `outputColumn` поля в значение NULL; `param` поля не затрагиваются.

Для работы с `param` полями необходимо указать фактический адрес человека, с которым `param` вы хотите работать, например:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Это означает, что нельзя задать `param` для всех полей значение null, как это можно сделать с `outputColumn` полями.

## <a name="crecordsetsetfieldnull"></a><a name="setfieldnull"></a>CRecordset:: Сетфиелднулл

Помечает элемент данных поля набора записей как null (в частности без значения) или как значение, отличное от NULL.

```cpp
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Содержит адрес элемента данных поля в наборе записей или значение NULL. Если значение равно NULL, все элементы данных полей в наборе записей помечаются как помеченные. (C++ NULL не совпадает со значением NULL в терминологии базы данных, что означает отсутствие значения.)

*бнулл*<br/>
Ненулевое значение, если элемент данных поля должен быть помечен как не имеющий значения (null). В противном случае 0, если элемент данных поля должен быть помечен как не равный null.

### <a name="remarks"></a>Примечания

При добавлении новой записи в набор записей все элементы данных полей изначально устанавливаются в значение NULL и помечаются как "грязные" (изменено). При извлечении записи из источника данных ее столбцы либо уже имеют значения, либо имеют значение null.

> [!NOTE]
> Не вызывайте эту функцию члена для наборов записей, использующих функцию групповой выборки строк. При реализации групповой выборки строк вызов `SetFieldNull` приводит к неудачному утверждению. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Если вы хотите, чтобы поле текущей записи было назначено без значения, вызовите `SetFieldNull` с параметром *бнулл* , имеющим значение true, чтобы пометить его как null. Если поле ранее было отмечено как null, и теперь нужно присвоить ему значение, просто задайте его новое значение. Нет необходимости удалять флаг NULL с `SetFieldNull` . Чтобы определить, может ли поле иметь значение null, вызовите `IsFieldNullable` .

> [!CAUTION]
> Вызывайте эту функцию члена только после вызова [Edit](#edit) или [AddNew](#addnew).

Использование значения NULL для первого аргумента функции приведет к применению функции только к `outputColumn` полям, а не к `param` полям. Например, вызов

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

устанавливает только `outputColumn` поля в значение NULL; `param` поля не затрагиваются.

Для работы с `param` полями необходимо указать фактический адрес человека, с которым `param` вы хотите работать, например:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Это означает, что нельзя задать `param` для всех полей значение null, как это можно сделать с `outputColumn` полями.

> [!NOTE]
> При установке параметров в значение NULL вызов `SetFieldNull` перед открытием набора записей приводит к утверждению. В этом случае вызовите [сетпарамнулл](#setparamnull).

`SetFieldNull`реализуется с помощью [DoFieldExchange](#dofieldexchange).

## <a name="crecordsetsetlockingmode"></a><a name="setlockingmode"></a>CRecordset:: Сетлоккингмоде

Устанавливает режим блокировки «Оптимистическая» блокировка (по умолчанию) или «пессимистическая» блокировка. Определяет, как записи блокируются для обновлений.

```cpp
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>Параметры

*нмоде*<br/>
Содержит одно из следующих значений из `enum LockMode` :

- `optimistic`Оптимистическая блокировка блокирует обновляемую запись только во время вызова `Update` .

- `pessimistic`Пессимистическая блокировка блокирует запись сразу же после `Edit` вызова и сохраняет ее до тех пор, пока не `Update` завершится вызов или не перейдете на новую запись.

### <a name="remarks"></a>Примечания

Эту функцию-член следует вызывать, если необходимо указать, какие из двух стратегий блокировки записей использует набор записей для обновлений. По умолчанию режим блокировки набора записей — `optimistic` . Это можно сделать более `pessimistic` стратегией блокировки с осторожностью. Вызовите `SetLockingMode` после создания и открытия объекта Recordset, но перед вызовом `Edit` .

## <a name="crecordsetsetparamnull"></a><a name="setparamnull"></a>CRecordset:: Сетпарамнулл

Помечает параметр как null (без значения) или как значение, отличное от NULL.

```cpp
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Отсчитываемый с нуля индекс параметра.

*бнулл*<br/>
Если TRUE (значение по умолчанию), параметр помечается как null. В противном случае параметр помечается как не имеющий значение null.

### <a name="remarks"></a>Примечания

В отличие от [сетфиелднулл](#setfieldnull), можно вызвать `SetParamNull` перед открытием набора записей.

`SetParamNull`обычно используется с предопределенными запросами (хранимыми процедурами).

## <a name="crecordsetsetrowsetcursorposition"></a><a name="setrowsetcursorposition"></a>CRecordset:: Сетровсеткурсорпоситион

Перемещает курсор в строку в текущем наборе строк.

```cpp
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Параметры

*вров*<br/>
Порядковый номер строки в текущем наборе строк, отсчитываемый от единицы. Это значение может находиться в диапазоне от 1 до размера набора строк.

*влокктипе*<br/>
Значение, указывающее, как заблокировать строку после ее обновления. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

При реализации групповой выборки строк записи извлекаются наборами строк, где первая запись в извлеченном наборе строк является текущей записью. Чтобы сделать другую запись в наборе строк текущей записи, вызовите `SetRowsetCursorPosition` . Например, можно объединить `SetRowsetCursorPosition` с функцией члена [GetFieldValue](#getfieldvalue) , чтобы динамически получать данные из любой записи набора записей.

Для использования необходимо `SetRowsetCursorPosition` реализовать многострочную выборку строк, указав `CRecordset::useMultiRowFetch` параметр параметра *Двоптионс* в функции [Open](#open) Member.

`SetRowsetCursorPosition`вызывает функцию API ODBC `SQLSetPos` . Параметр *влокктипе* задает состояние блокировки строки после `SQLSetPos` ее выполнения. В следующей таблице описаны возможные значения для *влокктипе*.

|влокктипе|Описание|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (значение по умолчанию)|Драйвер или источник данных гарантирует, что строка находится в том же заблокированном или разблокированном состоянии, как и до `SetRowsetCursorPosition` вызова метода.|
|SQL_LOCK_EXCLUSIVE|Драйвер или источник данных блокирует строку в монопольном режиме. Не все источники данных поддерживают этот тип блокировки.|
|SQL_LOCK_UNLOCK|Драйвер или источник данных разблокирует строку. Не все источники данных поддерживают этот тип блокировки.|

Дополнительные сведения о `SQLSetPos` см. в Windows SDK. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetsetrowsetsize"></a><a name="setrowsetsize"></a>CRecordset:: Сетровсетсизе

Указывает количество записей, которые необходимо получить во время выборки.

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>Параметры

*двневровсетсизе*<br/>
Число строк, извлекаемых во время данной выборки.

### <a name="remarks"></a>Примечания

Эта виртуальная функция-член указывает, сколько строк вы хотите получить во время одной выборки при использовании групповой выборки строк. Для реализации групповой выборки строк необходимо задать `CRecordset::useMultiRowFetch` параметр в параметре *Двоптионс* функции [Open](#open) Member.

> [!NOTE]
> Вызов `SetRowsetSize` без реализации групповой выборки строк приведет к неудачному утверждению.

Вызовите метод `SetRowsetSize` перед вызовом метода, `Open` чтобы изначально задать размер набора строк для набора записей. Размер набора строк по умолчанию при реализации групповой выборки строк равен 25.

> [!NOTE]
> Будьте внимательны при вызове `SetRowsetSize` . Если вы вручную выделяете хранилище для данных (как указано `CRecordset::userAllocMultiRowBuffers` параметром параметра двоптионс в `Open` ), следует проверить, нужно ли перераспределять эти буферы хранения после вызова `SetRowsetSize` , но до выполнения любой операции перехода курсора.

Чтобы получить текущую настройку для размера набора строк, вызовите [жетровсетсизе](#getrowsetsize).

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetupdate"></a><a name="update"></a>CRecordset:: Update

Завершает `AddNew` `Edit` операцию или, сохраняя новые или измененные данные в источнике данных.

```
virtual BOOL Update();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если одна запись успешно обновлена; в противном случае — 0, если столбцы не изменялись. Если ни одна из записей не обновлялась или было обновлено более одной записи, создается исключение. Кроме того, для любого другого сбоя в источнике данных выдается исключение.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член после вызова функции-члена [AddNew](#addnew) или [Edit](#edit) . Этот вызов необходим для завершения `AddNew` `Edit` операции или.

> [!NOTE]
> При реализации групповой выборки строк нельзя вызвать `Update` . Это приведет к неудачному утверждению. Хотя класс не `CRecordset` предоставляет механизм для обновления строк данных, можно написать собственные функции с помощью функции API ODBC `SQLSetPos` . Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`AddNew`И, и `Edit` подготавливают буфер редактирования, в котором добавленные или измененные данные помещаются для сохранения в источнике данных. `Update`сохраняет данные. Обновляются только поля, помеченные или обнаруженные как измененные.

Если источник данных поддерживает транзакции, можно сделать `Update` вызов (и его соответствующий `AddNew` или `Edit` вызов) частью транзакции. Дополнительные сведения о транзакциях см. в описании [транзакции статьи (ODBC)](../../data/odbc/transaction-odbc.md).

> [!CAUTION]
> При вызове `Update` без предварительного вызова либо `AddNew` `Edit` `Update` вызывает исключение `CDBException` . При вызове `AddNew` или `Edit` необходимо вызвать метод `Update` перед вызовом `Move` операции или перед закрытием набора записей или соединения с источником данных. В противном случае изменения будут потеряны без уведомления.

Дополнительные сведения об обработке `Update` сбоев см. в статье [набор записей: как набор записей обновляет записи (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

### <a name="example"></a>Пример

См. статью [транзакция: выполнение транзакции в наборе записей (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

## <a name="see-also"></a>См. также раздел

[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Класс CRecordView](../../mfc/reference/crecordview-class.md)
