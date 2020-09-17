---
title: URL-адреса для анализа глобальных и вспомогательных функций
ms.date: 04/03/2017
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
ms.openlocfilehash: c7ce6eeee6deb4537d09e102b925a742ada04650
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837168"
---
# <a name="internet-url-parsing-globals-and-helpers"></a>URL-адреса для анализа глобальных и вспомогательных функций

Когда клиент отправляет запрос на Интернет-сервер, для извлечения сведений о клиенте можно использовать один из глобальных экземпляров синтаксического анализа URL. Вспомогательные функции предоставляют другие функциональные возможности Интернета.

## <a name="internet-url-parsing-globals"></a>Глобальные объекты разбора URL-адресов

|Имя|Описание|
|-|-|
|[AfxParseURL](#afxparseurl)|Анализирует строку URL-адреса и возвращает тип службы и ее компонентов.|
|[AfxParseURLEx](#afxparseurlex)|Анализирует строку URL-адреса и возвращает тип службы и ее компонентов, а также предоставляет имя пользователя и пароль.|

## <a name="other-internet-helpers"></a>Другие вспомогательные функции Интернета

|Имя|Описание|
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Создает исключение, связанное с подключением к Интернету.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Определяет тип обработчика Интернета.|

## <a name="afxparseurl"></a><a name="afxparseurl"></a> афкспарсеурл

Этот глобальный шаблон используется в [Цинтернетсессион:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

```
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort);
```

### <a name="parameters"></a>Параметры

*пструрл*<br/>
Указатель на строку, содержащую URL-адрес для синтаксического анализа.

*двсервицетипе*<br/>
Указывает тип службы Интернета. Возможные значения:

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*стрсервер*<br/>
Первый сегмент URL-адреса, следующий за типом службы.

*strObject*<br/>
Объект, на который ссылается URL-адрес (может быть пустым).

*Nпорт*<br/>
Определяется либо на сервере, либо с помощью частей URL-адреса, если они существуют.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если был успешно проанализирован URL-адрес. в противном случае — значение 0, если оно пусто или не содержит известного типа службы Интернета.

### <a name="remarks"></a>Примечания

Он анализирует строку URL-адреса и возвращает тип службы и ее компонентов.

Например, `AfxParseURL` анализирует URL-адреса формы *Service://Server/dir/DIR/Object.ext:Port* и возвращает ее компоненты, сохраненные следующим образом:

*стрсервер* = = "сервер"

*strObject* = = "/Дир/Дир/обжект/обжект.екст"

*nпорт* = = #port

*двсервицетипе* = = #service

> [!NOTE]
> Для вызова этой функции проект должен включать АФКСИНЕТ. Высоты.

### <a name="requirements"></a>Требования

  **Заголовок** афксинет.h

## <a name="afxparseurlex"></a><a name="afxparseurlex"></a> афкспарсеурлекс

Эта глобальная функция является расширенной версией [афкспарсеурл](#afxparseurl) и используется в [Цинтернетсессион:: OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).

```
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,
    DWORD& dwServiceType,
    CString& strServer,
    CString& strObject,
    INTERNET_PORT& nPort,
    CString& strUsername,
    CString& strPassword,
    DWORD dwFlags = 0);
```

### <a name="parameters"></a>Параметры

*пструрл*<br/>
Указатель на строку, содержащую URL-адрес для синтаксического анализа.

*двсервицетипе*<br/>
Указывает тип службы Интернета. Возможные значения:

- AFX_INET_SERVICE_FTP

- AFX_INET_SERVICE_HTTP

- AFX_INET_SERVICE_HTTPS

- AFX_INET_SERVICE_GOPHER

- AFX_INET_SERVICE_FILE

- AFX_INET_SERVICE_MAILTO

- AFX_INET_SERVICE_NEWS

- AFX_INET_SERVICE_NNTP

- AFX_INET_SERVICE_TELNET

- AFX_INET_SERVICE_WAIS

- AFX_INET_SERVICE_MID

- AFX_INET_SERVICE_CID

- AFX_INET_SERVICE_PROSPERO

- AFX_INET_SERVICE_AFS

- AFX_INET_SERVICE_UNK

*стрсервер*<br/>
Первый сегмент URL-адреса, следующий за типом службы.

*strObject*<br/>
Объект, на который ссылается URL-адрес (может быть пустым).

*Nпорт*<br/>
Определяется либо на сервере, либо с помощью частей URL-адреса, если они существуют.

*струсернаме*<br/>
Ссылка на объект, `CString` содержащий имя пользователя.

*стрпассворд*<br/>
Ссылка на объект, `CString` содержащий пароль пользователя.

*dwFlags*<br/>
Флаги, управляющие анализом URL-адреса. Может быть сочетанием следующих значений:

|Значение|Значение|
|-----------|-------------|
|ICU_DECODE|Преобразование escape-последовательностей% XX в символы.|
|ICU_NO_ENCODE|Не преобразуйте ненадежные символы в escape-последовательность.|
|ICU_NO_META|Не удаляйте мета-последовательности (например, "\"). и "\..") из URL-адреса.|
|ICU_ENCODE_SPACES_ONLY|Закодировать только пробелы.|
|ICU_BROWSER_MODE|Не закодировать или декодировать символы после "#" или "" и не удалять конечные пробелы после "". Если это значение не указано, то весь URL-адрес кодируется, а конечные пробелы удаляются.|

При использовании значения по умолчанию MFC, которое не является флагом, функция преобразует все ненадежные символы и meta-последовательности (такие как \\ ., \.. и \\ ...) в escape-последовательности.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если был успешно проанализирован URL-адрес. в противном случае — значение 0, если оно пусто или не содержит известного типа службы Интернета.

### <a name="remarks"></a>Примечания

Он анализирует строку URL-адреса и возвращает тип службы и ее компонентов, а также предоставляет имя пользователя и пароль. Флаги указывают, как обрабатываются ненадежные символы.

> [!NOTE]
> Для вызова этой функции проект должен включать АФКСИНЕТ. Высоты.

### <a name="requirements"></a>Требования

  **Заголовок** афксинет.h

## <a name="afxgetinternethandletype"></a><a name="afxgetinternethandletype"></a> афксжетинтернесандлетипе

Используйте эту глобальную функцию для определения типа обработчика Интернета.

### <a name="syntax"></a>Синтаксис

  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );
```

### <a name="parameters"></a>Параметры

*хкуери*<br/>
Маркер для Интернет-запроса.

### <a name="return-value"></a>Возвращаемое значение

Любой из типов служб Интернета, определенных WININET. Высоты. Список этих служб Интернета см. в разделе "Примечания". Если маркер имеет значение NULL или не распознан, функция возвращает AFX_INET_SERVICE_UNK.

### <a name="remarks"></a>Примечания

В следующем списке перечислены возможные типы Интернета, возвращаемые `AfxGetInternetHandleType` .

- INTERNET_HANDLE_TYPE_INTERNET

- INTERNET_HANDLE_TYPE_CONNECT_FTP

- INTERNET_HANDLE_TYPE_CONNECT_GOPHER

- INTERNET_HANDLE_TYPE_CONNECT_HTTP

- INTERNET_HANDLE_TYPE_FTP_FIND

- INTERNET_HANDLE_TYPE_FTP_FIND_HTML

- INTERNET_HANDLE_TYPE_FTP_FILE

- INTERNET_HANDLE_TYPE_FTP_FILE_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FIND

- INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML

- INTERNET_HANDLE_TYPE_GOPHER_FILE

- INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML

- INTERNET_HANDLE_TYPE_HTTP_REQUEST

> [!NOTE]
> Чтобы вызвать эту функцию, проект должен включать АФКСИНЕТ. Высоты.

### <a name="requirements"></a>Требования

**Заголовок:** афксинет.h

## <a name="afxthrowinternetexception"></a><a name="afxthrowinternetexception"></a> афкссровинтернетексцептион

Вызывает исключение Интернета.

### <a name="syntax"></a>Синтаксис

```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );
```

### <a name="parameters"></a>Параметры

*двконтекст*<br/>
Идентификатор контекста для операции, вызвавшей ошибку. Значение по умолчанию *двконтекст* указывается изначально в [Цинтернетсессион](cinternetsession-class.md) и передается в классы, производные от [Цинтернетконнектион](cinternetconnection-class.md)и [Цинтернетфиле](cinternetfile-class.md). Для конкретных операций, выполняемых с подключением или файлом, вы обычно переопределяете значение по умолчанию собственным *двконтекст* . Затем это значение возвращается в [Цинтернетсессион:: онстатускаллбакк](cinternetsession-class.md#onstatuscallback) для обнаружения состояния конкретной операции.

*дверрор*<br/>
Ошибка, ставшая причиной исключения.

### <a name="remarks"></a>Примечания

Вы несете ответственность за определение причины на основе кода ошибки операционной системы.

> [!NOTE]
> Для вызова этой функции проект должен включать АФКСИНЕТ. Высоты.

### <a name="requirements"></a>Требования

**Заголовок:** афксинет.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Класс Цинтернетексцептион](cinternetexception-class.md)<br/>
[AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
