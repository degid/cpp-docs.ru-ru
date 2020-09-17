---
title: Класс CHttpfile
ms.date: 11/04/2016
f1_keywords:
- CHttpFile
- AFXINET/CHttpFile
- AFXINET/CHttpFile::CHttpFile
- AFXINET/CHttpFile::AddRequestHeaders
- AFXINET/CHttpFile::EndRequest
- AFXINET/CHttpFile::GetFileURL
- AFXINET/CHttpFile::GetObject
- AFXINET/CHttpFile::GetVerb
- AFXINET/CHttpFile::QueryInfo
- AFXINET/CHttpFile::QueryInfoStatusCode
- AFXINET/CHttpFile::SendRequest
- AFXINET/CHttpFile::SendRequestEx
helpviewer_keywords:
- CHttpFile [MFC], CHttpFile
- CHttpFile [MFC], AddRequestHeaders
- CHttpFile [MFC], EndRequest
- CHttpFile [MFC], GetFileURL
- CHttpFile [MFC], GetObject
- CHttpFile [MFC], GetVerb
- CHttpFile [MFC], QueryInfo
- CHttpFile [MFC], QueryInfoStatusCode
- CHttpFile [MFC], SendRequest
- CHttpFile [MFC], SendRequestEx
ms.assetid: 399e7c68-bbce-4374-8c55-206e9c7baac6
ms.openlocfilehash: cba3ba7d86577703de2bf5709d66bbd5e0298863
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368391"
---
# <a name="chttpfile-class"></a>Класс CHttpfile

Предоставляет функции для запроса и чтения файлов на HTTP-сервере.

## <a name="syntax"></a>Синтаксис

```
class CHttpFile : public CInternetFile
```

## <a name="members"></a>Участники

