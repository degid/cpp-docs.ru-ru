---
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: b1eeba2fced21f5a38799db7fc4af259e03bc266
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841848"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

Определяет шаблон `tuple`, экземпляры которого содержат объекты различных типов.

## <a name="requirements"></a>Требования

**Заголовок:**\<tuple>

**Пространство имен:** std

## <a name="members"></a>Элементы

### <a name="classes-and-structs"></a>Классы и структуры

|Имя|Описание|
|-|-|
|[Класс Tuple](../standard-library/tuple-class.md)|Создает последовательность элементов фиксированной длины.|
|[Класс tuple_element](../standard-library/tuple-element-class-tuple.md)|Заключает в оболочку тип элемента `tuple`.|
|[Класс tuple_size](../standard-library/tuple-size-class-tuple.md)|Создает оболочку для счетчика элементов `tuple` .|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||

### <a name="objects"></a>Объекты

|Имя|Описание|
|-|-|
|[tuple_element_t](../standard-library/tuple-functions.md#tuple_element_t)||
|[tuple_size_v](../standard-library/tuple-functions.md#tuple_size_v)||

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|Сравнение `tuple` объектов, равное.|
|[operator!=](../standard-library/tuple-operators.md#op_neq)|Сравнение `tuple` объектов, не равно.|
|[operator<](../standard-library/tuple-operators.md#op_lt)|Сравнение `tuple` объектов, меньше.|
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|Сравнение `tuple` объектов, меньше или равно.|
|[operator>](../standard-library/tuple-operators.md#op_gt)|Сравнение `tuple` объектов, большее, чем.|
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|Сравнение `tuple` объектов, больше или равно.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[apply](../standard-library/tuple-functions.md#apply)|Вызывает функцию с кортежем.|
|[forward_as_tuple](../standard-library/tuple-functions.md#forward)|Конструирует кортеж ссылок.|
|[get](../standard-library/tuple-functions.md#get)|Возвращает элемент из объекта `tuple`.|
|[make_from_tuple](../standard-library/tuple-functions.md#make_from_tuple)|Краткая форма для создания `tuple` .|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|Создает `tuple` из значений элементов.|
|[swap](../standard-library/tuple-functions.md#swap)||
|[tie](../standard-library/tuple-functions.md#tie)|Создает `tuple` из ссылок на элементы.|
|[tuple_cat](../standard-library/tuple-functions.md#tuple_cat)|Конструирует объект кортежа с диапазоном элементов типа.|

## <a name="see-also"></a>См. также раздел

[\<array>](../standard-library/array.md)
