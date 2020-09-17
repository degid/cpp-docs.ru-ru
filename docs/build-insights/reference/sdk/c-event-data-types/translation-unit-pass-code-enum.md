---
title: TRANSLATION_UNIT_PASS_CODE enum
description: SDK Build Insights TRANSLATION_UNIT_PASS_CODE ссылку.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TRANSLATION_UNIT_PASS_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b0162d7e53bb7ee7035b94a6b640f6db87cd8b8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325288"
---
# <a name="translation_unit_pass_code-enum"></a>TRANSLATION_UNIT_PASS_CODE enum

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

В `TRANSLATION_UNIT_PASS_CODE` enum.

## <a name="members"></a>Участники

| name | Значение | Описание |
|--|--|--|
| `TRANSLATION_UNIT_PASS_CODE_FRONT_END` | 0 (0x0000000000) | Передний проход, ответственный за разбор исходного кода и преобразование его в промежуточный язык. |
| `TRANSLATION_UNIT_PASS_CODE_BACK_END` | 1 (0x00000001) | Обратный проход, ответственный за оптимизацию промежуточного языка и преобразование его в машинный код. |

## <a name="remarks"></a>Примечания

Используется функциями C SDK.

::: moniker-end
