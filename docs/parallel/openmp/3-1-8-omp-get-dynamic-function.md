---
title: "3.1.8 omp_get_dynamic Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.8 omp_get_dynamic Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Omp\_get\_dynamic функция возвращает ненулевое значение, если динамическую настройку потоков включена, и возвращает 0, в противном случае.  Формат следующий:  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 Если реализация не реализует динамическую корректировку числа потоков, эта функция всегда возвращает значение 0.  
  
## Перекрестные ссылки:  
  
-   Описание динамической настройки потока, см. в разделе [Раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.