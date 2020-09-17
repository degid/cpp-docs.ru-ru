---
title: Класс sync_none
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
helpviewer_keywords:
- stdext::sync_none
- stdext::sync_none [C++], allocate
- stdext::sync_none [C++], deallocate
- stdext::sync_none [C++], equals
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
ms.openlocfilehash: dac4dc1182de32af485d37a00ff96370ea8d8943
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562120"
---
# <a name="sync_none-class"></a>Класс sync_none

Описывает [фильтр синхронизации](../standard-library/allocators-header.md) , который не обеспечивает синхронизацию.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class sync_none
```

### <a name="parameters"></a>Параметры

`Cache`\
Тип кэша, связанный с фильтром синхронизации. Это может быть [`cache_chunklist`](../standard-library/cache-chunklist-class.md) , [`cache_freelist`](../standard-library/cache-freelist-class.md) или [`cache_suballoc`](../standard-library/cache-suballoc-class.md) .

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[памяти](#allocate)|Выделяет блок памяти.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:**\<allocators>

**Пространство имен:** stdext

## <a name="sync_noneallocate"></a><a name="allocate"></a> sync_none:: allocate

Выделяет блок памяти.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Параметры

*count*\
Число выделяемых элементов в массиве.

### <a name="remarks"></a>Примечания

Функция-член возвращает `cache.allocate(count)`, где `cache` — объект кэша.

## <a name="sync_nonedeallocate"></a><a name="deallocate"></a> sync_none::d еаллокате

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

Эта функция-член вызывает `cache.deallocate(ptr, count)`, где `cache` представляет объект кэша.

## <a name="sync_noneequals"></a><a name="equals"></a> sync_none:: Equals

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Параметры

*Мбайта*\
Объект кэша фильтра синхронизации.

*Other*\
Объект кэша для сравнения на равенство.

### <a name="return-value"></a>Возвращаемое значение

Функция – член всегда возвращает значение **`true`** .

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
