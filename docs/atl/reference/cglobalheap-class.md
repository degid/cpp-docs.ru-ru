---
title: Класс CGlobalHeap
ms.date: 11/04/2016
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
helpviewer_keywords:
- CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
ms.openlocfilehash: d596fd51c1bf33f606c1f14c9e8dbd2f1926c7f8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326945"
---
# <a name="cglobalheap-class"></a>Класс CGlobalHeap

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с использованием функций глобальной кучи Win32.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CGlobalHeap : public IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CGlobalHeap::Выделение](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|
|[CGlobal Heap::Бесплатно](#free)|Вызовите этот метод, чтобы освободить блок памяти, выделенный этим менеджером памяти.|
|[CGlobal Heap::GetSize](#getsize)|Вызовите этот метод, чтобы получить выделенный размер блока памяти, выделенный этим менеджером памяти.|
|[CGlobalHeap::Перераспределить](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|

## <a name="remarks"></a>Примечания

`CGlobalHeap`реализует функции распределения памяти с использованием функций глобальной кучи Win32.

> [!NOTE]
> Функции глобальной кучи медленнее, чем другие функции управления памятью, и не предоставляют столько функций. Таким образом, новые приложения должны использовать [функции кучи.](/windows/win32/Memory/heap-functions) Они доступны в классе [CWin32Heap.](../../atl/reference/cwin32heap-class.md) Глобальные функции по-прежнему используются функциями DDE и буфера обмена.

## <a name="example"></a>Пример

Смотрите пример [iAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlMemMgr`

`CGlobalHeap`

## <a name="requirements"></a>Требования

**Заголовок:** atlmem.h

## <a name="cglobalheapallocate"></a><a name="allocate"></a>CGlobalHeap::Выделение

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

Вызов [CGlobalHeap::Free](#free) или [CGlobalHeap::Перераспределить,](#reallocate) чтобы освободить память, выделенную этим методом.

Реализовано с использованием [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc) с парапарам флага GMEM_FIXED.

## <a name="cglobalheapfree"></a><a name="free"></a>CGlobal Heap::Бесплатно

Вызовите этот метод, чтобы освободить блок памяти, выделенный этим менеджером памяти.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти. NULL является действительным значением и ничего не делает.

### <a name="remarks"></a>Примечания

Реализовано с помощью [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree).

## <a name="cglobalheapgetsize"></a><a name="getsize"></a>CGlobal Heap::GetSize

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

Реализовано с помощью [GlobalSize](/windows/win32/api/winbase/nf-winbase-globalsize).

## <a name="cglobalheapreallocate"></a><a name="reallocate"></a>CGlobalHeap::Перераспределить

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

Вызов [CGlobalHeap::Бесплатно,](#free) чтобы освободить память, выделенную этим методом.

Реализовано с использованием [GlobalReAlloc](/windows/win32/api/winbase/nf-winbase-globalrealloc).

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CComHeap](../../atl/reference/ccomheap-class.md)<br/>
[Класс CWin32 Heap](../../atl/reference/cwin32heap-class.md)<br/>
[Класс CLocalHeap](../../atl/reference/clocalheap-class.md)<br/>
[Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)<br/>
[Класс IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)
