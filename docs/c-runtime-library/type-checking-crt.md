---
title: "Проверка типов (CRT) | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.types
dev_langs: C++
helpviewer_keywords:
- checking type
- variable argument functions
- type checking
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6bffc721ac685be91531b3d876234de8be2477c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="type-checking-crt"></a>Проверка типов (CRT)
Компилятор выполняет ограниченную проверку типов для функций, которые могут принимать переменное число аргументов, как указано ниже:  
  
|Вызов функции |Аргументы, для которых проверяется тип|  
|-------------------|-----------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Первый аргумент (строка форматирования)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Первые два аргумента (файл или буфер и строка форматирования)|  
|`_snprintf_s`|Первые три аргумента (файл или буфер, количество и строка форматирования)|  
|`_open`|Первые два аргумента (путь и флаг `_open`)|  
|`_sopen_s`|Первые три аргумента (путь, флаг `_open` и режим общего доступа)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Первые два аргумента (путь и первый указатель на аргумент)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Первые три аргумента (флаг режима, путь и первый указатель на аргумент)|  
  
 Компилятор выполняет такую же ограниченную проверку типов для аналогов этих функций для расширенных символов.  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки CRT](../c-runtime-library/crt-library-features.md)