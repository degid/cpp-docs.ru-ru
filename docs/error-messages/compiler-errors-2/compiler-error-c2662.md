---
title: Ошибка компилятора C2662
ms.date: 11/04/2016
f1_keywords:
- C2662
helpviewer_keywords:
- C2662
ms.assetid: e172c2a4-f29e-4034-8232-e7dc6f83689f
ms.openlocfilehash: 5e2dd6b01db5f7d3026f14c5032ab4623eb6fb58
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220292"
---
# <a name="compiler-error-c2662"></a>Ошибка компилятора C2662

"функция": невозможно преобразовать указатель "this" из "тип1" в "тип2"

Компилятору не удалось преобразовать **`this`** указатель из `type1` в `type2` .

Эта ошибка может быть вызвана вызовом функции, не являющейся **`const`** членом, для **`const`** объекта.  Возможные решения:

- Удалите **`const`** из объявления объекта.

- Добавьте **`const`** в функцию члена.

Следующий пример приводит к возникновению ошибки C2662:

```cpp
// C2662.cpp
class C {
public:
   void func1();
   void func2() const{}
} const c;

int main() {
   c.func1();   // C2662
   c.func2();   // OK
}
```

При компиляции с **параметром/CLR**нельзя вызывать функцию для **`const`** или **`volatile`** квалифицированного управляемого типа. Нельзя объявить константную функцию-член управляемого класса, поэтому нельзя вызывать методы для объектов, управляемых константами.

```cpp
// C2662_b.cpp
// compile with: /c /clr
ref struct M {
   property M^ Type {
      M^ get() { return this; }
   }

   void operator=(const M %m) {
      M ^ prop = m.Type;   // C2662
   }
};

ref struct N {
   property N^ Type {
      N^ get() { return this; }
   }

   void operator=(N % n) {
      N ^ prop = n.Type;   // OK
   }
};
```

Следующий пример приводит к возникновению ошибки C2662:

```cpp
// C2662_c.cpp
// compile with: /c
// C2662 expected
typedef int ISXVD;
typedef unsigned char BYTE;

class LXBASE {
protected:
    BYTE *m_rgb;
};

class LXISXVD:LXBASE {
public:
   // Delete the following line to resolve.
   ISXVD *PMin() { return (ISXVD *)m_rgb; }

   ISXVD *PMin2() const { return (ISXVD *)m_rgb; };   // OK
};

void F(const LXISXVD *plxisxvd, int iDim) {
   ISXVD isxvd;
   // Delete the following line to resolve.
   isxvd = plxisxvd->PMin()[iDim];

   isxvd = plxisxvd->PMin2()[iDim];
}
```
