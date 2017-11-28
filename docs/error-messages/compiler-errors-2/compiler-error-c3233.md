---
title: "Ошибка компилятора C3233 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3233
dev_langs:
- C++
helpviewer_keywords:
- C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d3d29fbfb33a0697120fa0386d94f4023360abd1
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3233"></a>Ошибка компилятора C3233
"тип": параметр универсального типа уже ограничен  
  
 Ограничение универсального параметра в нескольких предложениях `where` недопустимо.  
  
 Следующий пример приводит к возникновению ошибки C3233:  
  
```  
// C3233.cpp  
// compile with: /clr /LD  
  
interface struct C {};  
interface struct D {};  
  
generic <class T>  
where T : C  
where T : D  
ref class E {};   // C3233  
```