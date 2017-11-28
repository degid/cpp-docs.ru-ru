---
title: "Использование типов данных TCHAR.H совместно с _MBCS | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mbcs
dev_langs: C++
helpviewer_keywords:
- TCHAR.H data types
- MBCS data type
- _MBCS data type
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c015c8ff7481f0d5ba25eba023b21f4877deaa4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="using-tcharh-data-types-with-mbcs"></a>Использование типов данных TCHAR.H с _MBCS
**Блок, относящийся только к системам Майкрософт**  
  
 Как показано в таблице универсальных текстовых сопоставлений (см. раздел [Generic-Text Mappings](../c-runtime-library/generic-text-mappings.md) (Универсальные текстовые сопоставления)), при установленном значении константы манифеста `_MBCS` каждая универсальная текстовая подпрограмма сопоставляются с подпрограммой одного из следующих типов:  
  
-   Подпрограмма для однобайтовой кодировки, которая правильно обрабатывает многобайтовые символы и строки. В этом случае ожидается, что строковые аргументы будут иметь тип `char*`. Например, функция `_tprintf` сопоставляется с функцией `printf`; строковые аргументы функции `printf` имеют тип `char*`. При использовании универсального строкового типа данных `_TCHAR` типы формальных и фактических параметров функции `printf` совпадают, потому что `_TCHAR*` сопоставляется с `char*`.  
  
-   Подпрограмма, специально созданная для многобайтовой кодировки. В этом случае ожидается, что строковые аргументы будут иметь тип `unsigned char*`. Например, функция `_tcsrev`сопоставляется с функцией `_mbsrev`, которая ожидает и возвращает строку типа `unsigned char*`. Как и ранее, при использовании универсального строкового типа данных `_TCHAR` существует потенциальная вероятность конфликта типов, потому что `_TCHAR` сопоставляется с типом `char`.  
  
 Есть три способа предотвратить такой конфликт типов (и избежать предупреждений компилятора C или ошибок компиляции C++).  
  
-   Использовать поведение по умолчанию. Файл TCHAR.H содержит прототипы универсальных текстовых подпрограмм, реализованных в библиотеках времени выполнения, как показано в следующем примере.  
  
    ```  
    char *_tcsrev(char *);  
    ```  
  
     В случае по умолчанию прототип функции `_tcsrev` сопоставляется с функцией `_mbsrev` через преобразователь в LIBC.LIB. При этом тип входного параметра и результата функции `_mbsrev` изменяется с `_TCHAR *` (например, `char *`) на `unsigned char *`. Данный метод гарантирует соответствие типов при использовании `_TCHAR`, но он является сравнительно медленным из-за дополнительного вызова функции.  
  
-   Использовать встраивание функций, включив в код следующую инструкцию препроцессора.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     При этом подходе вызывается встроенный преобразователь функции, реализованный в файле TCHAR.H, который непосредственно отображает универсальную текстовую подпрограмму на соответствующую MBCS-подпрограмму. Следующий фрагмент кода из TCHAR.H иллюстрирует вышесказанное.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     Это решение будет оптимальным, если используется встраивание, поскольку гарантирует соответствие типов и не замедляет работу.  
  
-   Использовать "прямое отображение" путем включения в код следующей инструкции препроцессора.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Такой подход позволяет быстро решить проблему, если вы не хотите использовать поведение по умолчанию или не можете использовать встраивание. При этом универсальная текстовая подпрограмма отображается через макрос непосредственно на MBCS-версию подпрограммы, как в следующем фрагменте из TCHAR.H.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
 При использовании этого подхода необходимо следить, чтобы для строковых аргументов и выходного значения использовались соответствующие типы данных. Можно воспользоваться явным приведением типов, чтобы гарантировать соответствие типов, либо универсальным строковым типом данных `_TXCHAR`. Тип `_TXCHAR` сопоставляется с типом `char` в коде с однобайтовой кодировкой, но в коде с многобайтовой кодировкой он сопоставляется с типом `unsigned char`. Дополнительные сведения об универсальных текстовых макросах см. в статье [Generic-Text Mappings](../c-runtime-library/generic-text-mappings.md) (Универсальные текстовые сопоставления).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Интернационализация](../c-runtime-library/internationalization.md)   
 [Процедуры среды выполнения по категориям](../c-runtime-library/run-time-routines-by-category.md)