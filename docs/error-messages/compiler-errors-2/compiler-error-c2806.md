---
title: "Ошибка компилятора C2806 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2806
dev_langs:
- C++
helpviewer_keywords:
- C2806
ms.assetid: 7c9ff1f4-1590-4c47-991d-b1075a173b48
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ddecb9434866d65bffba30bf7728ce82e84d6b46
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2806"></a>Ошибка компилятора C2806
«оператор» имеет слишком много формальных параметров  
  
 Перегруженный оператор имеет слишком много параметров.  
  
 Следующий пример приводит к возникновению ошибки C2806:  
  
```  
// C2806.cpp  
// compile with: /c  
class X {  
public:  
   X operator++ ( int, int );   // C2806 more than 1 parameter  
   X operator++ ( int );   // OK  
} ;  
```