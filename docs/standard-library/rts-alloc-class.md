---
title: Класс rts_alloc
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
helpviewer_keywords:
- stdext::rts_alloc
- stdext::rts_alloc [C++], allocate
- stdext::rts_alloc [C++], deallocate
- stdext::rts_alloc [C++], equals
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
ms.openlocfilehash: 04a6578c7abd07ff84f4c0a5cee68cfd7ec8ef04
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560560"
---
# <a name="rts_alloc-class"></a>Класс rts_alloc

Шаблон класса rts_alloc описывает [Фильтр](../standard-library/allocators-header.md) , содержащий массив экземпляров кэша, и определяет, какой экземпляр следует использовать для выделения и освобождения во время выполнения, а не во времени компиляции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>Параметры

*Мбайта*\
Тип экземпляров кэша, содержащихся в массиве. Это может быть [`cache_chunklist`](../standard-library/cache-chunklist-class.md) , [`cache_freelist`](../standard-library/cache-freelist-class.md) или [`cache_suballoc`](../standard-library/cache-suballoc-class.md) .

## <a name="remarks"></a>Примечания

Этот шаблон класса содержит несколько экземпляров распределителя блоков и определяет, какой экземпляр следует использовать для выделения или освобождения в среде выполнения, а не во время компиляции. Он используется с компиляторами, которые не могут скомпилировать повторную привязку.

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[памяти](#allocate)|Выделяет блок памяти.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:**\<allocators>

**Пространство имен:** stdext

## <a name="rts_allocallocate"></a><a name="allocate"></a> rts_alloc:: allocate

Выделяет блок памяти.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Параметры

*count*\
Число выделяемых элементов в массиве.

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Примечания

Функция-член возвращает `caches[_IDX].allocate(count)` , где индекс `_IDX` определяется запрошенным *количеством*размеров блоков, или, если *Count* слишком велик, возвращается значение `operator new(count)` . `cache`, представляющий объект кэша.

## <a name="rts_allocdeallocate"></a><a name="deallocate"></a> rts_alloc::d еаллокате

Освобождает указанное число объектов из памяти, начиная с заданной позиции.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Параметры

*ptr*\
Указатель на первый объект, который должен быть освобожден из хранилища.

*count*\
Количество объектов для освобождения из хранилища.

### <a name="remarks"></a>Примечания

Функция-член вызывает `caches[_IDX].deallocate(ptr, count)` , где индекс `_IDX` определяется запрошенным *количеством*размеров блока, или, если *Count* слишком велик, возвращается значение `operator delete(ptr)` .

## <a name="rts_allocequals"></a><a name="equals"></a> rts_alloc:: Equals

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync<_Cache>& _Other) const;
```

### <a name="parameters"></a>Параметры

*_Cache*\
Объект кэша, связанный с фильтром.

*_Other*\
Объект кэша для сравнения на равенство.

### <a name="remarks"></a>Примечания

**`true`** значение, если результат `caches[0].equals(other.caches[0])` ; в противном случае — **`false`** . `caches` представляет массив объектов кэша.

## <a name="see-also"></a>См. также раздел

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)\
[\<allocators>](../standard-library/allocators-header.md)
