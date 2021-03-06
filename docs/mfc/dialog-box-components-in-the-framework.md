---
title: Компоненты диалоговых окон в платформе
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], creating
- dialog classes [MFC], dialog box components
- MFC dialog boxes [MFC], about MFC dialog boxes
- dialog templates [MFC], MFC framework
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 592db160-0a8a-49be-ac72-ead278aca53f
ms.openlocfilehash: b3290107337f60854e6abbd2f744aaa38af0b741
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616925"
---
# <a name="dialog-box-components-in-the-framework"></a>Компоненты диалоговых окон в платформе

В платформе MFC диалоговое окно содержит два компонента:

- Ресурс диалогового шаблона, указывающий элементы управления диалогового окна и их размещение.

   В ресурсе диалогового окна сохраняется шаблон диалогового окна, из которого Windows создает диалоговое окно и отображает его. Шаблон определяет характеристики диалогового окна, включая его размер, расположение, стиль, а также типы и положения элементов управления диалогового окна. Обычно используется шаблон диалогового окна, хранящийся в качестве ресурса, но можно также создать собственный шаблон в памяти.

- Класс диалогового окна, производного от класса [CDialog](reference/cdialog-class.md), для предоставления программного интерфейса для управления диалоговым окном.

   Диалоговое окно является окном и будет присоединено к окну Windows, когда оно видимо. При создании диалогового окна ресурс диалога-шаблона используется в качестве шаблона для создания дочерних элементов управления окна для диалогового окна.

## <a name="see-also"></a>См. также раздел

[Диалоговые окна](dialog-boxes.md)<br/>
[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)
