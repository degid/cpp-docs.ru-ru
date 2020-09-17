---
title: Класс CHttpConnection
ms.date: 03/27/2019
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
helpviewer_keywords:
- CHttpConnection [MFC], CHttpConnection
- CHttpConnection [MFC], OpenRequest
ms.assetid: a402b662-c445-4988-800d-c8278551babe
ms.openlocfilehash: af402b532b3aba28bdfefea5afa67331765db4c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351817"
---
# <a name="chttpconnection-class"></a>Класс CHttpConnection

Управление подключением к HTTP-серверу.

## <a name="syntax"></a>Синтаксис

```
class CHttpConnection : public CInternetConnection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CHttpConnection:CHttpConnection](#chttpconnection)|Создает объект `CHttpConnection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CHttpConnection::OpenRequest](#openrequest)|Открывает запрос HTTP.|

## <a name="remarks"></a>Примечания

HTTP является одним из трех протоколов интернет-сервера, реализованных классами MFC WinInet.

Класс `CHttpConnection` содержит конструктор и функцию одного элемента, [OpenRequest,](#openrequest)которая управляет соединениями с сервером с помощью протокола HTTP.

Чтобы связаться с сервером HTTP, необходимо сначала создать экземпляр [CInternetSession,](../../mfc/reference/cinternetsession-class.md)а затем создать объект [CHttpConnection.](#chttpconnection) Вы никогда `CHttpConnection` не создаете объект напрямую; скорее, позвоните [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection), который создает `CHttpConnection` объект и возвращает указатель к нему.

Чтобы узнать `CHttpConnection` больше о том, как работает с другими классами МФЦ Интернет, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md) Для получения дополнительной информации о подключении к серверам с использованием [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) двух других поддерживаемых интернет-протоколов, суслик и FTP, см. [CFtpConnection](../../mfc/reference/cftpconnection-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CHttpConnection`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="chttpconnectionchttpconnection"></a><a name="chttpconnection"></a>CHttpConnection:CHttpConnection

Эта функция члена называется `CHttpConnection` для построения объекта.

```
CHttpConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);

CHttpConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    DWORD dwFlags,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pСессия*<br/>
Указатель на объект [CInternetSession.](../../mfc/reference/cinternetsession-class.md)

*hПодключено*<br/>
Ручка к подключению к Интернету.

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера.

*Dwcontext*<br/>
Идентификатор `CInternetConnection` контекста для объекта. Для получения дополнительной информации о *dwContext*, смотрите раздел **Замечания.**

*nПорт*<br/>
Номер, идентифицирует интернет-порт для этого соединения.

*pstrUserName*<br/>
Указатель на строку с нулевым завершением, которая определяет имя пользователя для вхлых в систему. Если NULL, по умолчанию является анонимным.

*pstrPassword*<br/>
Указатель на строку с нулевым завершением, которая определяет пароль для вху-на-айму для входе в систему. Если *pstrPassword* и *pstrUserName* являются NULL, анонимный пароль по умолчанию — это имя электронной почты пользователя. Если *pstrPassword* является NULL или пустой строкой, но *pstrUserName* не является NULL, используется пустой пароль. В следующей таблице описывается поведение для четырех возможных настроек *pstrUserName* и *pstrPassword:*

|*pstrUserName*|*pstrPassword*|Имя пользователя, отправленное на сервер FTP|Пароль, отправленный на сервер FTP|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL или "|NULL или "|"анонимный"|Имя пользователя по электронной почте|
|Не-NULL строка|NULL или "|*pstrUserName*|" "|
|NULL |Не-NULL строка|ошибка|ошибка|
|Не-NULL строка|Не-NULL строка|*pstrUserName*|*pstrPassword*|

*dwFlags*<br/>
Любое сочетание `INTERNET_FLAG_*` флагов. Смотрите таблицу в разделе **Замечания** [CHttpConnection::OpenRequest](#openrequest) для описания значений *dwFlags.*

### <a name="remarks"></a>Примечания

Вы никогда `CHttpConnection` не создаете непосредственно. Скорее, вы создаете объект, позвонив [в CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection).

## <a name="chttpconnectionopenrequest"></a><a name="openrequest"></a>CHttpConnection::OpenRequest

Вызовите эту функцию участника, чтобы открыть соединение HTTP.

```
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

CHttpFile* OpenRequest(
    int nVerb,
    LPCTSTR pstrObjectName,
    LPCTSTR pstrReferer = NULL,
    DWORD_PTR dwContext = 1,
    LPCTSTR* ppstrAcceptTypes = NULL,
    LPCTSTR pstrVersion = NULL,
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```

### <a name="parameters"></a>Параметры

*pstrVerb*<br/>
Указатель строки, содержащей глагол, для использования в запросе. Если NULL, используется "GET".

*pstrObjectName*<br/>
Указатель на строку, содержащую целевой объект указанного глагола. Эта строка обычно представляет собой имя файла, исполняемый модуль или спецификатор поиска.

*pstrReferer*<br/>
Указатель на строку, которая определяет адрес (URL) документа, из которого был получен URL в запросе *(pstrObjectName*). Если NULL, не указан заголовок HTTP.

*Dwcontext*<br/>
Идентификатор `OpenRequest` контекста для операции. Для получения дополнительной информации о *dwContext*, смотрите раздел Замечания.

*ppstrAcceptTypes*<br/>
Указатель на нулевые массивуказатели LPCTSTR к строкам, указывающим типы содержимого, принятые клиентом. Если *ppstrAcceptTypes* является NULL, серверы интерпретируют, что клиент принимает только документы типа "текст/" (т.е. только текстовые документы, а не фотографии или другие двоичные файлы). Тип содержимого эквивалентен переменной CGI CONTENT_TYPE, которая определяет тип данных для запросов, которые прилагали информацию, такую как HTTP POST и PUT.

*pstrVersion*<br/>
Указатель на строку, определяющую версию HTTP. Если NULL, используется "HTTP/1.0".

*dwFlags*<br/>
Любая комбинация INTERNET_ флагов FLAG_. Ознакомьтесь с разделом «Замечания» для описания возможных значений *dwFlags.*

*nVerb*<br/>
Номер, связанный с типом запроса HTTP. Может применяться один из перечисленных ниже типов.

|Тип запроса HTTP|*значение nVerb*|
|-----------------------|-------------------|
|HTTP_VERB_POST|0|
|HTTP_VERB_GET|1|
|HTTP_VERB_HEAD|2|
|HTTP_VERB_PUT|3|
|HTTP_VERB_LINK|4|
|HTTP_VERB_DELETE|5|
|HTTP_VERB_UNLINK|6|

### <a name="return-value"></a>Возвращаемое значение

Запрашиваемый указатель на объект [CHttpFile.](../../mfc/reference/chttpfile-class.md)

### <a name="remarks"></a>Примечания

*dwFlags* может быть одним из следующих:

|Флаг Интернета|Описание|
|-------------------|-----------------|
|INTERNET_FLAG_RELOAD|Вынуждает загрузку запрашиваемого файла, объекта или каталога с сервера происхождения, а не из кэша.|
|INTERNET_FLAG_DONT_CACHE|Не добавляет возвращенную сущность в кэш.|
|INTERNET_FLAG_MAKE_PERSISTENT|Добавляет возвращенную сущность в кэш как постоянную сущность. Это означает, что стандартная очистка кэша, проверка согласованности или сбор мусора не могут удалить этот элемент из кэша.|
|INTERNET_FLAG_SECURE|Использует безопасную семантику транзакций. Он переводится с помощью SSL/PCT и имеет смысл только в запросах HTTP|
|INTERNET_FLAG_NO_AUTO_REDIRECT|Используется только с HTTP, указывает, что перенаправления не должны обрабатываться автоматически в [CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest).|

Переувитрите `dwContext` значение по умолчанию, чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста связан с `CHttpConnection` этой конкретной операцией объекта, созданного его объектом [CInternetSession.](../../mfc/reference/cinternetsession-class.md) Значение возвращается [в CInternetSession::OnStatusCallback,](../../mfc/reference/cinternetsession-class.md#onstatuscallback) чтобы предоставить статус операции, с которой он идентифицирован. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

Исключения могут быть брошены с этой функцией.

## <a name="see-also"></a>См. также раздел

[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CHttpfile](../../mfc/reference/chttpfile-class.md)
