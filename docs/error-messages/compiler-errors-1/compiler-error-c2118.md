---
title: "Ошибка компилятора C2118 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2118
dev_langs: C++
helpviewer_keywords: C2118
ms.assetid: bf4315d0-f085-4323-b813-96ee61a13bde
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d09ed769975b522b0b881148ed684a99552bb099
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2118"></a>Ошибка компилятора C2118
отрицательный индекс  
  
 Значение, определяющее размер массива, размер которых превышает максимальный размер массива или меньше нуля.  
  
 Следующий пример приводит к возникновению ошибки C2118:  
  
```  
// C2118.cpp  
int main() {  
   int array1[-1];   // C2118  
   int array2[3];   // OK  
}  
```