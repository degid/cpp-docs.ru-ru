---
title: Ошибка компилятора C2065
ms.date: 08/19/2019
f1_keywords:
- C2065
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
ms.openlocfilehash: 68817498d6f29ef5982b72a2fee4e64a4423ccde
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214819"
---
# <a name="compiler-error-c2065"></a>Ошибка компилятора C2065

> "*идентификатор*": необъявленный идентификатор

Компилятору не удается найти объявление идентификатора. Эта ошибка имеет несколько возможных причин. Наиболее распространенными причинами C2065 является то, что идентификатор не был объявлен, идентификатор написан неправильно, заголовок, где объявляется идентификатор, не включается в файл, или в идентификаторе отсутствует квалификатор области, например, `cout` вместо `std::cout` . Дополнительные сведения об объявлениях в C++ см. в разделе [объявления и определения (c++)](../../cpp/declarations-and-definitions-cpp.md).

Ниже приведены некоторые распространенные проблемы и более подробные решения.

## <a name="the-identifier-is-undeclared"></a>Идентификатор не объявлен

Если идентификатор является переменной или именем функции, его необходимо объявить перед тем, как его можно будет использовать. Перед использованием функции в объявлении функции также должны быть включены типы его параметров. Если переменная объявлена с помощью **`auto`** , компилятор должен иметь возможность определить тип из его инициализатора.

Если идентификатор является членом класса или структуры или объявлен в пространстве имен, он должен уточняться именем класса или структуры или именем пространства имен при использовании вне структуры, класса или области пространства имен. Кроме того, пространство имен должно быть помещено в область с помощью **`using`** директивы, такой как `using namespace std;` , или имя члена должно быть помещено в область с помощью **`using`** объявления, такого как `using std::string;` . В противном случае неполное имя считается необъявленным идентификатором в текущей области.

Если идентификатор является тегом для определяемого пользователем типа, например, **`class`** или **`struct`** , тип тега должен быть объявлен до его использования. Например, объявление `struct SomeStruct { /*...*/ };` должно существовать, прежде чем можно будет объявить переменную `SomeStruct myStruct;` в коде.

Если идентификатор является псевдонимом типа, тип должен быть объявлен с помощью **`using`** объявления или **`typedef`** перед тем, как его можно будет использовать. Например, необходимо объявить, `using my_flags = std::ios_base::fmtflags;` прежде чем можно будет использовать `my_flags` в качестве псевдонима типа для `std::ios_base::fmtflags` .

## <a name="example-misspelled-identifier"></a>Пример: идентификатор с ошибками

Эта ошибка обычно возникает, когда имя идентификатора написано неправильно или идентификатор использует неправильные прописные и строчные буквы. Имя в объявлении должно точно совпадать с именем, которое вы используете.

```cpp
// C2065_spell.cpp
// compile with: cl /EHsc C2065_spell.cpp
#include <iostream>
using namespace std;
int main() {
    int someIdentifier = 42;
    cout << "Some Identifier: " << SomeIdentifier << endl;
    // C2065: 'SomeIdentifier': undeclared identifier
    // To fix, correct the spelling:
    // cout << "Some Identifier: " << someIdentifier << endl;
}
```

## <a name="example-use-an-unscoped-identifier"></a>Пример. Использование неограниченного идентификатора

Эта ошибка может возникать, если идентификатор не является правильно заданной областью. Если вы видите C2065 при использовании `cout` , это является причиной. Если функции и операторы стандартной библиотеки C++ не полностью определены в пространстве имен или вы не передали `std` пространство имен в текущую область с помощью **`using`** директивы, компилятор не сможет их найти. Чтобы устранить эту проблему, необходимо либо полностью определить имена идентификаторов, либо указать пространство имен с помощью **`using`** директивы.

Этот пример не компилируется `cout` , поскольку и `endl` определены в `std` пространстве имен:

```cpp
// C2065_scope.cpp
// compile with: cl /EHsc C2065_scope.cpp
#include <iostream>
// using namespace std;   // Uncomment this line to fix

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead
    std::cout << "Hello" << std::endl;
}
```

Идентификаторы, объявляемые внутри **`class`** типов, **`struct`** или, **`enum class`** также должны уточняться именем их включающей области при их использовании за пределами этой области.

## <a name="example-precompiled-header-isnt-first"></a>Пример: предварительно скомпилированный заголовок не является первым

Эта ошибка может возникать, если вы поместили директивы препроцессора, такие как #include, #define или #pragma, перед #includeом предкомпилированного файла заголовка. Если исходный файл использует предварительно скомпилированный заголовочный файл (то есть если он компилируется с помощью параметра компилятора **/Yu** ), то все директивы препроцессора перед файлом предкомпилированного заголовка будут проигнорированы.

Этот пример не компилируется `cout` , поскольку и `endl` определены в \<iostream> заголовке, который игнорируется, поскольку он включается перед предкомпилированным файлом заголовка. Чтобы выполнить сборку этого примера, создайте все три файла, а затем скомпилируйте файл stdafx. cpp, а затем скомпилируйте C2065_pch. cpp.

```cpp
// pch.h (stdafx.h in Visual Studio 2017 and earlier)
#include <stdio.h>
```

