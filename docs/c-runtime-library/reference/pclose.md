---
title: "_pclose | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _pclose
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _pclose
- pclose
dev_langs: C++
helpviewer_keywords:
- _pclose function
- pclose function
- pipes, closing
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 13609bbe4dae9b493b8467fd0ac9fe7d1437fa83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="pclose"></a>_pclose
Ожидает новый обработчик команд и закрывает поток по связанному каналу.  
  
> [!IMPORTANT]
>  Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      int _pclose(  
FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Возвращаемое значение из предыдущего вызова функции `_popen`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает состояние завершения завершающий обработчик команд, или значение -1 при возникновении ошибки. Формат возвращаемого значения является идентичным формату соответствующего значения `_cwait`, за исключением того, что байты низкого и байты высокого порядка меняются местами. Если поток имеет значение **NULL**, то функция `_pclose` задает для `errno` значение `EINVAL` и возвращает –1.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_pclose` выполняет поиск идентификатора процесса в обработчике команд (Cmd.exe), запущенного связанным вызовом `_popen`, выполняет вызов [_cwait](../../c-runtime-library/reference/cwait.md) в новом обработчике команд и закрывает поток по связанному каналу.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`_pclose`|\<stdio.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [_pipe](../../c-runtime-library/reference/pipe.md)   
 [_popen, _wpopen](../../c-runtime-library/reference/popen-wpopen.md)