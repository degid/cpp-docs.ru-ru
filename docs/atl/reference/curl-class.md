---
title: Класс CUrl
ms.date: 05/06/2019
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
ms.openlocfilehash: 3468e17b031d0a72bc56d915c689fbe4c78859e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330476"
---
# <a name="curl-class"></a>Класс CUrl

Этот класс представляет URL-адрес. Это позволяет манипулировать каждым элементом URL независимо от других, независимо от того, разбор существующей строки URL или построение строки с нуля.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CUrl
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CUrl::CUrl](#curl)|Конструктор.|
|[CUrl::-CUrl](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CUrl::Каноникализация](#canonicalize)|Вызовите этот метод для преобразования строки URL в каноническую форму.|
|[CUrl::Ясно](#clear)|Вызовите этот метод, чтобы очистить все поля URL.|
|[CUrl::CrackUrl](#crackurl)|Вызов исчерпайте этот метод для декодирования и разбора URL- данных.|
|[CUrl::CreateUrl](#createurl)|Вызовите этот метод для создания URL-адреса.|
|[CUrl::GetExtraInfo](#getextrainfo)|Вызовите этот метод, чтобы получить дополнительную информацию (например, *текст* или *текст)* из URL.|
|[CUrl:GetExtraInfoДлина](#getextrainfolength)|Вызовите этот метод, чтобы получить длину дополнительной информации (например, *текст* или *текст),* чтобы извлечь из URL.|
|[CUrl::GetHostName](#gethostname)|Вызовите этот метод, чтобы получить имя хоста из URL.|
|[CUrl::GetHostNameДлин](#gethostnamelength)|Вызовите этот метод, чтобы получить длину имени хоста.|
|[CUrl::GetPassword](#getpassword)|Позвоните по этому методу, чтобы получить пароль от URL.|
|[CUrl:GetPasswordДлина](#getpasswordlength)|Вызовите этот метод, чтобы получить длину пароля.|
|[CUrl::GetPortNumber](#getportnumber)|Вызовите этот метод, чтобы получить номер порта с точки зрения ATL_URL_PORT.|
|[CUrl::GetScheme](#getscheme)|Вызовите этот метод, чтобы получить схему URL.|
|[CUrl::GetSchemeName](#getschemename)|Вызовите этот метод, чтобы получить имя схемы URL.|
|[CUrl::GetSchemeNameДлин](#getschemenamelength)|Вызовите этот метод, чтобы получить длину имени схемы URL.|
|[CUrl::GetUrlДлин](#geturllength)|Вызовите этот метод, чтобы получить длину URL.|
|[CUrl::GetUrlPath](#geturlpath)|Вызовите этот метод, чтобы получить путь URL.|
|[CUrl::GetUrlPathДлин](#geturlpathlength)|Вызовите этот метод, чтобы получить длину пути URL.|
|[CUrl::GetUserName](#getusername)|Вызовите этот метод, чтобы получить имя пользователя из URL.|
|[CUrl::GetUserNameДлин](#getusernamelength)|Вызовите этот метод, чтобы получить длину имени пользователя.|
|[CUrl::SetExtraInfo](#setextrainfo)|Вызовите этот метод, чтобы установить дополнительную информацию (например, *текст* или *текст)* URL.|
|[CUrl::SetHostName](#sethostname)|Вызовите этот метод, чтобы установить имя узла.|
|[CUrl::SetPassword](#setpassword)|Вызовите этот метод, чтобы установить пароль.|
|[CUrl::SetPortNumber](#setportnumber)|Вызовите этот метод, чтобы установить номер порта с точки зрения ATL_URL_PORT.|
|[CUrl::SetScheme](#setscheme)|Вызовите этот метод, чтобы настроить схему URL.|
|[CUrl::SetSchemeName](#setschemename)|Вызовите этот метод, чтобы установить имя схемы URL.|
|[CUrl::SetUrlPath](#seturlpath)|Вызовите этот метод, чтобы установить путь URL.|
|[CUrl::SetUserName](#setusername)|Вызовите этот метод, чтобы установить имя пользователя.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CUrl::оператор](#operator_eq)|Присваивает `CUrl` указанный `CUrl` объект текущему объекту.|

## <a name="remarks"></a>Примечания

`CUrl`позволяет манипулировать полями URL, такими как путь или номер порта. `CUrl`понимает URL-адреса следующей формы:

\<\<Схема>:// ПользовательИмя\<>: Пароль>\@ \<Хостимя>:\<PortNumber>/\<UrlPath>\<ExtraInfo>

(Некоторые поля не являются обязательными.) Например, рассмотрим этот URL:

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[CUrl::CrackUrl](#crackurl) разбирает его следующим образом:

- Схема: "http" или [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- UserName: "кто-то"

- Пароль: "секретно"

- ХостНам: "`www.microsoft.com`

- ПортНомер: 80

- UrlPath: "visualc/stuff.htm"

- ЭкстраИнфо: "#contents"

Для манипулирования полем UrlPath (например), вы будете использовать [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength)и [SetUrlPath](#seturlpath). Для создания полной строки URL можно использовать [CreateUrl.](#createurl)

## <a name="requirements"></a>Требования

**Заголовок:** atlutil.h

## <a name="curlcanonicalize"></a><a name="canonicalize"></a>CUrl::Каноникализация

Вызовите этот метод для преобразования строки URL в каноническую форму.

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*dwFlags*<br/>
Флаги, контролирующие канонизацию. Если флаги не указаны *(dwFlags* - 0), метод преобразует все небезопасные \\символы и мета-последовательности (например, ..,, и \\...) для избежания последовательностей. *dwFlags* может быть одним из следующих значений:

- ATL_URL_BROWSER_MODE: не кодирует и не расшифровывает символы после "я" или "" и не удаляет захдневое белое пространство после "". Если это значение не указано, весь URL закодирован и задняющее белое пространство удаляется.

- ATL_URL _DECODE: Преобразует все последовательности %XX в символы, включая последовательности побега, до того, как URL будет разогнан.

- ATL_URL _ENCODE_PERCENT: Кодирует любые процентные знаки. По умолчанию знаки процента не кодируются.

- ATL_URL _ENCODE_SPACES_ONLY: Кодирует только пробелы.

- ATL_URL _NO_ENCODE: не преобразует небезопасные символы, чтобы избежать последовательностей.

- ATL_URL _NO_META: не удаляет мета-последовательности (такие как "." и "..) из URL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Преобразование в каноническую форму включает в себя преобразование небезопасных символов и пробелов, чтобы избежать последовательностей.

## <a name="curlclear"></a><a name="clear"></a>CUrl::Ясно

Вызовите этот метод, чтобы очистить все поля URL.

```
inline void Clear() throw();
```

## <a name="curlcrackurl"></a><a name="crackurl"></a>CUrl::CrackUrl

Вызов исчерпайте этот метод для декодирования и разбора URL- данных.

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Параметры

*lpszUrl*<br/>
URL-адрес.

*dwFlags*<br/>
Укажите ATL_URL_DECODE или ATL_URL_ESCAPE конвертировать все символы побега в *lpszUrl* в их реальные значения после разбора. (Перед визуальным C' 2005, ATL_URL_DECODE преобразовал все символы побега до разбора.)

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="curlcreateurl"></a><a name="createurl"></a>CUrl::CreateUrl

Этот метод строит строку URL из полей компонентов объекта CUrl.

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>Параметры

*lpszUrl*<br/>
Буфер строки для удержания полной строки URL.

*pdwMaxДлина*<br/>
Максимальная длина строки *lpszUrl* буфера.

*dwFlags*<br/>
Укажите ATL_URL_ESCAPE преобразовать все символы побега в *lpszUrl* в их реальные значения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Этот метод придатков к отдельным полям для построения полной строки URL с использованием следующего формата:

**\<\<схема>://\<пользователь>: пройти>\@ \< \<домена \<>:\<путь>порта>дополнительные>**

При вызове этого метода параметр *pdwMaxLength* должен изначально содержать максимальную длину строки буфера, на который ссылается параметр *lpszUrl.* Значение параметра *pdwMaxLength* будет обновляться с фактической длиной строки URL.

### <a name="example"></a>Пример

Этот пример демонстрирует создание объекта CUrl и извлечение его строки URL

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

## <a name="curlcurl"></a><a name="curl"></a>CUrl::CUrl

Конструктор.

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Параметры

*urlThat*<br/>
Объект `CUrl` для копирования для создания URL-адреса.

## <a name="curlcurl"></a><a name="dtor"></a>CUrl::-CUrl

Деструктор

```
~CUrl() throw();
```

## <a name="curlgetextrainfo"></a><a name="getextrainfo"></a>CUrl::GetExtraInfo

Вызовите этот метод, чтобы получить дополнительную информацию (например, *текст* или *текст)* из URL.

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку, содержащую дополнительную информацию.

## <a name="curlgetextrainfolength"></a><a name="getextrainfolength"></a>CUrl:GetExtraInfoДлина

Вызовите этот метод, чтобы получить длину дополнительной информации (например, *текст* или *текст),* чтобы извлечь из URL.

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину строки, содержащей дополнительную информацию.

## <a name="curlgethostname"></a><a name="gethostname"></a>CUrl::GetHostName

Вызовите этот метод, чтобы получить имя хоста из URL.

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает имя хоста.

## <a name="curlgethostnamelength"></a><a name="gethostnamelength"></a>CUrl::GetHostNameДлин

Вызовите этот метод, чтобы получить длину имени хоста.

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину имени хоста.

## <a name="curlgetpassword"></a><a name="getpassword"></a>CUrl::GetPassword

Позвоните по этому методу, чтобы получить пароль от URL.

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает пароль.

## <a name="curlgetpasswordlength"></a><a name="getpasswordlength"></a>CUrl:GetPasswordДлина

Вызовите этот метод, чтобы получить длину пароля.

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину пароля.

## <a name="curlgetportnumber"></a><a name="getportnumber"></a>CUrl::GetPortNumber

Вызовите этот метод, чтобы получить номер порта.

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает номер порта.

## <a name="curlgetscheme"></a><a name="getscheme"></a>CUrl::GetScheme

Вызовите этот метод, чтобы получить схему URL.

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает [ATL_URL_SCHEME](atl-url-scheme-enum.md) значение, описывающее схему URL.

## <a name="curlgetschemename"></a><a name="getschemename"></a>CUrl::GetSchemeName

Вызовите этот метод, чтобы получить имя схемы URL.

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает имя схемы URL (например, "http" или "ftp").

## <a name="curlgetschemenamelength"></a><a name="getschemenamelength"></a>CUrl::GetSchemeNameДлин

Вызовите этот метод, чтобы получить длину имени схемы URL.

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину имени схемы URL.

## <a name="curlgeturllength"></a><a name="geturllength"></a>CUrl::GetUrlДлин

Вызовите этот метод, чтобы получить длину URL.

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину URL-адреса.

## <a name="curlgeturlpath"></a><a name="geturlpath"></a>CUrl::GetUrlPath

Вызовите этот метод, чтобы получить путь URL.

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает путь URL-адреса.

## <a name="curlgeturlpathlength"></a><a name="geturlpathlength"></a>CUrl::GetUrlPathДлин

Вызовите этот метод, чтобы получить длину пути URL.

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину пути URL.

## <a name="curlgetusername"></a><a name="getusername"></a>CUrl::GetUserName

Вызовите этот метод, чтобы получить имя пользователя из URL.

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает имя пользователя.

## <a name="curlgetusernamelength"></a><a name="getusernamelength"></a>CUrl::GetUserNameДлин

Вызовите этот метод, чтобы получить длину имени пользователя.

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает длину имени пользователя.

## <a name="curloperator-"></a><a name="operator_eq"></a>CUrl::оператор

Присваивает `CUrl` указанный `CUrl` объект текущему объекту.

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Параметры

*urlThat*<br/>
Объект `CUrl` для копирования в текущий объект.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на текущий объект.

## <a name="curlsetextrainfo"></a><a name="setextrainfo"></a>CUrl::SetExtraInfo

Вызовите этот метод, чтобы установить дополнительную информацию (например, *текст* или *текст)* URL.

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>Параметры

*lpszInfo*<br/>
Строка, содержащая дополнительную информацию для включения в URL-

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="curlsethostname"></a><a name="sethostname"></a>CUrl::SetHostName

Вызовите этот метод, чтобы установить имя узла.

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>Параметры

*lpszHost*<br/>
Имя сервера.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="curlsetpassword"></a><a name="setpassword"></a>CUrl::SetPassword

Вызовите этот метод, чтобы установить пароль.

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>Параметры

*lpszPass*<br/>
Пароль.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="curlsetportnumber"></a><a name="setportnumber"></a>CUrl::SetPortNumber

Вызовите этот метод, чтобы установить номер порта.

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>Параметры

*nPrt*<br/>
номер порта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="curlsetscheme"></a><a name="setscheme"></a>CUrl::SetScheme

Вызовите этот метод, чтобы настроить схему URL.

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>Параметры

*nСхема*<br/>
Одним из [ATL_URL_SCHEME](atl-url-scheme-enum.md) значений для схемы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Вы также можете установить схему по имени (см. [CUrl::SetSchemeName).](#setschemename)

## <a name="curlsetschemename"></a><a name="setschemename"></a>CUrl::SetSchemeName

Вызовите этот метод, чтобы установить имя схемы URL.

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>Параметры

*lpszSchm*<br/>
Имя схемы URL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

### <a name="remarks"></a>Примечания

Вы также можете установить схему, используя [ATL_URL_SCHEME](atl-url-scheme-enum.md) константу (см. [CUrl:: SetScheme).](#setscheme)

## <a name="curlseturlpath"></a><a name="seturlpath"></a>CUrl::SetUrlPath

Вызовите этот метод, чтобы установить путь URL.

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>Параметры

*lpszPath*<br/>
Путь URL-.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="curlsetusername"></a><a name="setusername"></a>CUrl::SetUserName

Вызовите этот метод, чтобы установить имя пользователя.

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>Параметры

*lpszUser*<br/>
Имя пользователя.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успех, FALSE на неудачу.

## <a name="see-also"></a>См. также раздел

[Классы](../../atl/reference/atl-classes.md)
