---
title: "Системные вызовы | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.system
dev_langs: C++
helpviewer_keywords:
- Windows [C++], system calls
- system calls
ms.assetid: 0255f2ec-a5a0-487e-8b09-9dad001d81ed
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4de63e6ded4e2bd4b0aaf29d3e934db00ba0e2cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="system-calls"></a>Системные вызовы
Следующие функции являются вызовами операционной системы Windows.  
  
### <a name="system-call-functions"></a>Функции системных вызовов  
  
|Функция|Применение|  
|--------------|---------|  
|[_findclose](../c-runtime-library/reference/findclose.md)|Освобождение ресурсов от предыдущих операций поиска|  
|[_findfirst, _findfirst32, _findfirst64, _findfirsti64, _findfirst32i64, _findfirst64i32, _wfindfirst, _wfindfirst32, _wfindfirst64, _wfindfirsti64, _wfindfirst32i64, _wfindfirst64i32](../c-runtime-library/reference/findfirst-functions.md)|Поиск файла с указанными атрибутами|  
|[_findnext, _findnext32, _findnext64, _findnexti64, _findnext32i64, _findnext64i32, _wfindnext, _wfindnext32, _wfindnexti64, _wfindnext64, _wfindnexti64](../c-runtime-library/reference/findnext-functions.md)|Поиск следующего файла с указанными атрибутами|  
  
## <a name="see-also"></a>См. также  
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)   
 [Обработка файлов](../c-runtime-library/file-handling.md)   
 [Управление каталогами](../c-runtime-library/directory-control.md)   
 [Низкоуровневый ввод-вывод](../c-runtime-library/low-level-i-o.md)