---
title: "Поддержка мастера для других языков | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.EastAsianLanguages
dev_langs: C++
helpviewer_keywords:
- wizards [C++], language support
- language support for MFC projects
- projects [C++], language support
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f5741f6b09ec466c04794bf049222d344df34a85
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="wizard-support-for-other-languages"></a>Поддержка мастера для других языков
При установке Visual Studio программа установки определят язык и региональные параметры системы и устанавливает соответствующий языковой шаблон или шаблоны для данного языкового стандарта. Например для западноевропейских европейских языков, программа установки устанавливает английский, французский, итальянский, испанский и немецкий. Эти языки отражены в **язык ресурсов** списке [тип приложения](../mfc/reference/application-type-mfc-application-wizard.md) мастера приложений MFC.  
  
## <a name="language-templates"></a>Шаблоны языка  
 Не все шаблоны устанавливаются во всех системах, поскольку шаблоны основаны на кодировке ANSI, а не все ресурсы могут редактироваться во всех системах. Например по умолчанию нельзя изменить японский ресурсов в системе.  
  
 Если вы используете Windows 2000 или более поздней версии, и вы хотите создать приложение MFC на другом языке, затем необходимо скопировать каталог шаблонов для соответствующего языка из INI-файла установщика Visual Studio (диск 1) в систему.  
  
> [!NOTE]
>  Чтобы изменить созданный проект, необходимо задать региональные параметры системы в соответствующий языковой стандарт для выбранного языка.  
  
 Шаблоны являются каждому присвоить папке в каталоге \Microsoft Visual Studio .NET 2003\Vc7\VCWizards\mfcappwiz\templates\, перечисленные в следующей таблице. С помощью шаблона нужного языка, скопируйте соответствующую папку в каталог \mfcappwiz\templates\ на компьютере. После копирования папки языка будут отображаться в **язык ресурсов** списке **тип приложения** мастера приложений MFC.  
  
### <a name="language-templates-provided-in-visual-studio-net"></a>Язык шаблонов в Visual Studio .NET  
  
|Язык|Шаблон|  
|--------------|--------------|  
|Китайский (традиционный)|1028|  
|Китайский (упрощенный)|2052|  
|английский|1033|  
|Французский|1036|  
|Немецкий|1031|  
|Итальянский|1040|  
|Японский|1041|  
|Корейский|1042|  
|Испанский|3082|  
  
## <a name="format-of-visual-c-wizard-generated-files"></a>Формат файлов Visual C++ мастера  
 Мастера Visual C++ создают проекты в Юникод при установленной языковой версии Visual Studio, не соответствует языкового стандарта системы. Например при установке японскую версию Visual Studio на компьютере с региональными параметрами любого другого языка, мастера Visual C++ создает проекты, содержащие файлы в кодировке Юникод. Обычно это используется на компьютерах с Windows многоязыкового интерфейса (MUI) пакетов.  
  
 Это поведение отличается от систем, настроить таким образом, языковой стандарт системы является таким же, как языковая версия Visual Studio. В этом случае файлы проекта будут создаваться в формате ANSI в системную кодовую страницу.  
  
## <a name="see-also"></a>См. также  
 [Типы файлов, создаваемых для проектов Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Создание проектов Visual C++ и управление ими](../ide/creating-and-managing-visual-cpp-projects.md)