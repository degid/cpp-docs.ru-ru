---
title: Класс Катлтемпорарифиле
ms.date: 11/04/2016
f1_keywords:
- CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::CAtlTemporaryFile
- ATLFILE/ATL::CAtlTemporaryFile::Close
- ATLFILE/ATL::CAtlTemporaryFile::Create
- ATLFILE/ATL::CAtlTemporaryFile::Flush
- ATLFILE/ATL::CAtlTemporaryFile::GetPosition
- ATLFILE/ATL::CAtlTemporaryFile::GetSize
- ATLFILE/ATL::CAtlTemporaryFile::HandsOff
- ATLFILE/ATL::CAtlTemporaryFile::HandsOn
- ATLFILE/ATL::CAtlTemporaryFile::LockRange
- ATLFILE/ATL::CAtlTemporaryFile::Read
- ATLFILE/ATL::CAtlTemporaryFile::Seek
- ATLFILE/ATL::CAtlTemporaryFile::SetSize
- ATLFILE/ATL::CAtlTemporaryFile::TempFileName
- ATLFILE/ATL::CAtlTemporaryFile::UnlockRange
- ATLFILE/ATL::CAtlTemporaryFile::Write
helpviewer_keywords:
- CAtlTemporaryFile class
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
ms.openlocfilehash: f3d0be66bf0b5a6c07a72c8ae6cc9c90e176728f
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167894"
---
# <a name="catltemporaryfile-class"></a>Класс Катлтемпорарифиле

