---
title: Преобразование данных, не поддерживаемых поставщиком
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
ms.openlocfilehash: e87aebc4d6f23343af9a2f966d2c522e95b304ea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211501"
---
# <a name="converting-data-not-supported-by-the-provider"></a>Преобразование данных, не поддерживаемых поставщиком

Когда потребитель запрашивает тип данных, который не поддерживается поставщиком, код шаблона поставщика OLE DB для `IRowsetImpl::GetData` вызывает Мсдадк. dll для преобразования типа данных.

При реализации интерфейса, такого как `IRowsetChange`, для которого требуется преобразование данных, можно вызвать Мсдаенум. dll, чтобы выполнить преобразование. В качестве примера используйте `GetData`, определенные в ATLDB.h.

## <a name="see-also"></a>См. также раздел

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)
