---
title: "__uncaught_exception | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __uncaught_exception
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- __uncaught_exception
dev_langs:
- C++
helpviewer_keywords:
- __uncaught_exception
ms.assetid: 4d9b75c6-c9c7-4876-b761-ea9ab1925e96
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2b43a6b08087dcaeeda7959eaadbee9c250f4de9
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="uncaughtexception"></a>__uncaught_exception
Указывает, возникло ли одно или несколько исключений, которые еще не были обработаны с помощью соответствующего блока `catch` инструкции [try-catch](../../cpp/try-throw-and-catch-statements-cpp.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
bool __uncaught_exception(  
   );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение `true` с момента возникновения исключения в блоке `try` и до инициализации соответствующего блока `catch`; в противном случае — `false`.  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|__uncaught_exception|eh.h|  
  
## <a name="see-also"></a>См. также  
 [Операторы try, throw и catch (C++)](../../cpp/try-throw-and-catch-statements-cpp.md)