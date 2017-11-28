---
title: "Неустранимая ошибка C1020 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1020
dev_langs:
- C++
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c2689b2526b2cf9dc513052e292aca429113c129
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1020"></a>Неустранимая ошибка C1020
непредвиденный #endif  
  
 Директива `#endif` не имеет соответствующей директивы `#if`, `#ifdef`или `#ifndef` . Убедитесь, что каждая директива `#endif` имеет соответствующую директиву.  
  
 В следующем примере возникает ошибка C1020:  
  
```  
// C1020.cpp  
#endif     // C1020  
```  
  
 Возможное решение:  
  
```  
// C1020b.cpp  
// compile with: /c  
#if 1  
#endif  
```