---
title: "Неустранимая ошибка NMAKE U1000 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1000"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1000"
ms.assetid: 49b9bd9e-f1bc-4b55-a171-c748e40b195e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Неустранимая ошибка NMAKE U1000
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

синтаксическая ошибка: отсутствие "\)" в макровызове  
  
 Левая круглая скобка **\(** используется в макровызове без соответствующей правой скобки **\)**.  Правильной формой является **$\(***имя***\)**; использование `$`*n* допускается для односимвольных имен.