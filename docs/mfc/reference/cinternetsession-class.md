---
title: Класс CInternetSession
ms.date: 06/20/2018
f1_keywords:
- CInternetSession
- AFXINET/CInternetSession
- AFXINET/CInternetSession::CInternetSession
- AFXINET/CInternetSession::Close
- AFXINET/CInternetSession::EnableStatusCallback
- AFXINET/CInternetSession::GetContext
- AFXINET/CInternetSession::GetCookie
- AFXINET/CInternetSession::GetCookieLength
- AFXINET/CInternetSession::GetFtpConnection
- AFXINET/CInternetSession::GetGopherConnection
- AFXINET/CInternetSession::GetHttpConnection
- AFXINET/CInternetSession::OnStatusCallback
- AFXINET/CInternetSession::OpenURL
- AFXINET/CInternetSession::SetCookie
- AFXINET/CInternetSession::SetOption
helpviewer_keywords:
- CInternetSession [MFC], CInternetSession
- CInternetSession [MFC], Close
- CInternetSession [MFC], EnableStatusCallback
- CInternetSession [MFC], GetContext
- CInternetSession [MFC], GetCookie
- CInternetSession [MFC], GetCookieLength
- CInternetSession [MFC], GetFtpConnection
- CInternetSession [MFC], GetGopherConnection
- CInternetSession [MFC], GetHttpConnection
- CInternetSession [MFC], OnStatusCallback
- CInternetSession [MFC], OpenURL
- CInternetSession [MFC], SetCookie
- CInternetSession [MFC], SetOption
ms.assetid: ef54feb4-9d0f-4e65-a45d-7a4cf6c40e51
ms.openlocfilehash: ddd7ca6676805e6de1b7afb5ebc77733701dfef9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372379"
---
# <a name="cinternetsession-class"></a>Класс CInternetSession

Создает и инициализирует один или несколько параллельных сеансов Интернета и, при необходимости, описывает подключение к прокси-серверу.

## <a name="syntax"></a>Синтаксис

