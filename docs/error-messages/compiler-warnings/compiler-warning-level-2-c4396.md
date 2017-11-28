---
title: "Предупреждение (уровень 2) C4396 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4396
dev_langs: C++
helpviewer_keywords: C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5bee2614d479ec54bf9d49c92deb336eee05d285
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4396"></a>Предупреждение компилятора (уровень 2) C4396
"имя": если дружественное объявление ссылается на специализацию функции-шаблона, встроенный спецификатор использовать невозможно  
  
 Специализации шаблона функции нельзя задавать любые [встроенного](../../cpp/inline-functions-cpp.md) спецификаторы. В этом случае при компиляции возникает предупреждение C4396, а спецификатор inline пропускается.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите спецификатор `inline`, `__inline`или `__forceinline` из объявления дружественной функции.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показано недопустимое объявление дружественной функции со спецификатором `inline` .  
  
```  
// C4396.cpp  
// compile with: /W2 /c  
  
class X;   
template<class T> void Func(T t, int i);  
  
class X {  
    friend inline void Func<char>(char t, int i);  //C4396  
// try the following line instead  
//    friend void Func<char>(char t, int i);   
    int i;  
};  
```