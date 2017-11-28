---
title: "Явная специализация шаблонов функций | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e4962366c2519e9e291994ba0df39a62bfe81c67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="explicit-specialization-of-function-templates"></a>Явная специализация шаблонов функций
Используя шаблон функции, можно указать особое поведение для определенного типа, предоставив явную специализацию (переопределение) шаблона функции для этого типа. Пример:  
  
```cpp
template<> void MySwap(double a, double b);  
```  
  
 Это объявление позволяет определить другую функцию для **двойные** переменных. Подобно функциям, не являющимся шаблоном, стандартные преобразования типов (например, преобразование типа **float** для **двойные**) применяются.  
  
## <a name="example"></a>Пример  
  
```cpp
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Шаблоны функций](../cpp/function-templates.md)