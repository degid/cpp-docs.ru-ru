---
title: Функции &lt;vector&gt;
ms.date: 11/04/2016
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
ms.openlocfilehash: bf28e44b4f603b1e4d6a87f0c28b42d6cc159980
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224556"
---
# <a name="ltvectorgt-functions"></a>Функции &lt;vector&gt;

## <a name="swap"></a><a name="swap"></a>позиции

Меняет местами элементы двух векторов.

```cpp
template <class Type, class Allocator>
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*right*\
Вектор, предоставляющий элементы для перестановки, или вектор, элементы которого должны быть заменены элементами вектора *слева*.

*left*\
Вектор, элементы которого должны быть заменены элементами, расположенными *справа*от вектора.

### <a name="remarks"></a>Примечания

Функция-шаблон — это алгоритм, специализированный на векторе класса контейнера для выполнения функции-члена `left` . [вектор:: Swap](../standard-library/vector-class.md) *(правый*). Это экземпляры частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **`template`** \< **class T**> **void swap**( **t&**, **t&**) в классе Algorithm работает по назначению и является очень высокой операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [vector::swap](../standard-library/vector-class.md), в котором используется версия шаблона `swap`.
