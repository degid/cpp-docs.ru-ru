---
title: "Ошибка компилятора предупреждение (уровень 1) C4036 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4036
dev_langs:
- C++
helpviewer_keywords:
- C4036
ms.assetid: f0b15359-4d62-48ec-8cb1-a7b36587a47f
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6392ba12c14ca3ef89f992e358bf019d1d92e5db
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4036"></a>Предупреждение компилятора (уровень 1) C4036
неименованный "тип" в качестве фактического параметра  
  
 Не задано имя типа для структуры, объединения, перечисления или класса, используемого в качестве фактического параметра. Если вы создаете прототипы функций с помощью параметра [/Zg](../../build/reference/zg-generate-function-prototypes.md) , компилятор выдает это предупреждение и переводит в комментарий этот формальный параметр в созданном прототипе.  
  
 Укажите имя типа, чтобы устранить это предупреждение.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C4036.  
  
```  
// C4036.c  
// compile with: /Zg /W1  
// D9035 expected  
typedef struct { int i; } T;  
void f(T* t) {}   // C4036  
  
// OK  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```