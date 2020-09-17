---
title: Структура iterator
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: b45cdb5c3d4608296cca34ad6a0be6e25b588d28
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222307"
---
# <a name="iterator-struct"></a>Структура iterator

Пустая базовая структура, используемая, чтобы гарантировать, что определяемый пользователем класс итератора правильно работает с `iterator_trait` s.

## <a name="syntax"></a>Синтаксис

```cpp
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };
```

## <a name="remarks"></a>Примечания

Данная структура-шаблон используется как базовый тип для всех итераторов. Она определяет типы членов

- `iterator_category` (синоним для параметра-шаблона `Category`).

- `value_type` (синоним для параметра-шаблона `Type`).

- `difference_type` (синоним для параметра-шаблона `Distance`).

- `distance_type` (синоним для параметра-шаблона `Distance`)

- `pointer` (синоним для параметра-шаблона `Pointer`).

- `reference` (синоним для параметра-шаблона `Reference`).

Обратите внимание, что `value_type` не должен быть константным типом, даже если `pointer` точки в объекте **`const`** `Type` и ссылка указывает на объект **`const`** `Type` .

## <a name="example"></a>Пример

См. раздел [iterator_traits](../standard-library/iterator-traits-struct.md) с примером того, как объявить и использовать типы в базовом классе итератора.

## <a name="requirements"></a>Требования

**Заголовок:**\<iterator>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[\<iterator>](../standard-library/iterator.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)
