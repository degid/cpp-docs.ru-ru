---
title: Константы действий signal
ms.date: 11/04/2016
f1_keywords:
- SIG_IGN
- SIG_DFL
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
ms.openlocfilehash: a7448730501d6f3b50008966134f708ae99ddb5b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830765"
---
# <a name="signal-action-constants"></a>Константы действий signal

Действие, выполняемое при получении сигнала прерывания, зависит от значения `func`.

## <a name="syntax"></a>Синтаксис

```
#include <signal.h>
```

## <a name="remarks"></a>Примечания

Аргумент `func` должен содержать адрес функции или одну из констант манифеста, определенных в SIGNAL.H (перечислены ниже).

|Константа|Описание|
|-|-|
| `SIG_DFL`  | Использует ответ системы по умолчанию. Если вызывающая программа использует потоковый ввод-вывод, созданные библиотекой времени выполнения буферы не очищаются.  |
| `SIG_IGN`  | Игнорирует сигнал прерывания. Это значение нельзя использовать для `SIGFPE`, так как в этом случае состояние процесса с плавающей запятой остается неопределенным.  |
| `SIG_SGE`  | Указывает, что в signal произошла ошибка.  |
| `SIG_ACK`  | Указывает, что было получено подтверждение.  |
| `SIG_ERR`  | Тип значения, возвращаемого из signal с информацией о произошедшей ошибке.  |

## <a name="see-also"></a>См. также раздел

[signal](../c-runtime-library/reference/signal.md);<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
