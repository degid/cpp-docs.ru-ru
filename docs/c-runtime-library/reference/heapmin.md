---
title: "_heapmin | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _heapmin
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _heapmin
- heapmin
dev_langs: C++
helpviewer_keywords:
- heap memory
- minimizing heaps
- memory, releasing
- heaps, releasing unused memory
- _heapmin function
- heapmin function
ms.assetid: c0bccdf6-2d14-4d7b-a7ff-d6a17bdb410f
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1318e8d18ddeb5031efdf3066f9fa3020c8e9afd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="heapmin"></a>_heapmin
Освобождает неиспользуемую память кучи для операционной системы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _heapmin( void );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения `_heapmin` возвращает 0; в противном случае функция возвращает –1 и задает для `errno` значение `ENOSYS`.  
  
 Дополнительные сведения об этом и других кодах возврата см. в статье [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_heapmin` устанавливает минимальный размер кучи, высвобождая неиспользуемую память для операционной системы. Если операционная система не поддерживает `_heapmin`(например, Windows 98), функция возвращает -1 и задает `errno` для `ENOSYS`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_heapmin`|\<malloc.h>|\<errno.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="see-also"></a>См. также  
 [Выделение памяти](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [_heapset](../../c-runtime-library/heapset.md)   
 [_heapwalk](../../c-runtime-library/reference/heapwalk.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)