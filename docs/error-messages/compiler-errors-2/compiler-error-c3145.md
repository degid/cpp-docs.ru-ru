---
title: "Ошибка компилятора C3145 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3145
dev_langs: C++
helpviewer_keywords: C3145
ms.assetid: f165c874-0f51-45c7-85e8-ebe321cbc168
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6b6548d04d701cb510669d91780979951c485685
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3145"></a>Ошибка компилятора C3145
object: глобальная или статическая переменная не может иметь управляемый тип или тип WinRT type  
  
 В пределах области видимости функции можно определить только объекты среды CLR или WinRT.  
  
 В следующем примере показано возникновение ошибки C3145 и приводятся сведения по ее устранению.  
  
```  
// C3145.cpp  
// compile with: /clr  
using namespace System;   
ref class G {};   
  
G ^ ptr;   // C3145  
G ^ ptr2 = gcnew G;   // C3145  
  
ref class GlobalObjects {  
public:  
   static G ^ ptr;   // OK  
   static G ^ ptr2 = gcnew G;   // OK   
};   
  
int main() {  
   G ^ ptr;   // OK  
   G ^ ptr2 = gcnew G;   // OK  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C3145:  
  
```  
// C3145b.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   static int data;  
};  
  
interior_ptr<int> p = &(MyClass::data);   // C3145  
  
void Test(interior_ptr<int> x) {}  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   interior_ptr<int> p = &(h_MyClass->data);  
}  
```  