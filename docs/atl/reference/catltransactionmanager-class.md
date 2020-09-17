---
title: Класс Катлтрансактионманажер
ms.date: 11/04/2016
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
ms.openlocfilehash: 74afc1a82c12d6138198f5696d300825e06aba1e
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562220"
---
# <a name="catltransactionmanager-class"></a>Класс Катлтрансактионманажер

Класс Катлтрансактионманажер предоставляет оболочку для функций диспетчера транзакций ядра (KTM).

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class CAtlTransactionManager;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[~ Катлтрансактионманажер](#dtor)|Деструктор Катлтрансактионманажер.|
|[катлтрансактионманажер](#catltransactionmanager)|Конструктор Катлтрансактионманажер.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Закрыть](#close)|Закрывает один маркер транзакции.|
|[Фиксация](#commit)|Запрашивает фиксацию транзакции.|
|[Создание](#create)|Создает обработчик транзакции.|
|[CreateFile](#createfile)|Создает или открывает файл, файловый поток или каталог в качестве транзакционной операции.|
|[DeleteFile](#deletefile)|Удаляет существующий файл как транзакционную операцию.|
|[FindFirstFile](#findfirstfile)|Выполняет поиск файла или подкаталога в каталоге в качестве транзакционной операции.|
|[GetFileAttributes](#getfileattributes)|Получает атрибуты файловой системы для указанного файла или каталога в качестве транзакционной операции.|
|[Сбой getfileattributesex](#getfileattributesex)|Получает атрибуты файловой системы для указанного файла или каталога в качестве транзакционной операции.|
|[GetHandle](#gethandle)|Возвращает маркер транзакции.|
|[Возврат](#isfallback)|Определяет, включены ли резервные вызовы.|
|[MoveFile](#movefile)|Перемещает существующий файл или каталог, включая его дочерние элементы, в качестве транзакционной операции.|
|[регкреатекэйекс](#regcreatekeyex)|Создает указанный раздел реестра и связывает его с транзакцией. Если ключ уже существует, функция открывает его.|
|[регделетекэй](#regdeletekey)|Удаляет подраздел и его значения из указанного представления реестра для конкретной платформы в качестве транзакционной операции.|
|[RegOpenKeyEx](#regopenkeyex)|Открывает указанный раздел реестра и связывает его с транзакцией.|
|[Отката](#rollback)|Запрашивает откат транзакции.|
|[сетфилеаттрибутес](#setfileattributes)|Задает атрибуты для файла или каталога в качестве транзакционной операции.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[m_bFallback](#m_bfallback)|Значение TRUE, если резервная поддержка поддерживается; В противном случае — значение FALSE.|
|[m_hTransaction](#m_htransaction)|Маркер транзакции.|

## <a name="remarks"></a>Примечания

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[Библиотека ATL:: Катлтрансактионманажер](../../atl/reference/catltransactionmanager-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** атлтрансактионманажер.h

## <a name="catltransactionmanager"></a><a name="dtor"></a>  ~ Катлтрансактионманажер

Деструктор Катлтрансактионманажер.

```cpp
virtual ~CAtlTransactionManager();
```

### <a name="remarks"></a>Примечания

При нормальной обработке транзакция автоматически фиксируется и закрывается. Если деструктор вызывается во время очистки исключения, происходит откат и закрытие транзакции.

## <a name="catltransactionmanager"></a><a name="catltransactionmanager"></a> катлтрансактионманажер

Конструктор Катлтрансактионманажер.

```cpp
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```

### <a name="parameters"></a>Параметры

*бфаллбакк*<br/>
Значение TRUE указывает на поддержку отката. Если транзакционная функция завершается с ошибкой, класс автоматически вызывает функцию, не поддерживающую транзакции. Значение FALSE указывает на отсутствие "резервных" вызовов.

*баутокреатетрансактион*<br/>
Значение TRUE указывает, что обработчик транзакций создается в конструкторе автоматически. Значение FALSE указывает, что это не так.

### <a name="remarks"></a>Примечания

## <a name="close"></a><a name="close"></a> Выхода

Закрывает маркер транзакции.

```cpp
inline BOOL Close();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `CloseHandle` функцию. Метод автоматически вызывается в деструкторе.

## <a name="commit"></a><a name="commit"></a> Сохраните

Запрашивает фиксацию транзакции.

```cpp
inline BOOL Commit();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `CommitTransaction` функцию. Метод автоматически вызывается в деструкторе.

## <a name="create"></a><a name="create"></a> Создание

Создает обработчик транзакции.

```cpp
inline BOOL Create();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `CreateTransaction` функцию. Проверьте его на наличие

## <a name="createfile"></a><a name="createfile"></a> CreateFile

Создает или открывает файл, файловый поток или каталог в качестве транзакционной операции.

```cpp
inline HANDLE CreateFile(
    LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```

### <a name="parameters"></a>Параметры

*лпфиленаме*<br/>
Имя объекта, который необходимо создать или открыть.

*двдесиредакцесс*<br/>
Доступ к объекту, который можно суммировать как чтение, запись, оба или ни один (ноль). Наиболее часто используемые значения — GENERIC_READ, GENERIC_WRITE или и то, и другое: GENERIC_READ &#124; GENERIC_WRITE.

*двшаремоде*<br/>
Режим общего доступа объекта, который может быть доступен для чтения, записи, обоих, удаления, всех или пустых: 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.

*лпсекуритяттрибутес*<br/>
Указатель на структуру SECURITY_ATTRIBUTES, которая содержит необязательный дескриптор безопасности, а также определяет, может ли возвращаемый дескриптор быть унаследован дочерними процессами. Параметр может иметь значение NULL.

*двкреатиондиспоситион*<br/>
Действие, выполняемое с файлами, которые существуют и не существуют. Этот параметр должен иметь одно из следующих значений, которые не могут быть объединены: CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING или TRUNCATE_EXISTING.

*двфлагсандаттрибутес*<br/>
Атрибуты и флаги файла. Этот параметр может включать любое сочетание доступных атрибутов файлов (FILE_ATTRIBUTE_ *). Все остальные атрибуты файла переопределяют FILE_ATTRIBUTE_NORMAL. Этот параметр также может содержать сочетания флагов (FILE_FLAG_ \* ) для управления поведением буферизации, режимами доступа и другими флагами специального назначения. Они объединяются с любыми FILE_ATTRIBUTE_ными \* значениями.

*хтемплатефиле*<br/>
Допустимый маркер файла шаблона с правом доступа GENERIC_READ. Файл шаблона предоставляет атрибуты файлов и дополнительные атрибуты для создаваемого файла. Этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер, который можно использовать для доступа к объекту.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `CreateFileTransacted` функцию.

## <a name="deletefile"></a><a name="deletefile"></a> DeleteFile

Удаляет существующий файл как транзакционную операцию.

```cpp
inline BOOL DeleteFile(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Параметры

*лпфиленаме*<br/>
Имя файла, предназначенного для удаления.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `DeleteFileTransacted` функцию.

## <a name="findfirstfile"></a><a name="findfirstfile"></a> FindFirstFile

Выполняет поиск файла или подкаталога в каталоге в качестве транзакционной операции.

```cpp
inline HANDLE FindFirstFile(
    LPCTSTR lpFileName,
    WIN32_FIND_DATA* pNextInfo);
```

### <a name="parameters"></a>Параметры

*лпфиленаме*<br/>
Каталог или путь, а также имя искомого файла. Этот параметр может содержать подстановочные знаки, например звездочку (*) или вопросительный знак ().

*пнекстинфо*<br/>
Указатель на структуру WIN32_FIND_DATA, которая получает сведения о найденном файле или подкаталоге.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение является маркером поиска, используемым при последующем вызове метода `FindNextFile` или `FindClose` . Если функция завершается ошибкой или не находит файлы из строки поиска в параметре *лпфиленаме* , возвращается значение INVALID_HANDLE_VALUE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `FindFirstFileTransacted` функцию.

## <a name="getfileattributes"></a><a name="getfileattributes"></a> GetFileAttributes

Получает атрибуты файловой системы для указанного файла или каталога в качестве транзакционной операции.

```cpp
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```

### <a name="parameters"></a>Параметры

*лпфиленаме*<br/>
Имя файла или каталога.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `GetFileAttributesTransacted` функцию.

## <a name="getfileattributesex"></a><a name="getfileattributesex"></a> Сбой getfileattributesex

Получает атрибуты файловой системы для указанного файла или каталога в качестве транзакционной операции.

```cpp
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```

### <a name="parameters"></a>Параметры

*лпфиленаме*<br/>
Имя файла или каталога.

*финфолевелид*<br/>
Уровень извлекаемых сведений об атрибутах.

*лпфилеинформатион*<br/>
Указатель на буфер, который получает сведения об атрибуте. Тип сведений об атрибутах, хранящихся в этом буфере, определяется значением *финфолевелид*. Если параметр *финфолевелид* имеет значение жетфиликсинфостандард, то этот параметр указывает на структуру WIN32_FILE_ATTRIBUTE_DATA.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `GetFileAttributesTransacted` функцию.

## <a name="gethandle"></a><a name="gethandle"></a> GetHandle

Возвращает маркер транзакции.

```cpp
HANDLE GetHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер транзакции для класса. Возвращает значение NULL, если `CAtlTransactionManager` не присоединен к маркеру.

### <a name="remarks"></a>Примечания

## <a name="isfallback"></a><a name="isfallback"></a> Возврат

Определяет, включены ли резервные вызовы.

```cpp
BOOL IsFallback() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если класс поддерживает резервные вызовы. В противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

## <a name="m_bfallback"></a><a name="m_bfallback"></a> m_bFallback

Значение TRUE, если резервная поддержка поддерживается; В противном случае — значение FALSE.

```cpp
BOOL m_bFallback;
```

### <a name="remarks"></a>Примечания

## <a name="m_htransaction"></a><a name="m_htransaction"></a> m_hTransaction

Маркер транзакции.

```cpp
HANDLE m_hTransaction;
```

### <a name="remarks"></a>Примечания

## <a name="movefile"></a><a name="movefile"></a> MoveFile

Перемещает существующий файл или каталог, включая его дочерние элементы, в качестве транзакционной операции.

```cpp
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```

### <a name="parameters"></a>Параметры

*лполдфиленаме*<br/>
Текущее имя существующего файла или каталога на локальном компьютере.

*лпневфиленаме*<br/>
Новое имя для файла или каталога. Это имя уже не должно существовать. Новый файл может находиться в другой файловой системе или на диске. Новый каталог должен находиться на том же диске.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `MoveFileTransacted` функцию.

## <a name="regcreatekeyex"></a><a name="regcreatekeyex"></a> регкреатекэйекс

Создает указанный раздел реестра и связывает его с транзакцией. Если ключ уже существует, функция открывает его.

```cpp
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Маркер открытого раздела реестра.

*лпсубкэй*<br/>
Имя подраздела, который открывается или создается этой функцией.

*двресервед*<br/>
Этот параметр зарезервирован и должен быть равен нулю.

*лпкласс*<br/>
Определяемый пользователем класс этого ключа. Этот параметр можно игнорировать. Этот параметр может иметь значение NULL.

*двоптионс*<br/>
Этот параметр может принимать одно из следующих значений: REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE или REG_OPTION_VOLATILE.

*самдесиред*<br/>
Маска, указывающая права доступа для ключа.

*лпсекуритяттрибутес*<br/>
Указатель на структуру SECURITY_ATTRIBUTES определяет, может ли возвращаемый дескриптор быть унаследован дочерними процессами. Если *лпсекуритяттрибутес* имеет значение null, маркер не может быть унаследован.

*фкресулт*<br/>
Указатель на переменную, которая получает маркер для открытого или созданного ключа. Если ключ не является одним из предопределенных разделов реестра, вызовите `RegCloseKey` функцию после завершения использования маркера.

*лпдвдиспоситион*<br/>
Указатель на переменную, которая получает одно из следующих значений метода обработки: REG_CREATED_NEW_KEY или REG_OPENED_EXISTING_KEY.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение будет ERROR_SUCCESS. Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в файле Winerror.h.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `RegCreateKeyTransacted` функцию.

## <a name="regdeletekey"></a><a name="regdeletekey"></a> регделетекэй

Удаляет подраздел и его значения из указанного представления реестра для конкретной платформы в качестве транзакционной операции.

```cpp
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```

### <a name="parameters"></a>Параметры

*hKey*\
Маркер открытого раздела реестра.

*лпсубкэй*\
Имя удаляемого ключа.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение будет ERROR_SUCCESS. Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в файле Winerror.h.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `RegDeleteKeyTransacted` функцию.

## <a name="regopenkeyex"></a><a name="regopenkeyex"></a> RegOpenKeyEx

Открывает указанный раздел реестра и связывает его с транзакцией.

```cpp
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```

### <a name="parameters"></a>Параметры

*hKey*<br/>
Маркер открытого раздела реестра.

*лпсубкэй*<br/>
Имя открываемого подраздела реестра.

*улоптионс*<br/>
Этот параметр зарезервирован и должен быть равен нулю.

*самдесиред*<br/>
Маска, указывающая права доступа для ключа.

*фкресулт*<br/>
Указатель на переменную, которая получает маркер для открытого или созданного ключа. Если ключ не является одним из предопределенных разделов реестра, вызовите `RegCloseKey` функцию после завершения использования маркера.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполнена, возвращаемое значение будет ERROR_SUCCESS. Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки, определенным в файле Winerror.h.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `RegOpenKeyTransacted` функцию.

## <a name="rollback"></a><a name="rollback"></a> Отката

Запрашивает откат транзакции.

```cpp
inline BOOL Rollback();
```

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если успешно; в противном случае — FALSE.

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `RollbackTransaction` функцию.

## <a name="setfileattributes"></a><a name="setfileattributes"></a> сетфилеаттрибутес

Задает атрибуты для файла или каталога в качестве транзакционной операции.

```cpp
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```

### <a name="parameters"></a>Параметры

*лпфиленаме*<br/>
Имя файла или каталога.

*дваттрибутес*<br/>
Атрибуты файла, которые необходимо задать для файла. Дополнительные сведения см. в разделе [сетфилеаттрибутестрансактед](/windows/win32/api/winbase/nf-winbase-setfileattributestransactedw).

### <a name="remarks"></a>Примечания

Эта оболочка вызывает `SetFileAttributesTransacted` функцию.

## <a name="see-also"></a>См. также

[Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)
