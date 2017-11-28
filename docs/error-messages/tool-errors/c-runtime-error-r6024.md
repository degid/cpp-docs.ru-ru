---
title: "R6024 ошибку во время выполнения C | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: R6024
dev_langs: C++
helpviewer_keywords: R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2d032bbcb6e28d78f5e43b9c12499c6d47ca0310
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="c-runtime-error-r6024"></a>R6024 ошибка времени выполнения C
не хватает места для таблицы _onexit/atexit  
  
> [!NOTE]
>  Если это сообщение об ошибке возникает во время выполнения приложения, приложения была завершена из-за проблемы с внутренней памяти. Эта ошибка обычно происходит при условии очень нехватки памяти или редко, ошибки в программе или повреждением библиотек Visual C++, которые он использует.  
>   
>  Для устранения этой ошибки попробуйте выполнить следующие действия:  
>   
>  -   Закройте другие приложения, выполняющегося или перезагрузить компьютер, чтобы освободить память.  
> -   Используйте **программы и компоненты** или **программы и компоненты** страницы в **панели управления** восстановите или переустановите программу.  
> -   Используйте **программы и компоненты** или **программы и компоненты** страницы в **панели управления** восстановите или переустановите все копии распространяемого компонента Microsoft Visual C++.  
> -   Проверьте **центра обновления Windows** в **панели управления** для обновлений программного обеспечения.  
> -   Проверьте наличие обновленной версии приложения. Обратитесь к поставщику приложения, если ошибка повторится.  
  
 **Сведения для программистов**  
  
 Эта ошибка возникает из-за недостаточно памяти для `_onexit` или `atexit` функции. Эта ошибка вызвана нехватки памяти. Попробуйте выйти из предварительно выделение буферов при запуске приложения для сохранения данных пользователя и выполнение очистки приложения в условиях нехватки памяти.