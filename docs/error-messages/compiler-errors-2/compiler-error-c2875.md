---
title: "Ошибка компилятора C2875 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2875
dev_langs:
- C++
helpviewer_keywords:
- C2875
ms.assetid: d589fc0c-08b2-4a79-bc0e-dca5eb80bdd5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2e4a6a509bd445b5d3acda538e92d5d4c6b42a6f
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2875"></a>Ошибка компилятора C2875
using объявление вызвало наличие нескольких объявлений для «класс::идентификатор»  
  
 Объявление вызывает один и тот же элемент дважды определен.  
  
 Следующий пример приводит к возникновению ошибки C2875:  
  
```  
// C2875.cpp  
struct A {  
   void f(int*);  
};  
  
struct B {  
   void f(double*);  
};  
  
struct AB : A, B {  
   using A::f;  
   using A::f;   // C2875  
   using B::f;  
};  
```