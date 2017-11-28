---
title: "Неустранимая ошибка ML A1007 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1007
dev_langs: C++
helpviewer_keywords: A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bb4b55ce7a16620cd501fa8e687339f1bc48e3b3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ml-fatal-error-a1007"></a>Неустранимая ошибка ML A1007
**слишком глубокий уровень вложенности**  
  
 Код на языке ассемблера достигнут предел вложенности. Ограничение составляет 20 уровни, за исключением случаев, оговоренных в противном случае.  
  
 Одно из следующих были вложены слишком глубоко:  
  
-   Директиву высокого уровня, такие как [. Если](../../assembler/masm/dot-if.md), [. ПОВТОРИТЕ](../../assembler/masm/dot-repeat.md), или [. Во время](../../assembler/masm/dot-while.md).  
  
-   Определение структуры.  
  
-   Директива условной сборки.  
  
-   Определение процедуры.  
  
-   Объект [PUSHCONTEXT](../../assembler/masm/pushcontext.md) директивы (ограничение составляет 10).  
  
-   Определение сегмента.  
  
-   Файл заголовка.  
  
-   Макрос.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)