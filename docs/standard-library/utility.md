---
title: '&lt;utility&gt;'
ms.date: 11/04/2016
f1_keywords:
- <utility>
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
ms.openlocfilehash: 1beade28ceec0f1552def4bc70c2e95e6b2aa24d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215443"
---
# <a name="ltutilitygt"></a>&lt;utility&gt;

Определяет типы, функции и операторы стандартной библиотеки C++, которые помогают создавать пары объектов и управлять ими, что удобно, когда два объекта должны рассматриваться как один.

## <a name="requirements"></a>Требования

**Заголовок:**\<utility>

**Пространство имен:** std

## <a name="remarks"></a>Примечания

Пары широко используются в стандартной библиотеке C++. Они используются как аргументы и возвращаемые значения для различных функций и как типы элементов для контейнеров, таких как [класс map](../standard-library/map-class.md) и [класс multimap](../standard-library/multimap-class.md). \<utility>Заголовок автоматически включается \<map> для помощи в управлении элементами типа пары "ключ — значение".

> [!NOTE]
> \<utility>Заголовок использует инструкцию `#include <initializer_list>` . Он также ссылается `class tuple` как определенный в \<tuple> .

## <a name="members"></a>Элементы

### <a name="classes"></a>Классы

|Тип|Description|
|-|-|
|[chars_format](../standard-library/chars-format-class.md)|Формат с плавающей запятой для преобразования примитивных чисел.|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Класс, который заключает в оболочку тип элемента `pair`.|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Класс, который заключает в оболочку счетчик элементов `pair`.|

### <a name="objects"></a>Объекты

|Шаблон|Описание|
|-|-|
|[index_sequence](../standard-library/utility-functions.md#index_sequence)|Шаблон псевдонима, определенный для общего случая `T` , где —`std::size_t`  |
|[index_sequence_for](../standard-library/utility-functions.md#index_sequence_for)|Шаблон вспомогательного псевдонима для преобразования любого пакета параметров типа в последовательность индекса той же длины|
|[make_index_sequence](../standard-library/utility-functions.md#make_index_sequence)| Шаблон вспомогательного псевдонима для упрощения создания `std::index_sequence` типа. |
|[make_integer_sequence](../standard-library/utility-functions.md#make_integer_sequence)|Шаблон вспомогательного псевдонима для упрощения создания `std::integer_sequence` типа.|

### <a name="functions"></a>Функции

|Компонент|Описание|
|-|-|
|[as_const](../standard-library/utility-functions.md#asconst)|Возвращает тип.|
|[деклвал](../standard-library/utility-functions.md#declval)|Вычисление сокращенного выражения.|
|[сообщения](../standard-library/utility-functions.md#exchange)|Присваивает новое значение объекту и возвращает его старое значение.|
|[переадресован](../standard-library/utility-functions.md#forward)|Не позволяет изменить ссылочный тип (`lvalue` или `rvalue`) аргумента при точной пересылке.|
|[from_chars](../standard-library/utility-functions.md#from_chars)||
|[get](../standard-library/utility-functions.md#get)|Функция, которая возвращает элемент из объекта `pair`.|
|[make_pair](../standard-library/utility-functions.md#make_pair)|Вспомогательная функция шаблона, которую можно использовать для построения объектов типа `pair` на основе типов данных, переданных в качестве параметров.|
|[move](../standard-library/utility-functions.md#move)|Возвращает переданный аргумент в виде ссылки `rvalue`.|
|[move_if_noexcept](../standard-library/utility-functions.md#moveif)||
|[swap](../standard-library/utility-functions.md#swap)|Меняет местами элементы двух объектов `pair`.|
|[to_chars](../standard-library/utility-functions.md#to_chars)|Преобразует значение в символьную строку.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](../standard-library/utility-operators.md#op_neq)|Проверяет неравенство объекта pair слева от оператора объекту pair справа от оператора.|
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|Проверяет равенство объекта pair слева от оператора объекту pair справа от оператора.|
|[оператор\<](../standard-library/utility-operators.md#op_lt)|Проверяет, меньше ли объект pair слева от оператора объекта pair справа от оператора.|
|[оператор\<=](../standard-library/utility-operators.md#op_gt_eq)|Проверяет, что объект pair слева от оператора меньше или равен объекту pair справа от оператора.|
|[operator>](../standard-library/utility-operators.md#op_gt)|Проверяет, больше ли объект pair слева от оператора объекта pair справа от оператора.|
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|Проверяет, больше или равен ли объект pair слева от оператора объекту pair справа от оператора.|

### <a name="structs"></a>Структуры

|Структура|Описание|
|-|-|
|[from_chars_result](../standard-library/from-chars-result-structure.md)|Структура, используемая для `from_chars` .|
|[identity](../standard-library/identity-structure.md)|Структура, предоставляющая определение типа как параметр шаблона.|
|[in_place_t](../standard-library/in-place-t-struct.md)|Также включает структуры `in_place_type_t` и `in_place_index_t` .|
|[integer_sequence](../standard-library/integer-sequence-class.md)|Представляет последовательность целых чисел.|
|[поставлен](../standard-library/pair-structure.md)|Тип, позволяющий обрабатывать два объекта как один объект.|
|[piecewise_construct_t](../standard-library/piecewise-construct-t-structure.md)|Тип, используемый для сохранения отдельного конструктора и перегрузки функции.|
|[to_chars_result](../standard-library/to-chars-result-structure.md)|Структура, используемая для `to_chars` .|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
