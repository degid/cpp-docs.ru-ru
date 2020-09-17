---
title: Практическое руководство. Хранение ссылки на объект в неуправляемой памяти
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
ms.openlocfilehash: 2f2471e36d7551cab9edb68d7babeb1419e8e20c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544955"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>Практическое руководство. Хранение ссылки на объект в неуправляемой памяти

Можно использовать gcroot.h, который заключает в оболочку <xref:System.Runtime.InteropServices.GCHandle>для хранения ссылки на объект CLR в неуправляемой памяти. Кроме того, можно использовать `GCHandle` напрямую.

## <a name="example"></a>Пример

```cpp
// hold_object_reference.cpp
// compile with: /clr
#include "gcroot.h"
using namespace System;

#pragma managed
class StringWrapper {

private:
   gcroot<String ^ > x;

public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      x = str;
   }

   void PrintString() {
      String ^ targetStr = x;
      Console::WriteLine("StringWrapper::x == {0}", targetStr);
   }
};
#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::x == ManagedString
```

## <a name="example"></a>Пример

`GCHandle` предоставляет средства для хранения ссылки на управляемый объект в неуправляемой памяти.  Метод <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> используется для создания непрозрачного маркера для управляемого объекта и <xref:System.Runtime.InteropServices.GCHandle.Free%2A> для его освобождения. Кроме того, метод <xref:System.Runtime.InteropServices.GCHandle.Target%2A> позволяет получить ссылку на объект из обработчика в управляемом коде.

```cpp
// hold_object_reference_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed
class StringWrapper {
   IntPtr m_handle;
public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));
   }
   ~StringWrapper() {
      static_cast<GCHandle>(m_handle).Free();
   }

   void PrintString() {
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);
   }
};

#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::m_handle == ManagedString
```

## <a name="see-also"></a>См. также:

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
