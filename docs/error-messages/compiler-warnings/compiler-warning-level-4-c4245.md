---
title: "Предупреждение (уровень 4) C4245 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4245
dev_langs: C++
helpviewer_keywords: C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8e6e369717c6133d49de0a44a625b251ddf671cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4245"></a>Предупреждение компилятора (уровень 4) C4245
«Преобразование»: преобразование из «тип1» в «тип2», несоответствие со знаком и без  
  
 Предпринята попытка преобразовать со знаком **const** , имеет отрицательное значение для `unsigned`.  
  
 Следующий пример приводит к возникновению ошибки C4245:  
  
```  
// C4245.cpp  
// compile with: /W4 /c  
const int i = -1;  
unsigned int j = i; // C4245  
  
const int k = 1;  
unsigned int l = k; // okay  
  
int m = -1;  
unsigned int n = m; // okay  
  
void Test(size_t i) {}  
  
int main() {  
   Test( -19 );   // C4245  
}  
```