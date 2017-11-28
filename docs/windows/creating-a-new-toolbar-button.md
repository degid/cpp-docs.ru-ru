---
title: "Создание новой кнопки панели инструментов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.toolbar
dev_langs: C++
helpviewer_keywords:
- Toolbar editor, creating buttons
- toolbar buttons (in Toolbar editor), button image
- toolbar buttons (in Toolbar editor), creating
- toolbar buttons (in Toolbar editor)
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 340756fcb85af8402f3c01d9efb8f1c62c6b0b41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-new-toolbar-button"></a>Создание новой кнопки панели инструментов
### <a name="to-create-a-new-toolbar-button"></a>Создание новой кнопки панели инструментов  
  
1.  В [представление ресурсов](../windows/resource-view-window.md) разверните папку ресурсов (например, Project1.rc).  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Разверните **инструментов** папку и выберите команду панели инструментов для изменения.  
  
3.  Назначение идентификатора пустую кнопку в правом конце панели инструментов. Это можно сделать, изменив **идентификатор** свойство в [окно свойств](/visualstudio/ide/reference/properties-window). Например можно назначить тот же идентификатор, как пункт меню кнопке. В этом случае используйте поле раскрывающегося списка для выбора **идентификатор** пункта меню.  
  
     -или-  
  
     Выберите пустую кнопку в правом конце панели инструментов (в области представления панели инструментов) и начните рисование. Назначается идентификатор команды кнопки по умолчанию (ID_BUTTON\<n >).  
  
 Можно также скопировать и вставить изображение на панель инструментов в качестве новой кнопки.  
  
#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>Добавление изображения на панель инструментов, как кнопка  
  
1.  В [представление ресурсов](../windows/resource-view-window.md), откройте панель инструментов, дважды щелкнув его.  
  
2.  Затем откройте изображение, которое вы хотите добавить на панель инструментов.  
  
    > [!NOTE]
    >  При открытии изображения в Visual Studio, она откроется в редакторе изображений. Можно также открыть изображение в других программах графики.  
  
3.  Из **изменить** меню, выберите **копирования**.  
  
4.  Переключитесь на панель инструментов, щелкнув вкладку в верхней части окна исходного кода.  
  
5.  Из **изменить** меню, выберите **вставить**.  
  
     Изображение появится на панели инструментов, как новую кнопку.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](https://msdn.microsoft.com/library/f45fce5x.aspx) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](https://msdn.microsoft.com/library/xbx3z216.aspx). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
### <a name="requirements"></a>Требования  
 MFC или ATL  
  
## <a name="see-also"></a>См. также  
 [Свойства кнопок панели инструментов](../windows/toolbar-button-properties.md)   
 [Создание, перемещение и редактирование кнопок панели инструментов](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [Редактор панелей инструментов](../windows/toolbar-editor.md)
