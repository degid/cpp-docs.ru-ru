---
title: Практическое руководство. Загрузка неуправляемых ресурсов в массив байтов
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- native resources, loading into Byte array
- unmanaged resources, loading into Byte array
- native resources
ms.assetid: cdada6cd-6d42-437a-a90f-44a0b18d6a93
ms.openlocfilehash: b2b98ff3c4bbd857e3f5d861c1e0e8e2bd2f357b
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685809"
---
# <a name="how-to-load-unmanaged-resources-into-a-byte-array"></a>Практическое руководство. Загрузка неуправляемых ресурсов в массив байтов

В этом разделе обсуждается несколько способов загрузки неуправляемых ресурсов в <xref:System.Byte> массив.

## <a name="examples"></a>Примеры

Если вы знакомы с размером неуправляемого ресурса, можно предварительно выделить массив CLR, а затем загрузить ресурс в массив с помощью указателя на блок массива в массиве CLR.

```cpp
// load_unmanaged_resources_into_Byte_array.cpp
// compile with: /clr
using namespace System;
void unmanaged_func( unsigned char * p ) {
   for ( int i = 0; i < 10; i++ )
      p[ i ] = i;
}

public ref class A {
public:
   void func() {
      array<Byte> ^b = gcnew array<Byte>(10);
      pin_ptr<Byte> p =  &b[ 0 ];
      Byte * np = p;
      unmanaged_func( np );   // pass pointer to the block of CLR array.
      for ( int i = 0; i < 10; i++ )
         Console::Write( b[ i ] );
      Console::WriteLine();
   }
};

int main() {
   A^ g = gcnew A;
   g->func();
}
```

```Output
0123456789
```

В этом примере показано, как скопировать данные из неуправляемого блока памяти в управляемый массив.

```cpp
// load_unmanaged_resources_into_Byte_array_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#include <string.h>
int main() {
   char buf[] = "Native String";
   int len = strlen(buf);
   array<Byte> ^byteArray = gcnew array<Byte>(len + 2);

   // convert any native pointer to IntPtr by doing C-Style cast
   Marshal::Copy( (IntPtr)buf, byteArray, 0, len );
}
```

## <a name="see-also"></a>См. также

[Использование взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
