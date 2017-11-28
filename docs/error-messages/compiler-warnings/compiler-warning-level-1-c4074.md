---
title: "Предупреждение компилятора (уровень 1) C4074 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4074"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4074"
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4074
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

инициализаторы размещены в зарезервированной области инициализации компилятора  
  
 Область инициализации компилятора, задаваемая прагма\-директивой [\#pragma init\_seg](../../preprocessor/init-seg.md), зарезервирована для использования Майкрософт.  Код в этой области может выполняться перед инициализацией библиотеки времени выполнения C.  
  
 Следующий пример приводит к возникновению ошибки C4074:  
  
```  
// C4074.cpp  
// compile with: /W1  
#pragma init_seg( compiler )   // C4074  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```