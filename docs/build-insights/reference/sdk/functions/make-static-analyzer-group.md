---
title: MakeStaticAnalyzerGroup
description: Справочник по функциям пакета средств разработки C++ MakeStaticAnalyzerGroup для аналитики сборки.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 81c5654c78e086af1c33d0791768ceea52575c51
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224179"
---
# <a name="makestaticanalyzergroup"></a>MakeStaticAnalyzerGroup

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MakeStaticAnalyzerGroup` используется для создания статической группы анализаторов, которую можно передать в такие функции, как [`Analyze`](analyze.md) или [`Relog`](relog.md). Члены группы анализаторов получают события по одному слева направо, пока не будут проанализированы все события в трассировке.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>Параметры

*TAnalyzerPtrs*\
Этот параметр выводится во всех случаях.

*analyzers*\
Пакет параметров для указателей [`IAnalyzer`](../other-types/ianalyzer-class.md), включенных в статическую группу анализаторов. Эти указатели могут иметь следующий формат: необработанный, `std::unique_ptr` или `std::shared_ptr`.

### <a name="return-value"></a>Возвращаемое значение

Статическая группа анализаторов. Используйте ключевое слово **`auto`** для захвата возвращаемого значения.

## <a name="remarks"></a>Примечания

В отличие от динамических групп анализаторов, элементы статической группы анализаторов должны быть известны во время компиляции. Кроме того, статическая группа анализаторов содержит указатели [`IAnalyzer`](../other-types/ianalyzer-class.md), которые не имеют полиморфизма. При использовании статической группы анализаторов для анализа трассировки событий Windows (ETW) вызовы к интерфейсу `IAnalyzer` всегда будут разрешаться в объект, на который непосредственно указывает элемент группы анализаторов. Такая утрата гибкости связана с возможностью ускоренной обработки событий. Если элементы группы анализаторов неизвестны во время компиляции или требуется полиморфизм для указателей `IAnalyzer`, рекомендуется использовать динамическую группу анализаторов. Чтобы использовать динамическую группу анализаторов, вызовите [`MakeDynamicAnalyzerGroup`](make-static-analyzer-group.md).

::: moniker-end
