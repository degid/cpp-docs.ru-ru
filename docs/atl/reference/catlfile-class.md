---
title: Класс Катлфиле
ms.date: 11/04/2016
f1_keywords:
- CAtlFile
- ATLFILE/ATL::CAtlFile
- ATLFILE/ATL::CAtlFile::CAtlFile
- ATLFILE/ATL::CAtlFile::Create
- ATLFILE/ATL::CAtlFile::Flush
- ATLFILE/ATL::CAtlFile::GetOverlappedResult
- ATLFILE/ATL::CAtlFile::GetPosition
- ATLFILE/ATL::CAtlFile::GetSize
- ATLFILE/ATL::CAtlFile::LockRange
- ATLFILE/ATL::CAtlFile::Read
- ATLFILE/ATL::CAtlFile::Seek
- ATLFILE/ATL::CAtlFile::SetSize
- ATLFILE/ATL::CAtlFile::UnlockRange
- ATLFILE/ATL::CAtlFile::Write
- ATLFILE/ATL::CAtlFile::m_pTM
helpviewer_keywords:
- CAtlFile class
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
ms.openlocfilehash: 83a0a89bf6e2e21be33cf8c6003228111eff5394
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168115"
---
# <a name="catlfile-class"></a>Класс Катлфиле

Этот класс предоставляет тонкую оболочку для API-интерфейса обработки файлов Windows.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class CAtlFile : public CHandle
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Катлфиле:: Катлфиле](#catlfile)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Катлфиле:: Create](#create)|Вызовите этот метод, чтобы создать или открыть файл.|
|[Катлфиле:: Flush](#flush)|Вызовите этот метод, чтобы очистить буферы для файла и вызвать запись всех буферизованных данных в файл.|
|[Катлфиле:: GetOverlappedResult](#getoverlappedresult)|Вызовите этот метод, чтобы получить результаты операции перекрытия файла.|
|[Катлфиле:: Disposition](#getposition)|Вызовите этот метод, чтобы получить текущую позиции указателя файла из файла.|
|[Катлфиле:: DataSize](#getsize)|Вызовите этот метод, чтобы получить размер файла в байтах.|
|[Катлфиле:: Локкранже](#lockrange)|Вызовите этот метод, чтобы заблокировать область в файле, чтобы предотвратить доступ других процессов к нему.|
|[Катлфиле:: Read](#read)|Вызывайте этот метод для чтения данных из файла, начиная с позиции, указанной указателем файла.|
|[Катлфиле:: Seek](#seek)|Вызовите этот метод, чтобы переместить указатель файла файла.|
|[Катлфиле:: SetSize](#setsize)|Вызовите этот метод, чтобы задать размер файла.|
|[Катлфиле:: Унлоккранже](#unlockrange)|Вызовите этот метод, чтобы разблокировать область файла.|
|[Катлфиле:: Write](#write)|Вызывайте этот метод для записи данных в файл, начиная с позиции, указанной указателем файла.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[Катлфиле:: m_pTM](#m_ptm)|Указатель на `CAtlTransactionManager` объект|

## <a name="remarks"></a>Примечания

Используйте этот класс, если потребности в обработке файлов относительно просты, но требуется более абстракция, чем Windows API, без включения зависимостей MFC.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[чандле](../../atl/reference/chandle-class.md)

`CAtlFile`

## <a name="requirements"></a>Требования

**Заголовок:** атлфиле.h

## <a name="catlfilecatlfile"></a><a name="catlfile"></a>Катлфиле:: Катлфиле

Конструктор.

```cpp
CAtlFile() throw();
CAtlFile(CAtlTransactionManager* pTM = NULL) throw();
CAtlFile(CAtlFile& file) throw();
explicit CAtlFile(HANDLE hFile) throw();
```

### <a name="parameters"></a>Параметры

*File*<br/>
Объект File.

*hFile*<br/>
Маркер файла.

*pTM*<br/>
Указатель на объект CAtlTransactionManager.

### <a name="remarks"></a>Примечания

Конструктор копий передает владение маркером файла из исходного `CAtlFile` объекта в вновь сконструированный объект.

## <a name="catlfilecreate"></a><a name="create"></a>Катлфиле:: Create

Вызовите этот метод, чтобы создать или открыть файл.

```cpp
HRESULT Create(
    LPCTSTR szFilename,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes = FILE_ATTRIBUTE_NORMAL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    HANDLE hTemplateFile = NULL) throw();
```

### <a name="parameters"></a>Параметры

*сзфиленаме*<br/>
Имя файла.

*двдесиредакцесс*<br/>
Требуемый доступ. См. раздел *двдесиредакцесс* in [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew) в Windows SDK.

*двшаремоде*<br/>
Режим общего доступа. См *dwShareMode* . раздел `CreateFile`двшаремоде in.

*двкреатиондиспоситион*<br/>
Расстановка создания. См *dwCreationDisposition* . раздел `CreateFile`двкреатиондиспоситион in.

*двфлагсандаттрибутес*<br/>
Флаги и атрибуты. См *dwFlagsAndAttributes* . раздел `CreateFile`двфлагсандаттрибутес in.

*лпса*<br/>
Атрибуты безопасности. См *lpSecurityAttributes* . раздел `CreateFile`лпсекуритяттрибутес in.

*хтемплатефиле*<br/>
Файл шаблона. См *hTemplateFile* . раздел `CreateFile`хтемплатефиле in.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew) для создания или открытия файла.

## <a name="catlfileflush"></a><a name="flush"></a>Катлфиле:: Flush

Вызовите этот метод, чтобы очистить буферы для файла и вызвать запись всех буферизованных данных в файл.

```cpp
HRESULT Flush() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [FlushFileBuffers](/windows/win32/api/fileapi/nf-fileapi-flushfilebuffers) для сброса буферизованных данных в файл.

## <a name="catlfilegetoverlappedresult"></a><a name="getoverlappedresult"></a>Катлфиле:: GetOverlappedResult

Вызовите этот метод, чтобы получить результаты операции перекрытия файла.

```cpp
HRESULT GetOverlappedResult(
    LPOVERLAPPED pOverlapped,
    DWORD& dwBytesTransferred,
    BOOL bWait) throw();
```

### <a name="parameters"></a>Параметры

*поверлаппед*<br/>
Перекрывающаяся структура. См. раздел *лповерлаппед* в [GetOverlappedResult](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) в Windows SDK.

*двбитестрансферред*<br/>
Переданные байты. См *lpNumberOfBytesTransferred* . раздел `GetOverlappedResult`лпнумберофбитестрансферред in.

*бваит*<br/>
Параметр wait. См *bWait* . раздел `GetOverlappedResult`бваит in.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [GetOverlappedResult](/windows/win32/api/ioapiset/nf-ioapiset-getoverlappedresult) для получения результатов операции перекрытия файла.

## <a name="catlfilegetposition"></a><a name="getposition"></a>Катлфиле:: Disposition

Вызовите этот метод, чтобы получить текущую позиции указателя файла.

```cpp
HRESULT GetPosition(ULONGLONG& nPos) const throw();
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Расположение в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) , чтобы получить текущую позиции указателя файла.

## <a name="catlfilegetsize"></a><a name="getsize"></a>Катлфиле:: DataSize

Вызовите этот метод, чтобы получить размер файла в байтах.

```cpp
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Параметры

*нлен*<br/>
Число байтов в файле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [GetFileSize](/windows/win32/api/fileapi/nf-fileapi-getfilesize) для получения размера файла в байтах.

## <a name="catlfilelockrange"></a><a name="lockrange"></a>Катлфиле:: Локкранже

Вызовите этот метод, чтобы заблокировать область в файле, чтобы предотвратить доступ других процессов к нему.

```cpp
HRESULT LockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Место в файле, где должна начинаться блокировка.

*нкаунт*<br/>
Длина блокируемого диапазона байтов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [локкфиле](/windows/win32/api/fileapi/nf-fileapi-lockfile) для блокировки области в файле. Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать несколько регионов файла, но перекрывающиеся области не допускаются. При разблокировании области с помощью [катлфиле:: унлоккранже](#unlockrange)диапазон байтов должен точно соответствовать региону, который был ранее заблокирован. `LockRange`не выполняет слияние смежных областей; Если два заблокированных региона являются смежными, каждый из них необходимо разблокировать отдельно.

## <a name="catlfilem_ptm"></a><a name="m_ptm"></a>Катлфиле:: m_pTM

Указатель на `CAtlTransactionManager` объект.

```cpp
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Примечания

## <a name="catlfileread"></a><a name="read"></a>Катлфиле:: Read

Вызывайте этот метод для чтения данных из файла, начиная с позиции, указанной указателем файла.

```cpp
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();

HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Указатель на буфер, который будет принимать данные, считанные из файла.

*нбуфсизе*<br/>
Размер буфера в байтах.

*нбитесреад*<br/>
Число переданных байтов.

*поверлаппед*<br/>
Перекрывающаяся структура. См. раздел *лповерлаппед* in [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile) в Windows SDK.

*пфнкомплетионраутине*<br/>
Подпрограммы завершения. См. раздел *лпкомплетионраутине* в [реадфиликс](/windows/win32/api/fileapi/nf-fileapi-readfileex) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Первые три формы вызывают [ReadFile](/windows/win32/api/fileapi/nf-fileapi-readfile), последнюю [реадфиликс](/windows/win32/api/fileapi/nf-fileapi-readfileex) чтение данных из файла. Используйте [катлфиле:: Seek](#seek) для перемещения указателя файла.

## <a name="catlfileseek"></a><a name="seek"></a>Катлфиле:: Seek

Вызовите этот метод, чтобы переместить указатель файла файла.

```cpp
HRESULT Seek(
    LONGLONG nOffset,
    DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Параметры

*ноффсет*<br/>
Смещение от начальной точки, заданной параметром *двфром*.

*двфром*<br/>
Начальная точка (FILE_BEGIN, FILE_CURRENT или FILE_END).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) для перемещения указателя файла.

## <a name="catlfilesetsize"></a><a name="setsize"></a>Катлфиле:: SetSize

Вызовите этот метод, чтобы задать размер файла.

```cpp
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Параметры

*нневлен*<br/>
Новая длина файла в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [SetFilePointer](/windows/win32/api/fileapi/nf-fileapi-setfilepointer) и [SetEndOfFile](/windows/win32/api/fileapi/nf-fileapi-setendoffile) , чтобы задать размер файла. При возврате указатель файла размещается в конце файла.

## <a name="catlfileunlockrange"></a><a name="unlockrange"></a>Катлфиле:: Унлоккранже

Вызовите этот метод, чтобы разблокировать область файла.

```cpp
HRESULT UnlockRange(ULONGLONG nPos, ULONGLONG nCount) throw();
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Место в файле, где должна начинаться разблокировка.

*нкаунт*<br/>
Длина диапазона байтов для разблокировки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [унлоккфиле](/windows/win32/api/fileapi/nf-fileapi-unlockfile) , чтобы разблокировать регион файла.

## <a name="catlfilewrite"></a><a name="write"></a>Катлфиле:: Write

Вызывайте этот метод для записи данных в файл, начиная с позиции, указанной указателем файла.

```cpp
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped,
    LPOVERLAPPED_COMPLETION_ROUTINE pfnCompletionRoutine) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();

HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    LPOVERLAPPED pOverlapped) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Буфер, содержащий данные, записываемые в файл.

*нбуфсизе*<br/>
Число байтов, которое необходимо передать из буфера.

*поверлаппед*<br/>
Перекрывающаяся структура. См. раздел *лповерлаппед* в [WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile) в Windows SDK.

*пфнкомплетионраутине*<br/>
Подпрограммы завершения. См. раздел *лпкомплетионраутине* в [вритефиликс](/windows/win32/api/fileapi/nf-fileapi-writefileex) в Windows SDK.

*пнбитесвриттен*<br/>
Записанные байты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Первые три формы вызывают [WriteFile](/windows/win32/api/fileapi/nf-fileapi-writefile), последний вызывает [вритефиликс](/windows/win32/api/fileapi/nf-fileapi-writefileex) для записи данных в файл. Используйте [катлфиле:: Seek](#seek) для перемещения указателя файла.

## <a name="see-also"></a>См. также

[Образец бегущей строки](../../overview/visual-cpp-samples.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс Чандле](../../atl/reference/chandle-class.md)
