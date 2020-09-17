---
title: Спецификатор final
ms.date: 11/04/2016
f1_keywords:
- final_CPP
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
ms.openlocfilehash: 93e8d9b0b445d1120ec15911eb763ae1d7d2d359
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188665"
---
# <a name="final-specifier"></a>Спецификатор final

Ключевое слово **final** можно использовать для обозначения виртуальных функций, которые не могут быть переопределены в производном классе. Можно также использовать это ключевое слово для назначения классов, которые невозможно наследовать.

## <a name="syntax"></a>Синтаксис

```
function-declaration final;
class class-name final base-classes
```

## <a name="remarks"></a>Примечания

**final** является контекстно-зависимым и имеет специальное значение только в том случае, если оно используется после объявления функции или имени класса; в противном случае это не зарезервированное ключевое слово.

Если аргумент **final** используется в объявлениях класса, `base-classes` является необязательной частью объявления.

## <a name="example"></a>Пример

В следующем примере ключевое слово **final** используется для указания того, что виртуальную функцию нельзя переопределить.

```cpp
class BaseClass
{
    virtual void func() final;
};

class DerivedClass: public BaseClass
{
    virtual void func(); // compiler error: attempting to
                         // override a final function
};
```

Сведения о том, как указать, что функции элементов можно переопределить, см. в разделе [спецификатор переопределения](../cpp/override-specifier.md).

В следующем примере ключевое слово **final** используется для указания того, что класс не может быть унаследован.

```cpp
class BaseClass final
{
};

class DerivedClass: public BaseClass // compiler error: BaseClass is
                                     // marked as non-inheritable
{
};
```

## <a name="see-also"></a>См. также раздел

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Описатель override](../cpp/override-specifier.md)
