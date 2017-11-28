---
title: "Ошибка компилятора C2170 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2170
dev_langs: C++
helpviewer_keywords: C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8520e9ea71d90e7f97c6296d4326abb1fd4c7609
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2170"></a>Ошибка компилятора C2170
«Идентификатор»: не объявлена как функция, не может быть встроенной  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Директива pragma `intrinsic` используется для элемента, не являющихся функциями.  
  
2.  Директива pragma `intrinsic` используется для функции, не имеющей форму.