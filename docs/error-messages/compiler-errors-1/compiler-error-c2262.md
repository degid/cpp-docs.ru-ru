---
title: "Ошибка компилятора C2262 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2262
dev_langs:
- C++
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 216a82734603db0fd62692f7818dcb1e1fa67b06
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2262"></a>Ошибка компилятора C2262
"спецификаторы_атрибутов": в объявлениях InternalsVisibleTo невозможно указывать версию, культуру или архитектуру процессора  
  
 Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> указан неправильно.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2262:  
  
```  
// C2262.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262  
[assembly: InternalsVisibleTo("assembly_name ")];   // OK  
```