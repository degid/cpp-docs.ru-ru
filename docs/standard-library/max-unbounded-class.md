---
title: Класс max_unbounded
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_unbounded
- allocators/stdext::max_unbounded::allocated
- allocators/stdext::max_unbounded::deallocated
- allocators/stdext::max_unbounded::full
- allocators/stdext::max_unbounded::released
- allocators/stdext::max_unbounded::saved
helpviewer_keywords:
- stdext::max_unbounded
- stdext::max_unbounded [C++], allocated
- stdext::max_unbounded [C++], deallocated
- stdext::max_unbounded [C++], full
- stdext::max_unbounded [C++], released
- stdext::max_unbounded [C++], saved
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
ms.openlocfilehash: e0254563cc60db4a171527735b373c2954a5a9e5
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561964"
---
# <a name="max_unbounded-class"></a>Класс max_unbounded

Описывает объект [max class](../standard-library/allocators-header.md), который не ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class max_unbounded
```

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[allocated](#allocated)|Увеличивает счетчик выделенных блоков памяти.|
|[освобождена](#deallocated)|Уменьшает счетчик выделенных блоков памяти.|
|[full](#full)|Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.|
|[освободил](#released)|Уменьшает количество блоков памяти в свободном списке.|
|[saved](#saved)|Увеличивает количество блоков памяти в свободном списке.|

## <a name="requirements"></a>Требования

**Заголовок:**\<allocators>

**Пространство имен:** stdext

## <a name="max_unboundedallocated"></a><a name="allocated"></a> max_unbounded:: выделено

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

*_Nx*\
Значение приращения.

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Он вызывается после каждого успешного вызова `cache_freelist::allocate` оператором **`new`** . Аргумент *_Nx* — число блоков памяти в блоке, выделенном оператором **`new`** .

## <a name="max_unboundeddeallocated"></a><a name="deallocated"></a> max_unbounded::d еаллокатед

Уменьшает счетчик выделенных блоков памяти.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

*_Nx*\
Значение приращения.

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Эта функция-член вызывается после каждого вызова `cache_freelist::deallocate` оператором **`delete`** . Аргумент *_Nx* — число блоков памяти в блоке, освобожденных оператором **`delete`** .

## <a name="max_unboundedfull"></a><a name="full"></a> max_unbounded:: Full

Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

Функция – член всегда возвращает значение **`false`** .

### <a name="remarks"></a>Примечания

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает **`true`** , `deallocate` помещает блок памяти в свободный список; если возвращается значение false, `deallocate` вызывает оператор **`delete`** для освобождения блока.

## <a name="max_unboundedreleased"></a><a name="released"></a> max_unbounded:: Released

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.

## <a name="max_unboundedsaved"></a><a name="saved"></a> max_unbounded:: сохранен

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Вызывается методом `cache_freelist::deallocate` каждый раз, когда он помещает блок памяти свободного списка.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
