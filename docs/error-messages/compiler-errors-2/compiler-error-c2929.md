---
title: "Ошибка компилятора C2929 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2929
dev_langs: C++
helpviewer_keywords: C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1b9b5fe2d73d3c51e2946fc43ef2c5c5cbc5051d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2929"></a>Ошибка компилятора C2929
"идентификатор": явное создание экземпляра; не удается принудительно использовать и запретить создание экземпляра члена класса-шаблона  
  
 Невозможно явно создать экземпляр идентификатора и при этом запретить его создание.  
  
 Следующий пример приводит к возникновению ошибки C2929:  
  
```  
// C2929.cpp  
// compile with: /c  
template<typename T>  
class A {  
public:  
   A() {}  
};  
  
template A<int>::A();  
  
extern template A<int>::A();   // C2929  
```