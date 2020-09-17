---
title: Класс max_none
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
ms.openlocfilehash: 41ada338d9b8546202ecd49ff975f9642f190ba0
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560547"
---
# <a name="max_none-class"></a>Класс max_none

Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) нулем.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>Параметры

*Максимальной*\
Класс max, который определяет максимальное количество элементов для хранения в `freelist`.

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

## <a name="max_noneallocated"></a><a name="allocated"></a> max_none:: выделено

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

*_Nx*\
Значение приращения.

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Он вызывается после каждого успешного вызова `cache_freelist::allocate` оператором **`new`** . Аргумент *_Nx* — число блоков памяти в блоке, выделенном оператором **`new`** .

## <a name="max_nonedeallocated"></a><a name="deallocated"></a> max_none::d еаллокатед

Уменьшает счетчик выделенных блоков памяти.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

*_Nx*\
Значение приращения.

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Эта функция-член вызывается после каждого вызова `cache_freelist::deallocate` оператором **`delete`** . Аргумент *_Nx* — число блоков памяти в блоке, освобожденных оператором **`delete`** .

## <a name="max_nonefull"></a><a name="full"></a> max_none:: Full

Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция – член всегда возвращает значение **`true`** .

### <a name="remarks"></a>Примечания

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает **`true`** , `deallocate` блок памяти помещается в свободный список; если он возвращает **`false`** , `deallocate` вызывает оператор для освобождения **`delete`** блока.

## <a name="max_nonereleased"></a><a name="released"></a> max_none:: Released

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.

## <a name="max_nonesaved"></a><a name="saved"></a> max_none:: сохранен

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Вызывается методом `cache_freelist::deallocate` каждый раз, когда он помещает блок памяти свободного списка.

## <a name="see-also"></a>См. также раздел

[\<allocators>](../standard-library/allocators-header.md)
