---
title: Практическое руководство. Преобразование строки System::String в стандартную строку
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, converting System::String to standard string
- string conversion, System::String
ms.assetid: 79e2537e-d4eb-459f-9506-0e738045b59e
ms.openlocfilehash: 7dd73b8fed98918135b66af1b6351977426cd26e
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545303"
---
# <a name="how-to-convert-systemstring-to-standard-string"></a>Практическое руководство. Преобразование строки System::String в стандартную строку

<xref:System.String> можно преобразовать в `std::string` или `std::wstring`без использования `PtrToStringChars` в Вкклр.h.

## <a name="example"></a>Пример

```cpp
// convert_system_string.cpp
// compile with: /clr
#include <string>
#include <iostream>
using namespace std;
using namespace System;

void MarshalString ( String ^ s, string& os ) {
   using namespace Runtime::InteropServices;
   const char* chars =
      (const char*)(Marshal::StringToHGlobalAnsi(s)).ToPointer();
   os = chars;
   Marshal::FreeHGlobal(IntPtr((void*)chars));
}

void MarshalString ( String ^ s, wstring& os ) {
   using namespace Runtime::InteropServices;
   const wchar_t* chars =
      (const wchar_t*)(Marshal::StringToHGlobalUni(s)).ToPointer();
   os = chars;
   Marshal::FreeHGlobal(IntPtr((void*)chars));
}

int main() {
   string a = "test";
   wstring b = L"test2";
   String ^ c = gcnew String("abcd");

   cout << a << endl;
   MarshalString(c, a);
   c = "efgh";
   MarshalString(c, b);
   cout << a << endl;
   wcout << b << endl;
}
```

```Output
test
abcd
efgh
```

## <a name="see-also"></a>См. также:

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
