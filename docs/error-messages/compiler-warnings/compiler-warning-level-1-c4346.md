---
title: "Предупреждение (уровень 1) C4346 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4346
dev_langs: C++
helpviewer_keywords: C4346
ms.assetid: 68ee562d-cca9-4a2a-9a1b-14ad1a1e7396
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 17e4644901d127bf11637bc24ea155072f83e03c
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2017
---
# <a name="compiler-warning-level-1-c4346"></a>Предупреждение компилятора (уровень 1) C4346
«Имя»: зависимое имя не является типом  
  
 [Typename](../../cpp/typename.md) ключевое слово является обязательным, если зависимое имя должно рассматриваться как тип. Для кода, который работает одинаково во всех версиях Visual C++, добавьте `typename` к объявлению.  
  
 Следующий пример приводит к возникновению ошибки C4346:  
  
```  
// C4346.cpp  
// compile with: /WX /LD  
template<class T>  
struct C {  
   T::X* x;   // C4346  
   // try the following line instead  
   // typename T::X* x;  
};  
```  
  
 В следующем примере демонстрируются другие примеры где **typename** требуется ключевое слово:  
  
```  
// C4346b.cpp  
// compile with: /LD /W1  
template<class T>  
const typename T::X& f(typename T::Z* p);   // Required in both places  
  
template<class T, int N>  
struct L{};  
  
template<class T>  
struct M : public L<typename T::Type, T::Value>   
{   // required on type argument, not on non-type argument  
   typedef typename T::X   Type;  
   Type f();   // OK: "Type" is a type-specifer  
   typename T::X g();   // typename required  
   operator typename T::Z();   // typename required      
};  
```  
  
 а также:  
  
```  
// C4346c.cpp  
// compile with: /LD /WX  
struct Y {  
   typedef int Y_t;  
};  
  
template<class T>  
struct A {  
   typedef Y A_t;  
};  
  
template<class T>  
struct B {  
   typedef /*typename*/ A<T>::A_t B_t;   // C4346 typename needed here  
   typedef /*typename*/ B_t::Y_t  B_t2;   // typename also needed here  
};  
```