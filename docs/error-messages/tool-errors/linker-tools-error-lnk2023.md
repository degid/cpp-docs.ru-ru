---
title: "Ошибка средств компоновщика LNK2023 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2023
dev_langs: C++
helpviewer_keywords: LNK2023
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37370cd4637680783761e787e6ca38bdd5bada84
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2023"></a>Ошибка средств компоновщика LNK2023
Неверная библиотека dll или точка входа \<dll или точка входа >  
  
 Компоновщик загружается неправильная версия библиотеки msobj90.dll. Убедитесь, что link.exe и библиотеки msobj90.dll в пути имеют ту же версию.  
  
 Возможно, отсутствует зависимость от библиотеки msobj90.dll. Ниже приведен список зависимостей для библиотеки msobj90.dll.  
  
-   Msvcr90.dll  
  
-   Kernel32.dll  
  
 Проверьте свой компьютер и другие копии библиотеки msobj90.dll, которые могут быть устаревшими.