---
title: "Ошибка компилятора C2400 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2400
dev_langs:
- C++
helpviewer_keywords:
- C2400
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b819c81a3475a541fb672094bbdfa62b2fcfe6d6
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2400"></a>Ошибка компилятора C2400
Синтаксическая ошибка во встроенном ассемблерном коде в «context»; найден «токен»  
  
 Токен является причиной синтаксической ошибки в указанном контексте.  
  
 Следующий пример приводит к возникновению ошибки C2400:  
  
```  
// C2400.cpp  
// processor: x86  
int main() {  
   __asm {  
      heh ax,bx;   // C2400, heh is not a valid x86 instruction  
      mov ax,bx;   // OK  
   }  
}  
```