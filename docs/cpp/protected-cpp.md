---
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 25b25447737a075bcf4f02f1c3049c996fb4c678
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227170"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>Синтаксис

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>Примечания

**`protected`** Ключевое слово задает доступ к членам класса в *списке Members* до следующего спецификатора доступа ( **`public`** или **`private`** ) или в конце определения класса. Члены класса, объявленные как, **`protected`** могут использоваться только следующим образом:

- Функции-члены класса, который изначально объявил эти элементы.

- Дружественные элементы класса, который изначально объявил эти элементы.

- Классы, производные с использованием открытого или защищенного доступа от класса, который изначально объявил эти элементы.

- Прямые производные с использованием закрытого доступа классы, которые также имеют закрытый доступ к защищенным элементам.

При предшествующем имени базового класса **`protected`** ключевое слово указывает, что открытые и защищенные члены базового класса являются защищенными членами его производных классов.

Защищенные члены не являются частными как **`private`** члены, которые доступны только членам класса, в котором они объявляются, но не являются общими как **`public`** члены, доступные в любой функции.

Защищенные члены, которые также объявлены как **`static`** , доступны для любого дружественного или функции-члена производного класса. Защищенные члены, которые не объявлены как **`static`** , доступны друзьям и функциям-членам в производном классе только через указатель на, ссылку на или объект производного класса.

Дополнительные сведения см. в статьях [дружественный](../cpp/friend-cpp.md), [общедоступный](../cpp/public-cpp.md), [частный](../cpp/private-cpp.md)и таблица доступа к членам в разделе [Управление доступом к членам класса](member-access-control-cpp.md).

## <a name="clr-specific"></a>Специально для /clr

В типах CLR ключевые слова спецификатора доступа C++ ( **`public`** , **`private`** и **`protected`** ) могут влиять на видимость типов и методов относительно сборок. Дополнительные сведения см. в разделе [Управление доступом к членам](member-access-control-cpp.md).

> [!NOTE]
> Это поведение не влияет на файлы, скомпилированные с параметром [/LN](../build/reference/ln-create-msil-module.md) . В этом случае все управляемые классы (открытые или закрытые) будут видны.

## <a name="end-clr-specific"></a>КОНЕЦ специально для /clr

## <a name="example"></a>Пример

```cpp
// keyword_protected.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class X {
public:
   void setProtMemb( int i ) { m_protMemb = i; }
   void Display() { cout << m_protMemb << endl; }
protected:
   int  m_protMemb;
   void Protfunc() { cout << "\nAccess allowed\n"; }
} x;

class Y : public X {
public:
   void useProtfunc() { Protfunc(); }
} y;

int main() {
   // x.m_protMemb;         error, m_protMemb is protected
   x.setProtMemb( 0 );   // OK, uses public access function
   x.Display();
   y.setProtMemb( 5 );   // OK, uses public access function
   y.Display();
   // x.Protfunc();         error, Protfunc() is protected
   y.useProtfunc();      // OK, uses public access function
                        // in derived class
}
```

## <a name="see-also"></a>См. также

[Управление доступом к членам классов](member-access-control-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
