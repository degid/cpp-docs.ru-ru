---
title: "Неустранимая ошибка C1013 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1013
dev_langs:
- C++
helpviewer_keywords:
- C1013
ms.assetid: 5514a679-efe7-4055-bdd3-5693ca0c332f
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 72196927de45c639b8aea7e26bb721c57b6d7c1d
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1013"></a>Неустранимая ошибка C1013
ограничение компилятора: слишком много открывающих круглых скобок  
  
 Выражение содержит слишком много уровней круглых скобок в одном выражении. Упростите выражение или разбейте его на несколько инструкций.  
  
 До Visual C++ 6.0 с пакетом обновления 3 в одном выражении могло быть не более 59 вложенных круглых скобок. В настоящее время ограничение на количество круглых скобок увеличено до 256.