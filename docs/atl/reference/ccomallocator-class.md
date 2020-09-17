---
title: Класс CComAllocator
ms.date: 11/04/2016
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
ms.openlocfilehash: 165cdb8b0b16a4872214f4556c26ee141e6a4d89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321142"
---
# <a name="ccomallocator-class"></a>Класс CComAllocator

Этот класс предоставляет методы управления памятью с помощью процедур com памяти.

## <a name="syntax"></a>Синтаксис

```
class CComAllocator
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComAllocator::Выделение](#allocate)|Вызовите этот статический метод для выделения памяти.|
|[CComAllocator::Бесплатно](#free)|Вызовите этот статический метод, чтобы освободить выделенную память.|
|[CComAllocator:Перераспределить](#reallocate)|Вызовите этот статический метод для перераспределения памяти.|

## <a name="remarks"></a>Примечания

Этот класс используется [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) для обеспечения процедур распределения памяти COM. Класс аналогов, [CCRTAllocator,](../../atl/reference/ccrtallocator-class.md)предоставляет те же методы, используя процедуры CRT.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomallocatorallocate"></a><a name="allocate"></a>CComAllocator::Выделение

Вызовите эту статическую функция для выделения памяти.

```
static void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nБайт*<br/>
Количество байтов, которые необходимо выделить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель void на выделенное пространство или значение NULL, если памяти недостаточно.

### <a name="remarks"></a>Примечания

Выделяет память. Более подробную информацию можно узнать [в CoTaskMemAlloc.](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)

## <a name="ccomallocatorfree"></a><a name="free"></a>CComAllocator::Бесплатно

Вызовите эту статическую функцию, чтобы освободить выделенную память.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на выделенную область памяти.

### <a name="remarks"></a>Примечания

Освобождает выделенную память. Более подробную информацию можно узнать [в CoTaskMemFree.](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)

## <a name="ccomallocatorreallocate"></a><a name="reallocate"></a>CComAllocator:Перераспределить

Вызовите эту статическую функцию для повторного выделения памяти.

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на выделенную область памяти.

*nБайт*<br/>
Количество байтов, которые необходимо выделить повторно.

### <a name="return-value"></a>Возвращаемое значение

Возвращает пустоту указателя в выделенное пространство или NULL, если не хватает памяти

### <a name="remarks"></a>Примечания

Изменяет объем выделенной памяти. Более подробную информацию можно узнать [в CoTaskMemRealloc.](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)

## <a name="see-also"></a>См. также раздел

[Класс CComHeapPtr](../../atl/reference/ccomheapptr-class.md)<br/>
[Класс CCRTAllocator](../../atl/reference/ccrtallocator-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
