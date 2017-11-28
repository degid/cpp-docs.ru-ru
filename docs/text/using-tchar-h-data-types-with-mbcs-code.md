---
title: "Использование типов данных TCHAR.H с кодом _MBCS | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ""tchar.h""
  - "TCHAR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "создание текстовых типов данных [C++]"
  - "универсальные текстовые сопоставления [C++]"
  - "универсальное текстовое сопоставление"
  - "сопоставления [C++], TCHAR.H"
  - "MBCS [C++], универсальные текстовые сопоставления"
  - "типы данных TCHAR.H, сопоставление"
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Использование типов данных TCHAR.H с кодом _MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если определена константа манифеста **\_MBCS**, используемые в коде универсальные текстовые функции отображаются на процедуры одного из следующих видов:  
  
-   SBCS\-версии процедур, которые обрабатывают многобайтовые байты, знаки и строки соответствующим образом.  В этом случае ожидается, что строковые аргументы будут иметь тип **char\***.  Например, функция `_tprintf` отображается на функцию `printf`; строковые аргументы `printf` имеют тип **char\***.  При использовании универсального строкового типа данных **\_TCHAR** типы формальных и фактических параметров функции `printf` совпадают, потому что **\_TCHAR**\* отображается на **char\***.  
  
-   MBCS\-версии процедур.  В этом случае ожидается, что строковые аргументы будут иметь тип `unsigned` **char\***.  Например, функция `_tcsrev` отображается на функцию `_mbsrev`, которая ожидает и возвращает строку типа `unsigned` **char\***.  При использовании универсального строкового типа данных **\_TCHAR** существует вероятность конфликта типов, потому что **\_TCHAR** отображается на тип `char`.  
  
 Есть три способа предотвратить конфликт типов \(при конфликте типов компилятор C выдает предупреждение, а компилятор C\+\+ — сообщение об ошибке\):  
  
-   Использовать поведение по умолчанию.  Файл Tchar.h содержит прототипы универсальных текстовых процедур, реализованных в библиотеках времени выполнения, как показано в следующем примере.  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     В этом случае прототип функции `_tcsrev` отображается на функцию `_mbsrev` через преобразователь в Libc.lib.  Тип входного параметра и результата функции `_mbsrev` изменяется с **\_TCHAR \*** \(то есть с `char` **\***\) на `unsigned` `char` **\***.  Данный метод гарантирует совпадение типов при использовании **\_TCHAR**, но он является сравнительно медленным из\-за дополнительного вызова функции.  
  
-   Использовать подстановку функций путем включения в код следующей инструкции препроцессора.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     При этом подходе вызывается встроенный преобразователь функции, реализованный в файле Tchar.h, который непосредственно отображает универсальную текстовую процедуру на соответствующую MBCS\-процедуру.  Следующий фрагмент кода из Tchar.h иллюстрирует вышесказанное.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     По возможности рекомендуется использовать именно подставляемые функции, потому что они гарантируют соответствие типов и не замедляют код.  
  
-   Использовать прямое отображение путем включения в код следующей инструкции препроцессора.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Данный подход является быстрой альтернативой, если нет возможности использовать поведение по умолчанию или подставляемые функции.  При этом универсальная текстовая процедура отображается через макрос непосредственно на MBCS\-версию процедуры, как в следующем фрагменте из Tchar.h.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     При использовании этого подхода необходимо следить, чтобы для строковых входных параметров и выходного значения использовались соответствующие типы данных.  Можно воспользоваться явным приведением типов, чтобы гарантировать соответствие типов, либо универсальным строковым типом данных **\_TXCHAR**.  Тип **\_TXCHAR** отображается на тип `char` в SBCS\-коде, но в MBCS\-коде он отображается на тип `unsigned` `char`.  Дополнительные сведения об универсальных текстовых макросах см. в разделе [Универсальные текстовые отображения](../c-runtime-library/generic-text-mappings.md) *справки по библиотеке времени выполнения*.  
  
## См. также  
 [Универсальные текстовые сопоставления в файле Tchar.h](../Topic/Generic-Text%20Mappings%20in%20Tchar.h.md)