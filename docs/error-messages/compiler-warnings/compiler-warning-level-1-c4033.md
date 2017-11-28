---
title: "Предупреждение (уровень 1) C4033 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4033
dev_langs:
- C++
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a215fef10e75a3686cbb04121d419cc0861d4a1e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4033"></a>Предупреждение компилятора (уровень 1) C4033
Функция "функция" должна возвращать значение  
  
 Функция не возвращает значение. Возвращается неопределенное значение.  
  
 Функции, использующие `return` без возвращаемого значения, должны объявляться с типом `void`.  
  
 Эта ошибка для кода на языке C.  
  
 Следующий пример приводит к возникновению ошибки C4033:  
  
```  
// C4033.c  
// compile with: /W1 /LD  
int test_1(int x)   // C4033 expected  
{  
   if (x)  
   {  
      return;   // C4033  
   }  
}  
```