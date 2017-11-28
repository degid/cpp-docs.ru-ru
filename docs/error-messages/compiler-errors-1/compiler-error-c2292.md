---
title: "Ошибка компилятора C2292 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2292
dev_langs: C++
helpviewer_keywords: C2292
ms.assetid: 256b392f-2b8f-4162-b578-e7633984e162
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a4810da162223b6e9ca33781a608c416a34aa804
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2292"></a>Ошибка компилятора C2292
«Идентификатор»: наилучшее представление наследования: объявлено, но представление «2» требуется «Представление1»  
  
 Компиляция приведенного ниже кода с [/vmb](../../build/reference/vmb-vmg-representation-method.md) («лучшем всегда «представление) вызывает C2292.  
  
```  
// C2292.cpp  
// compile with: /vmb  
class __single_inheritance X;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2292, X uses multiple inheritance  
```