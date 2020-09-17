---
title: Класс CCRTHeap
ms.date: 11/04/2016
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
ms.openlocfilehash: caf5508079332689c2fff42f130951375dc35512
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327164"
---
# <a name="ccrtheap-class"></a>Класс CCRTHeap

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с использованием функций CRT кучи.

## <a name="syntax"></a>Синтаксис

```
class CCRTHeap : public IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCRTHeap::Выделение](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|
|[CCRTHeap::Бесплатно](#free)|Вызовите этот метод, чтобы освободить блок памяти, выделенный этим менеджером памяти.|
|[CCRTHeap::GetSize](#getsize)|Вызовите этот метод, чтобы получить выделенный размер блока памяти, выделенный этим менеджером памяти.|
|[CCRTHeap::Перераспределить](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|

## <a name="remarks"></a>Примечания

`CCRTHeap`реализует функции распределения памяти с использованием функций CRT кучи, в том числе [malloc](../../c-runtime-library/reference/malloc.md), [бесплатно,](../../c-runtime-library/reference/free.md) [realloc,](../../c-runtime-library/reference/realloc.md)и [_msize.](../../c-runtime-library/reference/msize.md)

## <a name="example"></a>Пример

Смотрите пример [iAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlMemMgr`

`CCRTHeap`

## <a name="requirements"></a>Требования

**Заголовок:** atlmem.h

## <a name="ccrtheapallocate"></a><a name="allocate"></a>CCRTHeap::Выделение

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

Вызов [CCRTHeap::Free](#free) или [CCRTHeap::Перераспределите,](#reallocate) чтобы освободить память, выделенную этим методом.

Реализовано с помощью [malloc](../../c-runtime-library/reference/malloc.md).

## <a name="ccrtheapfree"></a><a name="free"></a>CCRTHeap::Бесплатно

Вызовите этот метод, чтобы освободить блок памяти, выделенный этим менеджером памяти.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти. NULL является действительным значением и ничего не делает.

### <a name="remarks"></a>Примечания

Реализовано с помощью [бесплатного](../../c-runtime-library/reference/free.md).

## <a name="ccrtheapgetsize"></a><a name="getsize"></a>CCRTHeap::GetSize

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

Реализовано с использованием [_msize](../../c-runtime-library/reference/msize.md).

## <a name="ccrtheapreallocate"></a><a name="reallocate"></a>CCRTHeap::Перераспределить

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

Вызов [CCRTHeap:: Бесплатно](#free) освободить память, выделенную этим методом. Реализовано с помощью [realloc](../../c-runtime-library/reference/realloc.md).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CComHeap](../../atl/reference/ccomheap-class.md)<br/>
[Класс CWin32 Heap](../../atl/reference/cwin32heap-class.md)<br/>
[Класс CLocalHeap](../../atl/reference/clocalheap-class.md)<br/>
[Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)<br/>
[Класс IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)
