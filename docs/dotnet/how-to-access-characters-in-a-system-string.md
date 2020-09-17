---
title: Практическое руководство. Доступ к символам объекта System::String
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
ms.openlocfilehash: cb62eb0fecbee202e4d01635a60da565241822ee
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686799"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Практическое руководство. Доступ к символам объекта System::String

Можно получить доступ к символам <xref:System.String> объекта для высокопроизводительных вызовов неуправляемых функций, принимающих `wchar_t*` строки. Метод возвращает внутренний указатель на первый символ <xref:System.String> объекта. Этот указатель можно манипулировать напрямую или закрепленным и передать в функцию, ожидающую обычную **`wchar_t`** строку.

## <a name="examples"></a>Примеры

`PtrToStringChars` Возвращает объект <xref:System.Char> , который является внутренним указателем (также известным как `byref` ). Таким образом, он подлежит сборке мусора. Вам не нужно закреплять этот указатель, если он не будет передан в собственную функцию.

Рассмотрим следующий код.  Закрепление не требуется `ppchar` , поскольку является внутренним указателем, и если сборщик мусора перемещает строку, на которую он указывает, он также будет обновлен `ppchar` . Без [pin_ptr (C++/CLI)](../extensions/pin-ptr-cpp-cli.md)код будет работать и не станет потенциальной производительностью, вызванной закреплением.

Если передать `ppchar` в собственную функцию, то он должен быть закрепленным указателем; сборщик мусора не сможет обновлять указатели в неуправляемом кадре стека.

```cpp
// PtrToStringChars.cpp
// compile with: /clr
#include<vcclr.h>
using namespace System;

int main() {
   String ^ mystring = "abcdefg";

   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );

   for ( ; *ppchar != L'\0'; ++ppchar )
      Console::Write(*ppchar);
}
```

```Output
abcdefg
```

В этом примере показано, где требуется закрепление.

```cpp
// PtrToStringChars_2.cpp
// compile with: /clr
#include <string.h>
#include <vcclr.h>
// using namespace System;

size_t getlen(System::String ^ s) {
   // Since this is an outside string, we want to be secure.
   // To be secure, we need a maximum size.
   size_t maxsize = 256;
   // make sure it doesn't move during the unmanaged call
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);
   return wcsnlen(pinchars, maxsize);
};

int main() {
   System::Console::WriteLine(getlen("testing"));
}
```

```Output
7
```

Внутренний указатель имеет все свойства собственного указателя C++. Например, его можно использовать для прохода по связанной структуре данных, а вставки и удаления — только с одним указателем:

```cpp
// PtrToStringChars_3.cpp
// compile with: /clr /LD
using namespace System;
ref struct ListNode {
   Int32 elem;
   ListNode ^ Next;
};

void deleteNode( ListNode ^ list, Int32 e ) {
   interior_ptr<ListNode ^> ptrToNext = &list;
   while (*ptrToNext != nullptr) {
      if ( (*ptrToNext) -> elem == e )
         *ptrToNext = (*ptrToNext) -> Next;   // delete node
      else
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node
   }
}
```

## <a name="see-also"></a>См. также

[Использование взаимодействия C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
