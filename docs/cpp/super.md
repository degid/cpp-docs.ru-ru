---
title: __super
ms.date: 11/04/2016
f1_keywords:
- __super_cpp
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
ms.openlocfilehash: 3afc2e8049cfcca40db389bed84baa6f42dae126
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213155"
---
# `__super`

**Блок, относящийся только к системам Microsoft**

Позволяет явно указать, что для переопределяемой функции вызывается реализация из базового класса.

## <a name="syntax"></a>Синтаксис

```
__super::member_function();
```

## <a name="remarks"></a>Примечания

На этапе разрешения перегрузки учитываются все доступные методы базового класса, и вызывается функция, которая обеспечивает наилучшее совпадение.

**`__super`** может использоваться только в теле функции-члена.

**`__super`** не может использоваться с объявлением using. Дополнительные сведения см. [в разделе Использование объявления](../cpp/using-declaration.md) .

С появлением [атрибутов](../windows/attributes/attributes-alphabetical-reference.md) , которые вставляют код, код может содержать один или несколько базовых классов, имена которых могут быть незнакомы, но содержат методы, которые вы хотите вызвать.

## <a name="example"></a>Пример

```cpp
// deriv_super.cpp
// compile with: /c
struct B1 {
   void mf(int) {}
};

struct B2 {
   void mf(short) {}

   void mf(char) {}
};

struct D : B1, B2 {
   void mf(short) {
      __super::mf(1);   // Calls B1::mf(int)
      __super::mf('s');   // Calls B2::mf(char)
   }
};
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Ключевые слова](../cpp/keywords-cpp.md)
