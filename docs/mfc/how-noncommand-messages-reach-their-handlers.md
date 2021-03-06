---
title: Доступ некомандных сообщений к обработчикам
ms.date: 11/04/2016
helpviewer_keywords:
- messages [MFC], routing
- noncommand messages
- Windows messages [MFC], routing
- message handling [MFC], noncommand messages
ms.assetid: e7df8aef-9fae-41f4-9c11-881d8465f602
ms.openlocfilehash: c7b2bf819c5305da4039fae172578298d3b4e609
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618511"
---
# <a name="how-noncommand-messages-reach-their-handlers"></a>Доступ некомандных сообщений к обработчикам

В отличие от команд, стандартные сообщения Windows не направляются через цепочку целевых объектов команд, но обычно обрабатываются окном, в которое Windows отправляет сообщение. Окно может быть основным окном фрейма, дочерним окном MDI, стандартным элементом управления, диалоговым окном, представлением или другим видом дочернего окна.

Во время выполнения каждое окно Windows прикрепляется к объекту окна (производному прямо или косвенно от `CWnd` ), который имеет собственную связанную с ним схему сообщений и функции обработчика. Платформа использует схему сообщений, как для команды, чтобы сопоставлять входящие сообщения с обработчиками.

## <a name="see-also"></a>См. также раздел

[Вызовы обработчика со стороны платформы](how-the-framework-calls-a-handler.md)