Этот класс предоставляет методы для создания и использования временного файла.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class CAtlTemporaryFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Катлтемпорарифиле:: Катлтемпорарифиле](#catltemporaryfile)|Конструктор.|
|[Катлтемпорарифиле:: ~ Катлтемпорарифиле](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Катлтемпорарифиле:: Close](#close)|Вызовите этот метод, чтобы закрыть временный файл и либо удалить его содержимое, либо сохранить его по указанному имени файла.|
|[Катлтемпорарифиле:: Create](#create)|Вызовите этот метод, чтобы создать временный файл.|
|[Катлтемпорарифиле:: Flush](#flush)|Вызовите этот метод, чтобы принудительно записать все данные, остающиеся в буфере файла, во временный файл.|
|[Катлтемпорарифиле:: Disposition](#getposition)|Вызовите этот метод, чтобы получить текущую позиции указателя файла.|
|[Катлтемпорарифиле:: DataSize](#getsize)|Вызовите этот метод, чтобы получить размер временного файла в байтах.|
|[Катлтемпорарифиле:: Хандсофф](#handsoff)|Вызовите этот метод, чтобы разорвать связь файла `CAtlTemporaryFile` с объектом.|
|[Катлтемпорарифиле:: Хандсон](#handson)|Вызовите этот метод, чтобы открыть существующий временный файл и поместить указатель в конец файла.|
|[Катлтемпорарифиле:: Локкранже](#lockrange)|Вызовите этот метод, чтобы заблокировать область в файле, чтобы предотвратить доступ других процессов к нему.|
|[Катлтемпорарифиле:: Read](#read)|Вызывайте этот метод для чтения данных из временного файла, начиная с позиции, указанной указателем файла.|
|[Катлтемпорарифиле:: Seek](#seek)|Вызовите этот метод, чтобы переместить указатель файла для временного файла.|
|[Катлтемпорарифиле:: SetSize](#setsize)|Вызовите этот метод, чтобы задать размер временного файла.|
|[Катлтемпорарифиле:: Темпфиленаме](#tempfilename)|Вызовите этот метод, чтобы вернуть имя временного файла.|
|[Катлтемпорарифиле:: Унлоккранже](#unlockrange)|Вызовите этот метод, чтобы разблокировать регион временного файла.|
|[Катлтемпорарифиле:: Write](#write)|Вызывайте этот метод для записи данных во временный файл, начиная с позиции, указанной указателем файла.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[ОБРАБОТЧИК Катлтемпорарифиле::operator](#operator_handle)|Возвращает маркер для временного файла.|

## <a name="remarks"></a>Примечания

`CAtlTemporaryFile`упрощает создание и использование временного файла. Файл автоматически называется, открывается, закрывается и удаляется. Если содержимое файла требуется после закрытия файла, их можно сохранить в новый файл с указанным именем.

## <a name="requirements"></a>Требования

**Заголовок:** атлфиле.h

## <a name="example"></a>Пример

См. пример для [катлтемпорарифиле:: катлтемпорарифиле](#catltemporaryfile).

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="catltemporaryfile"></a>Катлтемпорарифиле:: Катлтемпорарифиле

Конструктор.

```cpp
CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Примечания

Файл на самом деле не открывается до тех пор, пока не будет выполнен вызов [катлтемпорарифиле:: Create](#create).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#73](../../atl/codesnippet/cpp/catltemporaryfile-class_1.cpp)]

## <a name="catltemporaryfilecatltemporaryfile"></a><a name="dtor"></a>Катлтемпорарифиле:: ~ Катлтемпорарифиле

Деструктор

```cpp
~CAtlTemporaryFile() throw();
```

### <a name="remarks"></a>Примечания

Деструктор вызывает [катлтемпорарифиле:: Close](#close).

## <a name="catltemporaryfileclose"></a><a name="close"></a>Катлтемпорарифиле:: Close

Вызовите этот метод, чтобы закрыть временный файл и либо удалить его содержимое, либо сохранить его по указанному имени файла.

```cpp
HRESULT Close(LPCTSTR szNewName = NULL) throw();
```

### <a name="parameters"></a>Параметры

*сзневнаме*<br/>
Имя нового файла, в котором будет храниться содержимое временного файла. Если этот аргумент имеет значение NULL, содержимое временного файла удаляется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

См. пример для [катлтемпорарифиле:: катлтемпорарифиле](#catltemporaryfile).

## <a name="catltemporaryfilecreate"></a><a name="create"></a>Катлтемпорарифиле:: Create

Вызовите этот метод, чтобы создать временный файл.

```cpp
HRESULT Create(LPCTSTR pszDir = NULL, DWORD dwDesiredAccess = GENERIC_WRITE) throw();
```

### <a name="parameters"></a>Параметры

*псздир*<br/>
Путь к временному файлу. Если это значение равно NULL, для назначения пути будет вызван [жеттемппас](/windows/win32/api/fileapi/nf-fileapi-gettemppathw) .

*двдесиредакцесс*<br/>
Требуемый доступ. См. раздел *двдесиредакцесс* in [CreateFile](/windows/win32/api/fileapi/nf-fileapi-createfilew) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="example"></a>Пример

См. пример для [катлтемпорарифиле:: катлтемпорарифиле](#catltemporaryfile).

## <a name="catltemporaryfileflush"></a><a name="flush"></a>Катлтемпорарифиле:: Flush

Вызовите этот метод, чтобы принудительно записать все данные, остающиеся в буфере файла, во временный файл.

```cpp
HRESULT Flush() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Аналогично [катлтемпорарифиле:: хандсофф](#handsoff), за исключением того, что файл не закрыт.

### <a name="example"></a>Пример

См. пример для [катлтемпорарифиле:: катлтемпорарифиле](#catltemporaryfile).

## <a name="catltemporaryfilegetposition"></a><a name="getposition"></a>Катлтемпорарифиле:: Disposition

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

Чтобы изменить положение указателя файла, используйте [катлтемпорарифиле:: Seek](#seek).

## <a name="catltemporaryfilegetsize"></a><a name="getsize"></a>Катлтемпорарифиле:: DataSize

Вызовите этот метод, чтобы получить размер временного файла в байтах.

```cpp
HRESULT GetSize(ULONGLONG& nLen) const throw();
```

### <a name="parameters"></a>Параметры

*нлен*<br/>
Число байтов в файле.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="catltemporaryfilehandsoff"></a><a name="handsoff"></a>Катлтемпорарифиле:: Хандсофф

Вызовите этот метод, чтобы разорвать связь файла `CAtlTemporaryFile` с объектом.

```cpp
HRESULT HandsOff() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

`HandsOff`и [катлтемпорарифиле:: Хандсон](#handson) используются для того, чтобы разорвать связь файла с объектом и при необходимости повторно присоединить его. `HandsOff`принудительно записывает все данные, оставшиеся в буфере файла, во временный файл, а затем закрывает файл. Если вы хотите закрыть и удалить файл без возможности восстановления или хотите закрыть и хранить содержимое файла с заданным именем, используйте [катлтемпорарифиле:: Close](#close).

## <a name="catltemporaryfilehandson"></a><a name="handson"></a>Катлтемпорарифиле:: Хандсон

Вызовите этот метод, чтобы открыть существующий временный файл и поместить указатель в конец файла.

```cpp
HRESULT HandsOn() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

[Катлтемпорарифиле:: хандсофф](#handsoff) и `HandsOn` используются для того, чтобы разорвать связь файла с объектом и при необходимости повторно присоединить его.

## <a name="catltemporaryfilelockrange"></a><a name="lockrange"></a>Катлтемпорарифиле:: Локкранже

Вызовите этот метод, чтобы заблокировать область во временном файле, чтобы предотвратить доступ других процессов к нему.

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

Блокировка байтов в файле предотвращает доступ других процессов к этим байтам. Можно заблокировать несколько регионов файла, но перекрывающиеся области не допускаются. Чтобы успешно разблокировать регион, используйте [катлтемпорарифиле:: унлоккранже](#unlockrange), гарантируя, что диапазон байтов точно соответствует региону, который ранее был заблокирован. `LockRange`не выполняет слияние смежных областей; Если два заблокированных региона являются смежными, каждый из них необходимо разблокировать отдельно.

## <a name="catltemporaryfileoperator-handle"></a><a name="operator_handle"></a>ОБРАБОТЧИК Катлтемпорарифиле::operator

Возвращает маркер для временного файла.

```cpp
operator HANDLE() throw();
```

## <a name="catltemporaryfileread"></a><a name="read"></a>Катлтемпорарифиле:: Read

Вызывайте этот метод для чтения данных из временного файла, начиная с позиции, указанной указателем файла.

```cpp
HRESULT Read(
    LPVOID pBuffer,
    DWORD nBufSize,
    DWORD& nBytesRead) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Указатель на буфер, который будет принимать данные, считанные из файла.

*нбуфсизе*<br/>
Размер буфера в байтах.

*нбитесреад*<br/>
Число переданных байтов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [катлфиле:: Read](../../atl/reference/catlfile-class.md#read). Чтобы изменить положение указателя файла, вызовите метод [катлтемпорарифиле:: Seek](#seek).

### <a name="example"></a>Пример

См. пример для [катлтемпорарифиле:: катлтемпорарифиле](#catltemporaryfile).

## <a name="catltemporaryfileseek"></a><a name="seek"></a>Катлтемпорарифиле:: Seek

Вызовите этот метод, чтобы переместить указатель файла для временного файла.

```cpp
HRESULT Seek(LONGLONG nOffset, DWORD dwFrom = FILE_CURRENT) throw();
```

### <a name="parameters"></a>Параметры

*ноффсет*<br/>
Смещение в байтах от начальной точки, заданной параметром *двфром.*

*двфром*<br/>
Начальная точка (FILE_BEGIN, FILE_CURRENT или FILE_END).

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [катлфиле:: Seek](../../atl/reference/catlfile-class.md#seek). Чтобы получить текущую позиции указателя файла, вызовите [катлтемпорарифиле:: Disposition](#getposition).

### <a name="example"></a>Пример

См. пример для [катлтемпорарифиле:: катлтемпорарифиле](#catltemporaryfile).

## <a name="catltemporaryfilesetsize"></a><a name="setsize"></a>Катлтемпорарифиле:: SetSize

Вызовите этот метод, чтобы задать размер временного файла.

```cpp
HRESULT SetSize(ULONGLONG nNewLen) throw();
```

### <a name="parameters"></a>Параметры

*нневлен*<br/>
Новая длина файла в байтах.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [катлфиле:: SetSize](../../atl/reference/catlfile-class.md#setsize). При возврате указатель файла размещается в конце файла.

## <a name="catltemporaryfiletempfilename"></a><a name="tempfilename"></a>Катлтемпорарифиле:: Темпфиленаме

Вызовите этот метод, чтобы вернуть имя временного файла.

```cpp
LPCTSTR TempFileName() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает LPCTSTR, указывающий на имя файла.

### <a name="remarks"></a>Примечания

Имя файла создается в [катлтемпорарифиле:: катлтемпорарифиле](#catltemporaryfile) с вызовом функции [жеттемпфиле](/windows/win32/api/fileapi/nf-fileapi-gettempfilenamew)Windows SDK. Для временного файла всегда будет использоваться расширение файла «ТФР».

## <a name="catltemporaryfileunlockrange"></a><a name="unlockrange"></a>Катлтемпорарифиле:: Унлоккранже

Вызовите этот метод, чтобы разблокировать регион временного файла.

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

Вызывает [катлфиле:: унлоккранже](../../atl/reference/catlfile-class.md#unlockrange).

## <a name="catltemporaryfilewrite"></a><a name="write"></a>Катлтемпорарифиле:: Write

Вызывайте этот метод для записи данных во временный файл, начиная с позиции, указанной указателем файла.

```cpp
HRESULT Write(
    LPCVOID pBuffer,
    DWORD nBufSize,
    DWORD* pnBytesWritten = NULL) throw();
```

### <a name="parameters"></a>Параметры

*pBuffer*<br/>
Буфер, содержащий данные, записываемые в файл.

*нбуфсизе*<br/>
Число байтов, которое необходимо передать из буфера.

*пнбитесвриттен*<br/>
Количество записанных байт.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Вызывает [катлфиле:: Write](../../atl/reference/catlfile-class.md#write).

### <a name="example"></a>Пример

См. пример для [катлтемпорарифиле:: катлтемпорарифиле](#catltemporaryfile).

## <a name="see-also"></a>См. также

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс Катлфиле](../../atl/reference/catlfile-class.md)
