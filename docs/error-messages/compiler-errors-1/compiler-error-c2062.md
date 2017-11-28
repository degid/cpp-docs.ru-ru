---
title: "Ошибка компилятора C2062 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2062
dev_langs: C++
helpviewer_keywords: C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 775923345052aba99b05f708c417b8bed267119b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2062"></a>Ошибка компилятора C2062
Тип «Тип» непредвиденная  
  
 Компилятор не ожидалось имя типа.  
  
 Следующий пример приводит к возникновению ошибки C2062:  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 C2062 также может возникать из-за способа компилятор обрабатывает неопределенных типов в списке параметров конструктора. Если компилятор обнаруживает неопределенный тип (с ошибкой?), предполагается конструктор — это выражение и выдает C2062. Чтобы решить, следует использовать только определенные типы в списке параметров конструктора.