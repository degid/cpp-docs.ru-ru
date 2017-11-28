---
title: "Ошибка компилятора C3016 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3016
dev_langs: C++
helpviewer_keywords: C3016
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b2c0ee841f74294957a3fa5aae40f8d99d78748b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3016"></a>Ошибка компилятора C3016
"переменная": переменная индекса в операторе For директивы OpenMP должна иметь тип целого со знаком  
  
 Переменная индекса в операторе `for` директивы OpenMP должна иметь целочисленный тип со знаком.  
  
 Следующий пример приводит к возникновению ошибки C3016:  
  
```  
// C3016.cpp  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel  
   {  
      unsigned int i = 0;  
      // Try the following line instead:  
      // int i = 0;  
  
      #pragma omp for  
      for (i = 0; i <= 10; ++i)   // C3016  
      {  
      }  
   }  
}  
```