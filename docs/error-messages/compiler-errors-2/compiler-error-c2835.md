---
title: "Ошибка компилятора C2835 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2835
dev_langs: C++
helpviewer_keywords: C2835
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 08a09c0ea495fcaff01527b0c4af720f2a831db5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2835"></a>Ошибка компилятора C2835
определенное пользователем преобразование «тип» не имеет формальных параметров  
  
 Определенные пользователем преобразования типа не могут принимать формальных параметров.  
  
 Следующий пример приводит к возникновению ошибки C2835:  
  
```  
// C2835.cpp  
class A {  
public:  
   char v_char;  
  
   A() {   
      v_char = 'A';   
   };  
   operator char(char a) {   // C2835  
   // try the following line instead  
   // operator char() {     
      return v_char + 1;   
   };  
};  
  
int main() {  
   A a;  
}  
```