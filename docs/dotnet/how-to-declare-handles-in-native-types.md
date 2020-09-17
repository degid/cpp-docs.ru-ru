---
title: Практическое руководство. Объявление дескрипторов в собственных типах
ms.custom: get-started-article
ms.date: 11/04/2016
f1_keywords:
- gcroot
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
ms.openlocfilehash: 1aca21402122a0c8641a7e57ace2a3477ff96f01
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221345"
---
# <a name="how-to-declare-handles-in-native-types"></a>Практическое руководство. Объявление дескрипторов в собственных типах

Нельзя объявить тип обработчика в собственном типе. вкклр.h предоставляет шаблон строгой оболочки `gcroot` для ссылки на объект CLR из кучи C++. Этот шаблон позволяет внедрить виртуальный обработчик в собственный тип и обрабатывать его как базовый тип. В большинстве случаев объект можно использовать `gcroot` как внедренный тип без приведения. Однако при использовании [for each в](../dotnet/for-each-in.md)необходимо использовать **`static_cast`** для получения базовой управляемой ссылки.

`gcroot`Шаблон реализуется с помощью средств класса значения System:: Runtime:: InteropServices:: GCHandle, который предоставляет "Handles" в кучу, в которой выполняется сборка мусора. Обратите внимание, что сами дескрипторы не собираются и освобождаются, если они больше не используются деструктором в `gcroot` классе (этот деструктор не может быть вызван вручную). При создании экземпляра `gcroot` объекта в собственной куче необходимо вызвать метод Delete для этого ресурса.

Среда выполнения будет поддерживать связь между маркером и объектом CLR, на который он ссылается. Когда объект CLR перемещается вместе с кучей со сбором мусора, этот обработчик возвращает новый адрес объекта. Переменная не обязательно должна быть закреплена, прежде чем она будет назначена `gcroot` шаблону.

## <a name="example"></a>Пример

В этом примере показано, как создать `gcroot` объект в собственном стеке.

```cpp
// mcpp_gcroot.cpp
// compile with: /clr
#include <vcclr.h>
using namespace System;

class CppClass {
public:
   gcroot<String^> str;   // can use str as if it were String^
   CppClass() {}
};

int main() {
   CppClass c;
   c.str = gcnew String("hello");
   Console::WriteLine( c.str );   // no cast required
}
```

```Output
hello
```

## <a name="example"></a>Пример

В этом примере показано, как создать `gcroot` объект в собственной куче.

```cpp
// mcpp_gcroot_2.cpp
// compile with: /clr
// compile with: /clr
#include <vcclr.h>
using namespace System;

struct CppClass {
   gcroot<String ^> * str;
   CppClass() : str(new gcroot<String ^>) {}

   ~CppClass() { delete str; }

};

int main() {
   CppClass c;
   *c.str = gcnew String("hello");
   Console::WriteLine( *c.str );
}
```

```Output
hello
```

## <a name="example"></a>Пример

В этом примере показано, как использовать `gcroot` для хранения ссылок на типы значений (не ссылочные типы) в собственном типе с помощью `gcroot` в упакованном типе.

```cpp
// mcpp_gcroot_3.cpp
// compile with: /clr
#include < vcclr.h >
using namespace System;

public value struct V {
   String^ str;
};

class Native {
public:
   gcroot< V^ > v_handle;
};

int main() {
   Native native;
   V v;
   native.v_handle = v;
   native.v_handle->str = "Hello";
   Console::WriteLine("String in V: {0}", native.v_handle->str);
}
```

```Output
String in V: Hello
```

## <a name="see-also"></a>См. также раздел

[Использование взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
