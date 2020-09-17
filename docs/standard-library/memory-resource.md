---
title: '&lt;memory_resource&gt;'
ms.date: 04/04/2019
f1_keywords:
- <memory_resource>
helpviewer_keywords:
- memory_resource header
ms.openlocfilehash: de88feb691d0ec1bc9bf9b9dc2bc40cbc31a1cfe
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831051"
---
# <a name="ltmemory_resourcegt"></a>&lt;memory_resource&gt;

Определяет шаблон класса контейнера memory_resource и его вспомогательные шаблоны.

## <a name="syntax"></a>Синтаксис

```cpp
#include <memory_resource>
```

## <a name="members"></a>Участники

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator!=](../standard-library/memory-resource-operators.md#op_neq)|Проверяет, не равен ли объект memory_resource в левой части оператора memory_resource объекту справа.|
|[operator==](../standard-library/memory-resource-operators.md#op_eq_eq)|Проверяет, равен ли объект memory_resource слева от оператора объекту memory_resource в правой части.|

### <a name="specialized-template-functions"></a>Специализированные функции шаблонов

|Имя|Описание|
|-|-|
|[polymorphic_allocator](../standard-library/memory-resource-functions.md#poly_alloc)||

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[get_default_resource](../standard-library/memory-resource-functions.md#get_default)||
|[new_delete_resource](../standard-library/memory-resource-functions.md#new_delete)||
|[null_memory_resource](../standard-library/memory-resource-functions.md#null_memory)||
|[set_default_resource](../standard-library/memory-resource-functions.md#set_default)||

### <a name="classes-and-structs"></a>Классы и структуры

|Имя|Описание|
|-|-|
|[Класс memory_resource](../standard-library/memory-resource-class.md)||
|[Класс monotonic_buffer_resource](../standard-library/monotonic-buffer-resource-class.md)||
|[Структура pool_options](../standard-library/pool-options-structure.md)||
|[Класс synchronized_pool_resource](../standard-library/synchronized-pool-resource-class.md)||
|[Класс unsynchronized_pool_resource](../standard-library/unsynchronized-pool-resource-class.md)||

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
