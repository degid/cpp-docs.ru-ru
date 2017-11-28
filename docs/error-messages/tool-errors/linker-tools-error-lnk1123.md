---
title: "Ошибка средств компоновщика LNK1123 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1123
dev_langs: C++
helpviewer_keywords: LNK1123
ms.assetid: fe47af69-0f42-4792-9133-541192cd8514
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ade68d51125167c34fc46f23a7c9ce7eccfdef5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1123"></a>Ошибка средств компоновщика LNK1123
сбой при преобразовании в COFF: файл недопустим или поврежден  
  
 Входные файлы должны иметь формат COFF. Если входной файл не имеет формат COFF, компоновщик автоматически пытается преобразовать 32-разрядные объекты OMF в формат COFF или запускает программу CVTRES.EXE для преобразования файлов ресурсов. Это сообщение означает, что компоновщик не может преобразовать файл. Эта ошибка также может происходить при использовании несовместимой версии CVTRES.EXE из другой установки Visual Studio, пакета средств разработки программного обеспечения для Windows или платформы .NET Framework.  
  
> [!NOTE]
>  Если используется более ранняя версия Visual Studio, автоматическое преобразование может не поддерживаться.  
  
### <a name="to-fix-the-problem"></a>Устранение проблемы  
  
-   Примените все обновления и пакеты обновления для используемой версии Visual Studio. Это особенно важно для Visual Studio 2010.  
  
-   Попробуйте выполнить сборку с отключенной инкрементной компоновкой. В строке меню выберите **Проект**, **Свойства**. В **страницы свойств** диалогового окна разверните **свойства конфигурации**, **компоновщика**. Измените значение **Включить инкрементную компоновку** для **нет**.  
  
-   Проверьте, соответствует ли версия CVTRES.EXE, указанная первой в переменной среды PATH, версии средств сборки или используемого проектом набора инструментов платформы,.  
  
-   Попробуйте отключить параметр «Внедренный манифест». В строке меню выберите **Проект**, **Свойства**. В **страницы свойств** диалогового окна разверните **свойства конфигурации**, **инструмент манифеста**, **входной и выходной**. Измените значение **внедренный манифест** для **нет**.  
  
-   Убедитесь в том, что тип файла является допустимым. Например, убедитесь в том, что объект OMF 32-разрядный, а не 16-разрядный. Дополнительные сведения см. в разделе [. OBJ-файлы в качестве входных данных компоновщика](../../build/reference/dot-obj-files-as-linker-input.md) и [Microsoft PE и COFF спецификации](http://go.microsoft.com/fwlink/p/?LinkId=93292).  
  
-   Убедитесь в том, что файл не поврежден. Заново выполните сборку, если нужно.  
  
## <a name="see-also"></a>См. также  
 [. OBJ-файлы в качестве входных данных компоновщика](../../build/reference/dot-obj-files-as-linker-input.md)   
 [Справочник ЕDITBIN](../../build/reference/editbin-reference.md)   
 [Справочник DUMPBIN](../../build/reference/dumpbin-reference.md)