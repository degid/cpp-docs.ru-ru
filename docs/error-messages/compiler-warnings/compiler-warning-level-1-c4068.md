---
title: "Предупреждение (уровень 1) C4068 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4068
dev_langs: C++
helpviewer_keywords: C4068
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 61cf61f2d1f1ea1575bc1259458d1711c41f189f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4068"></a>Предупреждение компилятора (уровень 1) C4068
Неизвестная директива pragma  
  
 Компилятор проигнорировал нераспознанную директиву [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md). Убедитесь, что директива **pragma** разрешена компилятором, который вы используете. При компиляции следующего примера будет выдано предупреждение C4068:  
  
```  
// C4068.cpp  
// compile with: /W1  
#pragma NotAValidPragmaName   // C4068, use valid name to resolve  
int main()  
{  
}  
```