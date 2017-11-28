---
title: "Обработка исключений в Visual C++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 622bf0194cbf5c3207d161edefcf7da23238fb85
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="exception-handling-in-visual-c"></a>Обработка исключений в Visual C++
Исключение — это условие ошибки, возможно вне элемента управления программы, которое не позволяет продолжать выполнение программы по обычному пути выполнения. Некоторые операции, включая создание объектов, ввод-вывод файлов и вызовы функций из других модулей, — это возможные источники исключений, даже если программа выполняется правильно. В надежном коде можно предвидеть и обработать исключения.  
  
 Чтобы обнаружить логические ошибки в одной программе или модуле, использовать утверждения вместо исключений (см. [использование утверждений](/visualstudio/debugger/c-cpp-assertions)).  
  
 Visual C++ поддерживает три типа обработки исключений.  
  
-   [Обработка исключений с ++](../cpp/cpp-exception-handling.md)  
  
     В большинстве программ на языке C++ необходимо использовать обработку исключений C++, поскольку она является типобезопасной и гарантирует вызов деструкторов объектов во время очистки стека.  
  
-   [Структурированная обработка исключений](../cpp/structured-exception-handling-c-cpp.md)  
  
     Windows предоставляет собственный механизм исключений — SEH. Его не рекомендуется использовать при программировании C++ или MFC. Используйте SEH только в программах C, не являющихся MFC.  
  
-   [Исключения MFC](../mfc/exception-handling-in-mfc.md)  
  
     Начиная с версии 3.0, MFC использует исключения C++, но по-прежнему поддерживает более старые макросы обработки исключений, которые по форме схожи с исключениями C++. Хотя эти макросы не рекомендуется использовать в новом программировании, они по-прежнему поддерживаются для обеспечения обратной совместимости. В программах, в которых уже используются макросы, можно также свободно использовать исключения C++. Во время предварительной обработки макросы вычисляются как ключевые слова обработки исключений, определенные в реализации Visual C++ языка C++, начиная с версии Visual C++ 2.0. Начиная работать с исключениями C++, разработчик может оставить существующие макросы исключений.  
  
 Используйте [/EH](../build/reference/eh-exception-handling-model.md) параметр компилятора, чтобы указать тип обработки исключений для использования в проекте; По умолчанию используется обработка исключений с ++. Не следует комбинировать механизмы обработки ошибок, например не следует использовать исключения C++ со структурированной обработкой исключений. Использование механизма обработки исключений языка C++ позволяет написать более переносимый код и обрабатывать исключения любого типа. Дополнительные сведения о недостатках структурированной обработки исключений см. в разделе [структурированную обработку исключений](../cpp/structured-exception-handling-c-cpp.md). Дополнительные сведения о комбинировании макросов MFC и исключений C++, в разделе [исключения: использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).  
  
 Сведения об обработке исключений в приложениях CLR см. в разделе [обработка исключений](../windows/exception-handling-cpp-component-extensions.md).  
  
 Сведения об исключении, обработку x64 процессоров, в разделе [(x64) обработка исключений](../build/exception-handling-x64.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по языку C++](../cpp/cpp-language-reference.md)