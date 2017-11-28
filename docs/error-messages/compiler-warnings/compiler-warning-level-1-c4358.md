---
title: "Предупреждение (уровень 1) C4358 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4358
dev_langs:
- C++
helpviewer_keywords:
- C4358
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 24ff4675d9286757599472ad5f1094be3157ea43
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4358"></a>Предупреждение компилятора (уровень 1) C4358
«operator»: возвращаемый тип значения объединенных делегатов не «void»; Возвращаемое значение не определено  
  
 Было произведено объединение двух делегатов, и возвращаемое значение не является void. При объединении двух делегатов с возвращаемыми значениями отличный от void, компилятор не будет возможность выполнить присвоение, если используется возвращаемое значение делегата.  
  
 Следующий пример приводит к возникновению ошибки C4358:  
  
```  
// C4358.cpp  
// compile with: /clr /W1  
delegate int D();  
delegate void E();  
  
ref class X {  
   int i;  
public:  
   X(int ii) : i(ii) {}  
   int f() {  
      return i;  
   }  
};  
  
ref class Y {  
   int i;  
public:  
   Y() {}  
   void g() {}  
};  
  
int main() {  
   D^ d = gcnew D(gcnew X(1), &X::f);  
   D^ d2 = gcnew D(gcnew X(2), &X::f);  
  
   d += d2;   // C4358  
   int j = d();   // return value indeterminate  
  
   E^ e = gcnew E(gcnew Y, &Y::g);  
   E^ e2 = gcnew E(gcnew Y, &Y::g);  
   e += e2;   // OK  
}  
```