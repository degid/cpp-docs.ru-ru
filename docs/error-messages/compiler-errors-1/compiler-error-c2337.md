---
title: "Ошибка компилятора C2337 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2337
dev_langs:
- C++
helpviewer_keywords:
- C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4ca2d5a7108d181ee6e93e94119b945ed7b9da9f
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2337"></a>Ошибка компилятора C2337
"имя_атрибута": атрибут не найден  
  
 Используется атрибут, который не поддерживается в этой версии Visual C++.  
  
 Следующий пример приводит к возникновению ошибки C2337:  
  
```  
// C2337.cpp  
// compile with: /c  
[emitidl];  
[module(name="x")];  
[grasshopper]   // C2337, not a supported attribute  
class a{};  
```