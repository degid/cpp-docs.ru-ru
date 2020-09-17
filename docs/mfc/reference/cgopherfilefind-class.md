---
title: Класс CGopherFileFind
ms.date: 11/04/2016
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
helpviewer_keywords:
- CGopherFileFind [MFC], CGopherFileFind
- CGopherFileFind [MFC], FindFile
- CGopherFileFind [MFC], FindNextFile
- CGopherFileFind [MFC], GetCreationTime
- CGopherFileFind [MFC], GetLastAccessTime
- CGopherFileFind [MFC], GetLastWriteTime
- CGopherFileFind [MFC], GetLength
- CGopherFileFind [MFC], GetLocator
- CGopherFileFind [MFC], GetScreenName
- CGopherFileFind [MFC], IsDots
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
ms.openlocfilehash: 7a42b99c919abd9098bff1897c4c5febf443314d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373677"
---
# <a name="cgopherfilefind-class"></a>Класс CGopherFileFind

Помогает в поиске файлов Интернета на серверах gopher.

> [!NOTE]
> Классы `CGopherConnection` `CGopherFile`, `CGopherFileFind` `CGopherLocator` , и их члены были уволены, потому что они не работают на платформе Windows XP, но они будут продолжать работать на более ранних платформах.

## <a name="syntax"></a>Синтаксис

```
class CGopherFileFind : public CFileFind
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|Формирует объект `CGopherFileFind`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CGopherFileFind::FindFile](#findfile)|Находит файл на сервере суслик.|
|[CGopherFileFind::FindNextFile](#findnextfile)|Продолжает поиск файлов от предыдущего вызова [FindFile](#findfile).|
|[CGopherFileFind::GetCreationTime](#getcreationtime)|Получает время создания указанного файла.|
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|Получает время, когда указанный файл был последним доступом.|
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|Получает время, в течение чем указанный файл был последним написанным.|
|[CGopherFileFind::GetLength](#getlength)|Получает длину найденного файла, в байтах.|
|[CGopherFileFind::GetLocator](#getlocator)|Получить `CGopherLocator` объект.|
|[CGopherFileFind::GetScreenName](#getscreenname)|Получает имя суслика экрана.|
|[CGopherFileFind::IsDots](#isdots)|Тесты для текущих маркеров каталога и родительских каталогов при итерации файлов.|

## <a name="remarks"></a>Примечания

`CGopherFileFind`включает функции участника, которые начинают поиск, находят файл и возвращают URL-адрес файла.

Другие классы MFC, предназначенные для поиска в Интернете и локальном файле, включают [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md) и [CFileFind.](../../mfc/reference/cfilefind-class.md) Вместе `CGopherFileFind`с этими классами обеспечивают бесшовный механизм для пользователя, чтобы найти конкретные файлы, независимо от протокола сервера, типа файла, или местоположение (либо локальной машины или удаленного сервера.) Обратите внимание, что нет класса MFC для поиска на серверах HTTP, потому что HTTP не поддерживает прямые манипуляции файлами, требуемые поиском.

> [!NOTE]
> `CGopherFileFind`не поддерживает следующие функции члена своего базового класса [CFileFind:](../../mfc/reference/cfilefind-class.md)

- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)

- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)

- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)

- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)

- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)

Кроме того, при `CGopherFileFind`использовании с функцией `CFileFind` члена [IsDots](../../mfc/reference/cfilefind-class.md#isdots) всегда FALSE.

Для получения дополнительной информации о том, как использовать `CGopherFileFind` и другие классы WinInet, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CGopherFileFind`

## <a name="requirements"></a>Требования

**Заголовок:** afxinet.h

## <a name="cgopherfilefindcgopherfilefind"></a><a name="cgopherfilefind"></a>CGopherFileFind::CGopherFileFind

Эта функция члена называется `CGopherFileFind` для построения объекта.

