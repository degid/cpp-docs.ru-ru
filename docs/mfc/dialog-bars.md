---
title: "Диалоговые панели | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 100d17c3b5594c7c44e6002d4f65577bb2ee701e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="dialog-bars"></a>Диалоговые панели
Диалоговая панель — панель инструментов, тип объекта [панель элементов управления](../mfc/control-bars.md) , может содержать любой тип элемента управления. Так как они имеют характеристики немодального диалогового [CDialogBar](../mfc/reference/cdialogbar-class.md) объект предоставляет больше возможностей панели инструментов.  
  
 Существует несколько ключевых различий между панель инструментов и `CDialogBar` объекта. Объект `CDialogBar` объект создается из ресурса шаблона диалогового окна, которую можно создать с помощью редактора диалоговых окон Visual C++ и которое может содержать любой элемент управления Windows. Пользователь переместиться из элемента управления для элемента управления. И вы можете указать стиль выравнивания выровнять диалоговой панели с любой частью родительское окно фрейма или даже если при изменении размеров родительского оставить на месте. На следующем рисунке показана панель диалогового окна с различных элементов управления.  
  
 ![Панель диалогового окна VC](../mfc/media/vc378t1.gif "vc378t1")  
Диалоговая панель  
  
 В других отношениях работа с `CDialogBar` объект аналогичен работе с немодального диалогового окна. Проектирование и Создание ресурса диалогового окна, используйте редактор диалоговых окон.  
  
 Одна из достоинства диалоговые панели заключается в том, что они могут включать элементы управления помимо кнопок.  
  
 Хотя могут наследовать свои собственные классы диалоговых окон из `CDialog`, обычно не наследовать класс диалоговой панели. Диалоговые панели являются расширениями для главного окна и любые сообщения диалоговая панель уведомление элемента управления, такие как **BN_CLICKED** или **EN_CHANGE**, будут отправляться на родительского диалогового окна панели главного окна.  
  
## <a name="see-also"></a>См. также  
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)   
 [Пример](../visual-cpp-samples.md)
