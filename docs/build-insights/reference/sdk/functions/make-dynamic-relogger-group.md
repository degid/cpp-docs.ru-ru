---
title: MakeDynamicReloggerGroup
description: Справочник по функции MakeDynamicReloggerGroup пакета SDK Аналитики сборок С++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c0d1348be8878e686aeba4a58c407264264c5bc4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224192"
---
# <a name="makedynamicreloggergroup"></a>MakeDynamicReloggerGroup

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MakeDynamicReloggerGroup` используется для создания динамической группы повторной записи в журнал. Члены группы повторной записи в журнал получают события по одному слева направо, пока не будут обработаны все события в трассировке.

## <a name="syntax"></a>Синтаксис

```cpp
auto MakeDynamicReloggerGroup(std::vector<IRelogger*> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::shared_ptr<IRelogger>> reloggers);

auto MakeDynamicReloggerGroup(std::vector<std::unique_ptr<IRelogger>> reloggers);
```

### <a name="parameters"></a>Параметры

*reloggers*\
Вектор указателей [IRelogger](../other-types/irelogger-class.md), включенных в динамическую группу повторной записи в журнал. Эти указатели могут иметь следующий формат: необработанный, `std::unique_ptr` или `std::shared_ptr`. Указатели [IAnalyzer](../other-types/ianalyzer-class.md) также считаются указателями `IRelogger` в силу отношений наследования.

### <a name="return-value"></a>Возвращаемое значение

Динамическая группа повторной записи в журнал. Используйте ключевое слово **`auto`** для захвата возвращаемого значения.

## <a name="remarks"></a>Примечания

В отличие от статических групп повторной записи в журнал, элементы динамической группы повторной записи в журнал могут быть неизвестны во время компиляции. Вы сможете выбрать членов группы повторной записи в журнал во время выполнения на основе входных данных программы или других значений, неизвестных во время компиляции. В отличие от статических групп повторной записи в журнал, указатели [`IRelogger`](../other-types/irelogger-class.md) в динамической группе повторной записи в журнал используют полиморфизм, а вызовы виртуальных функций распределяются правильно. Платой за такую гибкость может стать более длительное время обработки событий. Если все члены группы повторной записи в журнал известны во время компиляции и полиморфизм не требуется, попробуйте применить статическую группу повторной записи в журнал. Для этого вызовите [`MakeStaticReloggerGroup`](make-static-relogger-group.md).

Динамическую группу повторной записи в журнал можно инкапсулировать в статической группе повторной записи в журнал. Затем ее адрес передается в [`MakeStaticReloggerGroup`](make-static-relogger-group.md). Используйте этот метод для передачи динамических групп повторной записи в журнал в такие функции, как [`Relog`](relog.md), которые принимают только статические группы повторной записи в журнал.

::: moniker-end
