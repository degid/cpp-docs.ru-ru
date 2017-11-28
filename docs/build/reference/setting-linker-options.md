---
title: "Настройка параметров компоновщика | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b64b1dfd342598735124940d01b1bb4939242e10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="setting-linker-options"></a>Настройка параметров компоновщика
Можно задать параметры компоновщика, внутри или вне среды разработки. В этом разделе для каждого параметра компоновщика обсуждается, как это можно сделать в среде разработки. В разделе [параметры компоновщика](../../build/reference/linker-options.md) полный список.  
  
 При выполнении ссылки вне среды разработки, можно указать входные данные в один или несколько способов:  
  
-   На [командной строки](../../build/reference/linker-command-line-syntax.md)  
  
-   С помощью [командные файлы](../../build/reference/link-command-files.md)  
  
-   В [переменные среды](../../build/reference/link-environment-variables.md)  
  
 СВЯЗЬ первого обрабатывает параметры, заданные в переменной среды ссылки, следуют параметры в порядке, они были указаны в командной строке и в командных файлах. Если параметр повторяется с разными аргументами, обработанных последнее из них имеет приоритет.  
  
 Параметры применяются ко всей сборке; параметры не могут применяться для определенных входных файлов.  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о построении C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)