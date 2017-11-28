---
title: "Ошибка компилятора C3161 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4be981b2af166d85a3a83209a901f3e3e51b6246
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3161"></a>Ошибка компилятора C3161
«интерфейс»: вложенный класс, структура, объединение или интерфейс в интерфейсе недопустимы; недопустимо вложение интерфейса в класс, структура или объединение  
  
 [__Interface](../../cpp/interface.md) может появиться только в глобальной области видимости в пределах пространства имен. Класс, структура или объединение не может присутствовать в интерфейсе.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3161.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```