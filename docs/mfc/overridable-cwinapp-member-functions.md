---
title: Переопределяемые функции-члены CWinApp
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 7ae72a52c37582f8398ebc03f404ff105fe14650
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624011"
---
# <a name="overridable-cwinapp-member-functions"></a>Переопределяемые функции-члены CWinApp

[CWinApp](reference/cwinapp-class.md) предоставляет несколько ключевых функций-членов, допускающих `CWinApp` Переопределение (переопределяет эти члены из класса [CWinThread](reference/cwinthread-class.md), от которого `CWinApp` наследуется):

- [InitInstance](initinstance-member-function.md)

- [Выполнить](run-member-function.md)

- [ExitInstance](exitinstance-member-function.md)

- [Обработчик](onidle-member-function.md)

Единственной `CWinApp` функцией-членом, которую необходимо переопределить, является `InitInstance` .

## <a name="see-also"></a>См. также раздел

[CWinApp: класс приложений](cwinapp-the-application-class.md)
