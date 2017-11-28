---
title: "Ошибка компилятора C3634 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3634
dev_langs: C++
helpviewer_keywords: C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0ab2285ef47f704defbcca8644dbf63b8507096a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3634"></a>Ошибка компилятора C3634
«функция»: невозможно определить абстрактный метод управляемого типа или WinRTclass  
  
 Абстрактный метод может быть объявлен в управляемом классе или классе WinRT, но он не может быть определен.  
  
## <a name="example"></a>Пример  
Следующий пример приводит к возникновению ошибки C3634:  
  
```  
// C3634.cpp  
// compile with: /clr  
ref class C {  
   virtual void f() = 0;  
};  
  
void C::f() {   // C3634 - don't define managed class' pure virtual method  
}  
```  