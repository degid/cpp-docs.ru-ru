---
title: Поддержка признаков типов компилятором (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- __is_simple_value_class
- __has_trivial_destructor
- __has_assign
- __is_union
- __is_class
- __is_abstract
- __has_trivial_assign
- __has_virtual_destructor
- __is_ref_array
- __is_base_of
- __has_copy
- __is_polymorphic
- __has_nothrow_constructor
- __is_ref_class
- __is_delegate
- __is_convertible_to
- __is_value_class
- __is_interface_class
- __has_nothrow_copy
- __is_sealed
- __has_trivial_constructor
- __has_trivial_copy
- __is_enum
- __has_nothrow_assign
- __has_finalizer
- __is_empty
- __is_pod
- __has_user_destructor
helpviewer_keywords:
- __is_class keyword [C++]
- __is_pod keyword [C++]
- __is_delegate keyword [C++]
- __is_value_class keyword [C++]
- __has_copy keyword [C++]
- __has_nothrow_copy keyword [C++]
- __is_interface_class keyword [C++]
- __is_sealed keyword [C++]
- __is_convertible_to keyword [C++]
- __is_ref_class keyword [C++]
- __has_trivial_copy keyword [C++]
- __has_user_destructor keyword [C++]
- __is_abstract keyword [C++]
- __is_empty keyword [C++]
- __has_trivial_assign keyword [C++]
- __has_nothrow_constructor keyword [C++]
- __is_ref_array keyword [C++]
- __is_base_of keyword [C++]
- __has_nothrow_assign keyword [C++]
- __has_virtual_destructor keyword [C++]
- __has_finalizer keyword [C++]
- __is_union keyword [C++]
- __has_assign keyword [C++]
- __has_trivial_destructor keyword [C++]
- __is_polymorphic keyword [C++]
- __is_enum keyword [C++]
- __is_simple_value_class keyword [C++]
- __has_trivial_constructor keyword [C++]
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
ms.openlocfilehash: 16c79e05c6ba6f50a3e6c0d6dd5f48963be40fa8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219785"
---
# <a name="compiler-support-for-type-traits-ccli-and-ccx"></a>Поддержка признаков типов компилятором (C++/CLI и C++/CX)

Компилятор C++ Microsoft поддерживает *признаки типов* для расширений C++/CLI и C++/CX, которые указывают различные характеристики типов во время компиляции.

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="remarks"></a>Примечания

Признаки типов особенно важны для программистов, создающих библиотеки.

В следующем списке перечислены признаки типов, поддерживаемые компилятором. Все признаки типов возвращают, **`false`** Если условие, заданное именем типа, не выполнено.

(В списке ниже примеры кода представлены только на C++/CLI. Но соответствующий признак типа также поддерживается в C++/CX, если не указано иное. Термин "тип платформы" относится к типам среды выполнения Windows или типам среды CLR).

- `__has_assign(`*тип*`)`

   Возвращает **`true`** , если платформа или собственный тип имеет оператор присваивания копии.

    ```cpp
    ref struct R {
    void operator=(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_assign(R));
    }
    ```

- `__has_copy(`*тип*`)`

   Возвращает **`true`** , если платформа или собственный тип имеет конструктор копии.

    ```cpp
    ref struct R {
    R(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_copy(R));
    }
    ```

- `__has_finalizer(`*тип*`)`

   (Не поддерживается в C++/CX.) Возвращает значение **`true`** , если тип CLR имеет метод завершения. Дополнительные сведения см. [в статье деструкторы и методы завершения в разделе как определить и использовать классы и структуры (C++/CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) .

    ```cpp
    using namespace System;
    ref struct R {
    ~R() {}
    protected:
    !R() {}
    };

    int main() {
    Console::WriteLine(__has_finalizer(R));
    }
    ```

- `__has_nothrow_assign(`*тип*`)`

   Возвращает **`true`** , если оператор присваивания копии имеет пустую спецификацию исключения.

    ```cpp
    #include <stdio.h>
    struct S {
    void operator=(S& r) throw() {}
    };

    int main() {
    __has_nothrow_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_constructor(`*тип*`)`

   Возвращает, **`true`** Если конструктор по умолчанию имеет пустую спецификацию исключений.

    ```cpp
    #include <stdio.h>
    struct S {
    S() throw() {}
    };

    int main() {
    __has_nothrow_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_copy(`*тип*`)`

   Возвращает, **`true`** Если конструктор копии имеет пустую спецификацию исключения.

    ```cpp
    #include <stdio.h>
    struct S {
    S(S& r) throw() {}
    };

    int main() {
    __has_nothrow_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_assign(`*тип*`)`

   Возвращает **`true`** , если тип имеет простой, сформированный компилятором оператор присваивания.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_constructor(`*тип*`)`

   Возвращает **`true`** , если тип имеет простой конструктор, созданный компилятором.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_copy(`*тип*`)`

   Возвращает **`true`** , если тип имеет простой конструктор копии, созданный компилятором.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_destructor(`*тип*`)`

   Возвращает **`true`** , если тип имеет простой, созданный компилятором деструктор.

    ``` cpp
    // has_trivial_destructor.cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_user_destructor(`*тип*`)`

   Возвращает **`true`** , если платформа или собственный тип имеет объявленный пользователем деструктор.

    ```cpp
    // has_user_destructor.cpp

    using namespace System;
    ref class R {
    ~R() {}
    };

    int main() {
    Console::WriteLine(__has_user_destructor(R));
    }
    ```

- `__has_virtual_destructor(`*тип*`)`

   Возвращает **`true`** , если тип имеет виртуальный деструктор.

   Признак `__has_virtual_destructor` также работает с типами платформ, и любой определенный пользователем деструктор в типе платформы является виртуальным деструктором.

    ```cpp
    // has_virtual_destructor.cpp
    #include <stdio.h>
    struct S {
    virtual ~S() {}
    };

    int main() {
    __has_virtual_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_abstract(`*тип*`)`

   Возвращает, **`true`** Если тип является абстрактным типом. Дополнительные сведения о собственных абстрактных типах см. в статье [Abstract Classes](../cpp/abstract-classes-cpp.md) (Абстрактные типы (C++)).

   Признак `__is_abstract` также работает с типами платформ. Интерфейс хотя бы с одним членом является абстрактным типом, как и ссылочный тип по крайней мере с одним абстрактным членом. Дополнительные сведения об абстрактных типах платформ см. в статье [abstract (C++/CLI and C++/CX)](abstract-cpp-component-extensions.md) (abstract (C++/CLI и C++/CX)).

    ```cpp
    // is_abstract.cpp
    #include <stdio.h>
    struct S {
    virtual void Test() = 0;
    };

    int main() {
    __is_abstract(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_base_of(` `base` `,` `derived` `)`

   Возвращает **`true`** , если первый тип является базовым классом второго типа, если оба типа совпадают.

   Признак `__is_base_of` также работает с типами платформ. Например, он возвратит, **`true`** Если первый тип является [классом интерфейса](interface-class-cpp-component-extensions.md) , а второй тип реализует интерфейс.

    ```cpp
    // is_base_of.cpp
    #include <stdio.h>
    struct S {};
    struct T : public S {};

    int main() {
    __is_base_of(S, T) == true ?
    printf("true\n") : printf("false\n");

    __is_base_of(S, S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_class(`*тип*`)`

   Возвращает, **`true`** Если тип является машинным классом или структурой.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_class(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_convertible_to(` `from` `,`  `to` `)`

   Возвращает, **`true`** Если первый тип можно преобразовать во второй тип.

    ```cpp
    #include <stdio.h>
    struct S {};
    struct T : public S {};

    int main() {
    S * s = new S;
    T * t = new T;
    s = t;
    __is_convertible_to(T, S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_delegate(`*тип*`)`

   Возвращает, **`true`** Если `type` является делегатом. Дополнительные сведения см. в статье [delegate (C++/CLI and C++/CX)](delegate-cpp-component-extensions.md).

    ```cpp
    delegate void MyDel();
    int main() {
    System::Console::WriteLine(__is_delegate(MyDel));
    }
    ```

- `__is_empty(`*тип*`)`

   Возвращает **`true`** , если тип не имеет членов данных экземпляра.

    ```cpp
    #include <stdio.h>
    struct S {
    int Test() {}
    static int i;
    };
    int main() {
    __is_empty(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_enum(`*тип*`)`

   Возвращает, **`true`** Если тип является машинным перечислением.

    ```cpp
    // is_enum.cpp
    #include <stdio.h>
    enum E { a, b };

    struct S {
    enum E2 { c, d };
    };

    int main() {
    __is_enum(E) == true ?
    printf("true\n") : printf("false\n");

    __is_enum(S::E2) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_interface_class(`*тип*`)`

   Возвращает **`true`** , если передан интерфейс платформы. Дополнительные сведения см. в статье [interface class](interface-class-cpp-component-extensions.md).

    ```cpp
    // is_interface_class.cpp

    using namespace System;
    interface class I {};
    int main() {
    Console::WriteLine(__is_interface_class(I));
    }
    ```

- `__is_pod(`*тип*`)`

   Возвращает **`true`** , если тип является классом или объединением без конструктора или закрытыми или защищенными нестатическими членами, без базовых классов и без виртуальных функций. Дополнительные сведения о POD см. в разделах 8.5.1/1, 9/4 и 3.9/10 стандарта C++.

   Для фундаментальных типов признак `__is_pod` возвращает значение false.

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_pod(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_polymorphic(`*тип*`)`

   Возвращает значение **`true`** , если собственный тип содержит виртуальные функции.

    ```cpp
    #include <stdio.h>
    struct S {
    virtual void Test(){}
    };

    int main() {
    __is_polymorphic(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_ref_array(`*тип*`)`

   Возвращает значение **`true`** , если передается массив платформы. Дополнительные сведения см. в статье [Arrays (C++/CLI and C++/CX)](arrays-cpp-component-extensions.md) (Массивы (C++/CLI и C++/CX)).

    ```cpp
    using namespace System;
    int main() {
    array<int>^ x = gcnew array<int>(10);
    Console::WriteLine(__is_ref_array(array<int>));
    }
    ```

- `__is_ref_class(`*тип*`)`

   Возвращает **`true`** , если передан ссылочный класс. Дополнительные сведения об определяемых пользователем ссылочных типах см. в статье [ref class and ref struct (C++/CLI and C++/CX)](classes-and-structs-cpp-component-extensions.md) (ref class и ref struct (C++/CLI и C++/CX)).

    ```cpp
    using namespace System;
    ref class R {};
    int main() {
    Console::WriteLine(__is_ref_class(Buffer));
    Console::WriteLine(__is_ref_class(R));
    }
    ```

- `__is_sealed(`*тип*`)`

   Возвращает значение **`true`** , если передается платформа или собственный тип, помеченный как Sealed. Дополнительные сведения см. в статье [sealed (C++/CLI and C++/CX)](sealed-cpp-component-extensions.md).

    ```cpp
    ref class R sealed{};
    int main() {
    System::Console::WriteLine(__is_sealed(R));
    }
    ```

- `__is_simple_value_class(`*тип*`)`

   Возвращает **`true`** значение, если передается тип значения, не содержащий ссылок на кучу, в которой создается мусор. Дополнительные сведения об определяемых пользователем типах значений см. в статье [ref class and ref struct (C++/CLI and C++/CX)](classes-and-structs-cpp-component-extensions.md) (ref class и ref struct (C++/CLI и C++/CX)).

    ```cpp
    using namespace System;
    ref class R {};
    value struct V {};
    value struct V2 {
    R ^ r;   // not a simnple value type
    };

    int main() {
    Console::WriteLine(__is_simple_value_class(V));
    Console::WriteLine(__is_simple_value_class(V2));
    }
    ```

- `__is_union(`*тип*`)`

   Возвращает значение, **`true`** Если тип является объединением.

    ```cpp
    #include <stdio.h>
    union A {
    int i;
    float f;
    };

    int main() {
    __is_union(A) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_value_class(`*тип*`)`

   Возвращает **`true`** , если передан тип значения. Дополнительные сведения об определяемых пользователем типах значений см. в статье [ref class and ref struct (C++/CLI and C++/CX)](classes-and-structs-cpp-component-extensions.md) (ref class и ref struct (C++/CLI и C++/CX)).

    ```cpp
    value struct V {};

    int main() {
    System::Console::WriteLine(__is_value_class(V));
    }
    ```

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="remarks"></a>Примечания

`__has_finalizer(` *type* `)` Характеристика типа типа не поддерживается, так как эта платформа не поддерживает методы завершения.

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

### <a name="remarks"></a>Примечания

(Отсутствуют комментарии для данной возможности в рамках этой платформы).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

**Пример**

В следующем примере кода показано использование шаблона класса для предоставления признака типа компилятора при компиляции `/clr`. Дополнительные сведения см. в статье [Windows Runtime and Managed Templates (C++/CLI and C++/CX)](windows-runtime-and-managed-templates-cpp-component-extensions.md) (Среда выполнения Windows и управляемые шаблоны (C++/CLI и C++/CX)).

```cpp
// compiler_type_traits.cpp
// compile with: /clr
using namespace System;

template <class T>
ref struct is_class {
   literal bool value = __is_ref_class(T);
};

ref class R {};

int main () {
   if (is_class<R>::value)
      Console::WriteLine("R is a ref class");
   else
      Console::WriteLine("R is not a ref class");
}
```

```Output
R is a ref class
```

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