### <a name="protected-constructors"></a>Защищенные конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHttpfile::CHttpfile](#chttpfile)|Создает объект `CHttpFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHttpFile::AddRequestHeaders](#addrequestheaders)|Добавляет заголовки в запрос, отправленный на сервер HTTP.|
|[CHttpFile::EndRequest](#endrequest)|Завершает запрос, отправленный на сервер HTTP с функцией участника [SendRequestEx.](#sendrequestex)|
|[CHttpFile::GetFileURL](#getfileurl)|Получает URL для указанного файла.|
|[CHttpFile::GetObject](#getobject)|Получает целевой объект глагола в запросе на сервер HTTP.|
|[CHttpFile::GetVerb](#getverb)|Получает глагол, который использовался в запросе на сервер HTTP.|
|[CHttpFile::КеприИнфо](#queryinfo)|Возвращает заголовки ответов или запросов с сервера HTTP.|
|[CHttpFile::Квиинфостатускокод](#queryinfostatuscode)|Извлекает код состояния, связанный с запросом `dwStatusCode` HTTP, и помещает его в поставляемый параметр.|
|[CHttpFile::SendRequest](#sendrequest)|Отправляет запрос на сервер HTTP.|
|[CHttpFile::SendRequestEx](#sendrequestex)|Отправляет запрос на сервер HTTP с помощью методов `CInternetFile` [Write](../../mfc/reference/cinternetfile-class.md#write) или [WriteString.](../../mfc/reference/cinternetfile-class.md#writestring)|

## <a name="remarks"></a>Примечания

Если сеанс Интернета считывает данные с сервера `CHttpFile`HTTP, необходимо создать экземпляр:

Чтобы узнать `CHttpFile` больше о том, как работает с другими классами МФЦ Интернет, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CHttpFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="chttpfileaddrequestheaders"></a><a name="addrequestheaders"></a>CHttpFile::AddRequestHeaders

Вызовите эту функцию участника, чтобы добавить один или несколько заголовков запросов HTTP в ручку запроса HTTP.

```
BOOL AddRequestHeaders(
    LPCTSTR pstrHeaders,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW,
    int dwHeadersLen = -1);

BOOL AddRequestHeaders(
    CString& str,
    DWORD dwFlags = HTTP_ADDREQ_FLAG_ADD_IF_NEW);
```

### <a name="parameters"></a>Параметры

*pstrHeaders*<br/>
Указатель на строку, содержащую заголовок или заголовки, чтобы придать запрос. Каждый заголовок должен быть прекращен парой CR/LF.

*dwFlags*<br/>
Модифицирует семантику новых заголовков. Может применяться один из перечисленных ниже типов.

- HTTP_ADDREQ_FLAG_COALESCE заголовки Merges с тем же именем, используя флаг для добавления первого заголовка, найденного в последующем заголовке. Например, "Accept:\*text/ " с последующим "Accept: audio/\*" приводит к\*формированию\*единого заголовка "Accept: text/ , audio/ ". Это до вызова приложения для обеспечения сплоченной схемы в отношении данных, полученных по запросам, отправленным с объединились или отдельные заголовки.

- HTTP_ADDREQ_FLAG_REPLACE выполняет удаление и добавление для замены текущего заголовка. Имя заголовка будет использоваться для удаления текущего заголовка, а полное значение будет использоваться для добавления нового заголовка. Если значение заголовка пусто и заголовок найден, он удаляется. Если не пусто, заголовок значение заменяется.

- HTTP_ADDREQ_FLAG_ADD_IF_NEW только добавляет заголовок, если он еще не существует. Если он существует, возвращается ошибка.

- HTTP_ADDREQ_FLAG_ADD используется с REPLACE. Добавляет заголовок, если он не существует.

*dwHeadersLen*<br/>
Длина, в символах, *pstrHeaders*. Если это -1L, то *pstrHeaders* предполагается нулевой прекращения и длина вычисляется.

*Ул*<br/>
Ссылка на объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий дополнительный заголовок запроса или заголовки, которые будут добавлены.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Примечания

`AddRequestHeaders`прикладывает дополнительные заголовки свободного формата к ручке запроса HTTP. Он предназначен для использования сложными клиентами, которые нуждаются в детальном контроле над точным запросом, отправленным на сервер HTTP.

> [!NOTE]
> Приложение может передавать несколько заголовков в *pstrHeaders* или *str* для `AddRequestHeaders` вызова, используя HTTP_ADDREQ_FLAG_ADD или HTTP_ADDREQ_FLAG_ADD_IF_NEW. Если приложение пытается удалить или заменить заголовок с помощью HTTP_ADDREQ_FLAG_REMOVE или HTTP_ADDREQ_FLAG_REPLACE, только один заголовок может быть поставлен в *lpszHeaders.*

## <a name="chttpfilechttpfile"></a><a name="chttpfile"></a>CHttpfile::CHttpfile

Эта функция члена называется `CHttpFile` для построения объекта.

```
CHttpFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrObject,
    LPCTSTR pstrServer,
    LPCTSTR pstrVerb,
    DWORD_PTR dwContext);

CHttpFile(
    HINTERNET hFile,
    LPCTSTR pstrVerb,
    LPCTSTR pstrObject,
    CHttpConnection* pConnection);
```

### <a name="parameters"></a>Параметры

*hFile*<br/>
Ручка к интернет-файлу.

*hСессия*<br/>
Ручка для сеанса Интернета.

*pstrObject*<br/>
Указатель на строку, `CHttpFile` содержащую объект.

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера.

*pstrVerb*<br/>
Указатель строки, содержащей метод, используемый при отправке запроса. Может быть POST, HEAD, или GET.

*Dwcontext*<br/>
Идентификатор `CHttpFile` контекста для объекта. Более подробную информацию об этом параметре можно увидеть в **комментариях.**

*pConnection*<br/>
Указатель на объект [CHttpConnection.](../../mfc/reference/chttpconnection-class.md)

### <a name="remarks"></a>Примечания

Вы никогда `CHttpFile` не строите объект напрямую; скорее позвоните [cInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) вместо.

Значение по `dwContext` умолчанию для отправляется `CHttpFile` MFC на объект с `CHttpFile` объекта [CInternetSession,](../../mfc/reference/cinternetsession-class.md) который создал объект. При `CInternetSession::OpenURL` вызове `CHttpConnection` или `CHttpFile` построении объекта можно переопределить значение по умолчанию, чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста возвращается [в CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления статуса объекта, с помощью которого он идентифицируется. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

## <a name="chttpfileendrequest"></a><a name="endrequest"></a>CHttpFile::EndRequest

Вызовите эту функцию участника, чтобы закончить запрос, отправленный на сервер HTTP с функцией [участника SendRequestEx.](#sendrequestex)

```
BOOL EndRequest(
    DWORD dwFlags = 0,
    LPINTERNET_BUFFERS lpBuffIn = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаги, описывающие операцию. Список соответствующих флагов можно узнать в [SDK](/windows/win32/api/wininet/nf-wininet-httpendrequestw) Windows.

*lpBuffin*<br/>
Указатель на инициализированную [INTERNET_BUFFERS,](/windows/win32/api/wininet/ns-wininet-internet_buffersw) описывающий буфер ввода, используемый для операции.

*Dwcontext*<br/>
Идентификатор `CHttpFile` контекста для операции. Более подробную информацию об этом параметре можно увидеть в комментариях.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, определить причину сбоя, изучив брошенный объект [CInternetException.](../../mfc/reference/cinternetexception-class.md)

### <a name="remarks"></a>Примечания

Значение по умолчанию для *dwContext* отправляется MFC `CHttpFile` объекту с объекта [CInternetSession,](../../mfc/reference/cinternetsession-class.md) создавого `CHttpFile` объект. При вызове [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection](../../mfc/reference/chttpconnection-class.md) для построения `CHttpFile` объекта можно переопределить значение по умолчанию, чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста возвращается [в CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления статуса объекта, с помощью которого он идентифицируется. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

## <a name="chttpfilegetfileurl"></a><a name="getfileurl"></a>CHttpFile::GetFileURL

Вызовите эту функцию участника, чтобы получить имя файла HTTP в виде URL-адреса.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий URL-адрес, ссылающийся на ресурс, связанный с этим файлом.

### <a name="remarks"></a>Примечания

Используйте эту функцию участника только после успешного вызова [в SendRequest](#sendrequest) или на объекте, успешно созданном `CHttpFile` [OpenURL.](../../mfc/reference/cinternetsession-class.md#openurl)

## <a name="chttpfilegetobject"></a><a name="getobject"></a>CHttpFile::GetObject

Вызов исчергните эту функцию `CHttpFile`участника, чтобы получить имя объекта, связанного с этим.

```
CString GetObject() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий название объекта.

### <a name="remarks"></a>Примечания

Используйте эту функцию участника только после успешного вызова [в SendRequest](#sendrequest) или на объекте, успешно созданном `CHttpFile` [OpenURL.](../../mfc/reference/cinternetsession-class.md#openurl)

## <a name="chttpfilegetverb"></a><a name="getverb"></a>CHttpFile::GetVerb

Вызов эту функцию участника, чтобы получить глагол `CHttpFile`HTTP (или метод), связанный с этим.

```
CString GetVerb() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий название глагола HTTP (или метода).

### <a name="remarks"></a>Примечания

Используйте эту функцию участника только после успешного вызова [в SendRequest](#sendrequest) или на объекте, успешно созданном `CHttpFile` [OpenURL.](../../mfc/reference/cinternetsession-class.md#openurl)

## <a name="chttpfilequeryinfo"></a><a name="queryinfo"></a>CHttpFile::КеприИнфо

Вызовите эту функцию участника, чтобы вернуть ответ или запросить заголовки из запроса HTTP.

```
BOOL QueryInfo(
    DWORD dwInfoLevel,
    LPVOID lpvBuffer,
    LPDWORD lpdwBufferLength,
    LPDWORD lpdwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    CString& str,
    LPDWORD dwIndex = NULL) const;

BOOL QueryInfo(
    DWORD dwInfoLevel,
    SYSTEMTIME* pSysTime,
    LPDWORD dwIndex = NULL) const;
```

### <a name="parameters"></a>Параметры

*dwInfoLevel*<br/>
Сочетание атрибута с запросом и следующих флагов, определяющих тип запрашиваемых информации:

- HTTP_QUERY_CUSTOM находит имя заголовка и возвращает это значение в *lpvBuffer* на выходе. HTTP_QUERY_CUSTOM бросает утверждение, если заголовок не найден.

- HTTP_QUERY_FLAG_REQUEST_HEADERS Обычно приложение запрашивает заголовки ответов, но приложение также может запрашивать заголовки запросов с помощью этого флага.

- HTTP_QUERY_FLAG_SYSTEMTIME Для тех заголовков, значение которых является строкой даты/времени, например "Последнее изменение времени", этот флаг возвращает значение заголовка в качестве стандартной структуры Win32 [SYSTEMTIME,](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) которая не требует от приложения для анализа данных. Если вы используете этот флаг, `SYSTEMTIME` вы можете использовать переопределение функции.

- HTTP_QUERY_FLAG_NUMBER Для тех заголовков, значение которых является числом, например кодом состояния, этот флаг возвращает данные в виде 32-битного числа.

Список возможных значений можно оперется в разделе **«Замечания».**

*lpvBuffer*<br/>
Указатель на буфер, который получает информацию.

*lpdwBufferLength*<br/>
При входе это указывает на значение, содержащее длину буфера данных, в количестве символов или байтов. Более подробную информацию об этом параметре можно узнать в разделе **«Замечания».**

*lpdwIndex*<br/>
Указатель на нулевой индекс заголовка. Может иметь значение NULL. Используйте этот флаг для перечисления нескольких заголовков с тем же именем. При входе *lpdwIndex* указывает индекс указанного заголовка для возврата. На выходе *lpdwIndex* указывает индекс следующего заголовка. Если следующий индекс не может быть найден, ERROR_HTTP_HEADER_NOT_FOUND возвращается.

*Ул*<br/>
Ссылка на объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) получающий возвращенную информацию.

*dwIndex*<br/>
Значение индекса. Смотрите *lpdwIndex*.

*pSysTime*<br/>
Указатель на структуру Win32 [SYSTEMTIME.](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Примечания

Используйте эту функцию участника только после успешного вызова [в SendRequest](#sendrequest) или на объекте, успешно созданном `CHttpFile` [OpenURL.](../../mfc/reference/cinternetsession-class.md#openurl)

Вы можете получить следующие типы данных из: `QueryInfo`

- строки (по умолчанию)

- `SYSTEMTIME`(для "Данные:" "Expires:" и т.д., заголовки)

- DWORD (для STATUS_CODE, CONTENT_LENGTH и т.д.)

Когда строка написана в буфер, и функция `lpdwBufferLength` члена преуспевает, содержит длину строки в символах минус 1 для прекращения null символа.

Возможные значения *dwInfoLevel* включают в себя:

- HTTP_QUERY_MIME_VERSION

- HTTP_QUERY_CONTENT_TYPE

- HTTP_QUERY_CONTENT_TRANSFER_ENCODING

- HTTP_QUERY_CONTENT_ID

- HTTP_QUERY_CONTENT_DESCRIPTION

- HTTP_QUERY_CONTENT_LENGTH

- HTTP_QUERY_ALLOWED_METHODS

- HTTP_QUERY_PUBLIC_METHODS

- HTTP_QUERY_DATE

- HTTP_QUERY_EXPIRES

- HTTP_QUERY_LAST_MODIFIED

- HTTP_QUERY_MESSAGE_ID

- HTTP_QUERY_URI

- HTTP_QUERY_DERIVED_FROM

- HTTP_QUERY_LANGUAGE

- HTTP_QUERY_COST

- HTTP_QUERY_WWW_LINK

- HTTP_QUERY_PRAGMA

- HTTP_QUERY_VERSION

- HTTP_QUERY_STATUS_CODE

- HTTP_QUERY_STATUS_TEXT

- HTTP_QUERY_RAW_HEADERS

- HTTP_QUERY_RAW_HEADERS_CRLF

## <a name="chttpfilequeryinfostatuscode"></a><a name="queryinfostatuscode"></a>CHttpFile::Квиинфостатускокод

Вызовите эту функцию участника, чтобы получить код статуса, связанный с запросом HTTP, и поместите его в поставляемый параметр *dwStatusCode.*

```
BOOL QueryInfoStatusCode(DWORD& dwStatusCode) const;
```

### <a name="parameters"></a>Параметры

*dwStatusCode*<br/>
Ссылка на код статуса. Коды состояния указывают на успех или неудачу запрашиваемого события. Смотрите **примечания** для выбора описаний кода статуса.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

### <a name="remarks"></a>Примечания

Используйте эту функцию участника только после успешного вызова [в SendRequest](#sendrequest) или на объекте, успешно созданном `CHttpFile` [OpenURL.](../../mfc/reference/cinternetsession-class.md#openurl)

Коды статусов HTTP делятся на группы, указывающие на успех или сбой запроса. В следующих таблицах излагаются группы кодов статусов и наиболее распространенные коды статусов HTTP.

|Группа|Значение|
|-----------|-------------|
|200–299|Успешно|
|300–399|Сведения|
|400-499|Ошибка запроса|
|500-599|Ошибка сервера|

Общие коды состояния HTTP:

|Код состояния|Значение|
|-----------------|-------------|
|200|URL расположен, передача следует|
|400|Неразборчивый запрос|
|404|Запрошенный URL не найден|
|405|Сервер не поддерживает запрашиваемый метод|
|500|Неизвестная ошибка сервера|
|503|Емкость сервера достигнута|

## <a name="chttpfilesendrequest"></a><a name="sendrequest"></a>CHttpFile::SendRequest

Вызовите эту функцию участника, чтобы отправить запрос на сервер HTTP.

```
BOOL SendRequest(
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLen = 0,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);

BOOL SendRequest(
    CString& strHeaders,
    LPVOID lpOptional = NULL,
    DWORD dwOptionalLen = 0);
```

### <a name="parameters"></a>Параметры

*pstrHeaders*<br/>
Указатель строки, содержащей имя заголовков для отправки.

*dwHeadersLen*<br/>
Длина заголовков, идентифицированных *pstrHeaders*.

*lpФамонсемы*<br/>
Любые дополнительные данные для отправки сразу после заголовков запросов. Это обычно используется для операций POST и PUT. Это может быть NULL, если нет дополнительных данных для отправки.

*dwФактальтальтальтальтированны*<br/>
Длина *lpФаминально*.

*strHeaders*<br/>
Строка, содержащая имя заголовков для отправки запроса.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, определить причину сбоя, изучив брошенный объект [CInternetException.](../../mfc/reference/cinternetexception-class.md)

## <a name="chttpfilesendrequestex"></a><a name="sendrequestex"></a>CHttpFile::SendRequestEx

Вызовите эту функцию участника, чтобы отправить запрос на сервер HTTP.

```
BOOL SendRequestEx(
    DWORD dwTotalLen,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);

BOOL SendRequestEx(
    LPINTERNET_BUFFERS lpBuffIn,
    LPINTERNET_BUFFERS lpBuffOut,
    DWORD dwFlags = HSR_INITIATE,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*dwTotalLen*<br/>
Количество байтов, которые будут отправлены в запросе.

*dwFlags*<br/>
Флаги, описывающие операцию. Список соответствующих флагов можно узнать в [SDK](/windows/win32/api/wininet/nf-wininet-httpsendrequestexw) Windows.

*Dwcontext*<br/>
Идентификатор `CHttpFile` контекста для операции. Более подробную информацию об этом параметре можно увидеть в комментариях.

*lpBuffin*<br/>
Указатель на инициализированную [INTERNET_BUFFERS,](/windows/win32/api/wininet/ns-wininet-internet_buffersw) описывающий буфер ввода, используемый для операции.

*lpBuffOut*<br/>
Указатель на инициализированную INTERNET_BUFFERS, описывающий буфер вывода, используемый для операции.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно. Если вызов не удается, определить причину сбоя, изучив брошенный объект [CInternetException.](../../mfc/reference/cinternetexception-class.md)

### <a name="remarks"></a>Примечания

Эта функция позволяет приложению отправлять данные с помощью методов `CInternetFile` [Write](../../mfc/reference/cinternetfile-class.md#write) and [WriteString.](../../mfc/reference/cinternetfile-class.md#writestring) Вы должны знать длину данных для отправки, прежде чем вызывать либо переопределение этой функции. Первый переопределение позволяет указать длину данных, которые вы хотели бы отправить. Второй переопределение принимает указатели на INTERNET_BUFFERS структуры, которые могут быть использованы для описания буфера в мельчайших деталях.

После того, как содержимое будет записано в файл, позвоните [endRequest,](#endrequest) чтобы закончить операцию.

Значение по умолчанию для *dwContext* отправляется MFC `CHttpFile` объекту с объекта [CInternetSession,](../../mfc/reference/cinternetsession-class.md) создавого `CHttpFile` объект. При вызове [CInternetSession::OpenURL](../../mfc/reference/cinternetsession-class.md#openurl) или [CHttpConnection](../../mfc/reference/chttpconnection-class.md) для построения `CHttpFile` объекта можно переопределить значение по умолчанию, чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста возвращается [в CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления статуса объекта, с помощью которого он идентифицируется. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

### <a name="example"></a>Пример

Этот фрагмент кода отправляет содержимое строки в DLL под названием MFCISAPI. DLL на сервере LOCALHOST. Хотя в этом примере `WriteString`используется только один вызов, использование нескольких вызовов для отправки данных в блоках является приемлемым.

[!code-cpp[NVC_MFCWinInet#9](../../mfc/codesnippet/cpp/chttpfile-class_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)
