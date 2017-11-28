---
title: "CRowset::AddRefRows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset<TAccessor>.AddRefRows
- CRowset.AddRefRows
- ATL.CRowset.AddRefRows
- AddRefRows
- CRowset::AddRefRows
- CRowset<TAccessor>::AddRefRows
- ATL::CRowset::AddRefRows
- ATL.CRowset<TAccessor>.AddRefRows
- ATL::CRowset<TAccessor>::AddRefRows
dev_langs: C++
helpviewer_keywords: AddRefRows method
ms.assetid: 590b5a24-870f-4c42-b0c8-28491f368a82
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ad1cf9ea26db3d2bb111090520ccc2dc0930438c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetaddrefrows"></a>CRowset::AddRefRows
Вызовы [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) Увеличиваемое (один) счетчик ссылок, связанных с текущей дескриптор строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
HRESULT AddRefRows( ) throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод увеличивает счетчик ссылок для текущего дескриптора строки. Вызовите [ReleaseRows](../../data/oledb/crowset-releaserows.md) для уменьшения числа. Строки, возвращаемые методами перемещения имеют счетчик ссылок одного.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [CRowset::ReleaseRows](../../data/oledb/crowset-releaserows.md)