---
title: Класс cache_suballoc
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
ms.openlocfilehash: 410cdc7bd45c54c252ce33c7d8e3e2f883ac0eb4
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560625"
---
# <a name="cache_suballoc-class"></a>Класс cache_suballoc

Задает [распределитель блоков](../standard-library/allocators-header.md), который выделяет и освобождает блоки памяти одного размера.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>Параметры

*SZ*\
Число выделяемых элементов в массиве.

## <a name="remarks"></a>Примечания

Шаблон класса cache_suballoc сохраняет свободные блоки памяти в свободном списке с неограниченной длиной, используя `freelist<sizeof(Type), max_unbounded>` и подраспределяет блоки памяти из большего блока, выделенного с помощью **оператора New** , если свободный список пуст.

Каждый блок содержит `Sz * Nelts` байты доступной памяти и данные, необходимые **операторам New** и **Delete** . Выделенные участки памяти никогда не будут освобождены.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[cache_suballoc](#cache_suballoc)|Создает объект типа `cache_suballoc`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[памяти](#allocate)|Выделяет блок памяти.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|

## <a name="requirements"></a>Требования

**Заголовок:**\<allocators>

**Пространство имен:** stdext

## <a name="cache_suballocallocate"></a><a name="allocate"></a> cache_suballoc:: allocate

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

## <a name="cache_suballoccache_suballoc"></a><a name="cache_suballoc"></a> cache_suballoc:: cache_suballoc

Создает объект типа `cache_suballoc`.

```cpp
cache_suballoc();
```

### <a name="remarks"></a>Примечания

## <a name="cache_suballocdeallocate"></a><a name="deallocate"></a> cache_suballoc::d еаллокате

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

## <a name="see-also"></a>См. также раздел

[\<allocators>](../standard-library/allocators-header.md)
