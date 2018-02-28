---
title: "Производные классы окон | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- window class hierarchy
- hierarchies, window classes
- classes [MFC], derived
- CWnd class [MFC], classes derived from
- derived classes [MFC], window classes
- window classes [MFC], derived
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4601a04932f467be3b63527f12c46f797d9e11d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="derived-window-classes"></a>Производные классы окон
Можно создать windows непосредственно из [CWnd](../mfc/reference/cwnd-class.md), или произвести новые классы окна из `CWnd`. Это обычно Создание собственных пользовательских windows. Однако большинство окон, используемые в программе framework вместо этого создаются из одного из `CWnd`-производные классы окна фрейма, предоставляемые MFC.  
  
## <a name="frame-window-classes"></a>Классы окна фрейма  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 Используется для окна фрейма SDI, которые образуют один документ и его представление. Окна фрейма является фрейма главного окна приложения и окна фрейма в текущем документе.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 Используется в качестве главного фрейма окна для приложений MDI. Фрейма главного окна — это контейнер для всех окнах документов MDI и использует его меню с ними. Окне фрейма MDI является окном верхнего уровня, который отображается на рабочем столе.  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 Используется для отдельных документов, открытых в окне главного фрейма MDI. Каждый документ и его представление заключены в окне фрейма MDI дочерних содержащихся в окне главного фрейма MDI. Дочернего окна MDI похож типичный фрейм окна, но содержится в окне фрейма MDI, а не на рабочем столе. Тем не менее дочернее окно MDI не имеет свои собственные строки меню и должен предоставлять доступ к строке меню окна фрейма MDI, содержащей его.  
  
 Дополнительные сведения см. в разделе [фреймов](../mfc/frame-windows.md).  
  
## <a name="other-window-classes-derived-from-cwnd"></a>Другие окна классов, производных от CWnd  
 Помимо окна фрейма несколько других основных категорий windows являются производными от `CWnd`:  
  
 *Представления*  
 Представления создаются с помощью `CWnd`-производного класса [CView](../mfc/reference/cview-class.md) (или один из его производных классов). Представление прикрепляемые к документу и действует как посредник между документом и пользователя. Представление — это дочернее окно (не дочерних MDI-приложения), обычно заполняет собой клиентскую область окно рамки SDI или дочернего окна фрейма MDI (или части клиентской области, не связанная с панели инструментов и строка состояния).  
  
 *Диалоговые окна*  
 Диалоговые окна создаются с помощью `CWnd`-производного класса [CDialog](../mfc/reference/cdialog-class.md).  
  
 *Формы*  
 Представления форм на основе шаблона диалогового окна ресурсов, таких как диалоговые окна, создаются с помощью классов [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), или [CDaoRecordView](../mfc/reference/cdaorecordview-class.md).  
  
 *Элементы управления*  
 Элементы управления, такие как кнопки, списки и поля со списком создаются с помощью других классов, производных от `CWnd`. В разделе [управления разделы](../mfc/controls-mfc.md).  
  
 *Панели элементов управления*  
 Дочерние окна, которые содержат элементы управления. Например, панели инструментов и строки состояния. В разделе [панелей элементов управления](../mfc/control-bars.md).  
  
## <a name="window-class-hierarchy"></a>Иерархия классов окон  
 Ссылаться на [диаграммы иерархии MFC](../mfc/hierarchy-chart.md) в *Справочник по библиотеке MFC*. Описываются представления [архитектуры Document/View](../mfc/document-view-architecture.md). Описываются диалоговые окна [диалоговым окнам](../mfc/dialog-boxes.md).  
  
## <a name="creating-your-own-special-purpose-window-classes"></a>Создание собственных классов специальная окна  
 Кроме классов окон, предоставляемые библиотекой классов может потребоваться специальная дочерних окон. Чтобы создать такое окно, создайте собственную [CWnd](../mfc/reference/cwnd-class.md)-производного класса и сделать его дочернего окна фрейма или представления. Не забывайте, что среда управляет экстент клиентской области окна фрейма документа. Большая часть клиентской области управляется представления, но в других окнах, например, элемент управления полосы или собственные настраиваемые windows могут совместно использовать пространство с представлением. Может потребоваться взаимодействовать с механизмами в классах [CView](../mfc/reference/cview-class.md) и [CControlBar](../mfc/reference/ccontrolbar-class.md) для позиционирования дочерних окон в клиентской области окна фрейма.  
  
 [Создание окон](../mfc/creating-windows.md) обсуждается создание объектов окна и окна ими.  
  
## <a name="see-also"></a>См. также  
 [Объекты окон](../mfc/window-objects.md)
