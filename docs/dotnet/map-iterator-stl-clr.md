---
title: "MAP::iterator (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::map::iterator
dev_langs: C++
helpviewer_keywords: iterator member [STL/CLR]
ms.assetid: b2953b9b-0e6d-49f3-a28f-47d04d16d5f6
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b34c5d93fffd236cd16843fd074b5c1b8181c4b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="mapiterator-stlclr"></a>map::iterator (STL/CLR)
Тип итератора для управляемой последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef T1 iterator;  
```  
  
## <a name="remarks"></a>Примечания  
 Тип описывает объект незаданного типа `T1` , можно использовать в качестве двунаправленного итератора для управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_map_iterator.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    Mymap::iterator it = c1.begin();   
    for (; it != c1.end(); ++it)   
        System::Console::Write(" [{0} {1}]", it->first, it->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
[a 1] [b 2] [c 3]  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/map >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [Карта (STL/CLR)](../dotnet/map-stl-clr.md)   
 [map::const_iterator (STL/CLR)](../dotnet/map-const-iterator-stl-clr.md)