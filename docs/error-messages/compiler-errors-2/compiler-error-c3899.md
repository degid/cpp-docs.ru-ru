---
title: "Ошибка компилятора C3899 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3899
dev_langs:
- C++
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c7d9d32b3063dbecde375159ad90eec5bf128d56
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3899"></a>Ошибка компилятора C3899
«переменная»: l значения можно использовать элементы данных initonly не разрешается напрямую в параллельной области в классе «класс»  
  
 [Initonly (C + +/ CLI)](../../dotnet/initonly-cpp-cli.md) член данных не может инициализироваться внутри этой части конструктора, которая расположена в [параллельных](../../parallel/openmp/reference/parallel.md) области.  Это, поскольку компилятор выполняет внутреннего перемещения этого кода, таким образом, что он является больше не является частью конструктора.  
  
 Чтобы решить, инициализируйте элемент данных initonly в конструкторе, но вне параллельной области.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3899.  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```