---
title: "Ошибка BSCMAKE BK1509 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1509
dev_langs: C++
helpviewer_keywords: BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f661152774c8d5313a294e243a0f5a0083b4e114
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-error-bk1509"></a>Ошибка BSCMAKE BK1509
хватает размера кучи  
  
 BSCMAKE не хватило памяти, включая виртуальной памяти.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Освободите место на диске.  
  
2.  Увеличьте размер файла подкачки.  
  
3.  Увеличьте размер файла подкачки Windows.  
  
4.  Уменьшить размер памяти, требуемой BSCMAKE, с помощью параметров /Ei или/ES, чтобы исключить некоторые входные файлы или /Em, чтобы удалить тело макроса.