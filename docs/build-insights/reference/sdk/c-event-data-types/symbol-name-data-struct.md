---
title: структура SYMBOL_NAME_DATA
description: Ссылка на структуру СЗ Build Insights SDK SYMBOL_NAME_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1217572f20a772fde629533d6ab170c14dc5b5e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325341"
---
# <a name="symbol_name_data-structure"></a>структура SYMBOL_NAME_DATA

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Структура `SYMBOL_NAME_DATA` описывает фронтовой символ компилятора.

## <a name="syntax"></a>Синтаксис

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>Участники

|  |  |
|--|--|
| `Key` | Ключ символа. Это значение является уникальным в анализируемом следе. |
| `Name` | Название символа. |

## <a name="remarks"></a>Примечания

Символы, исходящие от двух различных компилятора переднего конца проходит может иметь то же имя, но другой ключ. В этом случае используйте имена символов, чтобы определить, одинаковы ли два типа.

::: moniker-end
