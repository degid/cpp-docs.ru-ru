---
title: "Мастер приложений Win32 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.win32.overview
dev_langs: C++
helpviewer_keywords:
- Win32 Application Wizard
- Win32 Project Wizard
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0f24f2c9629d79b6d3ced25b89f1d61f633ade7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="win32-application-wizard"></a>мастер приложений Win32
Мастер приложений Win32 Visual C++ позволяет создавать любой из четырех типов проектов (указаны в заголовке таблицы ниже). В каждом случае можно указать дополнительные параметры, подходящие для открытого вами типа проекта. В таблице ниже показано, какие параметры доступны для каждого типа приложения.  
  
|Тип поддержки|Консольное приложение|Исполняемое приложение (Windows)|Библиотека динамической компоновки|Статическая библиотека|  
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|  
|**Пустой проект**|Да|Да|Да|Нет|  
|**Символы экспорта**|Нет|Нет|Да|Нет|  
|**Предкомпилированный заголовок**|Нет|Нет|Нет|Да|  
|**поддержка ATL**|Да|Нет|Нет|Нет|  
|**поддержка MFC**|Да|Нет|Нет|Да|  
  
## <a name="overview"></a>Обзор  
 На этой странице мастера описываются текущие параметры проекта для создаваемого приложения Win32. По умолчанию заданы следующие параметры:  
  
-   проект является приложением Windows;  
  
-   проект не пустой;  
  
-   проект не содержит символов экспорта;  
  
-   проект не использует файл предкомпилированного заголовка (этот параметр доступен только для проектов статической библиотеки);  
  
-   проект не включает поддержку MFC и ATL.  
  
 Чтобы изменить эти значения по умолчанию, перейдите на вкладку [Параметры приложения](../windows/application-settings-win-32-project-wizard.md) в левом столбце мастера и внесите необходимые изменения.  
  
 Создав классическое приложение Windows, можно добавить универсальные классы C++ с помощью мастера [универсального](../ide/generic-cpp-class-wizard.md) кода. Можно добавить другие элементы, такие как файлы HTML, файлы заголовков, ресурсы или текстовые файлы.  
  
> [!NOTE]
>  Классы ATL добавить нельзя, а классы MFC можно добавить только в те типы классических приложений Windows, которые поддерживают MFC (см. предыдущую таблицу).  
  
 Файлы, созданные мастером для проекта, можно просмотреть в **обозревателе решений**. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [Типы файлов, создаваемых для проектов Visual C++](../ide/file-types-created-for-visual-cpp-projects.md).  
  
## <a name="see-also"></a>См. также  
 [Создание пустого классического приложения Windows](../windows/creating-an-empty-windows-desktop-application.md)   
 [Типы проектов Visual C++](../ide/visual-cpp-project-types.md)