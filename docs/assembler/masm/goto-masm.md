---
title: "ОПЕРАТОР GOTO (MASM) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: goto
dev_langs: C++
helpviewer_keywords: GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 896d99b2ed4abe2080e646b6a541eb1e489d2b75
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="goto-masm"></a>GOTO (MASM)
Передает строку, помеченную сборки **:***macrolabel*.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Оператор GOTO** разрешены только в [МАКРОС](../../assembler/masm/macro.md), [для](../../assembler/masm/for-masm.md), [FORC](../../assembler/masm/forc.md), [ПОВТОРИТЕ](../../assembler/masm/repeat.md), и **при**блоки. Метка должна быть только директивой в строке и должен предшествовать начальное двоеточие.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)