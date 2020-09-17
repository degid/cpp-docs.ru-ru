---
title: Класс allocator_base
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::allocator_base
- allocators/stdext::allocators::allocator_base
- allocators/stdext::allocator_base::const_pointer
- allocators/stdext::allocator_base::const_reference
- allocators/stdext::allocator_base::difference_type
- allocators/stdext::allocator_base::pointer
- allocators/stdext::allocator_base::reference
- allocators/stdext::allocator_base::size_type
- allocators/stdext::allocator_base::value_type
- allocators/stdext::allocator_base::_Charalloc
- allocators/stdext::allocator_base::_Chardealloc
- allocators/stdext::allocator_base::address
- allocators/stdext::allocator_base::allocate
- allocators/stdext::allocator_base::construct
- allocators/stdext::allocator_base::deallocate
- allocators/stdext::allocator_base::destroy
- allocators/stdext::allocator_base::max_size
helpviewer_keywords:
- stdext::allocator_base [C++]
- stdext::allocators [C++], allocator_base
- stdext::allocator_base [C++], const_pointer
- stdext::allocator_base [C++], const_reference
- stdext::allocator_base [C++], difference_type
- stdext::allocator_base [C++], pointer
- stdext::allocator_base [C++], reference
- stdext::allocator_base [C++], size_type
- stdext::allocator_base [C++], value_type
- stdext::allocator_base [C++], _Charalloc
- stdext::allocator_base [C++], _Chardealloc
- stdext::allocator_base [C++], address
- stdext::allocator_base [C++], allocate
- stdext::allocator_base [C++], construct
- stdext::allocator_base [C++], deallocate
- stdext::allocator_base [C++], destroy
- stdext::allocator_base [C++], max_size
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
ms.openlocfilehash: f642c21f2b1060dd5adc5c3d98144592c3413777
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562640"
---
# <a name="allocator_base-class"></a>Класс allocator_base

Определяет базовый класс и общие функции, необходимые для создания определяемого пользователем распределителя из фильтра синхронизации.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Type, class Sync>
class allocator_base
```

### <a name="parameters"></a>Параметры

*Type*\
Тип элементов, распределяемых распределителем.

*Nosync*\
Политика синхронизации распределителя: [класс sync_none](sync-none-class.md), [класс sync_per_container](sync-per-container-class.md), [класс sync_per_thread](sync-per-thread-class.md) или [класс sync_shared](sync-shared-class.md).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[allocator_base](#allocator_base)|Создает объект типа `allocator_base`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[const_pointer](#const_pointer)|Тип, предоставляющий постоянный указатель на тип объекта, управляемого распределителем.|
|[const_reference](#const_reference)|Тип, предоставляющий постоянную ссылку на тип объекта, управляемого распределителем.|
|[difference_type](#difference_type)|Тип целого числа со знаком, который может представлять разницу между значениями указателей на тип объекта, управляемого распределителем.|
|[pointer](#pointer)|Тип, предоставляющий указатель на тип объекта, управляемого распределителем.|
|[reference](#reference)|Тип, предоставляющий ссылку на тип объекта, управляемого распределителем.|
|[size_type](#size_type)|Целочисленный тип без знака, который может представлять длину любой последовательности, которую `allocator_base` может выделить объект типа.|
|[value_type](#value_type)|Тип, управляемый распределителем.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[_Charalloc](#charalloc)|Выделяет хранилище для массива типа **`char`** .|
|[_Chardealloc](#chardealloc)|Освобождает хранилище для массива, содержащего элементы типа **`char`** .|
|[address](#address)|Находит адрес объекта, значение которого задано.|
|[памяти](#allocate)|Выделяет блок памяти, достаточный для хранения по крайней мере некоторого указанного числа элементов.|
|[создания](#construct)|Создает определенный тип объекта по указанному адресу, инициализированный с использованием заданного значения.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[завершить](#destroy)|Вызывает деструктор объектов без освобождения памяти, в которой хранился объект.|
|[max_size](#max_size)|Возвращает количество элементов типа *Type*, которые могут быть выделены объектом класса allocator в пределах имеющейся свободной памяти.|

## <a name="requirements"></a>Требования

**Заголовок:**\<allocators>

**Пространство имен:** stdext

## <a name="allocator_base_charalloc"></a><a name="charalloc"></a> allocator_base:: _Charalloc

Выделяет хранилище для массива типа **`char`** .

```cpp
char *_Charalloc(size_type count);
```

### <a name="parameters"></a>Параметры

*count*\
Число выделяемых элементов в массиве.

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Примечания

Эта функция-член используется контейнерами при компиляции с компилятором, которому не удается скомпилировать повторную привязку. Она реализует `_Charalloc` для пользовательского распределителя, возвращая результат вызова функции `allocate` фильтра синхронизации.

## <a name="allocator_base_chardealloc"></a><a name="chardealloc"></a> allocator_base:: _Chardealloc

Освобождает хранилище для массива, содержащего элементы типа **`char`** .

```cpp
void _Chardealloc(void* ptr, size_type count);
```

### <a name="parameters"></a>Параметры

*ptr*\
Указатель на первый объект, который должен быть освобожден из хранилища.

*count*\
Количество объектов для освобождения из хранилища.

### <a name="remarks"></a>Примечания

Эта функция-член используется контейнерами при компиляции с компилятором, которому не удается скомпилировать повторную привязку. Она реализует `_Chardealloc` для пользовательского распределителя путем вызова функции `deallocate` фильтра синхронизации. Указатель указателя мыши должен быть ранее возвращен путем вызова метода `_Charalloc` для объекта распределителя, который сравнивает равно **`*this`** , с выделением объекта массива того же размера и типа. `_Chardealloc` никогда не создает исключений.

## <a name="allocator_baseaddress"></a><a name="address"></a> allocator_base:: Address

Находит адрес объекта, значение которого задано.

```cpp
pointer address(reference val);

