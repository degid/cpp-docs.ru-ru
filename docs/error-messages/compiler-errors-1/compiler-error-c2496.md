---
title: "Ошибка компилятора C2496 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2496
dev_langs: C++
helpviewer_keywords: C2496
ms.assetid: 9a25237d-5bbb-4112-98f3-29cd99d3f89f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 35caa51076bbd1f176c9509c80dd3586eb3d385c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2496"></a>Ошибка компилятора C2496
«Идентификатор»: «selectany» может применяться только к элементам данных с внешней компоновкой  
  
 [Selectany](../../cpp/selectany.md) атрибут может применяться только к элементам извне видимым и глобальных данных.  
  
 Следующий пример приводит к возникновению ошибки C2496:  
  
```  
// C2496.cpp  
// compile with: /c  
__declspec(selectany) int x1 = 1;  
const __declspec(selectany) int x2 = 2;   // C2496  
static __declspec(selectany) int x6 = 6;   // C2496  
  
extern const __declspec(selectany) int x3 = 3;  
  
__declspec(selectany) int x4;  
  
// dynamic initialization of x5  
int f();  
__declspec(selectany) int x5 = f();  
  
extern const int x7;  
// OK - redeclaration of x7 that is extern  
const __declspec(selectany) int x7 = 7;  
```