---
title: "Vector::End (STL/CLR) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::end
dev_langs: C++
helpviewer_keywords: end member [STL/CLR]
ms.assetid: 21fcaf1b-7f14-4dc4-a312-fa30e631ea0d
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e78c21dee78b4cd5528d581972bcc690072b591c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="vectorend-stlclr"></a>vector::end (STL/CLR)
Задает конец управляемой последовательности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
iterator end();  
```  
  
## <a name="remarks"></a>Примечания  
 Функция-член возвращает итератор произвольного доступа, указывающий на место сразу за конец управляемой последовательности. Используется для получения итератора, который обозначает `current` конец управляемой последовательности, но его состояние можно изменить при изменении длины управляемой последовательности.  
  
## <a name="example"></a>Пример  
  
```  
// cliext_vector_end.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last two items   
    cliext::vector<wchar_t>::iterator it = c1.end();   
    --it;   
    System::Console::WriteLine("*-- --end() = {0}", *--it);   
    System::Console::WriteLine("*--end() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
*-- --end() = b  
*--end() = c  
 a x y  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<cliext/vector >  
  
 **Пространство имен:** cliext  
  
## <a name="see-also"></a>См. также  
 [вектор (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [Vector::Back (STL/CLR)](../dotnet/vector-back-stl-clr.md)   
 [Vector::back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)   
 [vector::begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md)