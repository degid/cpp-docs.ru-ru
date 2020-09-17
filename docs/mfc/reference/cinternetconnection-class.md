---
title: Класс CInternetConnection
ms.date: 11/04/2016
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
helpviewer_keywords:
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
ms.openlocfilehash: 6649986f279e010a833b31157922cb4fd1ea8613
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372427"
---
# <a name="cinternetconnection-class"></a>Класс CInternetConnection

Управление подключением к интернет-серверу.

## <a name="syntax"></a>Синтаксис

```
class CInternetConnection : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Формирует объект `CInternetConnection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CInternetConnection::GetContext](#getcontext)|Получает идентификатор контекста для этого объекта соединения.|
|[CInternetConnection::GetServerName](#getservername)|Получает имя сервера, связанного с соединением.|
|[CInternetConnection::GetSession](#getsession)|Получает указатель на объект [CInternetSession,](../../mfc/reference/cinternetsession-class.md) связанный с соединением.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CInternetConnection::оператор HINTERNET](#operator_hinternet)|Ручка для сеанса Интернета.|

## <a name="remarks"></a>Примечания

Это базовый класс для классов MFC [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md)и [CGopherConnection.](../../mfc/reference/cgopherconnection-class.md) Каждый из этих классов предоставляет дополнительную функциональность для общения с соответствующим сервером FTP, HTTP или суслик.

Чтобы напрямую общаться с интернет-сервером, необходимо `CInternetConnection` иметь объект [CInternetSession](../../mfc/reference/cinternetsession-class.md) и объект.

Чтобы узнать больше о том, как работают классы WinInet, смотрите статью [Интернет Программирование с WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CInternetConnection`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cinternetconnectioncinternetconnection"></a><a name="cinternetconnection"></a>CInternetConnection::CInternetConnection

Эта функция члена вызывается при создании `CInternetConnection` объекта.

```
CInternetConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pСессия*<br/>
Указатель на объект [CInternetSession.](../../mfc/reference/cinternetsession-class.md)

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера.

*nПорт*<br/>
Номер, идентифицирует интернет-порт для этого соединения.

*Dwcontext*<br/>
Идентификатор `CInternetConnection` контекста для объекта. Смотрите **Замечания** для получения дополнительной информации о *dwContext*.

### <a name="remarks"></a>Примечания

Вы никогда не называете `CInternetConnection` себя; вместо этого позвоните в функцию участника [CInternetSession](../../mfc/reference/cinternetsession-class.md) для типа соединения, который вы хотите установить:

- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)

- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)

- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)

Значение по умолчанию для *dwContext* отправляется MFC `CInternetConnection`объекту, полученному из объекта [CInternetSession,](../../mfc/reference/cinternetsession-class.md) создавого объект **InternetConnection,** полученный в узе. Значение по умолчанию устанавливается на 1; однако можно явно назначить определенный идентификатор контекста в конструкторе [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) для соединения. Объект и любая работа, которую он выполняет, будут связаны с идентификатором контекста. Идентификатор контекста возвращается [в CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления статуса объекта, с помощью которого он идентифицируется. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

## <a name="cinternetconnectiongetcontext"></a><a name="getcontext"></a>CInternetConnection::GetContext

Вызовите эту функцию участника, чтобы получить идентификатор контекста для этой сессии.

```
DWORD_PTR GetContext() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор контекста, назначенный приложением.

### <a name="remarks"></a>Примечания

Идентификатор контекста первоначально указан в `CInternetConnection` [CInternetSession](../../mfc/reference/cinternetsession-class.md) и распространяется на - и [CInternetFile](../../mfc/reference/cinternetfile-class.md)- производные классы, если не указано по-разному в вызове к функции, которая открывает соединение. Идентификатор контекста связан с любой операцией данного объекта и идентифицирует информацию о состоянии операции, возвращенную [CInternetSession:OnStatusCallback.](../../mfc/reference/cinternetsession-class.md#onstatuscallback)

Для получения дополнительной `GetContext` информации о том, как работает с другими классами WinInet, чтобы дать информацию о статусе пользователя, смотрите статью [Интернет Первые шаги: WinInet](../../mfc/wininet-basics.md) для получения дополнительной информации об идентификаторе контекста.

## <a name="cinternetconnectiongetservername"></a><a name="getservername"></a>CInternetConnection::GetServerName

Вызовите эту функцию участника, чтобы получить имя сервера, связанного с этим подключением к Интернету.

```
CString GetServerName() const;
```

### <a name="return-value"></a>Возвращаемое значение

С именем сервера работает объект соединения.

## <a name="cinternetconnectiongetsession"></a><a name="getsession"></a>CInternetConnection::GetSession

Вызовите эту функцию участника, `CInternetSession` чтобы получить указатель на объект, связанный с этим соединением.

```
CInternetSession* GetSession() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CInternetSession,](../../mfc/reference/cinternetsession-class.md) связанный с этим объектом подключения КИнтернет.

## <a name="cinternetconnectionoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetConnection::оператор HINTERNET

Используйте этот оператор, чтобы получить ручку уровня API для текущей сессии Интернета.

```
operator HINTERNET() const;
```

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
