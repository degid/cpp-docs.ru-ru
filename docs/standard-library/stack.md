---
title: '&lt;stack&gt;'
ms.date: 11/04/2016
f1_keywords:
- <stack>
helpviewer_keywords:
- stack, stack header
- stack header
ms.assetid: 89d8999e-c773-46f2-86c1-4b3b5aedb1c1
ms.openlocfilehash: b2130994ca69dd23f7df3e521deb67263b13d0cc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844292"
---
# <a name="ltstackgt"></a>&lt;stack&gt;

Определяет стек шаблона класса и два поддерживающих шаблона.

## <a name="requirements"></a>Требования

**Заголовок:**\<stack>

**Пространство имен:** std

> [!NOTE]
> \<stack>Библиотека также использует `#include <initializer_list>` инструкцию.

## <a name="members"></a>Элементы

### <a name="operators"></a>Операторы

|Имя|Описание|
|-|-|
|[operator!=](../standard-library/stack-operators.md#op_neq)|Проверяет, не равен ли объект стека слева от оператора объекту стека справа от оператора.|
|[operator<](../standard-library/stack-operators.md#op_lt)|Проверяет, меньше ли объект стека слева от оператора объекта стека справа от оператора.|
|[operator\<=](../standard-library/stack-operators.md#op_lt_eq)|Проверяет, меньше или равен ли объект стека слева от оператора объекту стека справа от оператора.|
|[operator==](../standard-library/stack-operators.md#op_eq_eq)|Проверяет, равен ли объект стека слева от оператора объекту стека справа от оператора.|
|[operator>](../standard-library/stack-operators.md#op_gt)|Проверяет, больше ли объект стека слева от оператора объекта стека справа от оператора.|
|[operator>=](../standard-library/stack-operators.md#op_gt_eq)|Проверяет, больше или равен ли объект стека слева от оператора объекту стека справа от оператора.|

### <a name="classes"></a>Классы

|Имя|Описание|
|-|-|
|[Stack, класс](../standard-library/stack-class.md)|Класс адаптера контейнера шаблона, который предоставляет ограничение функциональности, ограничивая доступ к элементу, который был последним добавлен в некоторый тип базового контейнера.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
