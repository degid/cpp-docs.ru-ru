---
title: Предупреждение компилятора (уровень 1) C4503
ms.date: 05/14/2018
f1_keywords:
- C4503
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
ms.openlocfilehash: 1d3af2b5629906679db46f6f669084c11a41f7ca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233253"
---
# <a name="compiler-warning-level-1-c4503"></a>Предупреждение компилятора (уровень 1) C4503

> "*идентификатор*": превышена длина декорированного имени, имя усечено

## <a name="remarks"></a>Примечания

Это предупреждение компилятора устарело и не создается в компиляторах Visual Studio 2017 и более поздних версий.

Декорированное имя превысило ограничение компилятора (4096) и было усечено. Чтобы избежать этого предупреждения и усечения, сократите число аргументов или длину имен используемых идентификаторов. Внутренние имена, превышающие ограничение компилятора, имеют примененный хэш и не могут быть опасности конфликта имен.

При использовании более старой версии Visual Studio это предупреждение может быть выдано, если код содержит шаблоны, специализированные для шаблонов. Например, карта карт (из стандартной библиотеки C++). В этом случае можно сделать typedef типа ( **`struct`** например,), который содержит карту.

Однако вы можете не переструктурировать код.  Можно поставлять приложение, которое создает возникновения C4503, но при возникновении ошибок компоновки в усеченном символе может быть сложнее определить тип символа в ошибке. Отладка также может быть более сложной. отладчик может сложно сопоставить имя типа с именем символа. Однако правильное имя не влияет на правильность программы.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки возникновения C4503 в компиляторах до Visual Studio 2017:

```cpp
// C4503.cpp
// compile with: /W1 /EHsc /c
// C4503 expected
#include <string>
#include <map>

class Field{};

typedef std::map<std::string, Field> Screen;
typedef std::map<std::string, Screen> WebApp;
typedef std::map<std::string, WebApp> WebAppTest;
typedef std::map<std::string, WebAppTest> Hello;
Hello MyWAT;
```

В этом примере показан один из способов перезаписи кода для разрешения возникновения C4503:

```cpp
// C4503b.cpp
// compile with: /W1 /EHsc /c
#include <string>
#include <map>

class Field{};

struct Screen2 {
   std::map<std::string, Field> Element;
};

struct WebApp2 {
   std::map<std::string, Screen2> Element;
};

struct WebAppTest2 {
   std::map<std::string, WebApp2> Element;
};

struct Hello2 {
   std::map<std::string, WebAppTest2> Element;
};

Hello2 MyWAT2;
```
