---
title: "Ошибка компилятора C2946 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2946
dev_langs: C++
helpviewer_keywords: C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 887afb5a42a7dac47b5d3b8490acf8256601f189
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2946"></a>Ошибка компилятора C2946
явное создание экземпляра; "класс" не является специализацией класса-шаблона  
  
 Нельзя явно создать экземпляр класса без шаблона.  
  
## <a name="example"></a>Пример  
 При компиляции следующего примера возникнет ошибка C2946.  
  
```  
// C2946.cpp  
class C {};  
template C;  // C2946  
int main() {}  
```