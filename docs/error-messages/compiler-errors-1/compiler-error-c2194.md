---
title: "Ошибка компилятора C2194 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2194
dev_langs: C++
helpviewer_keywords: C2194
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c78d61d4497e104380e38df19133b1578d01057d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2194"></a>Ошибка компилятора C2194
«Идентификатор»: является сегментом текста  
  
 `data_seg` Pragma использует имя сегмента с `code_seg`.  
  
 Следующий пример приводит к возникновению ошибки C2194:  
  
```  
// C2194.cpp  
// compile with: /c  
#pragma code_seg("MYCODE")  
#pragma data_seg("MYCODE")   // C2194  
#pragma data_seg("MYCODE2")   // OK  
```