```cpp
class CInternetSession : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInternetSession::CInternetSession](#cinternetsession)|Формирует объект `CInternetSession`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CInternetSession::Закрыть](#close)|Закрывает подключение к Интернету при завершении сеанса Интернета.|
|[CInternetSession::EnableStatusCall](#enablestatuscallback)|Устанавливает процедуру обратного вызова статуса.|
|[CInternetSession::GetContext](#getcontext)|Закрывает подключение к Интернету при завершении сеанса Интернета.|
|[CInternetSession::GetCookie](#getcookie)|Возвращает файлы cookie для указанного URL-адреса и всех родительских URL-адресов.|
|[CInternetSession::GetCookieДлин](#getcookielength)|Извлекает переменную, определяющую длину файла cookie, хранящегося в буфере.|
|[CInternetSession::GetFtpConnection](#getftpconnection)|Открывает сеанс FTP с сервером. Входы на пользователя.|
|[CInternetSession::GetGopherConnection](#getgopherconnection)|Открывает сервер суслика для приложения, которое пытается открыть соединение.|
|[CInternetSession::GetHttpConnection](#gethttpconnection)|Открывает сервер HTTP для приложения, которое пытается открыть соединение.|
|[CInternetSession::OnStatusCallback](#onstatuscallback)|Обновляет состояние операции при включении обратного вызова статуса.|
|[CInternetSession::OpenURL](#openurl)|Парс и открывает URL.|
|[CInternetSession::SetCookie](#setcookie)|Устанавливает файл cookie для указанного URL- данных.|
|[CInternetSession::SetOption](#setoption)|Устанавливает варианты для сеанса Интернета.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CInternetSession:оператор HINTERNET](#operator_hinternet)|Ручка для текущей сессии Интернета.|

## <a name="remarks"></a>Примечания

Если подключение к Интернету должно быть сохранено в `CInternetSession` течение всего срока действия приложения, вы можете создать члена класса [CWinApp.](../../mfc/reference/cwinapp-class.md)

После того как вы создали Интернет-сессии, вы можете позвонить [OpenURL](#openurl). `CInternetSession`Затем разбирает URL для вас, позвонив в глобальную функцию [AfxParseURL.](internet-url-parsing-globals.md#afxparseurl) Независимо от типа `CInternetSession` протокола, интерпретирует URL и управляет им для вас. Он может обрабатывать запросы на локальные файлы, идентифицированные с ресурсом URL "file://". `OpenURL`вернет указатель на объект [CStdioFile,](../../mfc/reference/cstdiofile-class.md) если имя, которое вы передаете, является локальным файлом.

Если вы открываете URL-адрес `OpenURL`на интернет-сервере с помощью, вы можете прочитать информацию с сайта. Если вы хотите выполнять действия, связанные с обслуживанием (например, HTTP, FTP или суслик) на файлах, расположенных на сервере, необходимо установить соответствующее соединение с этим сервером. Чтобы открыть определенный вид подключения непосредственно к конкретной службе, используйте одну из следующих функций участника:

- [GetGopherConnection,](#getgopherconnection) чтобы открыть подключение к службе суслик.

- [GetHttpConnection,](#gethttpconnection) чтобы открыть подключение к службе HTTP.

- [GetFtpConnection,](#getftpconnection) чтобы открыть подключение к службе FTP.

[SetOption](#setoption) позволяет установить параметры запроса сеанса, такие как значения тайм-аута, количество повторов и так далее.

`CInternetSession`Функции участника [SetCookie,](#setcookie) [GetCookie](#getcookie)и [GetCookieLength](#getcookielength) предоставляют средства для управления базой данных cookie Win32, с помощью которой серверы и скрипты сохраняют государственную информацию о клиентской рабочей станции.

Для получения дополнительной информации об основных задачах программирования в Интернете, [см.](../../mfc/wininet-basics.md) Для получения общей информации об использовании Классов [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md)MFC WinInet см.

> [!NOTE]
> `CInternetSession`будет бросать [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception) для неподдерживаемых типов служб. В настоящее время поддерживаются только следующие типы служб: FTP, HTTP, суслик и файл.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;`CInternetSession`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cinternetsessioncinternetsession"></a><a name="cinternetsession"></a>CInternetSession::CInternetSession

Эта функция члена вызывается при создании `CInternetSession` объекта.

```cpp
CInternetSession(
    LPCTSTR pstrAgent = NULL,
    DWORD_PTR dwContext = 1,
    DWORD dwAccessType = PRE_CONFIG_INTERNET_ACCESS,
    LPCTSTR pstrProxyName = NULL,
    LPCTSTR pstrProxyBypass = NULL,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>Параметры

*pstrAgent*<br/>
Указатель на строку, идентифицирует название приложения или сущности, вызывающей функции Интернета (например, "Microsoft Internet Browser"). Если *pstrAgent* является NULL (по умолчанию), фреймворк вызывает глобальную функцию [AfxGetAppName,](application-information-and-management.md#afxgetappname)которая возвращает строку с нулевым завершением, содержащую имя приложения. Некоторые протоколы используют эту строку для идентификации приложения на сервере.

*Dwcontext*<br/>
Идентификатор контекста для операции. *dwContext* определяет информацию о состоянии операции, возвращенную [CInternetSession::OnStatusCallback](#onstatuscallback). Значение по умолчанию устанавливается на 1; однако можно явно назначить идентификатор контекста для операции. Объект и любая работа, которую он выполняет, будут связаны с идентификатором контекста.

*dwAccessType*<br/>
Тип требуемого доступа. Ниже приведены действительные значения, точно одно из которых может быть предоставлено:

- INTERNET_OPEN_TYPE_PRECONFIG Connect с использованием предварительно настроенных настроек в реестре. Этот тип доступа устанавливается как по умолчанию. Чтобы подключиться через прокси-сервер TIS, установите *dwAccessType* на это значение; Затем вы устанавливаете реестр надлежащим образом.

- INTERNET_OPEN_TYPE_DIRECT Подключайтесь непосредственно к Интернету.

- INTERNET_OPEN_TYPE_PROXY Подключитесь через прокси-сервер CERN.

Для получения информации о подключении к [Steps in a Typical FTP Client Application](../../mfc/steps-in-a-typical-ftp-client-application.md)различным типам прокси-сообщений см.

*pstrProxyName*<br/>
Имя предпочтительного прокси-сервера ЦЕРН, если *dwAccessType* устанавливается как INTERNET_OPEN_TYPE_PROXY. Значение по умолчанию — NULL.

*pstrProxyBypass*<br/>
Указатель на строку, содержащую дополнительный список адресов серверов. Эти адреса могут быть обойдятся при использовании прокси-доступа. При наличии значения NULL будет зачитано в реестре список обхода. Этот параметр имеет смысл только в том случае, если *dwAccessType* установлен на INTERNET_OPEN_TYPE_PROXY.

*dwFlags*<br/>
Указывает различные варианты кэширования. Значение по умолчанию установлено на 0. Возможные значения:

- INTERNET_FLAG_DONT_CACHE не кэшировать данные, либо локально, ни в любых серверах шлюза.

- INTERNET_FLAG_OFFLINE операции загрузки удовлетворяются только через постоянный кэш. Если элемент не существует в кэше, возвращается соответствующий код ошибки. Этот флаг может быть объединен с оператором bitwise **OR** **(&#124;). **

### <a name="remarks"></a>Примечания

`CInternetSession`является первой функцией Интернета, вызванной приложением. Он инициализирует внутренние структуры данных и готовится к будущим вызовам из приложения.

Если подключение к Интернету `CInternetSession` не может быть открыто, бросает [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).

### <a name="example"></a>Пример

Смотрите пример [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="cinternetsessionclose"></a><a name="close"></a>CInternetSession::Закрыть

Вызов используйте эту функцию `CInternetSession` участника, когда приложение закончило использовать объект.

```cpp
virtual void Close();
```

### <a name="example"></a>Пример

Смотрите пример [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="cinternetsessionenablestatuscallback"></a><a name="enablestatuscallback"></a>CInternetSession::EnableStatusCall

Вызов этой функции участника для включения обратного вызова статуса.

```cpp
BOOL EnableStatusCallback(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Параметры

*bEnable*<br/>
Уточняется, включен ли обратный вызов или отключен. Значение по умолчанию — TRUE.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, определить причину сбоя, изучив брошенный объект [CInternetException.](../../mfc/reference/cinternetexception-class.md)

### <a name="remarks"></a>Примечания

При обработке вызова статуса можно предоставить статус о ходе операции (например, решение имени, подключение к серверу и т.д.) в панели статуса приложения. Отображение статуса операции особенно желательно во время длительной операции.

Поскольку обратные вызовы происходят во время обработки запроса, приложение должно тратить как можно меньше времени на обратный вызов, чтобы предотвратить деградацию пропускной связи данных в сети. Например, ввод окна диалога в обратный вызов может быть такой длительной операцией, что сервер завершает запрос.

Обратный вызов статуса не может быть удален до тех пор, пока не будут рассмотрены обратные вызовы.

Чтобы выполнять любые операции асинхронно, необходимо либо создать свой собственный поток, либо использовать функции WinInet без MFC.

## <a name="cinternetsessiongetcontext"></a><a name="getcontext"></a>CInternetSession::GetContext

Вызовите эту функцию участника, чтобы получить значение контекста для определенного сеанса приложения.

```cpp
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор контекста, определяемый приложением.

### <a name="remarks"></a>Примечания

[OnStatusCallback](#onstatuscallback) использует идентификатор контекста, возвращенный, `GetContext` чтобы сообщить о состоянии конкретного приложения. Например, когда пользователь активирует интернет-запрос, связанный с возвратом информации о статусе, обратный вызов состояния использует идентификатор контекста для сообщения о состоянии данного конкретного запроса. Если пользователь активирует два отдельных Интернет-запроса, которые касаются получения информации о состоянии, `OnStatusCallback` использует идентификаторы контекста для возврата статуса соответствующих запросов. Следовательно, идентификатор контекста используется для всех операций обратного вызова состояния и связан с сеансом до окончания сеанса.

Для получения дополнительной информации об асинхронных операциях, [см.](../../mfc/wininet-basics.md)

## <a name="cinternetsessiongetcookie"></a><a name="getcookie"></a>CInternetSession::GetCookie

Эта функция члена реализует поведение функции Win32 [InternetGetCookie](/windows/win32/api/wininet/nf-wininet-internetgetcookiew), как описано в SDK Windows.

```cpp
static BOOL GetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPTSTR pstrCookieData,
    DWORD dwBufLen);

static BOOL GetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    CString& strCookieData);
```

### <a name="parameters"></a>Параметры

*pstrUrl*<br/>
Указатель на строку, содержащую URL.

*pstrCookieName*<br/>
Указатель на строку, содержащую имя файла cookie, чтобы получить для указанного URL.

*pstrCookieData*<br/>
В первой перегрузке указатель на строку, содержащую адрес буфера, который получает данные cookie. Это значение может быть NULL. Во второй перегрузке ссылка на объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) для получения данных cookie.

*dwBufLen*<br/>
Переменная, определяющая размер буфера *pstrCookieData.* Если функция успешно работает, буфер получает объем данных, скопированных в буфер *pstrCookieData.* Если *pstrCookieData* является NULL, этот параметр получает значение, которое определяет размер буфера, необходимого для копирования всех данных cookie.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE в случае успеха, или FALSE в противном случае. Если вызов не удается, позвоните в функцию Win32 [GetLastError,](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) чтобы определить причину ошибки. Применяются следующие значения ошибки:

- ERROR_NO_MORE_ITEMS Нет файла cookie для указанного URL-адреса и всех его родителей.

- ERROR_INSUFFICIENT_BUFFER Значение, передаваемые в *dwBufLen,* недостаточно для копирования всех данных cookie. Значение, возвращенное в *dwBufLen,* представляет собой размер буфера, необходимого для получения всех данных.

### <a name="remarks"></a>Примечания

Во второй перегрузке MFC получает данные `CString` cookie в поставляемый объект.

## <a name="cinternetsessiongetcookielength"></a><a name="getcookielength"></a>CInternetSession::GetCookieДлин

Вызов эту функцию участника, чтобы получить длину файла cookie, хранящегося в буфере.

```cpp
static DWORD GetCookieLength(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName);
```

### <a name="parameters"></a>Параметры

*pstrUrl*<br/>
Указатель на строку, содержащую URL

*pstrCookieName*<br/>
Указатель на строку, содержащую имя файла cookie.

### <a name="return-value"></a>Возвращаемое значение

Значение DWORD с указанием длины файла cookie, хранящегося в буфере. Ноль, если нет файла cookie с именем, указанным *pstrCookieName.*

### <a name="remarks"></a>Примечания

Это значение используется [GetCookie](#getcookie).

## <a name="cinternetsessiongetftpconnection"></a><a name="getftpconnection"></a>CInternetSession::GetFtpConnection

Вызовите эту функцию участника, чтобы установить `CFtpConnection` соединение FTP и получить указатель на объект.

```cpp
CFtpConnection* GetFtpConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    BOOL bPassive = FALSE);
```

### <a name="parameters"></a>Параметры

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера FTP.

*pstrUserName*<br/>
Указатель на строку с нулевым завершением, которая определяет имя пользователя для входа в систему. Если NULL, по умолчанию является анонимным.

*pstrPassword*<br/>
Указатель на строку с нулевым завершением, которая определяет пароль для входа в систему. Если *pstrPassword* и *pstrUserName* являются NULL, анонимный пароль по умолчанию — это имя электронной почты пользователя. Если *pstrPassword* является NULL (или пустой строки), но *pstrUserName* не является NULL, пустой пароль используется. В следующей таблице описывается поведение для четырех возможных настроек *pstrUserName* и *pstrPassword:*

| *pstrUserName*  | *pstrPassword*  | Имя пользователя, отправленное на сервер FTP | Пароль, отправленный на сервер FTP |
|-----------------|-----------------|-----------------------------|-----------------------------|
|   NULL или "   |   NULL или "   |         "анонимный"         |      Имя пользователя по электронной почте      |
| Не-NULL строка |   NULL или "   |       *pstrUserName*        |             " "             |
|      NULL       | Не-NULL строка |            ошибка            |            ошибка            |
| Не-NULL строка | Не-NULL строка |       *pstrUserName*        |       *pstrPassword*        |

*nПорт*<br/>
Номер, идентифицирующие порт TCP/IP для использования на сервере.

*bPassive*<br/>
Определяет пассивный или активный режим для этой сессии FTP. Если он установлен на ИСТИНу, он `dwFlag` устанавливает API Win32 для INTERNET_FLAG_PASSIVE.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CFtpConnection.](../../mfc/reference/cftpconnection-class.md) Если вызов не удается, определить причину сбоя, изучив брошенный объект [CInternetException.](../../mfc/reference/cinternetexception-class.md)

### <a name="remarks"></a>Примечания

`GetFtpConnection`подключается к серверу FTP, создает и `CFTPConnection` возвращает указатель на объект. Он не выполняет никаких конкретных операций на сервере. Например, если вы собираетесь читать или писать файлы, вы должны выполнять эти операции в виде отдельных шагов. Ознакомиться с классами [CFtpConnection](../../mfc/reference/cftpconnection-class.md) и [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) можно найти информацию о поиске файлов, открытии файлов, чтении или письме в файлах. Смотрите статью [Интернет Программирование с WinInet](../../mfc/win32-internet-extensions-wininet.md) для шагов в выполнении общих задач соединения FTP.

### <a name="example"></a>Пример

Смотрите пример [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md).

## <a name="cinternetsessiongetgopherconnection"></a><a name="getgopherconnection"></a>CInternetSession::GetGopherConnection

Вызовите эту функцию участника, чтобы установить новое `CGopherConnection` соединение суслика и получить указатель на объект.

```cpp
CGopherConnection* GetGopherConnection(
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Параметры

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера суслика.

*pstrUserName*<br/>
Указатель на строку, содержащую имя пользователя.

*pstrPassword*<br/>
Указатель на строку, содержащую пароль доступа.

*nПорт*<br/>
Номер, идентифицирующие порт TCP/IP для использования на сервере.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CGopherConnection.](../../mfc/reference/cgopherconnection-class.md) Если вызов не удается, определить причину сбоя, изучив брошенный объект [CInternetException.](../../mfc/reference/cinternetexception-class.md)

### <a name="remarks"></a>Примечания

`GetGopherConnection`подключается к серверу сусликов, создает `CGopherConnection` и возвращает указатель на объект. Он не выполняет никаких конкретных операций на сервере. Например, если вы собираетесь читать или писать данные, вы должны выполнять эти операции в виде отдельных шагов. Смотрите классы [CGopherConnection](../../mfc/reference/cgopherconnection-class.md), [CGopherFile](../../mfc/reference/cgopherfile-class.md)и [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) для получения информации о поиске файлов, открытии файлов и чтении или записи файлов. Для получения информации о просмотре сайта [OpenURL](#openurl)FTP см. Смотрите статью [Интернет Программирование с WinInet](../../mfc/win32-internet-extensions-wininet.md) для шагов в выполнении общих задач соединения суслик.

## <a name="cinternetsessiongethttpconnection"></a><a name="gethttpconnection"></a>CInternetSession::GetHttpConnection

Вызов ифункции этого участника, чтобы установить `CHttpConnection` соединение HTTP и получить указатель на объект.

```cpp
CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL);

CHttpConnection* GetHttpConnection(
    LPCTSTR pstrServer,
    DWORD dwFlags,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL);
```

### <a name="parameters"></a>Параметры

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера HTTP.

*nПорт*<br/>
Номер, идентифицирующие порт TCP/IP для использования на сервере.

*pstrUserName*<br/>
Указатель на строку, содержащую имя пользователя.

*pstrPassword*<br/>
Указатель на строку, содержащую пароль доступа.

*Dwflags*<br/>
Любое сочетание `INTERNET_FLAG_*` флагов. Смотрите таблицу в разделе **Замечания** [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest) для описания значений *dwFlags.*

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CHttpConnection.](../../mfc/reference/chttpconnection-class.md) Если вызов не удается, определить причину сбоя, изучив брошенный объект [CInternetException.](../../mfc/reference/cinternetexception-class.md)

### <a name="remarks"></a>Примечания

`GetHttpConnection`подключается к серверу HTTP, создает и `CHttpConnection` возвращает указатель объекту. Он не выполняет никаких конкретных операций на сервере. Например, если вы собираетесь запросить заголовок HTTP, необходимо выполнить эту операцию в качестве отдельного шага. Смотрите классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CHttpFile](../../mfc/reference/chttpfile-class.md) для получения информации об операциях, которые можно выполнить с помощью подключения к серверу HTTP. Для получения информации о просмотре сайта HTTP см. функцию участника [OpenURL](#openurl). Смотрите статью [Интернет Программирование с WinInet](../../mfc/win32-internet-extensions-wininet.md) для шагов в выполнении общих задач подключения HTTP.

## <a name="cinternetsessiononstatuscallback"></a><a name="onstatuscallback"></a>CInternetSession::OnStatusCallback

Эта функция элемента вызывается инфраструктурой для обновления статуса, когда вызов состояния включен и операция находится на рассмотрении.

```cpp
virtual void OnStatusCallback(
    DWORD_PTR dwContext,
    DWORD dwInternetStatus,
    LPVOID lpvStatusInformation,
    DWORD dwStatusInformationLength);
```

### <a name="parameters"></a>Параметры

*Dwcontext*<br/>
Контекстное значение, поставляемое приложением.

*dwInternetStatus*<br/>
Код состояния, указывающий причину вызова. Смотрите **замечания** для таблицы возможных значений.

*lpvStatusInformation*<br/>
Указатель на буфер, содержащий информацию, относящееся к этому обратному вызову.

*dwStatusInformationДлина*<br/>
Размер *lpvStatusInformation*.

### <a name="remarks"></a>Примечания

Сначала необходимо позвонить [в EnableStatusCallback,](#enablestatuscallback) чтобы воспользоваться обратным вызовом статуса.

Параметр *dwInternetStatus* указывает на выполняемую операцию и определяет, каким будет содержание *lpvStatusInformation.* *dwStatusInformationLength* указывает длину данных, включенных в *lpvStatusInformation*. Следующие значения статуса для *dwInternetStatus* определяются следующим образом:

|Значение|Значение|
|-----------|-------------|
|INTERNET_STATUS_RESOLVING_NAME|Поиск IP-адреса имени, содержащегося в *lpvStatusInformation*.|
|INTERNET_STATUS_NAME_RESOLVED|Успешно найден IP-адрес имени, содержащийся в *lpvStatusInformation*.|
|INTERNET_STATUS_CONNECTING_TO_SERVER|Подключение к адресу розетки[(SOCKADDR](/windows/win32/winsock/sockaddr-2)) указывается на *lpvStatusInformation*.|
|INTERNET_STATUS_CONNECTED_TO_SERVER|Успешно подключен к розетке адрес (SOCKADDR) указал на *lpvStatusInformation*.|
|INTERNET_STATUS_SENDING_REQUEST|Отправка запроса на сервер. Параметр *lpvStatusInformation* является NULL.|
|INTERNET_STATUS_ REQUEST_SENT|Успешно отправил информационный запрос на сервер. Параметр *lpvStatusInformation* является NULL.|
|INTERNET_STATUS_RECEIVING_RESPONSE|Ожидание ответа сервера на запрос. Параметр *lpvStatusInformation* является NULL.|
|INTERNET_STATUS_RESPONSE_RECEIVED|Успешно получил ответ от сервера. Параметр *lpvStatusInformation* является NULL.|
|INTERNET_STATUS_CLOSING_CONNECTION|Закрытие подключения к серверу. Параметр *lpvStatusInformation* является NULL.|
|INTERNET_STATUS_CONNECTION_CLOSED|Успешно закрыто подключение к серверу. Параметр *lpvStatusInformation* является NULL.|
|INTERNET_STATUS_HANDLE_CREATED|Используется функцией API Win32 [InternetConnect,](/windows/win32/api/wininet/nf-wininet-internetconnectw) чтобы указать, что она создала новую ручку. Это позволяет приложению вызывать функцию Win32 [InternetCloseHandle](/windows/win32/api/wininet/nf-wininet-internetclosehandle) из другого потока, если подключение занимает слишком много времени. Дополнительную информацию об этих функциях можно увидеть в Windows SDKFOR.|
|INTERNET_STATUS_HANDLE_CLOSING|Успешно упразднено это значение ручки.|

Переопределить эту функцию участника, чтобы потребовать некоторых действий до выполнения процедуры обратного вызова статуса.

> [!NOTE]
> Обратные вызовы состояния нуждаются в защите состояния потока. Если вы используете MFC в общей библиотеке, добавьте следующую строку к началу переопределения:

[!code-cpp[NVC_MFCHtmlHttp#8](../../mfc/reference/codesnippet/cpp/cinternetsession-class_1.cpp)]

Для получения дополнительной информации об асинхронных операциях, [см.](../../mfc/wininet-basics.md)

## <a name="cinternetsessionopenurl"></a><a name="openurl"></a>CInternetSession::OpenURL

Позвоните этой функции участника, чтобы отправить указанный запрос на сервер HTTP и позвольте клиенту указать дополнительные заголовки RFC822, MIME или HTTP для отправки вместе с запросом.

```cpp
CStdioFile* OpenURL(
    LPCTSTR pstrURL,
    DWORD_PTR dwContext = 1,
    DWORD dwFlags = INTERNET_FLAG_TRANSFER_ASCII,
    LPCTSTR pstrHeaders = NULL,
    DWORD dwHeadersLength = 0);
```

### <a name="parameters"></a>Параметры

*pstrURL*<br/>
Указатель на имя URL-адреса, чтобы начать чтение. Только URL-адреса, начиная с файла:, ftp:, суслик:, или http: поддерживаются. Утверждает, если *pstrURL* является NULL.

*Dwcontext*<br/>
Значение, определяемое приложением, пройдено с возвращенной ручкой в обратном порядке.

*dwFlags*<br/>
Флаги, описывающие, как справиться с этим соединением. Более подробную информацию о действительных флагах можно увидеть в **примечаниях.** Действительные флаги:

- INTERNET_FLAG_TRANSFER_ASCII значение по умолчанию. Передача файла в виде текста ASCII.

- INTERNET_FLAG_TRANSFER_BINARY перенесите файл в двоичный файл.

- INTERNET_FLAG_RELOAD получить данные из провода, даже если он локально кэшируется.

- INTERNET_FLAG_DONT_CACHE не кэшировать данные, либо локально, ни в каких-либо шлюзов.

- INTERNET_FLAG_SECURE этот флаг применим только к запросам HTTP. Он запрашивает безопасные транзакции на проводе с защищенным слоем розеток или РСТ.

- INTERNET_OPEN_FLAG_USE_EXISTING_CONNECT Если это возможно, повторно использовать существующие соединения `OpenUrl` на сервере для новых запросов, генерируемых вместо создания нового сеанса для каждого запроса на подключение.

- INTERNET_FLAG_PASSIVE используется для сайта FTP. Использует пассивную семантику FTP. Используется с [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) `OpenURL`.

*pstrHeaders*<br/>
Указатель строки, содержащей заголовки для отправки на сервер HTTP.

*dwHeadersДлина*<br/>
Длина, в символах, дополнительных заголовков. Если это -1L и *pstrHeaders* не является NULL, то *pstrHeaders* предполагается нулевой прекращено и длина рассчитывается.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку файла только для интернет-сервисов FTP, GOPHER, HTTP и FILE. Возвращает NULL, если разбор был неудачным.

Указатель, `OpenURL` который возвращается, зависит от типа *службы pstrURL.* Приведенная ниже таблица иллюстрирует `OpenURL` возможные указатели могут вернуться.

|Тип URL|Результаты|
|--------------|-------------|
|`file://`|`CStdioFile*`|
|`http://`|`CHttpFile*`|
|`gopher://`|`CGopherFile*`|
|`ftp://`|`CInternetFile*`|

### <a name="remarks"></a>Примечания

Параметр *dwFlags* должен включать либо INTERNET_FLAG_TRANSFER_ASCII, либо INTERNET_FLAG_TRANSFER_BINARY, но не оба. Остальные флаги могут быть объединены с bitwise **ИЛИ** оператора **(&#124;). **

`OpenURL`, который обертывает функцию `InternetOpenURL`Win32, позволяет только загружать, извлекать и читать данные с интернет-сервера. `OpenURL`позволяет не манипулировать файлами в удаленном месте, поэтому он не требует объекта [CInternetConnection.](../../mfc/reference/cinternetconnection-class.md)

Чтобы использовать специфические (т.е. конкретные функции протокола), такие как запись в файл, необходимо открыть сеанс, затем открыть определенный вид соединения, а затем использовать это соединение для открытия файла в нужном режиме. Дополнительную информацию о функциях, связанных с подключением, можно узнать. `CInternetConnection`

## <a name="cinternetsessionoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetSession:оператор HINTERNET

Используйте этот оператор, чтобы получить ручку Windows для текущей сессии Интернета.

```cpp
operator HINTERNET() const;
```

## <a name="cinternetsessionsetcookie"></a><a name="setcookie"></a>CInternetSession::SetCookie

Устанавливает файл cookie для указанного URL- данных.

```cpp
static BOOL SetCookie(
    LPCTSTR pstrUrl,
    LPCTSTR pstrCookieName,
    LPCTSTR pstrCookieData);
```

### <a name="parameters"></a>Параметры

*pstrUrl*<br/>
Указатель на строку с нулевым завершением, которая определяет URL-адрес, для которого должно быть установлено файлы cookie.

*pstrCookieName*<br/>
Указатель на строку, содержащую имя файла cookie.

*pstrCookieData*<br/>
Указатель строки, содержащей фактические данные строки, чтобы связать с URL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE в случае успеха, или FALSE в противном случае. Чтобы получить конкретный код ошибки, позвоните`GetLastError.`

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение сообщения Win32 [InternetSetCookie](/windows/win32/api/wininet/nf-wininet-internetsetcookiew), как описано в SDK Windows.

## <a name="cinternetsessionsetoption"></a><a name="setoption"></a>CInternetSession::SetOption

Вызовите эту функцию участника, чтобы установить параметры для сеанса Интернета.

```cpp
BOOL SetOption(
    DWORD dwOption,
    LPVOID lpBuffer,
    DWORD dwBufferLength,
    DWORD dwFlags = 0);

BOOL SetOption(
    DWORD dwOption,
    DWORD dwValue,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>Параметры

*dwOption*<br/>
Вариант Интернета для установки. Смотрите [флаги опций](/windows/win32/WinInet/option-flags) в Windows SDKfor список возможных вариантов.

*lpBuffer*<br/>
Буфер, содержащий параметр опциона.

*dwBufferДлина*<br/>
Длина *lpBuffer* или размер *dwValue*.

*dwValue*<br/>
DWORD, содержащий параметр опции.

*dwFlags*<br/>
Указывает различные варианты кэширования. Значение по умолчанию установлено на 0. Возможные значения:

- INTERNET_FLAG_DONT_CACHE не кэшировать данные, либо локально, ни в любых серверах шлюза.

- INTERNET_FLAG_OFFLINE операции загрузки удовлетворяются только через постоянный кэш. Если элемент не существует в кэше, возвращается соответствующий код ошибки. Этот флаг может быть объединен с оператором bitwise **OR** **(&#124;). **

### <a name="return-value"></a>Возвращаемое значение

Если операция прошла успешно, значение TRUE возвращается. При возникновении ошибки возвращается значение FALSE. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)<br/>
[Класс CFtpConnection](../../mfc/reference/cftpconnection-class.md)<br/>
[Класс CGopherConnection](../../mfc/reference/cgopherconnection-class.md)
