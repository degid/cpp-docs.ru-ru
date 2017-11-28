---
title: "Предупреждение компилятора (уровень 4) C4100 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4100"
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор" : неиспользованный формальный параметр  
  
 Формальный параметр не используется в теле функции.  Неиспользованный параметр игнорируется.  
  
 Ошибка C4100 также может выводиться, когда код вызывает деструктор для неиспользованного параметра типа\-примитива.  Это ограничение компилятора Visual C\+\+.  
  
 Следующий пример приводит к возникновению ошибки C4100:  
  
```  
// C4100.cpp  
// compile with: /W4  
void func(int i) {   // C4100, delete the unreferenced parameter to  
                     //resolve the warning  
   // i;   // or, add a reference like this  
}  
  
int main()  
{  
   func(1);  
}  
```