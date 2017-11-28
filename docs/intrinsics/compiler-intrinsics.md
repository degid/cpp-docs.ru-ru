---
title: "Встроенные объекты компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- intrinsics, compiler
- compiler intrinsics
- cl.exe compiler, performance
- cl.exe compiler, intrinsics
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 53d6986d569bbf928282dce9e9e1cba0601bc4ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-intrinsics"></a>Встроенные объекты компилятора
Большинство функций содержатся в библиотеках, но некоторые функции, встроенные (то есть внутренние) в компилятор. Они называются встроенными или внутренними функциями .  
  
## <a name="remarks"></a>Примечания  
 Если функция встроенная, код для этой обычно функции уже вставлен внутрь, что позволяет избежать вызова функции и позволяет максимально эффективно подготовить машинные инструкций для этой функции. Встроенная функция часто быстрее, чем эквивалентный встроенный ассемблер, потому что оптимизатор имеет собственные сведения о том, как ведут себя встроенные функции, поэтому могут быть доступны некоторые оптимизации, которые недоступны при использовании встроенный ассемблер. Кроме того, оптимизатор можно развернуть встроенную функцию по-разному, по-разному выровнять буферы или внести другие подстройки в зависимости от контекста и аргументов вызова.  
  
 Использование встроенных функций влияет на переносимость кода, поскольку встроенные функции, которые доступны в Visual C++, могут быть недоступны, если код компилируется с помощью других компиляторов, и некоторые встроенные функции, которые могут быть доступны для некоторых целевых архитектур, не доступны для всех архитектур. Однако встроенные функции обычно более переносимы по сравнению с встроенным ассемблером. Встроенные функции требуются для 64-разрядных архитектур, где встроенный ассемблер не поддерживается.  
  
 Некоторые встроенные функции, такие как `__assume` и `__ReadWriteBarrier`, передают компилятору информацию, которая влияет на поведение оптимизатора.  
  
 Некоторые встроенные функции доступны только как встроенные функции, а некоторые доступны как функции и их встроенные реализации. Можно указать компилятору использовать встроенные реализации одним из двух способов, в зависимости от того, хотите ли вы включить только определенные функции или нужно включить все встроенные функции. Первый способ — использовать `#pragma intrinsic(` *встроенная функция имя список-*`)`. Директива pragma может использоваться для указания одной или нескольких встроенных функций, разделенных запятыми. Второй — для использования [/Oi (Создание встроенных функций)](../build/reference/oi-generate-intrinsic-functions.md) параметр компилятора, который делает доступными все встроенные функции для данной платформы. В разделе **/Oi**, используйте `#pragma function(` *встроенная функция имя список-* `)` для принудительного вызова нужной функции вместо встроенной функции. Если в документации для определенных встроенных функций отмечает, что процедура доступна только как встроенная функция, то внутренняя реализация используется независимо **/Oi** или `#pragma intrinsic` указано. Во всех случаях **/Oi** или `#pragma intrinsic` позволяет, но не заставляет, оптимизатор запросов использовать встроенную функцию. Оптимизатор может по-прежнему вызвать функцию.  
  
 Некоторые стандартные функции библиотеки C/C++, доступные как встроенные реализации для некоторых архитектур. При вызове функции CRT, встроенная реализация используется, если **/Oi** указан в командной строке.  
  
 Файл заголовка \<intrin.h >, является объявлять прототипы для распространенных встроенных функций. Встроенные функции производителя доступны в \<immintrin.h > и \<ammintrin.h > файлы заголовков. Кроме того некоторые заголовки Windows объявляют функции, которые ссылаются на встроенные функции компилятора.  
  
 В следующих разделах перечислены все встроенные функции, доступные для различных архитектур. Дополнительные сведения об использовании встроенных функций для конкретного целевого процессора можно найти в документации производителя.  
  
-   [Встроенные объекты ARM](../intrinsics/arm-intrinsics.md)  
  
-   [Список встроенных объектов x86](../intrinsics/x86-intrinsics-list.md)  
  
-   [Список встроенных объектов x64 (amd64)](../intrinsics/x64-amd64-intrinsics-list.md)  
  
-   [Встроенные объекты, доступные для всех архитектур](../intrinsics/intrinsics-available-on-all-architectures.md)  
  
-   [Алфавитный список встроенных функций](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)  
  
## <a name="see-also"></a>См. также  
 [Справочник по ассемблеру ARM](../assembler/arm/arm-assembler-reference.md)   
 [Справочник по Microsoft Macro Assembler](../assembler/masm/microsoft-macro-assembler-reference.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Справочник по библиотеке времени выполнения C](../c-runtime-library/c-run-time-library-reference.md)