---
title: Класс is_pod
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_pod
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
ms.openlocfilehash: 1398da92890072d8aa8a6f07c61920fe3bee1776
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212245"
---
# <a name="is_pod-class"></a>Класс is_pod

Проверяет, является ли тип типом POD.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct is_pod;
```

### <a name="parameters"></a>Параметры

*T*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

`is_pod<T>::value`имеет значение, **`true`** Если тип *T* является обычным СТАРЫМ данными (Pod). В противном случае — значение **`false`** .

К типам POD относятся арифметические типы, типы перечисления, типы указателей и указатели на типы-члены.

Квалифицированная версия типа POD также обладает типом POD.

Массив данных типа POD также имеет тип POD.

Структура или объединение, все нестатические данные-члены которого имеют типа POD, также обладает типом POD при соблюдении следующих условий:

- Нет объявленных пользователем конструкторов.

- Нет закрытых или защищенных нестатических данных-членов.

- Отсутствие базовых классов.

- Нет виртуальных функций.

- Нет нестатических данных-членов ссылочного типа.

- Нет определяемого пользователем оператора присвоения копирования.

- Нет определяемого пользователем деструктора.

Таким образом, можно рекурсивно создавать структуры POD и массивы, содержащие структуры и массивы POD.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_pod.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial {
    int val;
};

struct throws {
    throws() {}  // User-declared ctor, so not POD

    int val;
};

int main() {
    std::cout << "is_pod<trivial> == " << std::boolalpha
        << std::is_pod<trivial>::value << std::endl;
    std::cout << "is_pod<int> == " << std::boolalpha
        << std::is_pod<int>::value << std::endl;
    std::cout << "is_pod<throws> == " << std::boolalpha
        << std::is_pod<throws>::value << std::endl;

    return (0);
}
```

```Output
is_pod<trivial> == true
is_pod<int> == true
is_pod<throws> == false
```

## <a name="requirements"></a>Требования

**Заголовок:**\<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[<type_traits>](../standard-library/type-traits.md)
