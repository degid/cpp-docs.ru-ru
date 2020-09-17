---
title: /SWAPRUN
ms.date: 11/04/2016
f1_keywords:
- /swaprun_editbin
helpviewer_keywords:
- /SWAPRUN editbin option
- -SWAPRUN editbin option
- SWAPRUN editbin option
ms.assetid: 6eefd7f3-ca47-48e3-8509-323d27cf4ae7
ms.openlocfilehash: 83aa2cdb445ed1ac6bac5b1237f90a116986b0a9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438847"
---
# <a name="swaprun"></a>/SWAPRUN

```
/SWAPRUN:{[!]NET|[!]CD}
```

## <a name="remarks"></a>Примечания

Этот параметр изменяет образ, чтобы операционная система скопировала образ в файл подкачки и запустил его. Используйте этот параметр для образов, которые находятся в сетях или съемных носителях.

Можно добавить или удалить квалификаторы NET или CD.

- Параметр NET указывает, что образ находится в сети.

- CD указывает, что образ находится на компакт-диске или аналогичном съемном носителе.

- Используйте! NET и! CD для отмены эффектов NET и CD.

## <a name="see-also"></a>См. также раздел

[Параметры EDITBIN](editbin-options.md)