```cpp
// pch.cpp (stdafx.cpp in Visual Studio 2017 and earlier)
// Compile by using: cl /EHsc /W4 /c /Ycstdafx.h stdafx.cpp
#include "pch.h"
```

```cpp
// C2065_pch.cpp
// compile with: cl /EHsc /W4 /Yustdafx.h C2065_pch.cpp
#include <iostream>
#include "stdafx.h"
using namespace std;

int main() {
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier
                               // C2065 'endl': undeclared identifier
}
```

Чтобы устранить эту проблему, добавьте #include \<iostream> в файл предкомпилированного заголовка или переместите его после включения файла предкомпилированного заголовка в исходный файл.

## <a name="example-missing-header-file"></a>Пример: отсутствует заголовочный файл

Вы не включили заголовочный файл, объявляющий идентификатор. Убедитесь, что файл, содержащий объявление идентификатора, включен в каждый исходный файл, который его использует.

```cpp
// C2065_header.cpp
// compile with: cl /EHsc C2065_header.cpp

//#include <stdio.h>
int main() {
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined
}
```

Другая возможная причина заключается в том, что при использовании списка инициализаторов не включается \<initializer_list> заголовок.

```cpp
// C2065_initializer.cpp
// compile with: cl /EHsc C2065_initializer.cpp

// #include <initializer_list>
int main() {
    for (auto strList : {"hello", "world"})
        if (strList == "hello") // C2065: 'strList': undeclared identifier
            return 1;
    // To fix, uncomment the #include <initializer_list> line
}
```

Эта ошибка может возникать в исходных файлах Windows Desktop App, если вы определяете `VC_EXTRALEAN` , `WIN32_LEAN_AND_MEAN` или `WIN32_EXTRA_LEAN` . Эти макросы препроцессора исключают некоторые файлы заголовков из Windows.h и афксв \_ W32.h для ускорения компиляции. Просмотрите Windows.h и afxv_w32.h, чтобы получить последние сведения о том, что исключено.

## <a name="example-missing-closing-quote"></a>Пример: отсутствует закрывающая кавычка

Эта ошибка может возникать, если отсутствует закрывающая кавычка после строковой константы. Это простой способ запутывания компилятора. Обратите внимание, что пропущенная закрывающая кавычка может быть в нескольких строках перед сообщаемым расположением ошибки.

```cpp
// C2065_quote.cpp
// compile with: cl /EHsc C2065_quote.cpp
#include <iostream>

int main() {
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee";
    std::cout << "Name: " << first
        << " " << last << std::endl; // C2065: 'last': undeclared identifier
}
```

## <a name="example-use-iterator-outside-for-loop-scope"></a>Пример. Использование итератора вне области действия цикла

Эта ошибка может возникать, если объявить переменную-итератор в **`for`** цикле, а затем попробовать использовать эту переменную итератора вне области **`for`** цикла. Компилятор включает параметр компилятора [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) по умолчанию. Дополнительные сведения см. в разделе [Поддержка итераторов отладки](../../standard-library/debug-iterator-support.md) .

```cpp
// C2065_iter.cpp
// compile with: cl /EHsc C2065_iter.cpp
#include <iostream>
#include <string>

int main() {
    // char last = '!';
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" };
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
}
```

## <a name="example-preprocessor-removed-declaration"></a>Пример: объявление удаленного препроцессора

Эта ошибка может возникать, если вы ссылаетесь на функцию или переменную, которая находится в коде, скомпилированном по условию, который не компилируется для текущей конфигурации. Это также может произойти при вызове функции в файле заголовка, который в настоящее время не поддерживается в среде сборки. Если определенные переменные или функции доступны только при определении конкретного макроса препроцессора, убедитесь, что код, вызывающий эти функции, может быть скомпилирован только при определении одного и того же макроса препроцессора. Эту ошибку легко выявить в интегрированной среде разработки, так как объявление функции недоступно, если требуемые макросы препроцессора не определены для текущей конфигурации сборки.

Это пример кода, который работает при сборке в отладке, но не в розницу:

```cpp
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate);
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```

## <a name="example-ccli-type-deduction-failure"></a>Пример: сбой выведения типа C++/CLI

Эта ошибка может возникать при вызове универсальной функции, если аргумент предполагаемого типа не может быть выведен из используемых параметров. Дополнительные сведения см. в разделе [универсальные функции (C++/CLI)](../../extensions/generic-functions-cpp-cli.md).

```cpp
// C2065_b.cpp
// compile with: cl /clr C2065_b.cpp
generic <typename ItemType>
void G(int i) {}

int main() {
   // global generic function call
   G<T>(10);     // C2065
   G<int>(10);   // OK - fix with a specific type argument
}
```

## <a name="example-ccli-attribute-parameters"></a>Пример: параметры атрибута C++/CLI

Эта ошибка также может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio 2005: Проверка параметров для Visual C++ атрибутов.

```cpp
// C2065_attributes.cpp
// compile with: cl /c /clr C2065_attributes.cpp
[module(DLL, name=MyLibrary)];   // C2065
// try the following line instead
// [module(dll, name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```
