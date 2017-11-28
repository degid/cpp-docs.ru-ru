---
title: "Неустранимая ошибка ML A1017 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1017
dev_langs: C++
helpviewer_keywords: A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ec10e14920572bd8001cf07676c4659bc08a4acc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ml-fatal-error-a1017"></a>Неустранимая ошибка ML A1017
**отсутствие исходного имени файла**  
  
 ML не удалось найти файл для сборки или передать в компоновщик.  
  
 Эта ошибка возникает, когда вы предоставляете ML параметры командной строки без указания имени файла, с которым выполняется действие. Чтобы собрать файлы, которые не имеют расширение .asm, используйте **/Ta** параметр командной строки.  
  
 Эта ошибка также может возникать путем вызова машинного Обучения без параметров, если переменная среды ML содержит параметры командной строки.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)