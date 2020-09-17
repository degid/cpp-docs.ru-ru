---
title: /Zc:implicitNoexcept (неявные спецификаторы исключений)
ms.date: 03/06/2018
f1_keywords:
- /Zc:implicitNoexcept
helpviewer_keywords:
- /Zc:implicitNoexcept
- Zc:implicitNoexcept
- -Zc:implicitNoexcept
ms.assetid: 71807652-6f9d-436b-899e-f52daa6f500b
ms.openlocfilehash: bb1a632ffe684ac0777d0089a2edfd514bf66d0b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223802"
---
# <a name="zcimplicitnoexcept-implicit-exception-specifiers"></a>/Zc:implicitNoexcept (неявные спецификаторы исключений)

Если указан параметр **/Zc: implicitNoexcept** , компилятор добавляет неявный спецификатор исключения, [Кроме](../../cpp/noexcept-cpp.md) , для определенных в компиляторе специальных функций-членов и для определяемых пользователем деструкторов и дераспределительов. По умолчанию **/Zc: implicitNoexcept** включен в соответствие стандарту ISO c++ 11. Отключение этого параметра отключает неявные действия **`noexcept`** для определяемых пользователем деструкторов и деаллоакаторс и специальных функций-членов, определенных компилятором.

## <a name="syntax"></a>Синтаксис

> **/Zc: implicitNoexcept**[ **-** ]

## <a name="remarks"></a>Примечания

**/Zc: implicitNoexcept** указывает компилятору следовать разделу 15,4 стандарта ISO c++ 11. Он неявно добавляет **`noexcept`** описатель исключения к каждой явно объявленной или явно заданной по умолчанию специальной функции-члену (конструктор по умолчанию, конструктор копирования, конструктор перемещения, деструктор, оператор присваивания копирования или оператор присваивания перемещения), а также каждый определяемый пользователем деструктор или функцию дераспределения. Определяемый пользователем метод освобождения содержит неявный описатель исключения `noexcept(true)`. Для пользовательских деструкторов неявный описатель исключение — `noexcept(true)`, если во внутреннем классе члена или базовом классе нет деструктора, отличного от типа `noexcept(true)`. Если для созданных компилятором специальных функций-членов любая функция, вызываемая напрямую этой функцией, фактически является `noexcept(false)`, а неявный описатель исключения — `noexcept(false)`. Иначе неявный описатель исключение — `noexcept(true)`.

Компилятор не создает неявный спецификатор исключения для функций, объявленных с помощью явных **`noexcept`** или **`throw`** описателей или `__declspec(nothrow)` атрибута.

По умолчанию параметр **/Zc: implicitNoexcept** включен. Параметр [/permissive-](permissive-standards-conformance.md) не влияет на **/Zc: implicitNoexcept**.

Если параметр отключен путем указания **/Zc: implicitNoexcept-**, компилятор не создает неявных описателей исключений. Это поведение аналогично Visual Studio 2013, где деструкторы и дераспределительы, у которых нет описателей исключений, могут иметь **`throw`** инструкции. По умолчанию и при указании параметра **/Zc: implicitNoexcept** , если **`throw`** инструкция обнаруживается во время выполнения в функции с неявным `noexcept(true)` описателем, это приводит к немедленному вызову `std::terminate` и нормальному раскрутке обработчиков исключений. Чтобы определить ситуацию, компилятор создает [Предупреждение компилятора (уровень 1) C4297](../../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md). Если **`throw`** это намеренно, мы рекомендуем изменить объявление функции, чтобы `noexcept(false)` вместо параметра **/Zc: implicitNoexcept-**.

В этом примере показано, как определяемый пользователем деструктор, который не имеет явного описателя исключений, ведет себя, если параметр **/Zc: implicitNoexcept** установлен или отключен. Чтобы отобразить поведение при установке, Скомпилируйте с помощью `cl /EHsc /W4 implicitNoexcept.cpp` . Чтобы отобразить поведение при отключении, Скомпилируйте с помощью `cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp` .

```cpp
// implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 implicitNoexcept.cpp
// Compile by using: cl /EHsc /W4 /Zc:implicitNoexcept- implicitNoexcept.cpp

#include <iostream>
#include <cstdlib>      // for std::exit, EXIT_FAILURE, EXIT_SUCCESS
#include <exception>    // for std::set_terminate

void my_terminate()
{
    std::cout << "Unexpected throw caused std::terminate" << std::endl;
    std::cout << "Exit returning EXIT_FAILURE" << std::endl;
    std::exit(EXIT_FAILURE);
}

struct A {
    // Explicit noexcept overrides implicit exception specification
    ~A() noexcept(false) {
        throw 1;
    }
};

struct B : public A {
    // Compiler-generated ~B() definition inherits noexcept(false)
    ~B() = default;
};

struct C {
    // By default, the compiler generates an implicit noexcept(true)
    // specifier for this user-defined destructor. To enable it to
    // throw an exception, use an explicit noexcept(false) specifier,
    // or compile by using /Zc:implicitNoexcept-
    ~C() {
        throw 1; // C4297, calls std::terminate() at run time
    }
};

struct D : public C {
    // This destructor gets the implicit specifier of its base.
    ~D() = default;
};

int main()
{
    std::set_terminate(my_terminate);

    try
    {
        {
            B b;
        }
    }
    catch (...)
    {
        // exception should reach here in all cases
        std::cout << "~B Exception caught" << std::endl;
    }
    try
    {
        {
            D d;
        }
    }
    catch (...)
    {
        // exception should not reach here if /Zc:implicitNoexcept
        std::cout << "~D Exception caught" << std::endl;
    }
    std::cout << "Exit returning EXIT_SUCCESS" << std::endl;
    return EXIT_SUCCESS;
}
```

При компиляции с использованием параметра **/Zc: implicitNoexcept**по умолчанию пример создает следующий результат:

```Output
~B Exception caught
Unexpected throw caused std::terminate
Exit returning EXIT_FAILURE
```

При компиляции с помощью параметра **/Zc: implicitNoexcept-**, образец создает следующие выходные данные:

```Output
~B Exception caught
~D Exception caught
Exit returning EXIT_SUCCESS
```

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** , чтобы включить **/Zc: implicitNoexcept** или **/Zc: ImplicitNoexcept-** и нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также статью

[/Zc (соответствие)](zc-conformance.md)<br/>
[noexcept](../../cpp/noexcept-cpp.md)<br/>
[Спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[заканчива](../../standard-library/exception-functions.md#terminate)<br/>
