---
title: Класс CGopherConnection
ms.date: 11/04/2016
f1_keywords:
- CGopherConnection
- AFXINET/CGopherConnection
- AFXINET/CGopherConnection::CGopherConnection
- AFXINET/CGopherConnection::CreateLocator
- AFXINET/CGopherConnection::GetAttribute
- AFXINET/CGopherConnection::OpenFile
helpviewer_keywords:
- CGopherConnection [MFC], CGopherConnection
- CGopherConnection [MFC], CreateLocator
- CGopherConnection [MFC], GetAttribute
- CGopherConnection [MFC], OpenFile
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
ms.openlocfilehash: eade1a82b674d5ad2e91146559139445ef017180
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373715"
---
# <a name="cgopherconnection-class"></a>Класс CGopherConnection

Управление подключением к интернет-серверу gopher.

> [!NOTE]
> Классы `CGopherConnection` `CGopherFile`, `CGopherFileFind` `CGopherLocator` , и их члены были уволены, потому что они не работают на платформе Windows XP, но они будут продолжать работать на более ранних платформах.

## <a name="syntax"></a>Синтаксис

```
class CGopherConnection : public CInternetConnection
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CGopherConnection::CGopherConnection](#cgopherconnection)|Формирует объект `CGopherConnection`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CGopherConnection::CreateLocator](#createlocator)|Создает объект [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) для поиска файлов на сервере сусликов.|
|[CGopherConnection::GetAttribute](#getattribute)|Извлекает информацию о объекте суслика.|
|[CGopherConnection::OpenFile](#openfile)|Открывает файл суслика.|

## <a name="remarks"></a>Примечания

Служба сусликов является одним из трех интернет-сервисов, признанных классами MFC WinInet.

Класс `CGopherConnection` содержит конструктор и три дополнительные функции члена, которые управляют службой суслик: [OpenFile,](#openfile) [CreateLocator](#createlocator)и [GetAttribute](#getattribute).

Чтобы общаться с сусликом интернет-сервер, вы должны сначала создать экземпляр [CInternetSession](../../mfc/reference/cinternetsession-class.md), а `CGopherConnection` затем позвонить [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), который создает объект и возвращает указатель к нему. Вы никогда `CGopherConnection` не создаете объект напрямую.

Чтобы узнать `CGopherConnection` больше о том, как работает с другими классами МФЦ Интернет, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md) Для получения дополнительной информации об использовании двух других поддерживаемых интернет-сервисов, FTP и HTTP [CFtpConnection](../../mfc/reference/cftpconnection-class.md)см. [CHttpConnection](../../mfc/reference/chttpconnection-class.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CInternetConnection](../../mfc/reference/cinternetconnection-class.md)

`CGopherConnection`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cgopherconnectioncgopherconnection"></a><a name="cgopherconnection"></a>CGopherConnection::CGopherConnection

Эта функция члена называется `CGopherConnection` для построения объекта.

```
CGopherConnection(
    CInternetSession* pSession,
    HINTERNET hConnected,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext);

