---
title: Класс CLocalHeap
ms.date: 11/04/2016
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
ms.openlocfilehash: 303e3b85ad11c309f862f59d6ec610701c4ef6db
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326761"
---
# <a name="clocalheap-class"></a>Класс CLocalHeap

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с использованием функций локальной кучи Win32.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CLocalHeap : public IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CLocalHeap::Выделение](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|
|[CLocalHeap::Бесплатно](#free)|Вызовите этот метод, чтобы освободить блок памяти, выделенный этим менеджером памяти.|
|[CLocalHeap::GetSize](#getsize)|Вызовите этот метод, чтобы получить выделенный размер блока памяти, выделенный этим менеджером памяти.|
|[CLocalHeap::Перераспределить](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|

## <a name="remarks"></a>Примечания

`CLocalHeap`реализует функции распределения памяти с использованием функций локальной кучи Win32.

> [!NOTE]
> Функции локальной кучи медленнее, чем другие функции управления памятью, и не предоставляют столько функций. Таким образом, новые приложения должны использовать [функции кучи.](/windows/win32/Memory/heap-functions) Они доступны в классе [CWin32Heap.](../../atl/reference/cwin32heap-class.md)

## <a name="example"></a>Пример

Смотрите пример [iAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlMemMgr`

`CLocalHeap`

## <a name="requirements"></a>Требования

**Заголовок:** atlmem.h

## <a name="clocalheapallocate"></a><a name="allocate"></a>CLocalHeap::Выделение

Вызовите этот метод, чтобы выделить блок памяти.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nБайт*<br/>
Запрошенное число байтов в новом блоке памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Вызов [CLocalHeap::Free](#free) или [CLocalHeap::Перераспределите,](#reallocate) чтобы освободить память, выделенную этим методом.

Реализовано с использованием [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc) с парапарам флага LMEM_FIXED.

## <a name="clocalheapfree"></a><a name="free"></a>CLocalHeap::Бесплатно

Вызовите этот метод, чтобы освободить блок памяти, выделенный этим менеджером памяти.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти. NULL является действительным значением и ничего не делает.

### <a name="remarks"></a>Примечания

Реализовано с помощью [LocalFree](/windows/win32/api/winbase/nf-winbase-localfree).

## <a name="clocalheapgetsize"></a><a name="getsize"></a>CLocalHeap::GetSize

Вызовите этот метод, чтобы получить выделенный размер блока памяти, выделенный этим менеджером памяти.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер выделенного блока памяти в байтах.

### <a name="remarks"></a>Примечания

Реализовано с помощью [LocalSize](/windows/win32/api/winbase/nf-winbase-localsize).

## <a name="clocalheapreallocate"></a><a name="reallocate"></a>CLocalHeap::Перераспределить

Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти.

*nБайт*<br/>
Запрошенное число байтов в новом блоке памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Вызов [CLocalHeap:: Бесплатно,](#free) чтобы освободить память, выделенную этим методом.

Реализовано с использованием [LocalReAlloc](/windows/win32/api/winbase/nf-winbase-localrealloc).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CComHeap](../../atl/reference/ccomheap-class.md)<br/>
[Класс CWin32 Heap](../../atl/reference/cwin32heap-class.md)<br/>
[Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)<br/>
[Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)<br/>
[Класс IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)
