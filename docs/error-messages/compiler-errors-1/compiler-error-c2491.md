---
title: "Ошибка компилятора C2491 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2491
dev_langs:
- C++
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 83b369d72b4d2ed296f6abeb68cc69b8c233326e
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2491"></a>Ошибка компилятора C2491
'идентификатор' : определение функции dllimport не разрешено  
  
 Данные, статические данные-члены могут быть объявлены, как `dllimport`, но не определены как `dllimport`.  
  
 Чтобы устранить эту проблему, удалите описатель `__declspec(dllimport)` из определения функции.  
  
 Следующий пример приводит к возникновению ошибки C2491:  
  
```  
// C2491.cpp  
// compile with: /c  
// function definition  
void __declspec(dllimport) funcB() {}   // C2491  
  
// function declaration  
void __declspec(dllimport) funcB();   // OK  
```