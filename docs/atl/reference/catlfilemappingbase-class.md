---
title: Класс Катлфилемаппингбасе
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
ms.openlocfilehash: 75177c195e83a4ab3ad2a6bd4d608d07f8c2234f
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168089"
---
# <a name="catlfilemappingbase-class"></a>Класс Катлфилемаппингбасе

Этот класс представляет размещенный в памяти файл.

> [!IMPORTANT]
> Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class CAtlFileMappingBase
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Катлфилемаппингбасе:: Катлфилемаппингбасе](#catlfilemappingbase)|Конструктор.|
|[Катлфилемаппингбасе:: ~ Катлфилемаппингбасе](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Катлфилемаппингбасе:: CopyFrom](#copyfrom)|Вызовите этот метод для копирования из объекта сопоставления файлов.|
|[Катлфилемаппингбасе:: GetData](#getdata)|Вызовите этот метод, чтобы получить данные из объекта сопоставления файлов.|
|[Катлфилемаппингбасе:: getHandler](#gethandle)|Вызовите этот метод, чтобы получить маркер файла.|
|[Катлфилемаппингбасе:: Жетмаппингсизе](#getmappingsize)|Вызовите этот метод, чтобы получить размер сопоставления из объекта сопоставления файлов.|
|[Катлфилемаппингбасе:: файла сопоставления](#mapfile)|Вызовите этот метод, чтобы создать объект сопоставления файлов.|
|[Катлфилемаппингбасе:: Мапшаредмем](#mapsharedmem)|Вызовите этот метод, чтобы создать объект сопоставления файлов, разрешающий полный доступ ко всем процессам.|
|[Катлфилемаппингбасе:: Опенмаппинг](#openmapping)|Вызовите этот метод, чтобы вернуть маркер для объекта сопоставления файлов.|
|[Катлфилемаппингбасе:: отмена сопоставления](#unmap)|Вызовите этот метод, чтобы отменить сопоставление объекта сопоставления файлов.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Катлфилемаппингбасе::operator=](#operator_eq)|Задает текущий объект сопоставления файлов для другого объекта сопоставления файлов.|

## <a name="remarks"></a>Примечания

Сопоставление файлов — это привязка содержимого файла к части виртуального адресного пространства процесса. Этот класс предоставляет методы для создания объектов сопоставления файлов, которые позволяют программам легко получать доступ к данным и предоставлять к ним общий доступ.

Дополнительные сведения см. в разделе [Сопоставление файлов](/windows/win32/Memory/file-mapping) в Windows SDK.

## <a name="requirements"></a>Требования

**Заголовок:** атлфиле.h

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="catlfilemappingbase"></a>Катлфилемаппингбасе:: Катлфилемаппингбасе

Конструктор.

```cpp
CAtlFileMappingBase(CAtlFileMappingBase& orig);
CAtlFileMappingBase() throw();
```

### <a name="parameters"></a>Параметры

*Orig*<br/>
Исходный объект сопоставления файлов для копирования для создания нового объекта.

### <a name="remarks"></a>Примечания

Создает новый объект сопоставления файлов, при необходимости используя существующий объект. По-прежнему необходимо вызвать [катлфилемаппингбасе:: файл сопоставления](#mapfile) , чтобы открыть или создать объект сопоставления файлов для определенного файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="dtor"></a>Катлфилемаппингбасе:: ~ Катлфилемаппингбасе

Деструктор

```cpp
~CAtlFileMappingBase() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все ресурсы, выделенные классом, и вызывает метод [катлфилемаппингбасе::](#unmap) uncall.

## <a name="catlfilemappingbasecopyfrom"></a><a name="copyfrom"></a>Катлфилемаппингбасе:: CopyFrom

Вызовите этот метод для копирования из объекта сопоставления файлов.

```cpp
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```

### <a name="parameters"></a>Параметры

*Orig*<br/>
Исходный объект сопоставления файлов, из которого производится копирование.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

## <a name="catlfilemappingbasegetdata"></a><a name="getdata"></a>Катлфилемаппингбасе:: GetData

Вызовите этот метод, чтобы получить данные из объекта сопоставления файлов.

```cpp
void* GetData() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на данные.

## <a name="catlfilemappingbasegethandle"></a><a name="gethandle"></a>Катлфилемаппингбасе:: getHandler

Вызовите этот метод, чтобы вернуть маркер для объекта сопоставления файлов.

```cpp
HANDLE GetHandle() throw ();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает маркер объекта сопоставления файлов.

## <a name="catlfilemappingbasegetmappingsize"></a><a name="getmappingsize"></a>Катлфилемаппингбасе:: Жетмаппингсизе

Вызовите этот метод, чтобы получить размер сопоставления из объекта сопоставления файлов.

```cpp
SIZE_T GetMappingSize() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер сопоставления.

### <a name="example"></a>Пример

См. пример для [катлфилемаппингбасе:: катлфилемаппингбасе](#catlfilemappingbase).

## <a name="catlfilemappingbasemapfile"></a><a name="mapfile"></a>Катлфилемаппингбасе:: файла сопоставления

Вызовите этот метод, чтобы открыть или создать объект сопоставления файлов для указанного файла.

```cpp
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```

### <a name="parameters"></a>Параметры

*hFile*<br/>
Обработайте с файлом, из которого создается объект сопоставления. *hFile* должен быть допустимым и не может принимать значение INVALID_HANDLE_VALUE.

*нмаппингсизе*<br/>
Размер сопоставления. Если значение равно 0, максимальный размер объекта сопоставления файлов равен текущему размеру файла, определенного параметром *hFile.*

*ноффсет*<br/>
Смещение файла, с которого начинается сопоставление. Значение смещения должно быть кратным степени гранулярности выделения памяти в системе.

*двмаппингпротектион*<br/>
Защита, необходимая для представления файла при сопоставлении файла. См. раздел *флпротект* в [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) в Windows SDK.

*дввиевдесиредакцесс*<br/>
Указывает тип доступа к представлению файла и, таким образом, защиту страниц, сопоставленных с файлом. См. раздел *двдесиредакцесс* в [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

После того как объект сопоставления файлов создан, размер файла не должен превышать размер объекта сопоставления файлов; Если это так, не все содержимое файла будет доступно для общего доступа. Дополнительные сведения см. в разделе [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) и [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) в Windows SDK.

### <a name="example"></a>Пример

См. пример для [катлфилемаппингбасе:: катлфилемаппингбасе](#catlfilemappingbase).

## <a name="catlfilemappingbasemapsharedmem"></a><a name="mapsharedmem"></a>Катлфилемаппингбасе:: Мапшаредмем

Вызовите этот метод, чтобы создать объект сопоставления файлов, разрешающий полный доступ ко всем процессам.

```cpp
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Параметры

*нмаппингсизе*<br/>
Размер сопоставления. Если значение равно 0, максимальный размер объекта сопоставления файлов равен текущему размеру объекта сопоставления файлов, определенного параметром *szName*.

*szName*<br/>
Имя объекта сопоставления.

*пбалреадексистед*<br/>
Указывает на логическое значение, равное TRUE, если объект сопоставления уже существовал.

*лпса*<br/>
Указатель на `SECURITY_ATTRIBUTES` структуру, которая определяет, может ли возвращаемый маркер наследоваться дочерними процессами. См. раздел *лпаттрибутес* в [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) в Windows SDK.

*двмаппингпротектион*<br/>
Защита, необходимая для представления файлов при сопоставлении файла. См *flProtect* . раздел `CreateFileMapping` флпротект в Windows SDK.

*дввиевдесиредакцесс*<br/>
Указывает тип доступа к представлению файла и, таким образом, защиту страниц, сопоставленных с файлом. См. раздел *двдесиредакцесс* в [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

`MapShareMem`позволяет совместно использовать существующий объект сопоставления файлов, созданный [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga), между процессами.

## <a name="catlfilemappingbaseopenmapping"></a><a name="openmapping"></a>Катлфилемаппингбасе:: Опенмаппинг

Вызовите этот метод, чтобы открыть именованный объект сопоставления файлов для указанного файла.

```cpp
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Параметры

*szName*<br/>
Имя объекта сопоставления. Если имеется открытый дескриптор объекта сопоставления файлов по этому имени, а дескриптор безопасности в объекте сопоставления не конфликтует с параметром *дввиевдесиредакцесс* , операция открытия будет выполнена.

*нмаппингсизе*<br/>
Размер сопоставления. Если значение равно 0, максимальный размер объекта сопоставления файлов равен текущему размеру объекта сопоставления файлов, определенного параметром *szName*.

*ноффсет*<br/>
Смещение файла, с которого начинается сопоставление. Значение смещения должно быть кратным степени гранулярности выделения памяти в системе.

*дввиевдесиредакцесс*<br/>
Указывает тип доступа к представлению файла и, таким образом, защиту страниц, сопоставленных с файлом. См. раздел *двдесиредакцесс* в [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

В отладочных сборках возникнет ошибка утверждения, если входные параметры являются недопустимыми.

## <a name="catlfilemappingbaseoperator-"></a><a name="operator_eq"></a>Катлфилемаппингбасе::operator=

Задает текущий объект сопоставления файлов для другого объекта сопоставления файлов.

```cpp
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```

### <a name="parameters"></a>Параметры

*Orig*<br/>
Текущий объект сопоставления файлов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на текущий объект.

## <a name="catlfilemappingbaseunmap"></a><a name="unmap"></a>Катлфилемаппингбасе:: отмена сопоставления

Вызовите этот метод, чтобы отменить сопоставление объекта сопоставления файлов.

```cpp
HRESULT Unmap() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK при успешном выполнении или ошибку HRESULT при сбое.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [UnmapViewOfFile](/windows/win32/api/memoryapi/nf-memoryapi-unmapviewoffile) в Windows SDK.

## <a name="see-also"></a>См. также

[Класс Катлфилемаппинг](../../atl/reference/catlfilemapping-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
