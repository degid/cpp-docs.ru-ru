---
title: "multimap::Swap (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::multimap::swap
dev_langs: C++
helpviewer_keywords: swap member [STL/CLR]
ms.assetid: 198018d2-7814-4237-8ec3-5f3ea950e8af
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 848203f896f8693bfc1bf4437f958fc64eb2f267
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="multimapswap-stlclr"></a>multimap::swap (STL/CLR)
Меняет местами содержимое двух контейнеров.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void swap(multimap<Key, Mapped>% right);  
```  
  
#### <a name="parameters"></a>Параметры  
 right  
 Контейнер для обмена содержимым.  
  
## <a name="remarks"></a>Примечания  
 Функция-член меняет местами управляемые последовательности между `this` и `right`. Она делает это в константном времени, и он не создает исключений. Используется в качестве быстро меняет местами содержимое двух контейнеров.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_multimap_swap.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    Mymultimap c2;   
    c2.insert(Mymultimap::make_value(L'd', 4));   
    c2.insert(Mymultimap::make_value(L'e', 5));   
    c2.insert(Mymultimap::make_value(L'f', 6));   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
[d 4] [e 5] [f 6]  
[d 4] [e 5] [f 6]  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [несколько карт (STL/CLR)](../dotnet/multimap-stl-clr.md)   
 [multimap::operator= (STL/CLR)](../dotnet/multimap-operator-assign-stl-clr.md)