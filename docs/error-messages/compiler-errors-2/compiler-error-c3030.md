---
title: "Ошибка компилятора C3030 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3030
dev_langs:
- C++
helpviewer_keywords:
- C3030
ms.assetid: de92fd7e-29ba-46e8-b43b-f4b985cd74de
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 472ff7495ab0e57f7aa9d03ea060faa813e20228
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3030"></a>Ошибка компилятора C3030
"переменная": переменная в предложении или директиве "reduction" не может быть ссылочного типа  
  
 Вы можете передавать параметры значений только в некоторые предложения, такие как предложение reduction.  
  
 Следующий пример приводит к возникновению ошибки C3030:  
  
```  
// C3030.cpp  
// compile with: /openmp /link vcomps.lib  
#include "omp.h"  
  
void test(int &r) {  
   #pragma omp parallel reduction(+ : r)   // C3030  
      ;  
}  
  
void test2(int r) {  
   #pragma omp parallel reduction(+ : r)   // OK  
      ;  
}  
  
int main(int argc, char** argv) {  
   int& r = *((int*)argv);  
   int s = *((int*)argv);  
  
   #pragma omp parallel reduction(+ : r)   // C3030  
      ;  
  
   #pragma omp parallel reduction(+ : s)   // OK  
      ;  
}  
```