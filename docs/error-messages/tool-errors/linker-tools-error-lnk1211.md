---
title: "Ошибка средств компоновщика LNK1211 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1211"
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка средств компоновщика LNK1211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не найдены сведения о предкомпилированном типе; "имя файла" не скомпоновано или перезаписано  
  
 Данный объектный файл, скомпилированный с помощью [\/Yc](../../build/reference/yc-create-precompiled-header-file.md), не был определен в команде LINK или был перезаписан.  
  
 Если при создании отладочной библиотеки, использующей предкомпилированные заголовки, заданы параметры \/Yc и [\/Z7](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md), Visual C\+\+ создает предкомпилированный объектный файл, в котором содержатся сведения CodeView об отладке.  Ошибка возникает только в том случае, если предкомпилированный объектный файл хранится в библиотеке, использует библиотеку для построения исполняемого образа, и те объектные файлы, на которые создается ссылка, не содержат транзитивных ссылок на любые функции, определенные предкомпилированным объектным файлом.  
  
 Существует два метода разрешения данной ситуации:  
  
-   Задать параметр компилятора [\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md), чтобы добавить данные CodeView из предкомпилированного заголовка в каждый модуль объекта.  Данный метод не рекомендуется использовать, поскольку он, как правило, создает большие модули объектов, из\-за которых процесс компоновки приложения будет занимать больше времени.  
  
-   При создании предкомпилированного файла заголовка, который не содержит определений функций, задать параметр [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) и передать имя любой произвольной строки.  В данном случае компилятор создает символ в предкомпилированном объектном файле и выдает ссылку на этот символ в каждом объектном файле, который использовал предкомпилированный файл заголовка, связанный с предкомпилированным объектным файлом.  
  
 При компиляции модуля с помощью параметров **\/Yc** и **\/Yl** компилятор создает символ, сходный с `__@@_PchSym_@00@...@symbol_name`, где многоточие \(...\) представляет сформированную компилятором строку символов, и хранит ее в модуле объекта.  Любой исходный файл, компилированный с помощью предкомпилированного заголовка, относится к заданному символу, вследствие чего компоновщик включает из библиотеки модуль объекта и данные о его отладке.  
  
 Дополнительные сведения о данной ошибке см. в статье информационной базы данных Q102697 PRB: Ошибки при построении с помощью предкомпилированного заголовка в отладочной библиотеке.