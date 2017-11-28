---
title: "PogoSafeMode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PogoSafeMode"
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# PogoSafeMode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Укажите, следует ли использовать быстрый режим или безопасный режим для профилирования приложения.  
  
## Синтаксис  
  
```  
PogoSafeMode  
```  
  
## Заметки  
 У профильной оптимизации \(PGO\) есть два возможных режима профилирования на данном этапе: быстрый режим и безопасный режим.  При профилировании в быстром режиме для увеличения счетчиков данных используется оператор **INC**.  Инструкция **INC** выполняется быстрее, но не является потокобезопасной.  При профилировании в безопасном режиме для увеличения счетчиков данных используется оператор **LOCK INC**.  Инструкция **LOCK INC** обладает такой же функциональностью, что и **INC**, является потокобезопасной, но работает медленнее, чем инструкция **INC**.  
  
 По умолчанию профилирование вероятностного оптимизатора работает в быстром режиме.  `PogoSafeMode` требуется только в том случае, если планируется использование безопасного режима.  
  
 Чтобы запустить профилирование с помощью вероятностного оптимизатора в безопасном режиме, необходимо использовать переменную среды `PogoSafeMode` или параметр компоновщика **\-PogoSafeMode** в зависимости от конкретной системы.  При выполнении профилирования на компьютере с процессором x64 необходимо использовать параметр компоновщика.  При выполнении профилирования на компьютере с процессором x86 необходимо задать для переменной среды любое значение перед началом процесса оптимизации.  
  
## Пример  
  
```  
set PogoSafeMode=1  
```  
  
## См. также  
 [Переменные среды для профильной оптимизации](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [Профильная оптимизация](../../build/reference/profile-guided-optimizations.md)