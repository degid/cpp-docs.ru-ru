---
title: "Ошибка компилятора C2762 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2762
dev_langs: C++
helpviewer_keywords: C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e121ab82b8e49fb1727e626eea7d060e8def2b8c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2762"></a>Ошибка компилятора C2762
«класс»: Недопустимое выражение в качестве аргумента шаблона для «аргумент»  
  
 При использовании [/Za](../../build/reference/za-ze-disable-language-extensions.md), компилятор не преобразует целочисленный к указателю.  
  
 Следующий пример приводит к возникновению ошибки C2762:  
  
```  
// C2762.cpp  
// compile with: /Za  
template<typename T, T *pT>  
class X2 {};  
  
void f2() {  
   X2<int, 0> x21;   // C2762  
   // try the following line instead  
   // X2<int, static_cast<int *>(0)> x22;  
}  
```