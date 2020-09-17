---
title: Стили элемента управления панели инструментов
ms.date: 11/04/2016
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
ms.openlocfilehash: eab4dbde68fcebdb0afd0d058b4678c464874c81
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837129"
---
# <a name="toolbar-control-styles"></a>Стили элемента управления панели инструментов

[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) имеет набор флагов стиля, определяющих внешний вид и поведение кнопки. Сочетание этих флагов можно задать, вызвав [CMFCToolBarButton:: SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). В этом разделе перечислены значения флагов стиля и их значение.

## <a name="property-values"></a>Значения свойств

Следующие значения определяют тип кнопки, которую представляет элемент управления:

|Имя|Описание|
|-|-|
|TBBS_BUTTON|Стандартная кнопка (по умолчанию).  |
|TBBS_CHECKBOX|Флажок.  |
|TBBS_CHECKGROUP|Начало группы флажков.  |
|TBBS_GROUP|Начало группы кнопок.  |
|TBBS_SEPARATOR|Двоеточи.  |

Следующие значения представляют текущее состояние элемента управления:

|Имя|Описание|
|-|-|
|TBBS_CHECKED|Флажок установлен.  |
|TBBS_DISABLED|Элемент управления отключен.  |
|TBBS_INDETERMINATE|Флажок находится в неопределенном состоянии.  |
|TBBS_PRESSED|Нажата кнопка.  |

Следующее значение изменяет макет кнопки на панели инструментов:

|Имя|Описание|
|-|-|
|TBBS_BREAK|Помещает элемент на новую строку или в новый столбец без разделения столбцов.  |

## <a name="remarks"></a>Примечания

Текущий стиль хранится в [CMFCToolBarButton:: m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). Не устанавливайте новое значение                 `m_nStyle` напрямую, так как некоторые производные классы выполняют дополнительную обработку при вызове `SetStyles` .

Визуальный диспетчер определяет внешний вид кнопок в каждом состоянии. Дополнительные сведения см. в статье [Диспетчер визуализации](../../mfc/visualization-manager.md) .

## <a name="requirements"></a>Требования

**Заголовок:** афкстулбарбуттон.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Класс CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Диспетчер визуализации](../../mfc/visualization-manager.md)
