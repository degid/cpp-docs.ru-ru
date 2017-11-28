---
title: "towctrans | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- towctrans
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- towctrans
dev_langs:
- C++
helpviewer_keywords:
- towctrans function
ms.assetid: 1ed1e70d-7b31-490f-a7d9-42564b5924ca
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: fcd97b3af0bb7e469db18b1a7ff8290af5df1bc4
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="towctrans"></a>towctrans
Преобразует символ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
wint_t towctrans(  
   wint_t c,  
   wctrans_t category   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `c`  
 Символ, который требуется преобразовать.  
  
 `category`  
 Идентификатор, который содержит возвращаемое значение [wctrans](../../c-runtime-library/reference/wctrans.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Символ `c` после того, как функция `towctrans` использовала правило преобразования в категории `category`.  
  
## <a name="remarks"></a>Примечания  
 Значение `category` должно возвращаться предыдущим успешным вызовом функции [wctrans](../../c-runtime-library/reference/wctrans.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`towctrans`|\<wctype.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 Пример использования функции `wctrans` см. в разделе `towctrans`.  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)