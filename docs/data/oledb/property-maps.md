---
title: Сопоставления свойств
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 79a65290c24ab016d9f81b54b9b7720d5c4ff352
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544558"
---
# <a name="property-maps"></a>Сопоставления свойств

С помощью сеанса, набора строк и необязательного объекта команды каждый поставщик поддерживает одно или несколько свойств. Эти свойства определяются в сопоставлениях свойств, которые хранятся в файлах заголовков, созданных **мастером OLE DB Provider**. Каждый файл заголовка содержит карту для свойств в группе свойств OLE DB, определенной для объекта или объектов, определенных в этом файле. Файл заголовка, содержащий объект источника данных, также содержит карту свойства для [свойств DataSource](/previous-versions/windows/desktop/ms724188(v=vs.85)). `Session.h` содержит карту свойств для [свойств сеанса](/previous-versions/windows/desktop/ms714221(v=vs.85)). Набор строк и командные объекты находятся в одном файле заголовка с именем *ProjectName*RS.h. Эти свойства являются элементами группы [свойств набора строк](/previous-versions/windows/desktop/ms711252(v=vs.85)) .

## <a name="see-also"></a>См. также:

[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
