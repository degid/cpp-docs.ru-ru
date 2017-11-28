---
title: "Ошибка компилятора C2364 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2364
dev_langs:
- C++
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d7c5042d4b5984a87b52cefafd1f591ec662ab48
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2364"></a>Ошибка компилятора C2364
«Тип»: недопустимый тип для настраиваемого атрибута  
  
 Именованные аргументы для пользовательских атрибутов ограничены константами времени компиляции. Например, целочисленные типы (int, char, т. д.), System::Type ^ и System::Object ^.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2364.  
  
```  
// c2364.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute(AttributeTargets::All)]  
public ref struct ABC {  
public:  
   // Delete the following line to resolve.  
   ABC( Enum^ ) {}   // C2364  
   ABC( int ) {}   // OK  
};  
```