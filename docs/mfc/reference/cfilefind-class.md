---
title: Класс CFileFind
ms.date: 11/04/2016
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
ms.openlocfilehash: 5bb53a6abf7040bd6ee9f5f2cf56b0feb4d62e66
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755030"
---
# <a name="cfilefind-class"></a>Класс CFileFind

Выполняет локальный поиск файлов и является базовым классом для [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) и [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), которые выполняют поиск файлов в Интернете.

## <a name="syntax"></a>Синтаксис

```
class CFileFind : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFileFind::CFileFind](#cfilefind)|Формирует объект `CFileFind`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFileFind::Закрыть](#close)|Закрывает запрос на поиск.|
|[CFileFind::FindFile](#findfile)|Поиск каталога для указанного имени файла.|
|[CFileFind::FindNextFile](#findnextfile)|Продолжает поиск файлов от предыдущего вызова [FindFile](#findfile).|
|[CFileFind::GetCreationTime](#getcreationtime)|Получает время создания файла.|
|[CFileFind::GetFileName](#getfilename)|Получает имя, включая расширение, найденного файла|
|[CFileFind::GetFilePath](#getfilepath)|Получает весь путь найденного файла.|
|[CFileFind::GetFileTitle](#getfiletitle)|Получает название найденного файла. Название не включает расширение.|
|[CFileFind::GetFileURL](#getfileurl)|Получает URL-адрес, включая путь файла, найденного файла.|
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Получает время, когда файл был последним доступом.|
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Получает время, когда файл был последний изменен и сохранен.|
|[CFileFind::GetLength](#getlength)|Получает длину найденного файла, в байтах.|
|[CFileFind::GetRoot](#getroot)|Получает корневой каталог найденного файла.|
|[CFileFind::Архив](#isarchived)|Определяет, архивируется ли найденный файл.|
|[CFileFind::IsCompressed](#iscompressed)|Определяет, сжимается ли найденный файл.|
|[CFileFind::IsDirectory](#isdirectory)|Определяет, является ли найденный файл каталогом.|
|[CFileFind::IsDots](#isdots)|Определяет, имеет ли имя найденного файла имя "." или "..", указывая, что на самом деле это каталог.|
|[CFileFind::IsHidden](#ishidden)|Определяет, является ли найденный файл скрытым.|
|[CFileFind::IsNormal](#isnormal)|Определяет, является ли найденный файл нормальным (другими словами, нет других атрибутов).|
|[CFileFind::IsReadOnly](#isreadonly)|Определяет, является ли найденный файл прочитан только для чтения.|
|[CFileFind::IsSystem](#issystem)|Определяет, является ли найденный файл системным файлом.|
|[CFileFind:: Временно](#istemporary)|Определяет, является ли найденный файл временным.|
|[CFileFind::MatchesMask](#matchesmask)|Указывает на найденные атрибуты файла.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CFileFind::ЗакрытьКонтекст](#closecontext)|Закрывает файл, указанный текущей ручкой поиска.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CFileFind::m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект.|

## <a name="remarks"></a>Примечания

`CFileFind`включает функции участника, которые начинают поиск, находят файл и возвращают заголовок, имя или путь файла. Для поиска в Интернете функция участника [GetFileURL](#getfileurl) возвращает URL-адрес файла.

`CFileFind`является базовым классом для двух других классов MFC, предназначенных для поиска определенных типов серверов: `CGopherFileFind` работает специально с серверами сусликов и `CFtpFileFind` работает специально с серверами FTP. Вместе эти три класса обеспечивают бесшовный механизм для клиента, чтобы найти файлы, независимо от протокола сервера, типа файла или местоположения, либо на локальной машине или удаленном сервере.

Следующий код будет перечислять все файлы в текущем каталоге, печатая имя каждого файла:

[!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]

Чтобы сохранить пример простым, этот код использует `cout` класс Стандартной библиотеки СЗ. Линия `cout` может быть заменена `CListBox::AddString`вызовом, например, в программе с графическим пользовательским интерфейсом.

Для получения дополнительной информации о том, как использовать `CFileFind` и другие классы WinInet, см. [Internet Programming with WinInet](../../mfc/win32-internet-extensions-wininet.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CFileFind`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cfilefindcfilefind"></a><a name="cfilefind"></a>CFileFind::CFileFind

Эта функция члена вызывается при построении `CFileFind` объекта.

