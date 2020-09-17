---
title: Функции &lt;map&gt;
ms.date: 11/04/2016
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: 8cc4a82e08963902f9ba5c21ace759c47bdd0014
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228223"
---
# <a name="ltmapgt-functions"></a>Функции &lt;map&gt;

## <a name="swap-map"></a><a name="swap_multimap"></a>переключить (map)

Обмен элементами между двумя сопоставлениями.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Параметры

*right*\
Схема, предоставляющая элементы для переключения, или карту, элементы которой должны быть заменены на те, которые расположены *слева*от схемы.

*left*\
Схема, элементы которой должны быть заменены соответствующими элементами схемы *right*.

### <a name="remarks"></a>Примечания

Функция-шаблон — это алгоритм, специализированный на карте класса контейнера для выполнения функции-члена `left` .[ Swap](../standard-library/map-class.md#swap)( `right` ). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **`template`** \< **class T**> **void swap**( **t&**, **t&**) в классе Algorithm работает по назначению и является очень высокой операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [map::swap](../standard-library/map-class.md#swap), в котором используется версия шаблона `swap`.

## <a name="swap-multimap"></a><a name="swap"></a>Swap (multimap)

Обмен элементами между двумя мультиотображениями.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Параметры

*right*\
Multimap, предоставляющий элементы для обмена, или multimap, элементы которого должны быть заменены элементами multimap *Left*.

*left*\
Объект multimap, элементы которого должны быть заменены элементами multimap *right*.

### <a name="remarks"></a>Примечания

Функция-шаблон — это алгоритм, специализированный на карте класса контейнера для выполнения в классе контейнера multimap для выполнения функции-члена `left` .[ Swap](../standard-library/multimap-class.md#swap) ( `right` ). Это экземпляр частичного упорядочивания шаблонов функций компилятором. Когда функции-шаблоны перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции-шаблона. Общая версия функции шаблона, **`template`** \< **class T**> **void swap**( **t&**, **t&**) в классе Algorithm работает по назначению и является очень высокой операцией. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.

### <a name="example"></a>Пример

См. пример кода для функции-члена [multimap::swap](../standard-library/multimap-class.md#swap), в котором используется версия шаблона `swap`.
