---
title: Константы signal
ms.date: 11/04/2016
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
ms.openlocfilehash: d26671b8c3d983e7f1c3fd559d8aa2029e3162fe
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841146"
---
# <a name="signal-constants"></a>Константы signal

## <a name="syntax"></a>Синтаксис

```
#include <signal.h>
```

## <a name="remarks"></a>Примечания

Аргумент `sig` должен представлять собой одну из констант манифеста, определенных в SIGNAL.H (перечислены ниже).

|Константа|Описание|
|-|-|
|SIGABRT|Аварийное завершение. По умолчанию завершает вызывающую программу с кодом выхода 3.  |
|SIGABRT_COMPAT|Аналогично SIGABRT. Для обеспечения совместимости с другими платформами.  |
|SIGFPE|Ошибка операций с плавающей запятой, например переполнение, деление на ноль или недопустимая операция. По умолчанию завершает вызывающую программу.  |
|SIGILL|Недопустимая инструкция. По умолчанию завершает вызывающую программу.  |
|SIGINT|Прерывание CTRL+C. По умолчанию завершает вызывающую программу с кодом выхода 3.  |
|SIGSEGV|Недопустимое обращение к хранилищу. По умолчанию завершает вызывающую программу.  |
|SIGTERM|В программу направлен запрос на прекращение. По умолчанию завершает вызывающую программу с кодом выхода 3.  |
|SIG_ERR|Тип значения, возвращаемого из signal с информацией о произошедшей ошибке.  |

## <a name="see-also"></a>См. также раздел

[signal](../c-runtime-library/reference/signal.md);<br/>
[вести](../c-runtime-library/reference/raise.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
