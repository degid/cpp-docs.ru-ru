---
title: "Ошибка компилятора C2911 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2911
dev_langs: C++
helpviewer_keywords: C2911
ms.assetid: 83c7c01a-ab6a-4179-9fb0-289a9ec8d44e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3f37aae72a38ecdf89da2a47683cc6e1c8f3ea9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2911"></a>Ошибка компилятора C2911
"член": невозможно объявить или определить в текущей области  
  
 В пределах пространства имен, класса или функции можно определять только члены, принадлежащие этим объектам или включаемые ими.  
  
 Следующий пример приводит к возникновению ошибки C2911:  
  
```  
// C2911.cpp  
struct A;  
  
namespace M {  
   struct D;  
}  
  
namespace N {  
   struct C;  
  
   namespace O {  
      struct B;  
   }  
  
   // in N  
   struct ::A {};   // C2911  A is member of global NS  
   struct O::B{};   // OK B is in O, O is inside of N  
   struct C {};     // OK C is member of N  
   struct M::D {};  // C2911 D is member of M, M not enclosed by N  
}  
```