---
title: "Предупреждение (уровень 1) C4178 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4178
dev_langs: C++
helpviewer_keywords: C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b692a31bd76196e0eb42691e5a9821aecf22e472
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4178"></a>Предупреждение компилятора (уровень 1) C4178
константа варианта "константа" слишком велика для типа, указанного в выражении выбора вариантов  
  
 Константа варианта в выражении `switch` не помещается в тип, которому она назначена.  
  
## <a name="example"></a>Пример  
  
```  
// C4178.cpp  
// compile with: /W1  
int main()  
{  
    int i;  // maximum size of unsigned long int is 4294967295  
    switch( i )  
    {  
        case 4294967295:   // OK  
            break;  
        case 4294967296:   // C4178  
            break;  
    }  
 }  
```