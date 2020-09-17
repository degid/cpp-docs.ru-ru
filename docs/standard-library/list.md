---
title: '&lt;list&gt;'
ms.date: 11/04/2016
f1_keywords:
- <list>
helpviewer_keywords:
- list header
ms.assetid: 2345823b-5612-44d8-95d3-aa96ed076d17
ms.openlocfilehash: cbc93500c3fe61b2a4640008b869f3a6b71b5c6c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833313"
---
# <a name="ltlistgt"></a>&lt;list&gt;

Определяет список шаблонов классов контейнеров и несколько вспомогательных шаблонов.

## <a name="syntax"></a>Синтаксис

```cpp
#include <list>
```

> [!NOTE]
> \<list>Библиотека также использует `#include <initializer_list>` инструкцию.

## <a name="members"></a>Элементы

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator!=](../standard-library/list-operators.md#op_neq)|Проверяет неравенство объекта-списка слева от оператора объекту-списку справа от оператора.|
|[operator<](../standard-library/list-operators.md#op_lt)|Проверяет, меньше ли объект-список слева от оператора, чем объект-список справа от оператора.|
|[operator\<=](../standard-library/list-operators.md#op_gt_eq)|Проверяет, что объект-список слева от оператора меньше или равен объекту-списку справа от оператора.|
|[operator==](../standard-library/list-operators.md#op_eq_eq)|Проверяет, равен ли объект-список слева от оператора объекту-списку справа от оператора.|
|[operator>](../standard-library/list-operators.md#op_gt)|Проверяет, больше ли объект-список слева от оператора, чем объект-список справа от оператора.|
|[operator>=](../standard-library/list-operators.md#op_gt_eq)|Проверяет, что объект-список слева от оператора больше или равен объекту-списку справа от оператора.|

### <a name="functions"></a>Функции

|Имя|Описание|
|-|-|
|[swap](../standard-library/list-functions.md#swap)|Меняет местами элементы двух списков.|

### <a name="classes"></a>Классы

|Имя|Описание|
|-|-|
|[Класс List](../standard-library/list-class.md)|Шаблон класса последовательностей контейнеров, который сохраняет свои элементы в линейном упорядочении и позволяет выполнять операции вставки и удаления в любом расположении в последовательности.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
