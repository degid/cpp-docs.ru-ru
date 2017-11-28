---
title: "Ошибка компилятора C3913 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3913
dev_langs:
- C++
helpviewer_keywords:
- C3913
ms.assetid: a678bfce-9524-470d-9f23-7d08ecb972c8
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ad34e5b74be2b19d0638f6f4b42b6f3a0cf4ab78
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3913"></a>Ошибка компилятора C3913
свойство по умолчанию должно быть индексировано  
  
 Было неправильно задано свойство по умолчанию.  
  
 Дополнительные сведения см. в разделе [property](../../windows/property-cpp-component-extensions.md).  
  
 Следующий пример приводит к возникновению ошибки C3913:  
  
```  
// C3913.cpp  
// compile with: /clr /c  
ref struct X {  
   property int default {   // C3913  
   // try the following line instead  
   // property int default[int] {  
      int get(int) { return 0; }  
      void set(int, int) {}  
   }  
};  
```