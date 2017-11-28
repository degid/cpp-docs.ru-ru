---
title: "/ENTRY (символ точки входа) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/entry"
  - "VC.Project.VCLinkerTool.EntryPointSymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ENTRY - параметр компоновщика"
  - "ENTRY - параметр компоновщика"
  - "-ENTRY - параметр компоновщика"
  - "начальный адрес"
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ENTRY (символ точки входа)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ENTRY:function  
```  
  
## Заметки  
 Здесь:  
  
 *функция*  
 Функция, указывающая пользовательский начальный адрес EXE\-файла или библиотеки DLL.  
  
## Заметки  
 Параметр \/ENTRY задает функцию точки входа в качестве начального адреса для EXE\-файла или DLL.  
  
 Эта функция должна быть определена с использованием соглашения о вызове `__stdcall`.  Параметры и возвращаемое значение зависят от того, является ли программа консольным приложением, приложением Windows или библиотекой DLL.  Рекомендуется позволить компоновщику установить точку входа таким образом, чтобы корректно выполнялась инициализация библиотеки времени выполнения языка C, и вызывались бы конструкторы для статических объектов в C\+\+.  
  
 По умолчанию начальным адресом является имя функции из библиотеки времени выполнения языка C.  Компоновщик выбирает ее в соответствии с атрибутами программы, как показано в следующей таблице.  
  
|Имя функции.|Используется по умолчанию для|  
|------------------|-----------------------------------|  
|**mainCRTStartup** \(или **wmainCRTStartup**\)|приложений, использующих параметр \/SUBSYSTEM:**CONSOLE**; функция вызывает функцию **main** \(или **wmain**\)|  
|**WinMainCRTStartup** \(или **wWinMainCRTStartup**\)|приложений, использующих параметр \/SUBSYSTEM:**WINDOWS**; функция вызывает функцию `WinMain` \(или **wWinMain**\), которая должна быть объявлена с соглашением о вызове `__stdcall`|  
|**\_DllMainCRTStartup**|библиотек DLL; функция вызывает функцию `DllMain` \(если она существует\), которая должна быть объявлена с соглашением о вызове `__stdcall`|  
  
 Если параметр [\/DLL](../../build/reference/dll-build-a-dll.md) или [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) не указан, то компоновщик выбирает подсистему и точку входа в зависимости от того, какая из функций **main** или `WinMain` была определена.  
  
 Функции **main**, `WinMain` и `DllMain` — три формы пользовательской точки входа.  
  
 Когда создается управляемый образ, указанная с помощью параметра \/ENTRY функция должна иметь сигнатуру \(LPVOID *var1*, DWORD *var2*, LPVOID *var3*\).  
  
 Дополнительные сведения о том, как определить собственную точку входа DllMain, см. в разделе [Поведение библиотеки времени выполнения](../../build/run-time-library-behavior.md).  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Дополнительно**.  
  
4.  Измените значение свойства **Точка входа**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)