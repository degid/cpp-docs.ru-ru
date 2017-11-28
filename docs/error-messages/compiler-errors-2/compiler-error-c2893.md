---
title: "Ошибка компилятора C2893 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2893
dev_langs: C++
helpviewer_keywords: C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6ad558968720a13b95fecc6860df5826b47874aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2893"></a>Ошибка компилятора C2893
Сбой при специализации шаблона функции «имя шаблона»  
  
 Сбой при специализации шаблона функции компилятор. Может быть много причин этой ошибки.  
  
 Как правило для устранения ошибки C2893 проще просмотрите сигнатуру функции и убедитесь, что можно создать экземпляры всех типов.  
  
## <a name="example"></a>Пример  
 C2893 возникает из-за `f`параметр шаблона `T` должен был быть `std::map<int,int>`, но `std::map<int,int>` не имеет члена `data_type` (`T::data_type` не может быть создан с `T = std::map<int,int>`.). Следующий пример приводит к возникновению ошибки C2893.  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```