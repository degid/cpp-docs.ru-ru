---
title: "Ошибка компилятора C2818 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2818
dev_langs: C++
helpviewer_keywords: C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 02c1b8e67679e7b8ce69b202c3ddef899439095d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2818"></a>Ошибка компилятора C2818
Применение перегруженного «operator ->» является рекурсивным через тип «тип»  
  
 Переопределение оператор доступа к членам класса содержится рекурсивный `return` инструкции. Чтобы переопределить `->` оператор, необходимо переместить рекурсивную подпрограмму в отдельную функцию, которая вызывается из оператора переопределить функцию.