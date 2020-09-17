---
title: Класс ColeStreamFile
ms.date: 11/04/2016
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
ms.openlocfilehash: 202f8381361881ce3b8b62f81da5bfb81a1f952d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753756"
---
# <a name="colestreamfile-class"></a>Класс ColeStreamFile

Представляет поток данных (`IStream`) в составном файле как часть структурированного хранения OLE.

## <a name="syntax"></a>Синтаксис

```
class COleStreamFile : public CFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[ColeStreamFile::COleStreamFile](#colestreamfile)|Формирует объект `COleStreamFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ColeStreamFile::Attach](#attach)|Связывает поток с объектом.|
|[ColeStreamFile::CreateMemoryStream](#creatememorystream)|Создает поток из глобальной памяти и связывает его с объектом.|
|[ColeStreamFile::CreateStream](#createstream)|Создает поток и связывает его с объектом.|
|[ColeStreamFile::Detach](#detach)|Отсажает поток от объекта.|
|[ColeStreamFile::GetStream](#getstream)|Возвращает текущий поток.|
|[ColeStreamFile::OpenStream](#openstream)|Безопасно открывает поток и связывает его с объектом.|

## <a name="remarks"></a>Примечания

Объект `IStorage` должен существовать до того, как поток может быть открыт или создан, если он не является потоком памяти.

`COleStreamFile`объектами манипулируют точно так же, как объекты [CFile.](../../mfc/reference/cfile-class.md)

Для получения дополнительной информации об манипулировании [Containers: Compound Files](../../mfc/containers-compound-files.md)потоками и хранилищами, см.

Для получения дополнительной информации [IStorage](/windows/win32/api/objidl/nn-objidl-istorage) [см.](/windows/win32/api/objidl/nn-objidl-istream)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`COleStreamFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxole.h

## <a name="colestreamfileattach"></a><a name="attach"></a>ColeStreamFile::Attach

Ассоциирует поставляемый поток OLE с объектом. `COleStreamFile`

```cpp
void Attach(LPSTREAM lpStream);
```

### <a name="parameters"></a>Параметры

*lpStream*<br/>
Очки к потоку`IStream`OLE (), чтобы быть связанным с объектом. Не может быть NULL.

### <a name="remarks"></a>Примечания

Объект уже не должен быть связан с потоком OLE.

Для получения дополнительной [IStream](/windows/win32/api/objidl/nn-objidl-istream) информации см.

## <a name="colestreamfilecolestreamfile"></a><a name="colestreamfile"></a>ColeStreamFile::COleStreamFile

Создает объект `COleStreamFile`.

```
COleStreamFile(LPSTREAM lpStream = NULL);
```

### <a name="parameters"></a>Параметры

*lpStream*<br/>
Указатель на поток OLE, связанный с объектом.

### <a name="remarks"></a>Примечания

Если *lpStream* является NULL, объект не связан с потоком OLE, в противном случае, объект связан с поставляемым потоком OLE.

Для получения дополнительной [IStream](/windows/win32/api/objidl/nn-objidl-istream) информации см.

## <a name="colestreamfilecreatememorystream"></a><a name="creatememorystream"></a>ColeStreamFile::CreateMemoryStream

Безопасно создает новый поток из глобальной, общей памяти, где сбой является нормальным, ожидаемым состоянием.

```
BOOL CreateMemoryStream(CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*pОшибка*<br/>
Указывает на объект [CFileException](../../mfc/reference/cfileexception-class.md) или NULL, указывающий состояние завершения операции создания. Подавайте этот параметр, если вы хотите отслеживать возможные исключения, генерируемые попыткой создания потока.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если поток создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Память выделяется подсистемой OLE.

Для получения дополнительной информации смотрите [CreateStreamOnHGlobal](/windows/win32/api/combaseapi/nf-combaseapi-createstreamonhglobal) в Windows SDK.

## <a name="colestreamfilecreatestream"></a><a name="createstream"></a>ColeStreamFile::CreateStream

Безопасно создает новый поток в поставляемом объекте хранения, где сбой является нормальным, ожидаемым состоянием.

```
BOOL CreateStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*lpStorage*<br/>
Указывает на объект хранения OLE, содержащий создаваемый поток. Не может быть NULL.

*lpszStreamName*<br/>
Название создаваемого потока. Не может быть NULL.

*nОткрытыефлаги*<br/>
Режим доступа для использования при открытии потока. По умолчанию используются эксклюзивные, читаемые/записные режимы. Полный список доступных режимов можно найти в [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).

*pОшибка*<br/>
Указывает на объект [CFileException](../../mfc/reference/cfileexception-class.md) или NULL. Подавайте этот параметр, если вы хотите отслеживать возможные исключения, генерируемые попыткой создания потока.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если поток создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Исключение файла будет брошено, если открытый сбой и *pError* не является NULL.

Для получения дополнительной информации см. [IStorage::CreateStream](/windows/win32/api/objidl/nf-objidl-istorage-createstream) в Windows SDK.

## <a name="colestreamfiledetach"></a><a name="detach"></a>ColeStreamFile::Detach

Отсажает поток от объекта, не закрывая поток.

```
LPSTREAM Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на поток`IStream`(), который был связан с объектом.

### <a name="remarks"></a>Примечания

Поток должен быть закрыт другим способом до завершения программы.

Для получения дополнительной [IStream](/windows/win32/api/objidl/nn-objidl-istream) информации см.

## <a name="colestreamfilegetstream"></a><a name="getstream"></a>ColeStreamFile::GetStream

Вызовите эту функцию, чтобы вернуть указатель в текущий поток.

```
IStream* GetStream() const;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий интерфейс потока [(IStream](/windows/win32/api/objidl/nn-objidl-istream)).

## <a name="colestreamfileopenstream"></a><a name="openstream"></a>ColeStreamFile::OpenStream

Открывает существующий поток.

```
BOOL OpenStream(
    LPSTORAGE lpStorage,
    LPCTSTR lpszStreamName,
    DWORD nOpenFlags = modeReadWrite|shareExclusive,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Параметры

*lpStorage*<br/>
Точки на объект хранения OLE, содержащий поток, который будет открыт. Не может быть NULL.

*lpszStreamName*<br/>
Название потока, который будет открыт. Не может быть NULL.

*nОткрытыефлаги*<br/>
Режим доступа для использования при открытии потока. По умолчанию используются эксклюзивные режимы чтения/записи. Полный список доступных режимов можно найти в [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).

*pОшибка*<br/>
Указывает на объект [CFileException](../../mfc/reference/cfileexception-class.md) или NULL. Подавайте этот параметр, если вы хотите отслеживать возможные исключения, генерируемые попыткой открыть поток.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если поток открыт успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Исключение файла будет брошено, если открытый сбой и *pError* не является NULL.

Для получения дополнительной информации см. [IStorage::OpenStream](/windows/win32/api/objidl/nf-objidl-istorage-openstream) в Windows SDK.

## <a name="see-also"></a>См. также раздел

[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
