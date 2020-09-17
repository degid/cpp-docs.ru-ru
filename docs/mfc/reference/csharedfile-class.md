---
title: Класс CSharedFile
ms.date: 11/04/2016
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
ms.openlocfilehash: c715ca1b8a2b647f89ada008f3c6606ca5e58783
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750389"
---
# <a name="csharedfile-class"></a>Класс CSharedFile

[CMemFile](../../mfc/reference/cmemfile-class.md)- производный класс, который поддерживает общие файлы памяти.

## <a name="syntax"></a>Синтаксис

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSharedFile::CSharedFile](#csharedfile)|Формирует объект `CSharedFile`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSharedFile::Detach](#detach)|Закрывает общий файл памяти и возвращает ручку блока памяти.|
|[CSharedFile::Set](#sethandle)|Прикрепляет файл общей памяти к блоку памяти.|

## <a name="remarks"></a>Примечания

Файлы памяти ведут себя как дисковые файлы. Разница в том, что файл памяти хранится в оперативной памяти, а не на диске. Файл памяти полезен для быстрого временного хранения или для передачи необработанных байтов или сериализованных объектов между независимыми процессами.

Общие файлы памяти отличаются от других файлов памяти тем, что память для них выделяется с функцией [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) Windows. Класс `CSharedFile` хранит данные в глобально выделенном `GlobalAlloc`блоке памяти (созданном с помощью), и этот блок памяти может быть общим `IDataObject`с помощью DDE, Clipboard или других однородных операций передачи данных OLE/COM, например, с использованием.

`GlobalAlloc`возвращает ручку HGLOBAL, а не указатель на память, например указатель, возвращенный [malloc.](../../c-runtime-library/reference/malloc.md) Ручка HGLOBAL необходима в некоторых приложениях. Например, для того, чтобы поместить данные на Clipboard, требуется ручка HGLOBAL.

`CSharedFile`не использует файлы с картографом памяти, и данные не могут быть непосредственно разделены между процессами.

`CSharedFile`объекты могут автоматически выделять свою собственную память. Или, вы можете прикрепить `CSharedFile` свой собственный блок памяти к объекту, позвонив [CSharedFile::SetHandle](#sethandle). В любом случае память для получения файла `nGrowBytes`памяти автоматически выделяется в приращениях размера, если `nGrowBytes` она не равна нулю.

Для получения дополнительной информации смотрите статью [Файлы в MFC](../../mfc/files-in-mfc.md) и [обработки файлов](../../c-runtime-library/file-handling.md) в *Run-Time Библиотека Справка*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxadv.h

## <a name="csharedfilecsharedfile"></a><a name="csharedfile"></a>CSharedFile::CSharedFile

Строит `CSharedFile` объект и выделяет память для него.

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>Параметры

*nAllocFlags*<br/>
Флаги, указывающие на выделение памяти. Список допустимых значений флага можно посмотреть [globalAlloc.](/windows/win32/api/winbase/nf-winbase-globalalloc)

*nGrowBytes*<br/>
Распределение памяти в байтах.

## <a name="csharedfiledetach"></a><a name="detach"></a>CSharedFile::Detach

Вызов и функции, чтобы закрыть файл памяти и отделить его от блока памяти.

```
HGLOBAL Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Ручка блока памяти, содержащая содержимое файла памяти.

### <a name="remarks"></a>Примечания

Вы можете вновь открыть его, позвонив [SetHandle](#sethandle), используя ручку, возвращенную **Detach.**

## <a name="csharedfilesethandle"></a><a name="sethandle"></a>CSharedFile::Set

Вызовите эту функцию, чтобы `CSharedFile` прикрепить блок глобальной памяти к объекту.

```cpp
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>Параметры

*hGlobalMemory*<br/>
Ручка к глобальной памяти, `CSharedFile`чтобы быть прикреплены к .

*bAllowGrow*<br/>
Определяет, может ли блок памяти расти.

### <a name="remarks"></a>Примечания

Если *bAllowGrow* незеро, размер блока памяти увеличивается по мере необходимости, например, если вы пытаетесь написать больше байтов в файл, чем размер блока памяти.

## <a name="see-also"></a>См. также раздел

[Класс CMemFile](../../mfc/reference/cmemfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMemFile](../../mfc/reference/cmemfile-class.md)
