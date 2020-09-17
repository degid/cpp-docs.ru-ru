---
title: MakeDynamicAnalyzerGroup
description: Справочник по функциям MakeDynamicAnalyzerGroup пакета SDK Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeDynamicAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c4c244066b41837a8dd95b44bab2b096134ed5d4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224205"
---
# <a name="makedynamicanalyzergroup"></a>MakeDynamicAnalyzerGroup

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MakeDynamicAnalyzerGroup` используется для создания динамической группы анализаторов. Члены группы анализаторов получают события по одному слева направо, пока не будут проанализированы все события в трассировке.

## <a name="syntax"></a>Синтаксис

```cpp
auto MakeDynamicAnalyzerGroup(std::vector<IAnalyzer*> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::shared_ptr<IAnalyzer>> analyzers);

auto MakeDynamicAnalyzerGroup(std::vector<std::unique_ptr<IAnalyzer>> analyzers);
```

### <a name="parameters"></a>Параметры

*analyzers*\
Вектор указателей [IAnalyzer](../other-types/ianalyzer-class.md), включенных в динамическую группу анализаторов. Эти указатели могут иметь следующий формат: необработанный, `std::unique_ptr` или `std::shared_ptr`.

### <a name="return-value"></a>Возвращаемое значение

Динамическая группа анализаторов. Используйте ключевое слово **`auto`** для захвата возвращаемого значения.

## <a name="remarks"></a>Примечания

В отличие от статических групп анализаторов, элементы динамической группы анализаторов могут быть неизвестны во время компиляции. Вы сможете выбрать членов группы анализаторов во время выполнения на основе входных данных программы или других значений, неизвестных во время компиляции. В отличие от статических групп анализаторов, указатели [`IAnalyzer`](../other-types/ianalyzer-class.md) в динамической группе анализаторов используют полиморфизм, а вызовы виртуальных функций распределяются правильно. Платой за такую гибкость может стать более длительное время обработки событий. Если все члены группы анализаторов известны во время компиляции и полиморфизм не требуется, попробуйте применить статическую группу анализаторов. Для этого вызовите [`MakeStaticAnalyzerGroup`](make-static-analyzer-group.md).

Динамическую группу анализаторов можно инкапсулировать внутри статической группы анализаторов. Для этого ее адрес следует передать в [`MakeStaticAnalyzerGroup`](make-static-analyzer-group.md). Используйте этот метод для передачи динамических групп анализатора в такие функции, как [`Analyze`](analyze.md), которые принимают только статические группы анализаторов.

::: moniker-end
