---
title: "Предупреждение (уровень 1) C4086 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4086
dev_langs: C++
helpviewer_keywords: C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d34694f2f991e31ee7a896e128881ff6f09c54d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4086"></a>Предупреждение компилятора (уровень 1) C4086
требуется параметр директивы pragma: "1", "2", "4", "8" или "16"  
  
 Параметр прагмы не имеет обязательное значение (1, 2, 4, 8 или 16).  
  
## <a name="example"></a>Пример  
  
```  
// C4086.cpp  
// compile with: /W1 /LD  
#pragma pack( 3 ) // C4086  
```