```
CFileFind();
CFileFind(CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Параметры

*Ptm*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="example"></a>Пример

  Смотрите пример [CFileFind::GetFileName](#getfilename).

## <a name="cfilefindclose"></a><a name="close"></a>CFileFind::Закрыть

Вызов ими функции участника, чтобы закончить поиск, сбросить контекст и высвободить все ресурсы.

```cpp
void Close();
```

### <a name="remarks"></a>Примечания

После `Close`вызова вам не нужно создавать `CFileFind` новый экземпляр перед вызовом [FindFile,](#findfile) чтобы начать новый поиск.

### <a name="example"></a>Пример

  Смотрите пример [CFileFind::GetFileName](#getfilename).

## <a name="cfilefindclosecontext"></a><a name="closecontext"></a>CFileFind::ЗакрытьКонтекст

Закрывает файл, указанный текущей ручкой поиска.

```
virtual void CloseContext();
```

### <a name="remarks"></a>Примечания

Закрывает файл, указанный текущим значением ручки поиска. Переизбь эту функцию для изменения поведения по умолчанию.

Вы должны позвонить [в Функции FindFile](#findfile) или [FindNextFile](#findnextfile) хотя бы один раз, чтобы получить действительную ручку поиска. `FindFile` Функции `FindNextFile` используют ручку поиска для поиска файлов с именами, которые соответствуют заданной фамилии.

## <a name="cfilefindfindfile"></a><a name="findfile"></a>CFileFind::FindFile

Вызовите эту функцию участника, чтобы открыть поиск файлов.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwUnused = 0);
```

### <a name="parameters"></a>Параметры

*pstrName*<br/>
Указатель на строку, содержащую имя файла, чтобы найти. Если вы проходите NULL для *pstrName* `FindFile` ,\*делает подстановочный знак (кв. ) поиск.

*dwUnused*<br/>
Зарезервировано, `FindFile` чтобы сделать полиморфные с производными классами. Должно быть равно 0.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенную информацию об ошибке, позвоните в функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Примечания

