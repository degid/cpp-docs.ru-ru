---
title: структура TEMPLATE_INSTANTIATION_DATA
description: Ссылка на структуру СЗ Build Insights SDK TEMPLATE_INSTANTIATION_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a38d19368e7c0a9912907f1da6e7a2e31ffe8d90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325334"
---
# <a name="template_instantiation_data-structure"></a>структура TEMPLATE_INSTANTIATION_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `TEMPLATE_INSTANTIATION_DATA` описывает мгновенное значение шаблона.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct TEMPLATE_INSTANTIATION_DATA_TAG
{
    unsigned long long  SpecializationSymbolKey;
    unsigned long long  PrimaryTemplateSymbolKey;
    int                 KindCode;

} TEMPLATE_INSTANTIATION_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `SpecializationSymbolKey` | Ключ для типа специализации шаблона. Это значение является уникальным в анализируемом следе. |
| `PrimaryTemplateSymbolKey` | Ключ для основного типа шаблона, который был специализированным. Это значение является уникальным в анализируемом следе. |
| `KindCode` | Тип мгновенного шаблона. Для получения дополнительной информации смотрите [TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md). |

## <a name="remarks"></a>Примечания

Ключи в `TEMPLATE_INSTANTIATION_DATA` структуре уникальны в анализируемом следе. Тем не менее, два разных ключа, поступающие из разных проходов фронт-энда компилятора, могут указывать на два одинаковых типа. При `TEMPLATE_INSTANTIATION_DATA` употреблении информации из нескольких проходов фронт-энда компилятора используйте [SYMBOL_NAME](../event-table.md#symbol-name) события, чтобы определить, являются ли два типа одинаковыми. `SymbolName`события излучаются в конце переднего прохода компилятора, после того, как все моменты шаблона имели место.

::: moniker-end
