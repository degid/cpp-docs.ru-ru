---
title: Сочетания клавиш для определенного потока
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: 49bac6ac357924c26f131bbd8e1092cd74514167
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511136"
---
# <a name="thread-specific-hot-keys"></a>Сочетания клавиш для определенного потока

Приложение устанавливает горячую клавишу для конкретного потока ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) с помощью функции Windows `RegisterHotKey` . Когда пользователь нажимает на специальную клавишу для конкретного потока, Windows отправляет сообщение [WM_HOTKEY](/windows/win32/inputdev/wm-hotkey) в начало очереди сообщений определенного потока. Сообщение WM_HOTKEY содержит виртуальный код ключа, состояние сдвига и определяемый пользователем идентификатор определенного сочетания клавиш. Список стандартных виртуальных клавиш см. в разделе Winuser.h. Дополнительные сведения об этом методе см. в разделе [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey).

Обратите внимание, что флаги состояния сдвига, `RegisterHotKey` используемые в вызове, не совпадают с параметрами [, возвращаемыми функцией члена функции](../mfc/reference/chotkeyctrl-class.md#gethotkey) . перед вызовом `RegisterHotKey`необходимо преобразовать эти флаги.

## <a name="see-also"></a>См. также

[Использование CHotKeyCtrl](../mfc/using-chotkeyctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
