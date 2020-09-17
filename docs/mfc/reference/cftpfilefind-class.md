---
title: Класс CFtpFileFind
ms.date: 05/28/2020
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
helpviewer_keywords:
- CFtpFileFind [MFC], CFtpFileFind
- CFtpFileFind [MFC], FindFile
- CFtpFileFind [MFC], FindNextFile
- CFtpFileFind [MFC], GetFileURL
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
ms.openlocfilehash: e53e16f738f0436cbd02074c10ca24dbcc9d0fd8
ms.sourcegitcommit: 426e327c9f7c3a3b02300e3f924f9786d62958e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "84206236"
---
# <a name="cftpfilefind-class"></a>Класс CFtpFileFind

Помогает в поиске файлов Интернета на FTP-серверах.

## <a name="syntax"></a>Синтаксис

```
class CFtpFileFind : public CFileFind
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кфтпфилефинд:: Кфтпфилефинд](#cftpfilefind)|Формирует объект `CFtpFileFind`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кфтпфилефинд:: Финдфиле](#findfile)|Находит файл на FTP-сервере.|
|[Кфтпфилефинд:: FindNextFile](#findnextfile)|Возобновляет Поиск файла из предыдущего вызова [финдфиле](#findfile).|
|[Кфтпфилефинд:: Жетфилеурл](#getfileurl)|Возвращает URL-адрес найденного файла, включая путь.|

## <a name="remarks"></a>Комментарии

`CFtpFileFind`включает функции-члены, которые начинают поиск, находят файл и возвращает URL или другие описательные сведения о файле.

Другие классы MFC, предназначенные для поиска в Интернете и локальном файле, включают [кгоферфилефинд](../../mfc/reference/cgopherfilefind-class.md) и [кфилефинд](../../mfc/reference/cfilefind-class.md). Вместе с `CFtpFileFind` эти классы предоставляют клиенту простой механизм поиска конкретных файлов, независимо от протокола сервера или типа файла (локального компьютера или удаленного сервера). Нет класса MFC для поиска на HTTP-серверах, так как HTTP не поддерживает прямую обработку файлов, необходимую для поиска.

Дополнительные сведения об использовании `CFtpFileFind` и других классах WinInet см. в статье [Интернет – программирование с помощью WinInet](../../mfc/win32-internet-extensions-wininet.md).

## <a name="example"></a>Пример

В следующем коде показано, как перечислить все файлы в текущем каталоге FTP-сервера.

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>Требования

**Заголовок:** афксинет.h

## <a name="cftpfilefindcftpfilefind"></a><a name="cftpfilefind"></a>Кфтпфилефинд:: Кфтпфилефинд

Эта функция-член вызывается для создания `CFtpFileFind` объекта.

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Параметры

*пконнектион*<br/>
Указатель на объект `CFtpConnection`. Вы можете получить FTP-соединение, вызвав [Цинтернетсессион:: жетфтпконнектион](../../mfc/reference/cinternetsession-class.md#getftpconnection).

*двконтекст*<br/>
Идентификатор контекста для `CFtpFileFind` объекта. Дополнительные сведения см. в следующих **примечаниях**.

### <a name="remarks"></a>Комментарии

Значение по умолчанию для *двконтекст* отправляется MFC `CFtpFileFind` объекту из объекта [Цинтернетсессион](../../mfc/reference/cinternetsession-class.md) , который создал `CFtpFileFind` объект. Можно переопределить значение по умолчанию, чтобы задать идентификатор контекста в качестве значения по своему усмотрению. Идентификатор контекста возвращается в [Цинтернетсессион:: онстатускаллбакк](../../mfc/reference/cinternetsession-class.md#onstatuscallback) , чтобы предоставить состояние для объекта, с которым он определен. Дополнительные сведения об идентификаторе контекста см. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) .

### <a name="example"></a>Пример

  См. пример в обзоре класса выше в этом разделе.

## <a name="cftpfilefindfindfile"></a><a name="findfile"></a>Кфтпфилефинд:: Финдфиле

Вызовите эту функцию-член для поиска файла FTP.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>Параметры

*пстрнаме*<br/>
Указатель на строку, содержащую имя искомого файла. Если значение равно NULL, вызов будет выполнять поиск по шаблону (*).

*dwFlags*<br/>
Флаги, описывающие способ управления этим сеансом. Эти флаги можно сочетать с оператором побитового или (&#124;) и следующими:

- `INTERNET_FLAG_RELOAD`Получение данных из сети, даже если они находятся локально в кэше. Это флаг по умолчанию.

- `INTERNET_FLAG_DONT_CACHE`Не кэшировать данные локально или в любых шлюзах.

- `INTERNET_FLAG_RAW_DATA`Переопределите значение по умолчанию, чтобы вернуть необработанные данные ( [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) структуры для FTP).

- `INTERNET_FLAG_SECURE`Обеспечивает защиту транзакций в сети с помощью SSL или PCT. Этот флаг применяется только к HTTP-запросам.

- `INTERNET_FLAG_EXISTING_CONNECT`По возможности повторно используйте существующие подключения к серверу для новых `FindFile` запросов вместо создания нового сеанса для каждого запроса.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Комментарии

После вызова `FindFile` для получения первого FTP-файла можно вызвать [FindNextFile](#findnextfile) для получения последующих FTP-файлов.

### <a name="example"></a>Пример

  См. предыдущий пример в этом разделе.

## <a name="cftpfilefindfindnextfile"></a><a name="findnextfile"></a>Кфтпфилефинд:: FindNextFile

Вызовите эту функцию-член, чтобы продолжить поиск файла, начатый с помощью вызова функции-члена [финдфиле](#findfile) .

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если есть больше файлов; нуль, если найденный файл является последним в каталоге или если произошла ошибка. Чтобы получить расширенные сведения об ошибке, вызовите функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Если найденный файл является последним файлом в каталоге или не удается найти соответствующие файлы, `GetLastError` функция возвращает ERROR_NO_MORE_FILES.

### <a name="remarks"></a>Комментарии

Эту функцию необходимо вызывать по крайней мере один раз перед вызовом любой функции атрибута (см. раздел [кфилефинд:: FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).

`FindNextFile`заключает в оболочку функцию Win32 [FindNextFile](/windows/win32/api/fileapi/nf-fileapi-findnextfilew).

### <a name="example"></a>Пример

  См. пример ранее в этом разделе.

## <a name="cftpfilefindgetfileurl"></a><a name="getfileurl"></a>Кфтпфилефинд:: Жетфилеурл

Вызовите эту функцию-член, чтобы получить URL указанного файла.

```
CString GetFileURL() const;
```

### <a name="return-value"></a>Возвращаемое значение

Файл и путь к универсальному указателю ресурсов (URL-адрес).

### <a name="remarks"></a>Комментарии

`GetFileURL`функция похожа на функцию-член [кфилефинд::-FilePath](../../mfc/reference/cfilefind-class.md#getfilepath) , за исключением того, что она предоставляет результат в формате URL-адреса. Как и в `CFileFind::GetFilePath` случае, результат не включает имя файла. Например, `file1.txt` находится в методе `//moose/dir/file1.txt:` Returns `ftp://moose/dir/` .

## <a name="see-also"></a>См. также статью

[Класс Кфилефинд](../../mfc/reference/cfilefind-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)<br/>
[Класс Цинтернетфиле](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс Чттпфиле](../../mfc/reference/chttpfile-class.md)
