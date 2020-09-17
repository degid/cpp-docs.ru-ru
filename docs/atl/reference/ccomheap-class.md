---
title: Класс CComHeap
ms.date: 11/04/2016
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
ms.openlocfilehash: a38d1147e718870c03af84ec1487e226805b956e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327824"
---
# <a name="ccomheap-class"></a>Класс CComHeap

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с использованием функций распределения памяти COM.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CComHeap : public IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComHeap::Выделение](#allocate)|Вызовите этот метод, чтобы выделить блок памяти.|
|[CComHeap::Бесплатно](#free)|Вызовите этот метод, чтобы освободить блок памяти, выделенный этим менеджером памяти.|
|[CComHeap::GetSize](#getsize)|Вызовите этот метод, чтобы получить выделенный размер блока памяти, выделенный этим менеджером памяти.|
|[CComHeap::Перераспределить](#reallocate)|Вызовите этот метод для перераспределения памяти, выделенной данным диспетчером памяти.|

## <a name="remarks"></a>Примечания

`CComHeap`реализует функции распределения памяти с использованием функций распределения COM, включая [CoTaskMemAlloc,](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc) [CoTaskMemFree,](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) [IMalloc::GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize)и [CoTaskMemRealloc.](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc) Максимальное количество памяти, которое может быть выделено, равно INT_MAX (2147483647) байтов.

## <a name="example"></a>Пример

Смотрите пример [iAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlMemMgr`

`CComHeap`

## <a name="requirements"></a>Требования

**Заголовок:** ATLComMem.h

## <a name="ccomheapallocate"></a><a name="allocate"></a>CComHeap::Выделение

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

Вызов [CComHeap::Free](#free) или [CComHeap::Перераспределите,](#reallocate) чтобы освободить память, выделенную этим методом.

Реализовано с помощью [CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc).

## <a name="ccomheapfree"></a><a name="free"></a>CComHeap::Бесплатно

Вызовите этот метод, чтобы освободить блок памяти, выделенный этим менеджером памяти.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на область памяти, выделенную ранее данным диспетчером памяти. NULL является действительным значением и ничего не делает.

### <a name="remarks"></a>Примечания

Реализовано с помощью [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree).

## <a name="ccomheapgetsize"></a><a name="getsize"></a>CComHeap::GetSize

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

Реализовано с помощью [IMalloc::GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize).

## <a name="ccomheapreallocate"></a><a name="reallocate"></a>CComHeap::Перераспределить

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

Вызов [CComHeap:: Бесплатно,](#free) чтобы освободить память, выделенную этим методом.

Реализовано с помощью [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc).

## <a name="see-also"></a>См. также раздел

[ДинамическийПотребительский образец](../../overview/visual-cpp-samples.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс CWin32 Heap](../../atl/reference/cwin32heap-class.md)<br/>
[Класс CLocalHeap](../../atl/reference/clocalheap-class.md)<br/>
[Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)<br/>
[Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)<br/>
[Класс IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)
