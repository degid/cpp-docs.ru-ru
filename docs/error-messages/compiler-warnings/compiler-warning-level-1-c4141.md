---
title: "Предупреждение (уровень 1) C4141 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4141
dev_langs: C++
helpviewer_keywords: C4141
ms.assetid: 6ce8c058-7f4c-41cf-93e7-90a466744656
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cbaf337c8896944816b64dd9e53fe14cb6dfc3a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4141"></a>Предупреждение компилятора (уровень 1) C4141
"модификатор" используется несколько раз  
  
## <a name="example"></a>Пример  
  
```  
// C4141.cpp  
// compile with: /W1 /LD  
inline inline void func ();   // C4141  
```