```
explicit CGopherFileFind(
    CGopherConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*pConnection*<br/>
Указатель на объект [CGopherConnection.](../../mfc/reference/cgopherconnection-class.md)

*Dwcontext*<br/>
Идентификатор контекста для операции. Смотрите **Замечания** для получения дополнительной информации о *dwContext*.

### <a name="remarks"></a>Примечания

Значение по умолчанию для *dwContext* отправляется MFC `CGopherFileFind` объекту с объекта [CInternetSession,](../../mfc/reference/cinternetsession-class.md) создавого `CGopherFileFind` объект. При построении `CGopherFileFind` объекта можно переопределить значение по умолчанию, чтобы установить идентификатор контекста на значение по вашему выбору. Идентификатор контекста возвращается [в CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления статуса объекта, с помощью которого он идентифицируется. Для получения дополнительной информации об идентификаторе контекста смотрите статью [Internet First Steps: WinInet.](../../mfc/wininet-basics.md)

## <a name="cgopherfilefindfindfile"></a><a name="findfile"></a>CGopherFileFind::FindFile

Вызовите эту функцию участника, чтобы найти файл суслика.

```
virtual BOOL FindFile(
    CGopherLocator& refLocator,
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

virtual BOOL FindFile(
    LPCTSTR pstrString,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>Параметры

*рефЛокатор*<br/>
Ссылка на объект [CGopherLocator.](../../mfc/reference/cgopherlocator-class.md)

*pstrString*<br/>
Указатель на строку, содержащую имя файла.

*dwFlags*<br/>
Флаги, описывающие, как обрабатывать этот сеанс. Действительные флаги:

- INTERNET_FLAG_RELOAD получить данные с удаленного сервера, даже если они локально кэшируются.

- INTERNET_FLAG_DONT_CACHE не кэшировать данные, либо локально, ни в каких-либо шлюзов.

- INTERNET_FLAG_SECURE Запрос безопасных транзакций на проводе с безопасных разъемов слоя или РСТ. Этот флаг применим только к запросам HTTP.

- INTERNET_FLAG_USE_EXISTING Если это возможно, повторно использовать существующие соединения на сервере для новых `FindFile` запросов, вместо создания нового сеанса для каждого запроса.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенную информацию об ошибке, позвоните в функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Примечания

После `FindFile` вызова, чтобы получить первый объект суслик, вы можете вызвать [FindNextFile](#findnextfile) для получения последующих файлов суслик.

## <a name="cgopherfilefindfindnextfile"></a><a name="findnextfile"></a>CGopherFileFind::FindNextFile

Вызов эту функцию участника для продолжения поиска файлов, начатого с вызова на [CGopherFileFind::FindFile](#findfile).

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если есть больше файлов; ноль, если найденный файл является последним в каталоге или если произошла ошибка. Чтобы получить расширенную информацию об ошибке, позвоните в функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Если найденный файл является последним файлом в каталоге, или если `GetLastError` не может быть найдено соответствие файлов, функция возвращается ERROR_NO_MORE_FILES.

## <a name="cgopherfilefindgetcreationtime"></a><a name="getcreationtime"></a>CGopherFileFind::GetCreationTime

Получает время создания для текущего файла.

```
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;
virtual BOOL GetCreationTime(CTime& refTime) const;
```

### <a name="parameters"></a>Параметры

*pTimeStamp*<br/>
Указатель на структуру [FILETIME,](/windows/win32/api/minwinbase/ns-minwinbase-filetime) содержащую время создания файла.

*refTime*<br/>
Ссылка на объект [CTime.](../../atl-mfc-shared/reference/ctime-class.md)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; 0, если не удается. `GetCreationTime`возвращает 0 только в том случае, `CGopherFileFind` если [FindNextFile](#findnextfile) никогда не был вызван на этот объект.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetCreationTime`по крайней мере один раз, прежде чем звонить .

> [!NOTE]
> Не все файловые системы используют одну и ту же семантику для реализации временной отметки, возвращенной этой функцией. Эта функция может вернуть то же значение, возвращенное другими функциями штампа времени, если базовая файловая система или сервер не поддерживает сохранение атрибута времени. Ознакомьтесь с [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) структурой для получения информации о временных форматах. На некоторых операционных системах, вернулся время в часовом поясе локальных к машине был файл находится. Для получения дополнительной информации смотрите API Win32 [FileTimeToLocalFileTime.](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)

## <a name="cgopherfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>CGopherFileFind::GetLastAccessTime

Получает время, когда указанный файл был последним доступом.

```
virtual BOOL GetLastAccessTime(CTime& refTime) const;
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;
```

### <a name="parameters"></a>Параметры

*refTime*<br/>
Ссылка на объект [CTime.](../../atl-mfc-shared/reference/ctime-class.md)

*pTimeStamp*<br/>
Указатель на структуру [FILETIME,](/windows/win32/api/minwinbase/ns-minwinbase-filetime) содержащую время последнего доступа к файлу.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; 0, если не удается. `GetLastAccessTime`возвращает 0 только в том случае, `CGopherFileFind` если [FindNextFile](#findnextfile) никогда не был вызван на этот объект.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetLastAccessTime`по крайней мере один раз, прежде чем звонить .

> [!NOTE]
> Не все файловые системы используют одну и ту же семантику для реализации временной отметки, возвращенной этой функцией. Эта функция может вернуть то же значение, возвращенное другими функциями штампа времени, если базовая файловая система или сервер не поддерживает сохранение атрибута времени. Ознакомьтесь с [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) структурой для получения информации о временных форматах. На некоторых операционных системах, вернулся время в часовом поясе локальных к машине был файл находится. Для получения дополнительной информации смотрите API Win32 [FileTimeToLocalFileTime.](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)

## <a name="cgopherfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>CGopherFileFind::GetLastWriteTime

Получает последний раз, когда файл был изменен.

```
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;
virtual BOOL GetLastWriteTime(CTime& refTime) const;
```

### <a name="parameters"></a>Параметры

*pTimeStamp*<br/>
Указатель на структуру [FILETIME,](/windows/win32/api/minwinbase/ns-minwinbase-filetime) содержащую время, в котором файл был последний раз написан.

*refTime*<br/>
Ссылка на объект [CTime.](../../atl-mfc-shared/reference/ctime-class.md)

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если успешно; 0, если не удается. `GetLastWriteTime`возвращает 0 только в том случае, `CGopherFileFind` если [FindNextFile](#findnextfile) никогда не был вызван на этот объект.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetLastWriteTime`по крайней мере один раз, прежде чем звонить .

> [!NOTE]
> Не все файловые системы используют одну и ту же семантику для реализации временной отметки, возвращенной этой функцией. Эта функция может вернуть то же значение, возвращенное другими функциями штампа времени, если базовая файловая система или сервер не поддерживает сохранение атрибута времени. Ознакомьтесь с [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) структурой для получения информации о временных форматах. На некоторых операционных системах, вернулся время в часовом поясе локальных к машине был файл находится. Для получения дополнительной информации смотрите API Win32 [FileTimeToLocalFileTime.](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)

## <a name="cgopherfilefindgetlength"></a><a name="getlength"></a>CGopherFileFind::GetLength

Вызовите эту функцию участника, чтобы получить длину, в байтах, найденного файла.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина, в байтах, найденного файла.

### <a name="remarks"></a>Примечания

`GetLength`использует структуру Win32 [WIN32_FIND_DATA,](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) чтобы получить значение размера файла в байтах.

> [!NOTE]
> По состоянию на MFC 7.0, `GetLength` поддерживает 64-битный целый ряд типов. Ранее существующий код, построенный с этой новой версией библиотеки, может привести к предупреждениям о усечении.

### <a name="example"></a>Пример

  Смотрите пример [для CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) (реализация базового класса).

## <a name="cgopherfilefindgetlocator"></a><a name="getlocator"></a>CGopherFileFind::GetLocator

Позвоните в эту функцию участника, чтобы получить объект [CGopherLocator,](../../mfc/reference/cgopherlocator-class.md) который [FindFile](#findfile) использует для поиска файла суслика.

```
CGopherLocator GetLocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CGopherLocator` .

## <a name="cgopherfilefindgetscreenname"></a><a name="getscreenname"></a>CGopherFileFind::GetScreenName

Позвоните в эту функцию участника, чтобы получить имя экрана суслика.

```
CString GetScreenName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название суслика экрана.

## <a name="cgopherfilefindisdots"></a><a name="isdots"></a>CGopherFileFind::IsDots

Тесты для текущих маркеров каталога и родительских каталогов при итерации файлов.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если найденный файл имеет имя "." или "..," указывает на то, что найденный файл на самом деле является каталогом. В противном случае 0.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `IsDots`по крайней мере один раз, прежде чем звонить .

## <a name="see-also"></a>См. также раздел

[Класс CFileFind](../../mfc/reference/cfilefind-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)<br/>
[Класс CFileFind](../../mfc/reference/cfilefind-class.md)<br/>
[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CHttpfile](../../mfc/reference/chttpfile-class.md)
