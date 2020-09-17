---
title: Класс Кфиле
ms.date: 06/12/2018
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
ms.openlocfilehash: 5be6a578fdd1d4e329c5b55d307d924a6c539e3d
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042086"
---
# <a name="cfile-class"></a>Класс Кфиле

Базовый класс для файловых классов Microsoft Foundation Class.

## <a name="syntax"></a>Синтаксис

```
class CFile : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кфиле:: Кфиле](#cfile)|Конструирует `CFile` объект на основе пути или файла.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Кфиле:: Abort](#abort)|Закрывает файл, игнорируя все предупреждения и ошибки.|
|[Кфиле:: Close](#close)|Закрывает файл и удаляет объект.|
|[Кфиле::D блировать](#duplicate)|Конструирует дубликат объекта на основе этого файла.|
|[Кфиле:: Flush](#flush)|Сбрасывает все данные, которые еще не были записаны.|
|[Кфиле:: имя_файла](#getfilename)|Извлекает имя файла выбранного файла.|
|[Кфиле:: FilePath](#getfilepath)|Возвращает полный путь к выбранному файлу.|
|[Кфиле:: Жетфилетитле](#getfiletitle)|Извлекает заголовок выбранного файла.|
|[Кфиле:: DATALENGTH](#getlength)|Получает длину файла.|
|[Кфиле:: Disposition](#getposition)|Извлекает текущий указатель на файл.|
|[Кфиле::/Status](#getstatus)|Получает состояние открытого файла или в статической версии, получает состояние указанного файла (статическая, виртуальная функция).|
|[Кфиле:: Локкранже](#lockrange)|Блокирует диапазон байтов в файле.|
|[Кфиле:: Open](#open)|Безопасно открывает файл с параметром тестирования ошибок.|
|[Кфиле:: Read](#read)|Считывает (без буферизации) данные из файла в текущей позиции файла.|
|[Кфиле:: Remove](#remove)|Удаляет указанный файл (статическую функцию).|
|[Кфиле:: Rename](#rename)|Переименовывает указанный файл (статическую функцию).|
|[Кфиле:: Seek](#seek)|Позиционирует текущий указатель на файл.|
|[Кфиле:: Сиктобегин](#seektobegin)|Позиционирует текущий указатель на файл в начале файла.|
|[Кфиле:: Сиктоенд](#seektoend)|Размещает текущий указатель файла в конце файла.|
|[Кфиле:: Сетфилепас](#setfilepath)|Задает полный путь к файлу выбранного файла.|
|[Кфиле:: SetLength](#setlength)|Изменяет длину файла.|
|[Кфиле:: SetStatus](#setstatus)|Задает состояние указанного файла (статическая, виртуальная функция).|
|[Кфиле:: Унлоккранже](#unlockrange)|Разблокирует диапазон байтов в файле.|
|[Кфиле:: Write](#write)|Записывает данные (без буферизации) в файле в текущее расположение файла.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[ОБРАБОТЧИК Кфиле::operator](#operator_handle)|Маркер `CFile` объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Кфиле:: Хфиленулл](#hfilenull)|Определяет, `CFile` имеет ли объект допустимый маркер.|
|[Кфиле:: m_hFile](#m_hfile)|Обычно содержит описатель файла операционной системы.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[Кфиле:: m_pTM](#m_ptm)|Указатель на объект `CAtlTransactionManager`.|

## <a name="remarks"></a>Комментарии

Он напрямую предоставляет небуферизованные службы ввода-вывода на двоичном диске и косвенно поддерживает текстовые файлы и файлы памяти с помощью производных классов. `CFile` работает в сочетании с `CArchive` классом для поддержки сериализации объектов Microsoft Foundation Class.

Иерархическая связь между этим классом и его производными классами позволяет программе обрабатывать все файловые объекты через интерфейс полиморфизма `CFile` . Файл памяти, например, ведет себя как файл на диске.

Используйте `CFile` и его производные классы для дискового ввода-вывода общего назначения. Используйте `ofstream` или другие `iostream` классы Майкрософт для форматированного текста, отправляемого в файл на диске.

Как правило, дисковый файл открывается автоматически при `CFile` создании и закрытии при уничтожении. Статические функции-члены позволяют опрашивать состояние файла, не открывая файл.

Дополнительные сведения об использовании см `CFile` . в статьях [файлы MFC](../../mfc/files-in-mfc.md) и [Обработка файлов](../../c-runtime-library/file-handling.md) в *справочнике по библиотеке времени выполнения*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>Требования

**Заголовок:** AFX.h

## <a name="cfileabort"></a><a name="abort"></a> Кфиле:: Abort

Закрывает файл, связанный с этим объектом, и делает его недоступным для чтения или записи.

```
virtual void Abort();
```

### <a name="remarks"></a>Комментарии

Если вы не закрыли файл перед уничтожением объекта, деструктор закроет его.

При обработке исключений `CFile::Abort` отличается от `CFile::Close` двух важных способов. Во-первых, `Abort` функция не будет вызывать исключение при сбоях, так как ошибки игнорируются `Abort` . Во вторых, `Abort` не будет **утверждать** , не был ли файл открыт или был закрыт ранее.

Если вы использовали **`new`** для выделения `CFile` объекта в куче, необходимо удалить его после закрытия файла. `Abort` Задает `m_hFile` для значение `CFile::hFileNull` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

## <a name="cfilecfile"></a><a name="cfile"></a> Кфиле:: Кфиле

Создает и инициализирует объект `CFile`.

```
CFile();
CFile(CAtlTransactionManager* pTM);
CFile(HANDLE hFile);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags,
CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Параметры

