---
title: Класс max_fixed_size
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
ms.openlocfilehash: e62884c83d71b4e9f1902fa4bc7f52f5e0a4e0ee
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561691"
---
# <a name="max_fixed_size-class"></a>Класс max_fixed_size

Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) определенным значением.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>Параметры

*Максимальной*\
Класс max, который определяет максимальное количество элементов для хранения в `freelist`.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[max_fixed_size](#max_fixed_size)|Создает объект типа `max_fixed_size`.|

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

## <a name="max_fixed_sizeallocated"></a><a name="allocated"></a> max_fixed_size:: выделено

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

*_Nx*\
Значение приращения.

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Эта функция-член вызывается после каждого успешного вызова `cache_freelist::allocate` оператором **`new`** . Аргумент *_Nx* — число блоков памяти в блоке, выделенном оператором **`new`** .

## <a name="max_fixed_sizedeallocated"></a><a name="deallocated"></a> max_fixed_size::d еаллокатед

Уменьшает счетчик выделенных блоков памяти.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

*_Nx*\
Значение приращения.

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Эта функция-член вызывается после каждого вызова `cache_freelist::deallocate` оператором **`delete`** . Аргумент *_Nx* — число блоков памяти в блоке, освобожденных оператором **`delete`** .

## <a name="max_fixed_sizefull"></a><a name="full"></a> max_fixed_size:: Full

Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

**`true`**`Max <= _Nblocks`в противном случае — значение **`false`** .

### <a name="remarks"></a>Примечания

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает **`true`** , `deallocate` помещает блок памяти в свободный список; если возвращается значение false, `deallocate` вызывает оператор **`delete`** для освобождения блока.

## <a name="max_fixed_sizemax_fixed_size"></a><a name="max_fixed_size"></a> max_fixed_size:: max_fixed_size

Создает объект типа `max_fixed_size`.

```cpp
max_fixed_size();
```

### <a name="remarks"></a>Примечания

Конструктор инициализирует сохраненное значение `_Nblocks` нулем.

## <a name="max_fixed_sizereleased"></a><a name="released"></a> max_fixed_size:: Released

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Примечания

Уменьшает хранимое значение `_Nblocks`. `released`Функция-член текущего [класса Max](../standard-library/allocators-header.md) вызывается при `cache_freelist::allocate` каждом удалении блока памяти из свободного списка.

## <a name="max_fixed_sizesaved"></a><a name="saved"></a> max_fixed_size:: сохранен

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Примечания

Эта функция-член увеличивает хранимое значение `_Nblocks`. Она вызывается `cache_freelist::deallocate` каждый раз при помещении блока памяти в свободный список.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
