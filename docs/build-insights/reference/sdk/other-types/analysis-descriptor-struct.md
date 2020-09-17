---
title: структура ANALYSIS_DESCRIPTOR
description: Ссылка на структуру SDK Build Insights sDK ANALYSIS_DESCRIPTOR.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1de7f2a5bc3f02a327daaecf8c2cebc44687ba43
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323613"
---
# <a name="analysis_descriptor-structure"></a>структура ANALYSIS_DESCRIPTOR

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `ANALYSIS_DESCRIPTOR` используется с функциями [AnalyseA](../functions/analyze-a.md) и [AnalyseW.](../functions/analyze-w.md) В нем описывается, как следует анализировать отслеживание событий для Windows (ETW).

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `NumberOfPasses` | Количество проходов анализа, которое должно быть сделано по следу ETW. |
| `Callbacks` | Объект [ANALYSIS_CALLBACKS,](analysis-callbacks-struct.md) который определяет, какие функции можно вызвать во время сеанса анализа. |
| `Context` | Контекст, предоставляемый пользователем, который передается в качестве аргумента для всех функций обратного вызова, указанных в`Callbacks` |

## <a name="remarks"></a>Примечания

Структура `Callbacks` принимает только указатели на функции, не являщиеся членами. Это ограничение можно обойти, `Context` установив указатель объекта. Этот указатель объекта будет передан в качестве аргумента всем вашим функциям обратного вызова, не являешься участником. Используйте этот указатель для вызова функций членов из ваших функций обратного вызова, не являваемых членами.

::: moniker-end
