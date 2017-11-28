---
title: "Предупреждение (уровень 1) C4530 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4530
dev_langs: C++
helpviewer_keywords: C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cd91b0c46e5243a223b3b8ab8cdfc9a03cd64cb2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4530"></a>Предупреждение компилятора (уровень 1) C4530
Обработчик исключений C++ используется, но семантика уничтожения объектов не включены. Задайте параметр/EHsc  
  
 Была использована обработка исключений C++, но [/EHsc](../../build/reference/eh-exception-handling-model.md) не был установлен.  
  
 Если параметр/EHsc не включен, объект автоматически сохраняемый во фрейме между функцией throw и функцию, перехватывающей оператор throw, не будут уничтожены. Однако создать объект с автоматического хранения в **повторите** или **перехватывать** блока будут уничтожены.  
  
 Следующий пример приводит к возникновению ошибки C4530:  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 Скомпилируйте образец с параметром/EHsc, чтобы устранить это предупреждение.