---
title: Типы анонимных классов
ms.date: 11/04/2016
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
ms.openlocfilehash: 77f0a5517cee5e4baeacbbdcae47bdeea2853a97
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216639"
---
# <a name="anonymous-class-types"></a>Типы анонимных классов

Классы могут быть анонимными, то есть их можно объявлять без *идентификатора*. Это полезно при замене имени класса **`typedef`** именем, как показано ниже:

```cpp
typedef struct
{
    unsigned x;
    unsigned y;
} POINT;
```

> [!NOTE]
> Использование анонимных классов, показанное в предыдущем примере, полезно для поддержки совместимости с существующими кодом C. В некоторых языках кода на языке C **`typedef`** распространено использование совместно с анонимными структурами.

Анонимные классы также полезны, если требуется, чтобы ссылка на член класса отображалась так, как если бы она не содержалась в отдельном классе, как показано в следующем примере.

```cpp
struct PTValue
{
    POINT ptLoc;
    union
    {
        int  iValue;
        long lValue;
    };
};

PTValue ptv;
```

В приведенном выше коде `iValue` можно получить доступ с помощью оператора выбора члена объекта (**.**) следующим образом:

```cpp
int i = ptv.iValue;
```

Анонимные классы имеют некоторые ограничения. (Дополнительные сведения о анонимных объединениях см. в разделе [объединения](../cpp/unions.md).) Анонимные классы:

- Не могут иметь конструктор или деструктор.

- Не может передаваться в качестве аргументов функциям (если только проверка типа не будет отменяться с помощью многоточия).

- Не могут быть возвращены в качестве возвращаемых значений из функций.

## <a name="anonymous-structs"></a>Анонимные структуры

**Блок, относящийся только к системам Microsoft**

Расширение Microsoft C позволяет объявить переменную структуры в другой структуре без указания ее имени. Эти вложенные структуры называются анонимными структурами. В C++ анонимные структуры не допускаются.

Можно получить доступ к членам анонимной структуры, как если бы они были членами содержащей их структуры.

```cpp
// anonymous_structures.c
#include <stdio.h>

struct phone
{
    int  areacode;
    long number;
};

struct person
{
    char   name[30];
    char   gender;
    int    age;
    int    weight;
    struct phone;    // Anonymous structure; no name needed
} Jim;

int main()
{
    Jim.number = 1234567;
    printf_s("%d\n", Jim.number);
}
//Output: 1234567
```

**Завершение блока, относящегося только к системам Майкрософт**
