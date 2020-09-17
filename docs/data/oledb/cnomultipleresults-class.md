---
title: Класс CNoMultipleResults
ms.date: 11/04/2016
f1_keywords:
- CNoMultipleResults
- ATL.CNoMultipleResults
- ATL::CNoMultipleResults
helpviewer_keywords:
- CNoMultipleResults class
ms.assetid: 343e77c4-b319-476e-b592-901ab9b2f34e
ms.openlocfilehash: 793b820264d001fbfbf7920fd322a55b98e90f0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211722"
---
# <a name="cnomultipleresults-class"></a>Класс CNoMultipleResults

Используется в качестве аргумента шаблона (*тмултипле*) [для создания](../../data/oledb/ccommand-class.md) оптимизированной команды, обрабатывающей один результирующий набор.

## <a name="syntax"></a>Синтаксис

```cpp
class CNoMultipleResults
```

## <a name="remarks"></a>Примечания

Если требуется, чтобы команда обрабатывала несколько результирующих наборов, используйте вместо него [CMultipleResults](../../data/oledb/cmultipleresults-class.md) .

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
