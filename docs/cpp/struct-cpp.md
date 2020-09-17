---
title: struct (C++)
ms.date: 11/04/2016
f1_keywords:
- struct_cpp
helpviewer_keywords:
- struct constructors
ms.assetid: 3c6ba273-e248-4ff1-8c69-d2abcf1263c6
ms.openlocfilehash: 5f247a99d3f04a15ebd54718a46dae8512a580d6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231121"
---
# <a name="struct-c"></a>struct (C++)

**`struct`** Ключевое слово определяет тип структуры и (или) переменную типа структуры.

## <a name="syntax"></a>Синтаксис

```
[template-spec] struct [ms-decl-spec] [tag [: base-list ]]
{
   member-list
} [declarators];
[struct] tag declarators;
```

#### <a name="parameters"></a>Параметры

*Спецификация шаблона*<br/>
Необязательные спецификации шаблона. Дополнительные сведения см. в разделе [спецификации шаблонов](templates-cpp.md).

*struct*<br/>
**`struct`** Ключевое слово.

*MS-decl-Spec*<br/>
Необязательная спецификация класса хранения. Дополнительные сведения см. в разделе ключевое слово [__declspec](../cpp/declspec.md) .

*тег*<br/>
Имя типа, присваиваемое структуре. Тег становится зарезервированным ключевым словом в области структуры. Тег является необязательным. Если он опущен, определяется анонимная структура. Дополнительные сведения см. в разделе [типы анонимных классов](../cpp/anonymous-class-types.md).

*base-list*<br/>
Необязательный список классов или структур, из которых эта структура будет наследовать члены. Дополнительные сведения см. в разделе [базовые классы](../cpp/base-classes.md) . Каждому базовому классу или имени структуры может предшествовать спецификатор доступа ([открытый](../cpp/public-cpp.md), [частный](../cpp/private-cpp.md), [защищенный](../cpp/protected-cpp.md)) и ключевое слово [Virtual](../cpp/virtual-cpp.md) . Дополнительные сведения см. в таблице доступ к элементам в разделе [Управление доступом к членам класса](member-access-control-cpp.md) .

*Список участников*<br/>
Список членов структуры. Дополнительные сведения см. в разделе [Обзор членов класса](../cpp/class-member-overview.md) . Единственное отличие заключается в том, что **`struct`** используется вместо **`class`** .

*declarators*<br/>
Список деклараторов, указывающий имена структуры. В списках деклараторов объявляются один или несколько экземпляров типа структуры. Деклараторы могут включать списки инициализаторов, если все элементы данных структуры имеют значение **`public`** . Списки инициализаторов являются общими в структурах, так как элементы данных **`public`** по умолчанию имеют значение.  Дополнительные сведения см. в разделе [Общие сведения об деклараторах](../cpp/overview-of-declarators.md) .

## <a name="remarks"></a>Примечания

Тип структуры — это пользовательский составной тип. Он состоит из полей или членов, которые могут иметь разные типы.

В C++ структура является такой же, как и класс, за исключением того, что ее члены по **`public`** умолчанию имеют значение.

Сведения об управляемых классах и структурах в C++/CLI см. в разделе [классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="using-a-structure"></a>Использование структуры

В языке C **`struct`** для объявления структуры необходимо явно использовать ключевое слово. В C++ не нужно использовать **`struct`** ключевое слово после определения типа.

Если тип структуры определен путем размещения одной или нескольких разделенных запятыми имен переменных между закрывающей фигурной скобкой и точкой с запятой, имеется возможность объявления переменных.

Переменные структуры можно инициализировать. Инициализация каждой переменной должна быть заключена в скобки.

Связанные сведения см. в разделе [класс](../cpp/class-cpp.md), [объединение](../cpp/unions.md)и [перечисление](../cpp/enumerations-cpp.md).

## <a name="example"></a>Пример

```cpp
#include <iostream>
using namespace std;

struct PERSON {   // Declare PERSON struct type
    int age;   // Declare member types
    long ss;
    float weight;
    char name[25];
} family_member;   // Define object of type PERSON

struct CELL {   // Declare CELL bit field
    unsigned short character  : 8;  // 00000000 ????????
    unsigned short foreground : 3;  // 00000??? 00000000
    unsigned short intensity  : 1;  // 0000?000 00000000
    unsigned short background : 3;  // 0???0000 00000000
    unsigned short blink      : 1;  // ?0000000 00000000
} screen[25][80];       // Array of bit fields

int main() {
    struct PERSON sister;   // C style structure declaration
    PERSON brother;   // C++ style structure declaration
    sister.age = 13;   // assign values to members
    brother.age = 7;
    cout << "sister.age = " << sister.age << '\n';
    cout << "brother.age = " << brother.age << '\n';

    CELL my_cell;
    my_cell.character = 1;
    cout << "my_cell.character = " << my_cell.character;
}
// Output:
// sister.age = 13
// brother.age = 7
// my_cell.character = 1
```
