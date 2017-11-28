---
title: "Ошибка компилятора C2373 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2373
dev_langs: C++
helpviewer_keywords: C2373
ms.assetid: 7a08bf0b-852d-48be-ba75-70df9f4b5951
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 93e9538b53b278f12af0a3b50566f444d5289362
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2373"></a>Ошибка компилятора C2373
"идентификатор": переопределение; различные модификаторы типа  
  
 Идентификатор уже объявлен с другим модификатором типа.  
  
 Следующий пример приводит к возникновению ошибки C2373:  
  
```  
// C2373.h  
void __clrcall func( void );  
const int i = 20;  
```  
  
 Затем:  
  
```  
// C2373.cpp  
// compile with: /c  
#include "C2373.h"  
extern void __cdecl func( void );   // C2373  
extern void __clrcall func( void );   // OK  
  
extern int i;   // C2373  
extern const int i;   // OK  
```