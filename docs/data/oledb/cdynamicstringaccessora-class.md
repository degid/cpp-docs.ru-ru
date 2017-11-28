---
title: "Класс CDynamicStringAccessorA | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDynamicStringAccessorA
dev_langs: C++
helpviewer_keywords: CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9e7e2119bf25fda107ff529781efa5c517b01fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicstringaccessora-class"></a>Класс CDynamicStringAccessorA
Дает возможность доступа к источнику данных, если у вас нет сведений о схеме базы данных (базовая структура).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>Примечания  
 Они оба запроса, что поставщик извлечь все данные из хранилища данных в виде строковых данных, но `CDynamicStringAccessor` запросов ANSI строковые данные.  
  
 `CDynamicStringAccessorA`наследует **GetString** и `SetString` из `CDynamicStringAccessor`. При использовании этих методов в `CDynamicStringAccessorA` объекта, ***BaseType*** — **CHAR**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:**atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-класс](../../data/oledb/caccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor-класс](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)