После `FindFile` вызова для начала поиска файлов, позвоните [FindNextFile](#findnextfile) для получения последующих файлов. Вы должны `FindNextFile` позвонить по крайней мере один раз, прежде чем позвонить любой из следующих функций члена атрибута:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [ПолучитьДлина](#getlength)

- [GetRoot](#getroot)

- [Архив](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [IsDots](#isdots)

- [Скрытый](#ishidden)

- [IsNormal](#isnormal)

- [Isreadonly](#isreadonly)

- [IsSystem](#issystem)

- [Временно](#istemporary)

- [СпичкиМаска](#matchesmask)

### <a name="example"></a>Пример

  Смотрите пример [CFileFind::IsDirectory](#isdirectory).

## <a name="cfilefindfindnextfile"></a><a name="findnextfile"></a>CFileFind::FindNextFile

Вызов эту функцию участника для продолжения поиска файлов от предыдущего вызова на [FindFile.](#findfile)

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если есть больше файлов; ноль, если найденный файл является последним в каталоге или если произошла ошибка. Чтобы получить расширенную информацию об ошибке, позвоните в функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Если найденный файл является последним файлом в каталоге, или если `GetLastError` не может быть найдено соответствие файлов, функция возвращается ERROR_NO_MORE_FILES.

### <a name="remarks"></a>Примечания

Вы должны `FindNextFile` позвонить по крайней мере один раз, прежде чем позвонить любой из следующих функций члена атрибута:

- [GetCreationTime](#getcreationtime)

- [GetFileName](#getfilename)

- [GetFileTitle](#getfiletitle)

- [GetFilePath](#getfilepath)

- [GetFileURL](#getfileurl)

- [GetLastAccessTime](#getlastaccesstime)

- [GetLastWriteTime](#getlastwritetime)

- [ПолучитьДлина](#getlength)

- [GetRoot](#getroot)

- [Архив](#isarchived)

- [IsCompressed](#iscompressed)

- [IsDirectory](#isdirectory)

- [IsDots](#isdots)

- [Скрытый](#ishidden)

- [IsNormal](#isnormal)

- [Isreadonly](#isreadonly)

- [IsSystem](#issystem)

- [Временно](#istemporary)

- [СпичкиМаска](#matchesmask)

`FindNextFile`обертывает функцию Win32 [FindNextFile](/windows/win32/api/fileapi/nf-fileapi-findnextfilew).

### <a name="example"></a>Пример

  Смотрите пример [CFileFind::IsDirectory](#isdirectory).

## <a name="cfilefindgetcreationtime"></a><a name="getcreationtime"></a>CFileFind::GetCreationTime

Вызов исчергнение функции участника, чтобы получить время создания указанного файла.

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

Nonzero, если успешно; 0, если не удается. `GetCreationTime`возвращает 0 только в том случае, `CFileFind` если [FindNextFile](#findnextfile) никогда не был вызван на этот объект.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetCreationTime`по крайней мере один раз, прежде чем звонить .

> [!NOTE]
> Не все файловые системы используют одну и ту же семантику для реализации временной отметки, возвращенной этой функцией. Эта функция может вернуть то же значение, возвращенное другими функциями штампа времени, если базовая файловая система или сервер не поддерживает сохранение атрибута времени. Ознакомьтесь с [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) структурой для получения информации о временных форматах. На некоторых операционных системах, возвращенное время находится в часовом поясе локальных к машине был файл находится. Для получения дополнительной информации смотрите API Win32 [FileTimeToLocalFileTime.](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindgetfilename"></a><a name="getfilename"></a>CFileFind::GetFileName

Вызовите эту функцию участника, чтобы получить имя найденного файла.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя самого недавно найденного файла.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) по крайней мере один раз, прежде чем звонить GetFileName.

`GetFileName`является одной `CFileFind` из трех функций члена, которые возвращают ту или иную форму имени файла. Следующий список описывает три и как они различаются:

- `GetFileName`возвращает имя файла, включая расширение. Например, `GetFileName` вызов для создания сообщения пользователя о файле *c: myhtml-myfile.txt* возвращает имя файла *myfile.txt*.

- [GetFilePath](#getfilepath) возвращает весь путь для файла. Например, `GetFilePath` вызов для создания сообщения пользователя о файле *c: myhtml-myfile.txt* возвращает путь файла *c: myhtml-myfile.txt*.

- [GetFileTitle](#getfiletitle) возвращает имя файла, за исключением расширения файла. Например, `GetFileTitle` вызов для создания сообщения пользователя о файле *c: myhtml-myfile.txt* возвращает название *файла myfile*.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]

## <a name="cfilefindgetfilepath"></a><a name="getfilepath"></a>CFileFind::GetFilePath

Вызов исчерпайте эту функцию участника, чтобы получить полный путь указанного файла.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Путь указанного файла.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetFilePath`по крайней мере один раз, прежде чем звонить .

`GetFilePath`является одной `CFileFind` из трех функций члена, которые возвращают ту или иную форму имени файла. Следующий список описывает три и как они различаются:

- [GetFileName](#getfilename) возвращает имя файла, включая расширение. Например, `GetFileName` вызов для создания сообщения пользователя о файле *c: myhtml-myfile.txt* возвращает имя файла *myfile.txt*.

- `GetFilePath`возвращает весь путь для файла. Например, `GetFilePath` вызов для создания сообщения `c:\myhtml\myfile.txt` пользователя о `c:\myhtml\myfile.txt`файле возвращает путь файла.

- [GetFileTitle](#getfiletitle) возвращает имя файла, за исключением расширения файла. Например, `GetFileTitle` вызов для создания сообщения пользователя о файле *c: myhtml-myfile.txt* возвращает название *файла myfile*.

### <a name="example"></a>Пример

  Смотрите пример [CFileFind::GetFileName](#getfilename).

## <a name="cfilefindgetfiletitle"></a><a name="getfiletitle"></a>CFileFind::GetFileTitle

Вызовите эту функцию участника, чтобы получить название найденного файла.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название файла.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetFileTitle`по крайней мере один раз, прежде чем звонить .

`GetFileTitle`является одной `CFileFind` из трех функций члена, которые возвращают ту или иную форму имени файла. Следующий список описывает три и как они различаются:

- [GetFileName](#getfilename) возвращает имя файла, включая расширение. Например, `GetFileName` вызов для создания сообщения пользователя о файле *c: myhtml-myfile.txt* возвращает имя файла *myfile.txt*.

- [GetFilePath](#getfilepath) возвращает весь путь для файла. Например, `GetFilePath` вызов для создания сообщения пользователя о файле *c: myhtml-myfile.txt* возвращает путь файла *c: myhtml-myfile.txt*.

- `GetFileTitle`возвращает имя файла, исключая расширение файла. Например, `GetFileTitle` вызов для создания сообщения пользователя о файле *c: myhtml-myfile.txt* возвращает название *файла myfile*.

### <a name="example"></a>Пример

  Смотрите пример [CFileFind::GetFileName](#getfilename).

## <a name="cfilefindgetfileurl"></a><a name="getfileurl"></a>CFileFind::GetFileURL

Вызов исчерпе эту функцию участника для получения указанного URL-адреса.

```
virtual CString GetFileURL() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный URL- АДРЕС.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetFileURL`по крайней мере один раз, прежде чем звонить .

`GetFileURL`похож на функцию члена [GetFilePath](#getfilepath), за исключением `file://path`того, что он возвращает URL в форме . Например, `GetFileURL` вызов, чтобы получить полный URL для *myfile.txt* возвращает URL: `file://c:\myhtml\myfile.txt`

### <a name="example"></a>Пример

  Смотрите пример [CFileFind::GetFileName](#getfilename).

## <a name="cfilefindgetlastaccesstime"></a><a name="getlastaccesstime"></a>CFileFind::GetLastAccessTime

Вызовите эту функцию участника, чтобы получить время, к которое был последний доступ к указанному файлу.

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

Nonzero, если успешно; 0, если не удается. `GetLastAccessTime`возвращает 0 только в том случае, `CFileFind` если [FindNextFile](#findnextfile) никогда не был вызван на этот объект.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetLastAccessTime`по крайней мере один раз, прежде чем звонить .

> [!NOTE]
> Не все файловые системы используют одну и ту же семантику для реализации временной отметки, возвращенной этой функцией. Эта функция может вернуть то же значение, возвращенное другими функциями штампа времени, если базовая файловая система или сервер не поддерживает сохранение атрибута времени. Ознакомьтесь с [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) структурой для получения информации о временных форматах. На некоторых операционных системах, возвращенное время находится в часовом поясе локальных к машине был файл находится. Для получения дополнительной информации смотрите API Win32 [FileTimeToLocalFileTime.](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindgetlastwritetime"></a><a name="getlastwritetime"></a>CFileFind::GetLastWriteTime

Вызовите эту функцию участника, чтобы получить последний раз, когда файл был изменен.

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

Nonzero, если успешно; 0, если не удается. `GetLastWriteTime`возвращает 0 только в том случае, `CFileFind` если [FindNextFile](#findnextfile) никогда не был вызван на этот объект.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetLastWriteTime`по крайней мере один раз, прежде чем звонить .

> [!NOTE]
> Не все файловые системы используют одну и ту же семантику для реализации временной отметки, возвращенной этой функцией. Эта функция может вернуть то же значение, возвращенное другими функциями штампа времени, если базовая файловая система или сервер не поддерживает сохранение атрибута времени. Ознакомьтесь с [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) структурой для получения информации о временных форматах. На некоторых операционных системах, возвращенное время находится в часовом поясе локальных к машине был файл находится. Для получения дополнительной информации смотрите API Win32 [FileTimeToLocalFileTime.](/windows/win32/api/fileapi/nf-fileapi-filetimetolocalfiletime)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindgetlength"></a><a name="getlength"></a>CFileFind::GetLength

Вызовите эту функцию участника, чтобы получить длину найденного файла в байтах.

```
ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина найденного файла, в байтах.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetLength`по крайней мере один раз, прежде чем звонить .

`GetLength`использует структуру Win32 [WIN32_FIND_DATA,](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) чтобы получить и вернуть значение размера файла, в байтах.

> [!NOTE]
> По состоянию на MFC 7.0, `GetLength` поддерживает 64-битный целый ряд типов. Ранее существующий код, построенный с этой новой версией библиотеки, может привести к предупреждениям о усечении.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]

## <a name="cfilefindgetroot"></a><a name="getroot"></a>CFileFind::GetRoot

Вызовите эту функцию участника, чтобы получить корень найденного файла.

```
virtual CString GetRoot() const;
```

### <a name="return-value"></a>Возвращаемое значение

Корень активного поиска.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `GetRoot`по крайней мере один раз, прежде чем звонить .

Эта функция пользователя возвращает разосужатель диска и имя пути, используемое для начала поиска. Например, вызов [FindFile](#findfile) `*.dat` `GetRoot` с результатами возврата пустой строки. Прохождение пути, `c:\windows\system\*.dll`например, `GetRoot` `c:\windows\system\`к возвращению `FindFile` результатов.

### <a name="example"></a>Пример

  Смотрите пример [CFileFind::GetFileName](#getfilename).

## <a name="cfilefindisarchived"></a><a name="isarchived"></a>CFileFind::Архив

Вызовите эту функцию участника, чтобы определить, архивирован ли найденный файл.

```
BOOL IsArchived() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Приложения отмечают архивный файл, который должен быть резервного копирования или удален, с FILE_ATTRIBUTE_ARCHIVE, атрибут файла, определенный в структуре [WIN32_FIND_DATA.](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)

Вы должны позвонить [FindNextFile](#findnextfile) `IsArchived`по крайней мере один раз, прежде чем звонить .

Для полного списка атрибутов файлов можно ознакомиться с функцией участников [MatchesMask.](#matchesmask)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindiscompressed"></a><a name="iscompressed"></a>CFileFind::IsCompressed

Вызовите эту функцию участника, чтобы определить, сжимается ли найденный файл.

```
BOOL IsCompressed() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Сжатый файл помечен FILE_ATTRIBUTE_COMPRESSED, атрибутом файла, указанным в структуре [WIN32_FIND_DATA.](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Для файла этот атрибут указывает на то, что все данные в файле сжаты. Для каталога этот атрибут указывает на то, что сжатие является значением по умолчанию для вновь созданных файлов и субдиректоров.

Вы должны позвонить [FindNextFile](#findnextfile) `IsCompressed`по крайней мере один раз, прежде чем звонить .

Для полного списка атрибутов файлов можно ознакомиться с функцией участников [MatchesMask.](#matchesmask)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindisdirectory"></a><a name="isdirectory"></a>CFileFind::IsDirectory

Вызовите эту функцию участника, чтобы определить, является ли найденный файл каталогом.

```
BOOL IsDirectory() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Файл, являющиеся каталогом, помечается FILE_ATTRIBUTE_DIRECTORY атрибутом файла, указанным в структуре [WIN32_FIND_DATA.](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw)

Вы должны позвонить [FindNextFile](#findnextfile) `IsDirectory`по крайней мере один раз, прежде чем звонить .

Для полного списка атрибутов файлов можно ознакомиться с функцией участников [MatchesMask.](#matchesmask)

### <a name="example"></a>Пример

Эта небольшая программа переквисает каждый каталог на C: диск и печатает название каталога.

[!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]

## <a name="cfilefindisdots"></a><a name="isdots"></a>CFileFind::IsDots

Вызовите эту функцию участника для тестирования для текущих маркеров каталога и родительских каталогов, пока итерации через файлы.

```
virtual BOOL IsDots() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если найденный файл имеет имя "." или "..," указывает на то, что найденный файл на самом деле является каталогом. В противном случае 0.

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `IsDots`по крайней мере один раз, прежде чем звонить .

### <a name="example"></a>Пример

  Смотрите пример [CFileFind::IsDirectory](#isdirectory).

## <a name="cfilefindishidden"></a><a name="ishidden"></a>CFileFind::IsHidden

Вызовите эту функцию участника, чтобы определить, является ли найденный файл скрытым.

```
BOOL IsHidden() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Скрытые файлы, которые помечены FILE_ATTRIBUTE_HIDDEN, атрибут файла, указанный в структуре [WIN32_FIND_DATA.](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Скрытый файл не включен в обычное перечисление каталога.

Вы должны позвонить [FindNextFile](#findnextfile) `IsHidden`по крайней мере один раз, прежде чем звонить .

Для полного списка атрибутов файлов можно ознакомиться с функцией участников [MatchesMask.](#matchesmask)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindisnormal"></a><a name="isnormal"></a>CFileFind::IsNormal

Вызовите эту функцию участника, чтобы определить, является ли найденный файл обычным файлом.

```
BOOL IsNormal() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Файлы, отмеченные FILE_ATTRIBUTE_NORMAL, атрибут файла, указанный в структуре [WIN32_FIND_DATA.](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Обычный файл не имеет другого набора атрибутов. Все остальные атрибуты файла переопределяют этот атрибут.

Вы должны позвонить [FindNextFile](#findnextfile) `IsNormal`по крайней мере один раз, прежде чем звонить .

Для полного списка атрибутов файлов можно ознакомиться с функцией участников [MatchesMask.](#matchesmask)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindisreadonly"></a><a name="isreadonly"></a>CFileFind::IsReadOnly

Вызовите эту функцию участника, чтобы определить, является ли найденный файл прочитан.

```
BOOL IsReadOnly() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Файл только для чтения помечен FILE_ATTRIBUTE_READONLY, атрибутом файла, указанным в структуре [WIN32_FIND_DATA.](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Приложения могут читать такой файл, но они не могут написать ему или удалить его.

Вы должны позвонить [FindNextFile](#findnextfile) `IsReadOnly`по крайней мере один раз, прежде чем звонить .

Для полного списка атрибутов файлов можно ознакомиться с функцией участников [MatchesMask.](#matchesmask)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindissystem"></a><a name="issystem"></a>CFileFind::IsSystem

Вызовите эту функцию участника, чтобы определить, является ли найденный файл системным файлом.

```
BOOL IsSystem() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Системный файл помечен FILE_ATTRIBUTE_SYSTEM, атрибутом файла, указанным в структуре [WIN32_FIND_DATA.](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Системный файл является частью операционной системы или используется исключительно операционной системой.

Вы должны позвонить [FindNextFile](#findnextfile) `IsSystem`по крайней мере один раз, прежде чем звонить .

Для полного списка атрибутов файлов можно ознакомиться с функцией участников [MatchesMask.](#matchesmask)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindistemporary"></a><a name="istemporary"></a>CFileFind:: Временно

Вызовите эту функцию участника, чтобы определить, является ли найденный файл временным файлом.

```
BOOL IsTemporary() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

Временный файл помечен FILE_ATTRIBUTE_TEMPORARY, атрибутом файла, определенным в структуре [WIN32_FIND_DATA.](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Временный файл используется для временного хранения. Заявки должны писать в файл только в случае крайней необходимости. Большая часть данных файла остается в памяти, не будучи смыты к средствам массовой информации, потому что файл скоро будет удален.

Вы должны позвонить [FindNextFile](#findnextfile) `IsTemporary`по крайней мере один раз, прежде чем звонить .

Для полного списка атрибутов файлов можно ознакомиться с функцией участников [MatchesMask.](#matchesmask)

### <a name="example"></a>Пример

  Смотрите пример [для CFileFind::GetLength](#getlength).

## <a name="cfilefindm_ptm"></a><a name="m_ptm"></a>CFileFind::m_pTM

Указатель на `CAtlTransactionManager` объект.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Примечания

## <a name="cfilefindmatchesmask"></a><a name="matchesmask"></a>CFileFind::MatchesMask

Вызовите эту функцию участника для проверки атрибутов файла в найденном файле.

```
virtual BOOL MatchesMask(DWORD dwMask) const;
```

### <a name="parameters"></a>Параметры

*dwMask*<br/>
Для найденного файла указывается один или несколько атрибутов файлов, идентифицированных в структуре [WIN32_FIND_DATA.](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) Для поиска нескольких атрибутов используйте оператора bitwise OR (&#124;). Любая комбинация следующих атрибутов является приемлемой:

- FILE_ATTRIBUTE_ARCHIVE Файл является архивным файлом. Приложения используют этот атрибут для обозначения файлов для резервного копирования или удаления.

- FILE_ATTRIBUTE_COMPRESSED файл или каталог сжимается. Для файла это означает, что все данные в файле сжаты. Для каталога это означает, что сжатие является значением по умолчанию для вновь созданных файлов и субдиректоров.

- FILE_ATTRIBUTE_DIRECTORY Файл является каталогом.

- FILE_ATTRIBUTE_NORMAL файл не имеет других наборов атрибутов. Этот атрибут действителен только при использовании в одиночку. Все остальные атрибуты файла переопределяют этот атрибут.

- FILE_ATTRIBUTE_HIDDEN Файл скрыт. Он не должен быть включен в обычный список каталогов.

- FILE_ATTRIBUTE_READONLY Файл читается только. Приложения могут читать файл, но не могут написать на него или удалить его.

- FILE_ATTRIBUTE_SYSTEM Файл является частью или используется исключительно операционной системой.

- FILE_ATTRIBUTE_TEMPORARY Файл используется для временного хранения. Заявки должны писать в файл только в случае крайней необходимости. Большая часть данных файла остается в памяти, не будучи смыты к средствам массовой информации, потому что файл скоро будет удален.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0. Чтобы получить расширенную информацию об ошибке, позвоните в функцию Win32 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Примечания

Вы должны позвонить [FindNextFile](#findnextfile) `MatchesMask`по крайней мере один раз, прежде чем звонить .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)<br/>
[Класс CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)<br/>
[Класс CInternetFile](../../mfc/reference/cinternetfile-class.md)<br/>
[Класс CGopherFile](../../mfc/reference/cgopherfile-class.md)<br/>
[Класс CHttpfile](../../mfc/reference/chttpfile-class.md)