const_pointer address(const_reference val);
```

### <a name="parameters"></a>Параметры

*val*\
Константное или неконстантное значение объекта, адрес которого ищется.

### <a name="return-value"></a>Возвращаемое значение

Константный или неконстантный указатель на найденный объект соответственно константного или неконстантного значения.

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем возврата `&val`.

## <a name="allocator_baseallocate"></a><a name="allocate"></a> allocator_base:: allocate

Выделяет блок памяти, достаточный для хранения по крайней мере некоторого указанного числа элементов.

```cpp
template <class Other>
pointer allocate(size_type _Nx, const Other* _Hint = 0);

pointer allocate(size_type _Nx);
```

### <a name="parameters"></a>Параметры

*_Nx*\
Число выделяемых элементов в массиве.

*_Hint*\
Этот параметр не учитывается.

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Примечания

Эта функция-член реализует выделение памяти для пользовательского распределителя путем возврата результата вызова функции `allocate` фильтра синхронизации типа Type `*`, если `_Nx == 1`, в противном случае — путем возврата результата вызова приведения `operator new(_Nx * sizeof(Type))` к типу Type `*`.

## <a name="allocator_baseallocator_base"></a><a name="allocator_base"></a> allocator_base:: allocator_base

Создает объект типа `allocator_base`.

```cpp
allocator_base();

template <class Other>
allocator_base(const allocator_base<Other, Sync>& right);
```

### <a name="parameters"></a>Параметры

*right*\
Объект allocator для копирования.

### <a name="remarks"></a>Примечания

Первый конструктор создает экземпляр [allocator_base](allocator-base-class.md). Второй конструктор создает экземпляр `allocator_base` так, что для любого экземпляра `allocator_base<Type, _Sync>``a`, `allocator_base<Type, Sync>(allocator_base<Other, Sync>(a)) == a`.

## <a name="allocator_baseconst_pointer"></a><a name="const_pointer"></a> allocator_base:: const_pointer

Тип, предоставляющий постоянный указатель на тип объекта, управляемого распределителем.

```cpp
typedef const Type *const_pointer;
```

## <a name="allocator_baseconst_reference"></a><a name="const_reference"></a> allocator_base:: const_reference

Тип, предоставляющий постоянную ссылку на тип объекта, управляемого распределителем.

```cpp
typedef const Type& const_reference;
```

## <a name="allocator_baseconstruct"></a><a name="construct"></a> allocator_base:: конструкция

Создает определенный тип объекта по указанному адресу, инициализированный с использованием заданного значения.

```cpp
void construct(pointer ptr, const Type& val);
```

### <a name="parameters"></a>Параметры

*ptr*\
Указатель места, в котором должен создаваться объект.

*val*\
Значение, с которым создаваемый объект будет инициализирован.

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем вызова `new((void*)ptr Type(val)`.

## <a name="allocator_basedeallocate"></a><a name="deallocate"></a> allocator_base::d еаллокате

Освобождает указанное число объектов из памяти, начиная с заданной позиции.

```cpp
void deallocate(pointer ptr, size_type _Nx);
```

### <a name="parameters"></a>Параметры

*ptr*\
Указатель на первый объект, который должен быть освобожден из хранилища.

*_Nx*\
Количество объектов для освобождения из хранилища.

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем вызова `deallocate(ptr)` в фильтре синхронизации `Sync`, если `_Nx == 1`, в противном случае — путем вызова `operator delete(_Nx * ptr)`.

## <a name="allocator_basedestroy"></a><a name="destroy"></a> allocator_base::d естрой

Вызывает деструктор объектов без освобождения памяти, в которой хранился объект.

```cpp
void destroy(pointer ptr);
```

### <a name="parameters"></a>Параметры

*ptr*\
Указатель, обозначающий адрес уничтожаемого объекта.

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем вызова `ptr->~Type()`.

## <a name="allocator_basedifference_type"></a><a name="difference_type"></a> allocator_base::difference_type

Тип целого числа со знаком, который может представлять разницу между значениями указателей на тип объекта, управляемого распределителем.

```cpp
typedef std::ptrdiff_t difference_type;
```

## <a name="allocator_basemax_size"></a><a name="max_size"></a> allocator_base:: max_size

Возвращает количество элементов типа `Type`, которые могут быть выделены объектом класса в пределах имеющейся свободной памяти.

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов, которые могут быть выделены.

### <a name="remarks"></a>Примечания

Эта функция-член реализуется для пользовательского распределителя путем возврата `(size_t)-1 / sizeof(Type)`, если `0 < (size_t)-1 / sizeof(Type)`в противном случае — `1`.

## <a name="allocator_basepointer"></a><a name="pointer"></a> allocator_base::p оинтер

Тип, предоставляющий указатель на тип объекта, управляемого распределителем.

```cpp
typedef Type *pointer;
```

## <a name="allocator_basereference"></a><a name="reference"></a> allocator_base:: Reference

Тип, предоставляющий ссылку на тип объекта, управляемого распределителем.

```cpp
typedef Type& reference;
```

## <a name="allocator_basesize_type"></a><a name="size_type"></a> allocator_base:: size_type

Целочисленный тип без знака, который может представлять длину любой последовательности, которую `allocator_base` может выделить объект типа.

```cpp
typedef std::size_t size_type;
```

## <a name="allocator_basevalue_type"></a><a name="value_type"></a> allocator_base:: value_type

Тип, управляемый распределителем.

```cpp
typedef Type value_type;
```

## <a name="see-also"></a>См. также

[\<allocators>](allocators-header.md)