*hFile*<br/>
Дескриптор файла, который будет присоединен к объекту `CFile`.

*лпсзфиленаме*<br/>
Относительный или полный путь к файлу, который будет присоединен к объекту `CFile`.

*нопенфлагс*<br/>
Побитовое сочетание (ИЛИ) параметров доступа к указанному файлу. Возможные параметры см. в разделе "Заметки".

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Комментарии

В следующих пяти таблицах перечислены возможные параметры для параметра *нопенфлагс* .

Выберите только один из следующих параметров режима доступа к файлу. Режим доступа к файлу по умолчанию — `CFile::modeRead`, т. е. только для чтения.

|Значение|Описание|
|-----------|-----------------|
|`CFile::modeRead`|Запрашивает доступ только для чтения.|
|`CFile::modeWrite`|Запрашивает доступ только для записи.|
|`CFile::modeReadWrite`|Запрашивает доступ для чтения и записи.|

Выберите один из следующих параметров режима символов.

|Значение|Описание|
|-----------|-----------------|
|`CFile::typeBinary`|Задает двоичный режим (используется только в производных классах).|
|`CFile::typeText`|Задает текстовый режим с особой обработкой для пар символов возврата каретки и перевода строки (используется только в производных классах).|
|`CFile::typeUnicode`|Задает режим Юникода (используется только в производных классах). Текст записывается в файл в формате Юникод, если приложение использует конфигурацию Юникода. Данные BOM в файл не записываются.|

Выберите только один из следующих параметров режима общего доступа к файлу. Режим общего доступа к файлу по умолчанию — `CFile::shareExclusive`, т. е. эксклюзивный доступ.

|Значение|Описание|
|-----------|-----------------|
|`CFile::shareDenyNone`|Нет ограничений по общему доступу.|
|`CFile::shareDenyRead`|Запрет доступа для чтения для всех других пользователей.|
|`CFile::shareDenyWrite`|Запрет доступа для записи для всех других пользователей.|
|`CFile::shareExclusive`|Запрет доступа для чтения и записи для всех других пользователей.|

Выберите первый или и первый, и второй из следующих параметров режима создания файла. Режим создания по умолчанию — `CFile::modeNoTruncate`, т. е. открывается существующий файл.

|Значение|Описание|
|-----------|-----------------|
|`CFile::modeCreate`|Создает новый файл, если файл не существует. Если файл уже существует, он перезаписывается и изначально устанавливается в нулевую длину.|
|`CFile::modeNoTruncate`|Создает новый файл, если файл не существует; в противном случае, если файл уже существует, он присоединяется к `CFile` объекту.|

