---
title: "Предупреждение (уровень 4) C4718 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4718
dev_langs: C++
helpviewer_keywords: C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 837e0e69d2a2f0694dc9c99e8c3425bbd12a94e2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4718"></a>Предупреждение компилятора (уровень 4) C4718
"вызов_функции": рекурсивный вызов не имеет побочных эффектов; удаление  
  
 Функция содержит рекурсивный вызов, но с другой стороны побочные эффекты отсутствуют. Вызов этой функции удаляется. Это повлияет на поведение программы, но не на ее правильность. В то время как оставленный вызов может привести к исключению переполнения стека, удаление этого вызова устраняет такую возможность.