---
title: модуль, импорт, экспорт
ms.date: 12/12/2019
f1_keywords:
- module_cpp
- import_cpp
- export_cpp
helpviewer_keywords:
- modules [C++]
- modules [C++], import
- modules [C++], export
description: Используйте объявления импорта и экспорта для доступа к типам и функциям, определенным в указанном модуле, и для публикации типов и функций.
ms.openlocfilehash: 5be1618d7e64f6887cf78bd863d428d6710eaf7e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87187196"
---
# <a name="module-import-export"></a>модуль, импорт, экспорт

**Модуль**, **Импорт**и **`export`** объявления доступны в c++ 20, и требуется параметр компилятора [/експериментал: module](../build/reference/experimental-module.md) вместе с [/std: C + + Latest](../build/reference/std-specify-language-standard-version.md). Дополнительные сведения см. в разделе Общие сведения о [модулях в C++](modules-cpp.md).

## <a name="module"></a>module

Поместите объявление **модуля** в начало файла реализации модуля, чтобы указать, что содержимое файла принадлежит к именованному модулю.

```cpp
module ModuleA;
```

## <a name="export"></a>экспорт

Используйте объявление **модуля экспорта** для основного файла интерфейса модуля, который должен иметь расширение **. икскс**:

```cpp
export module ModuleA;
```

В файле интерфейса используйте **`export`** Модификатор для имен, которые должны быть частью общего интерфейса:

```cpp
// ModuleA.ixx

export module ModuleA;

namespace Bar
{
   export int f();
   export double d();
   double internal_f(); // not exported
}
```

Неэкспортированные имена невидимы для кода, который импортирует модуль:

```cpp
//MyProgram.cpp

import module ModuleA;

int main() {
  Bar::f(); // OK
  Bar::d(); // OK
  Bar::internal_f(); // Ill-formed: error C2065: 'internal_f': undeclared identifier
}
```

**`export`** Ключевое слово не может присутствовать в файле реализации модуля. Когда **`export`** применяется к имени пространства имен, экспортируются все имена в пространстве имен.

## <a name="import"></a>импорт

Используйте объявление **импорта** , чтобы сделать имена модуля видимыми в программе. Объявление импорта должно располагаться после объявления модуля и после любой директивы #include, но перед любыми объявлениями в файле.

```cpp
module ModuleA;

#include "custom-lib.h"
import std.core;
import std.regex;
import ModuleB;

// begin declarations here:
template <class T>
class Baz
{...};
```

## <a name="remarks"></a>Примечания

**Импорт** и **модуль** рассматриваются как ключевые слова, только если они появляются в начале логической строки:

```cpp

// OK:
module ;
module module-name
import :
import <
import "
import module-name
export module ;
export module module-name
export import :
export import <
export import "
export import module-name

// Error:
int i; module ;
```

**Блок, относящийся только к системам Microsoft**

В Microsoft C++ **Импорт** и **модуль** маркеров всегда являются идентификаторами и никогда не являются ключевыми словами, когда они используются в качестве аргументов макроса.

### <a name="example"></a>Пример

```cpp
#define foo(…) __VA_ARGS__
foo(
import // Always an identifier, never a keyword
)
```

**Завершение Microsoft для конкретных**

## <a name="see-also"></a>См. также:

[Обзор модулей в C++](modules-cpp.md)