CGopherConnection(
    CInternetSession* pSession,
    LPCTSTR pstrServer,
    LPCTSTR pstrUserName = NULL,
    LPCTSTR pstrPassword = NULL,
    DWORD_PTR dwContext = 0,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Параметры

*pСессия*<br/>
Указатель на связанный объект [CInternetSession.](../../mfc/reference/cinternetsession-class.md)

*hПодключено*<br/>
Ручка Windows текущей сессии Интернета.

*pstrServer*<br/>
Указатель на строку, содержащую имя сервера FTP.

*Dwcontext*<br/>
Идентификатор контекста для операции. *dwContext* определяет информацию о состоянии операции, возвращенную [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback). Значение по умолчанию устанавливается на 1; однако можно явно назначить идентификатор контекста для операции. Объект и любая работа, которую он выполняет, будут связаны с идентификатором контекста.

*pstrUserName*<br/>
Указатель на строку с нулевым завершением, которая определяет имя пользователя для входа в систему. Если NULL, по умолчанию является анонимным.

*pstrPassword*<br/>
Указатель на строку с нулевым завершением, которая определяет пароль для входа в систему. Если *pstrPassword* и *pstrUserName* являются NULL, анонимный пароль по умолчанию — это имя электронной почты пользователя. Если *pstrPassword* является NULL (или пустой строки), но *pstrUserName* не является NULL, пустой пароль используется. В следующей таблице описывается поведение для четырех возможных настроек *pstrUserName* и *pstrPassword:*

|*pstrUserName*|*pstrPassword*|Имя пользователя, отправленное на сервер FTP|Пароль, отправленный на сервер FTP|
|--------------------|--------------------|---------------------------------|---------------------------------|
|NULL или "|NULL или "|"анонимный"|Имя пользователя по электронной почте|
|Не-NULL строка|NULL или "|*pstrUserName*|" "|
|NULL Non- NULL String|ошибка|ошибка||
|Не-NULL строка|Не-NULL строка|*pstrUserName*|*pstrPassword*|

*nПорт*<br/>
Номер, идентифицирующие порт TCP/IP для использования на сервере.

### <a name="remarks"></a>Примечания

Вы никогда `CGopherConnection` не создаете непосредственно. Скорее, позвоните [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection), который создает `CGopherConnection` объект и возвращает указатель к нему.

## <a name="cgopherconnectioncreatelocator"></a><a name="createlocator"></a>CGopherConnection::CreateLocator

Вызовите эту функцию участника, чтобы создать локатор суслика, чтобы найти или идентифицировать файл на сервере сусликов.

```
CGopherLocator CreateLocator(
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType);

static CGopherLocator CreateLocator(LPCTSTR pstrLocator);

static CGopherLocator CreateLocator(
    LPCTSTR pstrServerName,
    LPCTSTR pstrDisplayString,
    LPCTSTR pstrSelectorString,
    DWORD dwGopherType,
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER);
```

### <a name="parameters"></a>Параметры

*pstrDisplayString*<br/>
Указатель на строку, содержащую имя документа суслика или каталога, который необходимо извлечь. Если параметр *pstrDisplayString* является NULL, каталог по умолчанию для сервера сусликов возвращается.

*pstrSelectorString*<br/>
Указатель на строку селектора, которая будет отправлена на сервер суслика для получения элемента. *pstrSelectorString* может быть NULL.

*dwGopherType*<br/>
При этом указывается, относится ли *pstrSelectorString* к каталогу или документу, и является ли запрос сусликом или сусликом. Просмотреть атрибуты для структуры [GOPHER_FIND_DATA](/windows/win32/api/wininet/ns-wininet-gopher_find_dataw) в Windows SDK.

*pstrLocator*<br/>
Указатель строки, идентифицирующей файл для открытия. Как правило, эта строка возвращается с вызова [на CGopherFileFind::GetLocator](../../mfc/reference/cgopherfilefind-class.md#getlocator).

*pstrServerName*<br/>
Указатель на строку, содержащую имя сервера суслика.

*nПорт*<br/>
Номер, идентифицирующий интернет-порт для этого соединения.

### <a name="return-value"></a>Возвращаемое значение

Объект [CGopherLocator.](../../mfc/reference/cgopherlocator-class.md)

### <a name="remarks"></a>Примечания

Статическая версия функции участника требует указания сервера, в то время как нестатическая версия использует имя сервера из объекта соединения.

Для того, чтобы получить информацию с сервера суслик, приложение должно сначала получить суслик локатора. Приложение должно затем рассматривать локатор как непрозрачный маркер (т.е. приложение может использовать локатор, но не напрямую манипулировать или сравнивать его). Обычно приложение использует локатор для вызовов в функцию [cGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) для получения определенной части информации.

## <a name="cgopherconnectiongetattribute"></a><a name="getattribute"></a>CGopherConnection::GetAttribute

Вызовите эту функцию участника, чтобы получить конкретную информацию о атрибуте элемента с сервера сусликов.

```
BOOL GetAttribute(
    CGopherLocator& refLocator    CString strRequestedAttributes,
    CString& strResult,);
```

### <a name="parameters"></a>Параметры

*рефЛокатор*<br/>
Ссылка на объект [CGopherLocator.](../../mfc/reference/cgopherlocator-class.md)

*strRequestedАтрибуты*<br/>
Строка, разграниченная по пространству с указанием имен запрашиваемых атрибутов.

*strResult*<br/>
Ссылка на [CString,](../../atl-mfc-shared/reference/cstringt-class.md) который получает тип локатора.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Если вызов не удается, функция Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) может быть вызвана для определения причины ошибки.

## <a name="cgopherconnectionopenfile"></a><a name="openfile"></a>CGopherConnection::OpenFile

Вызовите эту функцию участника, чтобы открыть файл на сервере сусликов.

```
CGopherFile* OpenFile(
    CGopherLocator& refLocator,
    DWORD dwFlags = 0,
    LPCTSTR pstrView = NULL,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*рефЛокатор*<br/>
Ссылка на объект [CGopherLocator.](../../mfc/reference/cgopherlocator-class.md)

*dwFlags*<br/>
Любая комбинация INTERNET_FLAG_ флагов. Дополнительную информацию о INTERNET_FLAG_\* флагов можно просмотреть [CInternetSession::OpenUrl.](../../mfc/reference/cinternetsession-class.md#openurl)

*pstrView*<br/>
Указатель на строку просмотра файлов. Если на сервере существует несколько представлений файла, этот параметр определяет, какой файл может открыться. Если *pstrView* является NULL, используется представление файла по умолчанию.

*Dwcontext*<br/>
Идентификатор контекста для открываемого файла. Смотрите **Замечания** для получения дополнительной информации о *dwContext*.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [CGopherFile,](../../mfc/reference/cgopherfile-class.md) который будет открыт.

### <a name="remarks"></a>Примечания

Переизбь по умолчанию *dwContext,* чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста связан с `CGopherConnection` этой конкретной операцией объекта, созданного его объектом [CInternetSession.](../../mfc/reference/cinternetsession-class.md) Значение возвращается [в CInternetSession::OnStatusCallback,](../../mfc/reference/cinternetsession-class.md#onstatuscallback) чтобы предоставить статус операции, с которой он идентифицирован. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

## <a name="see-also"></a>См. также раздел

[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFtpConnection](../../mfc/reference/cftpconnection-class.md)<br/>
[Класс CHttpConnection](../../mfc/reference/chttpconnection-class.md)<br/>
[Класс CInternetConnection](../../mfc/reference/cinternetconnection-class.md)<br/>
[Класс CGopherLocator](../../mfc/reference/cgopherlocator-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CInternetSession](../../mfc/reference/cinternetsession-class.md)
