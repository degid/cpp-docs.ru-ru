---
title: Файлы заголовков (C++)
ms.date: 12/11/2019
helpviewer_keywords:
- header files [C++]
ms.openlocfilehash: 0b76773b8b7d55645c807588fe41b242df9eea2f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227456"
---
# <a name="header-files-c"></a>Файлы заголовков (C++)

Имена программных элементов, таких как переменные, функции, классы и т. д., должны быть объявлены, прежде чем их можно будет использовать. Например, нельзя просто писать `x = 42` без предварительного объявления "x".

```cpp
int x; // declaration
x = 42; // use x
```

Объявление сообщает компилятору, является ли элемент **`int`** , a **`double`** , **функцией** **`class`** или другим элементом.  Кроме того, каждое имя должно быть объявлено (прямо или косвенно) в каждом cpp-файле, в котором он используется. При компиляции программы каждый CPP-файл компилируется независимо в единицу компиляции. Компилятор не имеет сведений о том, какие имена объявляются в других единицах компиляции. Это означает, что если вы определите класс или функцию или глобальную переменную, необходимо предоставить объявление этого объекта в каждом дополнительном cpp-файле, который его использует. Каждое объявление этого элемента должно быть точно одинаковым во всех файлах. Небольшая несогласованность вызовет ошибки или непреднамеренное поведение, когда компоновщик пытается объединить все единицы компиляции в одну программу.

Чтобы максимально сокращать возможности ошибок, в C++ принято соглашение об использовании *файлов заголовков* для хранения объявлений. Объявления можно сделать в файле заголовка, а затем использовать директиву #include в каждом cpp-файле или другом файле заголовка, для которого требуется это объявление. Директива #include вставляет копию файла заголовка непосредственно в CPP-файл перед компиляцией.

> [!NOTE]
> В Visual Studio 2019 функция *модулей* c++ 20 появилась в качестве улучшения и в конечном итоге заменяет файлы заголовков. Дополнительные сведения см. в разделе Общие сведения о [модулях в C++](modules-cpp.md).

## <a name="example"></a>Пример

В следующем примере показан общий способ объявления класса и его использования в другом исходном файле. Начнем с файла заголовка, `my_class.h` . Он содержит определение класса, но обратите внимание, что определение не завершено; Функция-член `do_something` не определена:

```cpp
// my_class.h
namespace N
{
    class my_class
    {
    public:
        void do_something();
    };

}
```

Затем создайте файл реализации (обычно с расширением CPP или аналогичным модулем). Мы вызываем файл my_class. cpp и предоставим определение для объявления члена. Мы добавляем `#include` директиву для файла "my_class.h", чтобы объявление my_class, вставленное в этот момент в cpp, было включено в `<iostream>` объявление для `std::cout` . Обратите внимание, что кавычки используются для файлов заголовков в том же каталоге, что и исходный файл, а угловые скобки используются для заголовков стандартной библиотеки. Кроме того, многие заголовки стандартной библиотеки не имеют h или любого другого расширения файла.

В файле реализации при необходимости можно использовать **`using`** оператор, чтобы не указывать каждое упоминание "my_class" или "cout" с "N::" или "std::".  Не помещайте **`using`** операторы в файлы заголовков!

```cpp
// my_class.cpp
#include "my_class.h" // header in local directory
#include <iostream> // header in standard library

using namespace N;
using namespace std;

void my_class::do_something()
{
    cout << "Doing something!" << endl;
}
```

Теперь можно использовать `my_class` в другом cpp файле. Мы #include заголовочный файл, чтобы компилятор запрашивает объявление. Все компиляторы должны иметь представление о том, что my_class — это класс, имеющий открытую функцию-член с именем `do_something()` .

```cpp
// my_program.cpp
#include "my_class.h"

using namespace N;

int main()
{
    my_class mc;
    mc.do_something();
    return 0;
}
```

После того как компилятор завершит компиляцию каждого CPP-файла в OBJ-файлы, он передает OBJ-файлы компоновщику. Когда компоновщик объединяет объектные файлы, обнаруживается только одно определение для my_class; Он находится в OBJ-файле, созданном для my_class. cpp, и сборка выполняется.

## <a name="include-guards"></a>Включить условия

Как правило, файлы заголовков содержат директиву *include* или, `#pragma once` чтобы убедиться, что они не вставляются несколько раз в один CPP-файл.

```cpp
// my_class.h
#ifndef MY_CLASS_H // include guard
#define MY_CLASS_H

namespace N
{
    class my_class
    {
    public:
        void do_something();
    };
}

#endif /* MY_CLASS_H */
```

## <a name="what-to-put-in-a-header-file"></a>Что следует разместить в файле заголовка

Поскольку файл заголовка потенциально может включаться в несколько файлов, он не может содержать определения, которые могут формировать несколько определений с одним и тем же именем. Следующие действия не разрешены или считаются очень неправильными.

- встроенные определения типов в пространстве имен или глобальной области
- невстроенные определения функций
- определения неконстантных переменных
- агрегатные определения
- безымянные пространства имен
- Директивы using

Использование **`using`** директивы не обязательно приведет к ошибке, но может вызвать проблему, так как она переводит пространство имен в область каждого CPP-файла, который напрямую или косвенно включает этот заголовок.

## <a name="sample-header-file"></a>Пример файла заголовка

В следующем примере показаны различные виды объявлений и определений, допустимых в файле заголовка.

```cpp
// sample.h
#pragma once
#include <vector> // #include directive
#include <string>

namespace N  // namespace declaration
{
    inline namespace P
    {
        //...
    }

    enum class colors : short { red, blue, purple, azure };

    const double PI = 3.14;  // const and constexpr definitions
    constexpr int MeaningOfLife{ 42 };
    constexpr int get_meaning()
    {
        static_assert(MeaningOfLife == 42, "unexpected!"); // static_assert
        return MeaningOfLife;
    }
    using vstr = std::vector<int>;  // type alias
    extern double d; // extern variable

#define LOG   // macro definition

#ifdef LOG   // conditional compilation directive
    void print_to_log();
#endif

    class my_class   // regular class definition,
    {                // but no non-inline function definitions

        friend class other_class;
    public:
        void do_something();   // definition in my_class.cpp
        inline void put_value(int i) { vals.push_back(i); } // inline OK

    private:
        vstr vals;
        int i;
    };

    struct RGB
    {
        short r{ 0 };  // member initialization
        short g{ 0 };
        short b{ 0 };
    };

    template <typename T>  // template definition
    class value_store
    {
    public:
        value_store<T>() = default;
        void write_value(T val)
        {
            //... function definition OK in template
        }
    private:
        std::vector<T> vals;
    };

    template <typename T>  // template declaration
    class value_widget;
}
```