Выберите соответствующие параметры кэширования файлов, описанные далее. По умолчанию система использует схему кэширования общего назначения, которая недоступна в качестве параметра.

|Значение|Описание|
|-----------|-----------------|
|`CFile::osNoBuffer`|Система не использует промежуточный кэш для файла. Этот параметр отменяет использование следующих двух параметров.|
|`CFile::osRandomAccess`|Файловый кэш оптимизирован для случайного доступа. Не используйте этот параметр и параметр последовательного сканирования.|
|`CFile::osSequentialScan`|Файловый кэш оптимизирован для последовательного доступа. Не используйте этот параметр и параметр произвольного доступа.|
|`CFile::osWriteThrough`|Операции записи выполняются без задержки.|

Выберите следующий параметр безопасности, чтобы дескриптор файла не наследовался. По умолчанию любые новые дочерние процессы могут использовать дескриптор файла.

|Значение|Описание|
|-----------|-----------------|
|`CFile::modeNoInherit`|Запрещает дочерним процессам использовать дескриптор файла.|

Конструктор по умолчанию инициализирует элементы, но не прикрепляет файл к `CFile` объекту. После использования этого конструктора используйте метод [кфиле:: Open](#open) , чтобы открыть файл и присоединить его к `CFile` объекту.

Конструктор с одним параметром инициализирует члены и присоединяет существующий файл к объекту `CFile`.

Конструктор с двумя параметрами инициализирует члены и пытается открыть указанный файл. Если конструктор успешно открывает заданный файл, он присоединяется к объекту `CFile`. В противном случае конструктор возвращает указатель на объект `CInvalidArgException`. Дополнительные сведения об обработке исключений см. в разделе [исключения](../../mfc/exception-handling-in-mfc.md).

Если `CFile` объект успешно открывает указанный файл, он закрывает этот файл автоматически при `CFile` уничтожении объекта. в противном случае необходимо явным образом закрыть файл после того, как он больше не будет присоединен к `CFile` объекту.

### <a name="example"></a>Пример

В следующем коде показано использование `CFile`.

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

## <a name="cfileclose"></a><a name="close"></a> Кфиле:: Close

Закрывает файл, связанный с этим объектом, и делает его недоступным для чтения или записи.

```
virtual void Close();
```

### <a name="remarks"></a>Комментарии

Если вы не закрыли файл перед уничтожением объекта, деструктор закроет его.

Если вы использовали **`new`** для выделения `CFile` объекта в куче, необходимо удалить его после закрытия файла. `Close` Задает `m_hFile` для значение `CFile::hFileNull` .

### <a name="example"></a>Пример

См. пример для [кфиле:: кфиле](#cfile).

## <a name="cfileduplicate"></a><a name="duplicate"></a> Кфиле::D блировать

Конструирует дубликат `CFile` объекта для заданного файла.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на дубликат `CFile` объекта.

### <a name="remarks"></a>Комментарии

Эта функция эквивалентна функции времени выполнения C `_dup` .

## <a name="cfileflush"></a><a name="flush"></a> Кфиле:: Flush

Принудительная запись всех данных, остающихся в буфере файла, в файл.

```
virtual void Flush();
```

### <a name="remarks"></a>Комментарии

Использование параметра `Flush` не гарантирует очистку `CArchive` буферов. Если вы используете Архив, сначала вызовите [CArchive:: Flush](../../mfc/reference/carchive-class.md#flush) .

### <a name="example"></a>Пример

См. пример для [кфиле:: сетфилепас](#setfilepath).

## <a name="cfilegetfilename"></a><a name="getfilename"></a> Кфиле:: имя_файла

Вызовите эту функцию-член, чтобы получить имя указанного файла.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя файла.

### <a name="remarks"></a>Комментарии

Например, при вызове метода `GetFileName` для создания сообщения пользователю о файле `c:\windows\write\myfile.wri` возвращается имя файла, `myfile.wri` .

Чтобы получить полный путь к файлу, включая имя, [вызовите метод](#getfilepath)Multipath. Чтобы получить заголовок файла ( `myfile` ), вызовите [жетфилетитле](#getfiletitle).

### <a name="example"></a>Пример

Этот фрагмент кода открывает файл SYSTEM.INI в каталоге WINDOWS. Если он найден, в примере выводятся имя и путь и заголовок, как показано в разделе выходные данные:

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

## <a name="cfilegetfilepath"></a><a name="getfilepath"></a> Кфиле:: FilePath

Вызовите эту функцию-член, чтобы получить полный путь к указанному файлу.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Возвращаемое значение

Полный путь к указанному файлу.

### <a name="remarks"></a>Комментарии

Например, при вызове метода `GetFilePath` для создания сообщения пользователю о файле `c:\windows\write\myfile.wri` возвращается путь к файлу `c:\windows\write\myfile.wri` .

Чтобы вернуть только имя файла ( `myfile.wri` ), вызовите метод [filename](#getfilename). Чтобы получить заголовок файла ( `myfile` ), вызовите [жетфилетитле](#getfiletitle).

### <a name="example"></a>Пример

См. пример для [файла filename](#getfilename).

## <a name="cfilegetfiletitle"></a><a name="getfiletitle"></a> Кфиле:: Жетфилетитле

Вызовите эту функцию-член, чтобы получить заголовок файла (отображаемое имя) для файла.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Заголовок базового файла.

### <a name="remarks"></a>Комментарии

Этот метод вызывает [жетфилетитле](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) для получения заголовка файла. В случае успеха метод возвращает строку, которую система будет использовать для вывода имени файла пользователю. В противном случае метод вызывает [пасфиндфиленаме](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) для получения имени файла (включая расширение файла) базового файла. Это означает, что расширение файла не всегда включается в возвращаемую строку заголовка файла. Дополнительные сведения см. в разделе [жетфилетитле](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) и [пасфиндфиленаме](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) в Windows SDK.

Чтобы получить полный путь к файлу, включая имя, [вызовите метод](#getfilepath)Multipath. Чтобы вернуть только имя файла, вызовите метод [filename](#getfilename).

### <a name="example"></a>Пример

См. пример для [файла filename](#getfilename).

## <a name="cfilegetlength"></a><a name="getlength"></a> Кфиле:: DATALENGTH

Получает текущую логическую длину файла в байтах.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Возвращаемое значение

Длина файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

## <a name="cfilegetposition"></a><a name="getposition"></a> Кфиле:: Disposition

Получает текущее значение указателя файла, которое можно использовать в последующих вызовах метода `Seek` .

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

## <a name="cfilegetstatus"></a><a name="getstatus"></a> Кфиле::/Status

Этот метод получает сведения о состоянии, связанные с данным `CFile` экземпляром объекта или указанным путем к файлу.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*рстатус*<br/>
Ссылка на предоставляемую пользователем `CFileStatus` структуру, которая получит сведения о состоянии. `CFileStatus`Структура содержит следующие поля:

- `CTime m_ctime` Дата и время создания файла.

- `CTime m_mtime` Дата и время последнего изменения файла.

- `CTime m_atime` Дата и время последнего доступа к файлу для чтения.

- `ULONGLONG m_size` Логический размер файла в байтах, сообщаемый командой DIR.

- `BYTE m_attribute` Байт атрибута файла.

- `char m_szFullName[_MAX_PATH]` Абсолютное имя файла в наборе символов Windows.

*лпсзфиленаме*<br/>
Строка в наборе символов Windows, которая является путем к требуемому файлу. Путь может быть относительным или абсолютным, или он может содержать имя сетевого пути.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если сведения о состоянии для указанного файла успешно получены; в противном случае — значение FALSE.

### <a name="remarks"></a>Комментарии

Нестатическая версия `GetStatus` извлекает сведения о состоянии открытого файла, связанного с данным `CFile` объектом.  Статическая версия `GetStatus` получает состояние файла из заданного пути к файлу без открытия файла. Эта версия полезна для тестирования прав на существование и доступ к файлу.

`m_attribute`Элемент `CFileStatus` структуры ссылается на набор атрибутов файла. `CFile`Класс предоставляет тип перечисления **атрибута** , чтобы атрибуты файла можно было указать символьно:

```
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]

## <a name="cfilehfilenull"></a><a name="hfilenull"></a> Кфиле:: Хфиленулл

Определяет наличие допустимого обработчика файлов для `CFile` объекта.

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>Комментарии

Эта константа используется, чтобы определить, `CFile` имеет ли объект допустимый файловый обработчик.

Эта операция показана в следующем примере:

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

## <a name="cfilelockrange"></a><a name="lockrange"></a> Кфиле:: Локкранже

Блокирует диапазон байтов в открытом файле и создает исключение, если файл уже заблокирован.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Параметры

*двпос*<br/>
Смещение в байтах для начала диапазона байтов для блокировки.

*двкаунт*<br/>
Число байт в диапазоне для блокировки.

### <a name="remarks"></a>Комментарии

Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать несколько регионов файла, но перекрывающиеся области не допускаются.

При разблокировании области с помощью `UnlockRange` функции члена диапазон байтов должен точно соответствовать региону, который был ранее заблокирован. `LockRange`Функция не выполняет слияние смежных областей. Если два заблокированных региона являются смежными, каждый регион необходимо разблокировать отдельно.

> [!NOTE]
> Эта функция недоступна для `CMemFile` класса, производного от.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilem_hfile"></a><a name="m_hfile"></a> Кфиле:: m_hFile

Содержит описатель файла операционной системы для открытого файла.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>Комментарии

`m_hFile` — Это открытая переменная типа UINT. Он содержит `CFile::hFileNull` независимый от операционной системы индикатор пустого файла, если маркер не был назначен.

Использование `m_hFile` не рекомендуется, так как значение члена зависит от производного класса. `m_hFile` становится открытым членом для удобства в поддержке нонполиморфик использования класса.

## <a name="cfilem_ptm"></a><a name="m_ptm"></a> Кфиле:: m_pTM

Указатель на `CAtlTransactionManager` объект.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Комментарии

## <a name="cfileopen"></a><a name="open"></a> Кфиле:: Open

Перегружен. `Open` предназначен для использования с конструктором по умолчанию `CFile` .

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзфиленаме*<br/>
Строка, содержащая путь к нужному файлу. Путь может быть относительным, абсолютным или сетевым именем (UNC).

*нопенфлагс*<br/>
Значение типа UINT, определяющее общий доступ к файлу и режим доступа к нему. Указывает действие, выполняемое при открытии файла. Параметры можно комбинировать с помощью оператора побитового или ( **&#124;** ). Требуется одно разрешение на доступ и один параметр общего ресурса; `modeCreate` режимы и `modeNoInherit` являются необязательными. Список параметров режима см. в конструкторе [кфиле](#cfile) .

*pError*<br/>
Указатель на существующий объект исключения файла, который получит состояние невыполненной операции.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если открытие прошло успешно; в противном случае — 0. Параметр *perror* имеет смысл, только если возвращается значение 0.

### <a name="remarks"></a>Комментарии

Две `Open` функции — "надежные" методы для открытия файла, в которых сбой является нормальным ожидаемым условием.

Хотя `CFile` конструктор создает исключение в условии ошибки, `Open` возвращает значение false для условий ошибки. `Open` Однако по-прежнему может инициализировать объект [кфиликсцептион](../../mfc/reference/cfileexception-class.md) для описания ошибки. Если не указать параметр *perror* или передать значение NULL для *perror*, `Open` возвращает значение false и не создает исключение `CFileException` . Если передается указатель на существующий объект `CFileException` и `Open` возникает ошибка, функция заполняет ее данными, описывающими эту ошибку. `Open` не создает исключение в любом случае.

В следующей таблице описаны возможные результаты `Open` .

| `pError` | Произошла ошибка | Возвращаемое значение | Кфиликсцептион содержимое |
|--|--|--|--|
| NULL | Нет | true | Н/Д |
| PTR для `CFileException` | Нет | true | без изменений |
| NULL | Да | FALSE | Н/Д |
| PTR для `CFileException` | Да | FALSE | инициализировано для описания ошибки |

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

## <a name="cfileoperator-handle"></a><a name="operator_handle"></a> ОБРАБОТЧИК Кфиле::operator

Этот оператор используется для передачи в объект обработчика `CFile` таких функций, как [Реадфиликс](/windows/win32/api/fileapi/nf-fileapi-readfileex) и [функции getFileTime](/windows/win32/api/fileapi/nf-fileapi-getfiletime) , для которых требуется `HANDLE` .

```
operator HANDLE() const;
```

## <a name="cfileread"></a><a name="read"></a> Кфиле:: Read

Считывает данные в буфер из файла, связанного с `CFile` объектом.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*лпбуф*<br/>
Указатель на предоставляемый пользователем буфер, который получает данные, считанные из файла.

*нкаунт*<br/>
Максимальное число байтов, которое должно быть считано из файла. Для файлов текстового режима пары "возврат каретки-перевод строки" считаются одиночными символами.

### <a name="return-value"></a>Возвращаемое значение

Количество байтов, переданных в буфер. Для всех `CFile` классов возвращаемое значение может быть меньше *нкаунт* , если достигнут конец файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

Другой пример см. в разделе [кфиле:: Open](#open).

## <a name="cfileremove"></a><a name="remove"></a> Кфиле:: Remove

Эта статическая функция удаляет файл, указанный в пути.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзфиленаме*<br/>
Строка, которая является путем к требуемому файлу. Путь может быть относительным или абсолютным и может содержать сетевое имя.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Комментарии

`Remove` не удаляет каталог.

`Remove`Функция-член создает исключение, если подключенный файл открыт или невозможно удалить файл. Эта функция эквивалентна команде DEL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

## <a name="cfilerename"></a><a name="rename"></a> Кфиле:: Rename

Эта статическая функция переименовывает указанный файл.

```
static void PASCAL Rename(
    LPCTSTR lpszOldName,
    LPCTSTR lpszNewName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзолднаме*<br/>
Старый путь.

*лпсзневнаме*<br/>
Новый путь.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Комментарии

Каталоги нельзя переименовывать. Эта функция эквивалентна команде REN.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

## <a name="cfileseek"></a><a name="seek"></a> Кфиле:: Seek

Перемещает указатель файла в открытый файл.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>Параметры

*лофф*<br/>
Число байтов для перемещения указателя файла. Положительные значения перемещают указатель файла в конец файла; отрицательные значения перемещают указатель файла в начало файла.

*Nиз*<br/>
Положение для поиска. Возможные значения см. в разделе "Примечания".

### <a name="return-value"></a>Возвращаемое значение

Расположение указателя файла, если метод был успешным; в противном случае возвращаемое значение не определено и создается указатель на `CFileException` исключение.

### <a name="remarks"></a>Комментарии

В следующей таблице перечислены возможные значения для параметра *nиз* .

|Значение|Описание|
|-----------|-----------------|
|`CFile::begin`|Поиск с начала файла.|
|`CFile::current`|Поиск из текущего расположения указателя файла.|
|`CFile::end`|Поиск с конца файла.|

При открытии файла указатель файла располагается в положении 0, начало файла.

Можно задать указатель файла на позиции, расположенной за концом файла. В этом случае размер файла не будет увеличиваться до тех пор, пока не будет выполнена запись в файл.

Обработчик исключений для этого метода должен удалить объект исключения после обработки исключения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

## <a name="cfileseektobegin"></a><a name="seektobegin"></a> Кфиле:: Сиктобегин

Задает значение указателя файла в начале файла.

```cpp
void SeekToBegin();
```

### <a name="remarks"></a>Комментарии

`SeekToBegin()` эквивалентно правилу `Seek( 0L, CFile::begin )`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfileseektoend"></a><a name="seektoend"></a> Кфиле:: Сиктоенд

Задает значение указателя файла для логического конца файла.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>Возвращаемое значение

Длина файла в байтах.

### <a name="remarks"></a>Комментарии

`SeekToEnd()` эквивалентно правилу `CFile::Seek( 0L, CFile::end )`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfilesetfilepath"></a><a name="setfilepath"></a> Кфиле:: Сетфилепас

Вызовите эту функцию, чтобы указать путь к файлу. Например, если путь к файлу недоступен при создании объекта [кфиле](../../mfc/reference/cfile-class.md) , вызовите метод, `SetFilePath` чтобы предоставить его.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Параметры

*лпсзневнаме*<br/>
Указатель на строку, указывающую новый путь.

### <a name="remarks"></a>Комментарии

> [!NOTE]
> `SetFilePath` не открывает файл или не создает файл; Он просто связывает `CFile` объект с именем пути, которое затем можно использовать.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

## <a name="cfilesetlength"></a><a name="setlength"></a> Кфиле:: SetLength

Вызовите эту функцию, чтобы изменить длину файла.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>Параметры

*двневлен*<br/>
Требуемая длина файла в байтах. Это значение может быть больше или меньше текущей длины файла. Файл будет расширен или обрезан соответствующим образом.

### <a name="remarks"></a>Комментарии

> [!NOTE]
> С помощью `CMemFile` Эта функция может вызвать `CMemoryException` объект.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

## <a name="cfilesetstatus"></a><a name="setstatus"></a> Кфиле:: SetStatus

Задает состояние файла, связанного с этим расположением файла.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзфиленаме*<br/>
Строка, которая является путем к требуемому файлу. Путь может быть относительным или абсолютным и может содержать сетевое имя.

*status*<br/>
Буфер, содержащий новые сведения о состоянии. Вызовите `GetStatus` функцию члена для предзаполнения `CFileStatus` структуры текущими значениями, а затем внесите необходимые изменения. Если значение равно 0, соответствующий элемент состояния не обновляется. Описание структуры [GetStatus](#getstatus) см. в функции-члене-состоянии `CFileStatus` .

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Комментарии

Чтобы задать время, измените `m_mtime` поле *состояние*.

При вызове `SetStatus` в в случае попытки изменить только атрибуты файла, а `m_mtime` член структуры состояния файла — ненулевое значение, могут также затронуты атрибуты (изменение метки времени может иметь побочные эффекты на атрибуты). Если необходимо изменить только атрибуты файла, сначала установите `m_mtime` для элемента структуры состояния файла значение 0, а затем выполните вызов `SetStatus` .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

## <a name="cfileunlockrange"></a><a name="unlockrange"></a> Кфиле:: Унлоккранже

Разблокирует диапазон байтов в открытом файле.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Параметры

*двпос*<br/>
Байтовое смещение начала диапазона байтов для разблокировки.

*двкаунт*<br/>
Число байтов в диапазоне для разблокирования.

### <a name="remarks"></a>Комментарии

Дополнительные сведения см. в описании функции члена [локкранже](#lockrange) .

> [!NOTE]
> Эта функция недоступна для `CMemFile` класса, производного от.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilewrite"></a><a name="write"></a> Кфиле:: Write

Записывает данные из буфера в файл, связанный с `CFile` объектом.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Параметры

*лпбуф*<br/>
Указатель на предоставляемый пользователем буфер, содержащий данные, записываемые в файл.

*нкаунт*<br/>
Число байтов, которое необходимо передать из буфера. Для файлов текстового режима пары "возврат каретки-перевод строки" считаются одиночными символами.

### <a name="remarks"></a>Комментарии

`Write` создает исключение в ответ на несколько условий, включая полное условие на диске.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

См. также примеры для [кфиле:: кфиле](#cfile) и [Кфиле:: Open](#open).

## <a name="see-also"></a>См. также раздел

[Пример DRAWCLI для MFC](../../overview/visual-cpp-samples.md)<br/>
[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Кстдиофиле](../../mfc/reference/cstdiofile-class.md)<br/>
[Класс Кмемфиле](../../mfc/reference/cmemfile-class.md)
