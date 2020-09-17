---
title: Класс CWin32 Heap
ms.date: 11/04/2016
f1_keywords:
- CWin32Heap
- ATLMEM/ATL::CWin32Heap
- ATLMEM/ATL::CWin32Heap::CWin32Heap
- ATLMEM/ATL::CWin32Heap::Allocate
- ATLMEM/ATL::CWin32Heap::Attach
- ATLMEM/ATL::CWin32Heap::Detach
- ATLMEM/ATL::CWin32Heap::Free
- ATLMEM/ATL::CWin32Heap::GetSize
- ATLMEM/ATL::CWin32Heap::Reallocate
- ATLMEM/ATL::CWin32Heap::m_bOwnHeap
- ATLMEM/ATL::CWin32Heap::m_hHeap
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
ms.openlocfilehash: 2d79de308b1afb3059cf04ad40b63b6e603073c8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746032"
---
# <a name="cwin32heap-class"></a>Класс CWin32 Heap

Этот класс реализует [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) с использованием функций распределения кучи Win32.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWin32 Heap::CWin32 Heap](#cwin32heap)|Конструктор.|
|[CWin32 Heap:: CWin32 Heap](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWin32 Heap::Выделение](#allocate)|Выделяет блок памяти из кучи объекта.|
|[CWin32 Heap::Attach](#attach)|Прикрепляет объект кучи к существующей куче.|
|[CWin32Хэп: :Dэтахэт](#detach)|Отсоединяет объект из существующей кучи.|
|[CWin32 Heap::Бесплатно](#free)|Освобождает память, ранее выделенную из кучи.|
|[CWin32 Хип::GetSize](#getsize)|Возвращает размер блока памяти, выделенного из объекта кучи.|
|[CWin32Heap::Перераспределить](#reallocate)|Повторно выделяет блок памяти из кучи объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CWin32 Heap:::m_bOwnHeap](#m_bownheap)|Флаг, используемый для определения текущего владения ручкой кучи.|
|[CWin32 Heap::m_hHeap](#m_hheap)|Обработка к объекту кучи.|

## <a name="remarks"></a>Примечания

`CWin32Heap`реализует методы распределения памяти с использованием функций распределения кучи Win32, включая [HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc) и [HeapFree.](/windows/win32/api/heapapi/nf-heapapi-heapfree) В отличие от `CWin32Heap` других классов Кучи, требуется допустимая ручка кучи, которая должна быть предоставлена до выделения памяти: другие классы по умолчанию используют процессную кучу. Ручка может быть поставлена конструктору или методу [CWin32Heap::Attach.](#attach) Более подробную информацию можно узнать из метода [CWin32Heap::CWin32Heap.](#cwin32heap)

## <a name="example"></a>Пример

Смотрите пример [iAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>Требования

**Заголовок:** atlmem.h

## <a name="cwin32heapallocate"></a><a name="allocate"></a>CWin32 Heap::Выделение

Выделяет блок памяти из кучи объекта.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*nБайт*<br/>
Запрошенное число байтов в новом блоке памяти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Вызов [CWin32Heap::Free](#free) или [CWin32Heap::Перераспределите,](#reallocate) чтобы освободить память, выделенную этим методом.

Реализовано с помощью [HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc).

## <a name="cwin32heapattach"></a><a name="attach"></a>CWin32 Heap::Attach

Прикрепляет объект кучи к существующей куче.

```cpp
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>Параметры

*hHeap*<br/>
Существующая ручка кучи.

*bTakeOwnership*<br/>
Флаг, указывающий, должен ли `CWin32Heap` объект взять в собственность ресурсы кучи.

### <a name="remarks"></a>Примечания

Если *bTakeOwnership* является `CWin32Heap` правдой, объект несет ответственность за удаляние ручки кучи.

## <a name="cwin32heapcwin32heap"></a><a name="cwin32heap"></a>CWin32 Heap::CWin32 Heap

Конструктор.

```
CWin32Heap() throw();
CWin32Heap( HANDLE  hHeap) throw();
CWin32Heap(
    DWORD  dwFlags,
    size_t nInitialSize,
    size_t nMaxSize = 0);
```

### <a name="parameters"></a>Параметры

*hHeap*<br/>
Существующий объект кучи.

*dwFlags*<br/>
Флаги, используемые при создании кучи.

*nInitialSize*<br/>
Начальный размер кучи.

*nMaxSize*<br/>
Максимальный размер кучи.

### <a name="remarks"></a>Примечания

Перед выделением памяти необходимо предоставить объект `CWin32Heap` с действительным дескриптором кучи. Для этого проще всего использовать кучу процесса:

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

Также можно указать в конструкторе дескриптор существующей кучи; в этом случае новый объект не становится владельцем кучи. После удаления объекта `CWin32Heap` исходный дескриптор кучи будет по-прежнему действителен.

Существующая куча также может быть прикреплена к новому объекту с помощью [CWin32Heap::Attach](#attach).

Если куча требуется в ситуации, когда все операции выполняются из единственного потока, лучше всего создать объект следующим образом:

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

Параметр HEAP_NO_SERIALIZE указывает, что когда функции кучи выделяют и освобождают память, взаимное исключение не используется (с соответствующим увеличением производительности).

Третий параметр по умолчанию равен 0, что обеспечивает рост размера кучи по мере необходимости. См [HeapCreate](/windows/win32/api/heapapi/nf-heapapi-heapcreate) для объяснения размеров памяти и флагов.

## <a name="cwin32heapcwin32heap"></a><a name="dtor"></a>CWin32 Heap:: CWin32 Heap

Деструктор

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>Примечания

Уничтожает ручку `CWin32Heap` кучи, если объект имеет право собственности на кучу.

## <a name="cwin32heapdetach"></a><a name="detach"></a>CWin32Хэп: :Dэтахэт

Отсоединяет объект из существующей кучи.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку в кучу, к которой объект ранее был прикреплен.

## <a name="cwin32heapfree"></a><a name="free"></a>CWin32 Heap::Бесплатно

Освобождает память, ранее выделенную из кучи [CWin32Heap:::Allocate](#allocate) или [CWin32Heap::Reallocate](#reallocate).

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на блок памяти, чтобы освободить. NULL является действительным значением и ничего не делает.

## <a name="cwin32heapgetsize"></a><a name="getsize"></a>CWin32 Хип::GetSize

Возвращает размер блока памяти, выделенного из объекта кучи.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на блок памяти, размер которого получит метод. Это указатель вернулся [CWin32Heap::Распределение](#allocate) или [CWin32Heap::Reallocate](#reallocate).

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер в байтах выделенного блока памяти.

## <a name="cwin32heapm_bownheap"></a><a name="m_bownheap"></a>CWin32 Heap:::m_bOwnHeap

Флаг, используемый для определения текущего владения ручкой кучи, хранящейся в [m_hHeap.](#m_hheap)

```
bool m_bOwnHeap;
```

## <a name="cwin32heapm_hheap"></a><a name="m_hheap"></a>CWin32 Heap::m_hHeap

Обработка к объекту кучи.

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>Примечания

Переменная, используемая для хранения ручки к объекту кучи.

## <a name="cwin32heapreallocate"></a><a name="reallocate"></a>CWin32Heap::Перераспределить

Повторно выделяет блок памяти из кучи объекта.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель на блок памяти для перераспределения.

*nБайт*<br/>
Новый размер выделенного блока в байтах. Блок можно увеличить или уменьшить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на начало выделенного блока памяти.

### <a name="remarks"></a>Примечания

Если *p* является NULL, предполагается, что блок памяти еще не выделен и [CWin32Heap::Выделение](#allocate) называется, с аргументом *nBytes*.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)<br/>
[Класс IAtlMemgr](../../atl/reference/iatlmemmgr-class.md)<br/>
[Класс CLocalHeap](../../atl/reference/clocalheap-class.md)<br/>
[Класс CGlobalHeap](../../atl/reference/cglobalheap-class.md)<br/>
[Класс CCRTHeap](../../atl/reference/ccrtheap-class.md)<br/>
[Класс CComHeap](../../atl/reference/ccomheap-class.md)
