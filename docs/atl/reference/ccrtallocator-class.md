---
title: Класс CCRTAllocator
ms.date: 11/04/2016
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
ms.openlocfilehash: 2f6bae3818fa0f1639e0e3cee4e09121580da768
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327172"
---
# <a name="ccrtallocator-class"></a>Класс CCRTAllocator

Этот класс предоставляет методы управления памятью с помощью процедур CRT памяти.

## <a name="syntax"></a>Синтаксис

```
class ATL::CCRTAllocator
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCRTAllocator::Выделение](#allocate)|(Статик) Вызовите этот метод для выделения памяти.|
|[CCRTAllocator::Бесплатно](#free)|(Статик) Вызовите этот метод, чтобы освободить память.|
|[CCRTAllocator::Перераспределить](#reallocate)|(Статик) Вызовите этот метод для перераспределения памяти.|

## <a name="remarks"></a>Примечания

Этот класс используется [CHeapPtr](../../atl/reference/cheapptr-class.md) для обеспечения процедур распределения памяти CRT. Аналог класса, [CComAllocator](../../atl/reference/ccomallocator-class.md), предоставляет те же методы, используя COM процедур.

## <a name="requirements"></a>Требования

**Заголовок:** atlcore.h

## <a name="ccrtallocatorallocate"></a><a name="allocate"></a>CCRTAllocator::Выделение

Вызовите эту статическую функция для выделения памяти.

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nБайт*<br/>
Количество байтов, которые необходимо выделить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель void на выделенное пространство или значение NULL, если памяти недостаточно.

### <a name="remarks"></a>Примечания

Выделяет память. Подробнее о [малле.](../../c-runtime-library/reference/malloc.md)

## <a name="ccrtallocatorfree"></a><a name="free"></a>CCRTAllocator::Бесплатно

Вызовите эту статическую функцию для свободной памяти.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на выделенную область памяти.

### <a name="remarks"></a>Примечания

Освобождает выделенную память. Смотрите [бесплатно](../../c-runtime-library/reference/free.md) для получения более подробной информации.

## <a name="ccrtallocatorreallocate"></a><a name="reallocate"></a>CCRTAllocator::Перераспределить

Вызовите эту статическую функцию для повторного выделения памяти.

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на выделенную область памяти.

*nБайт*<br/>
Количество байтов, которые необходимо выделить повторно.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель void на выделенное пространство или значение NULL, если памяти недостаточно.

### <a name="remarks"></a>Примечания

Изменяет объем выделенной памяти. Более подробную информацию можно узнать в [realloc.](../../c-runtime-library/reference/realloc.md)

## <a name="see-also"></a>См. также раздел

[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Класс CComAllocator](../../atl/reference/ccomallocator-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
