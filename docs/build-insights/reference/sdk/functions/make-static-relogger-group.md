---
title: MakeStaticReloggerGroup
description: Справочник по функциям пакета средств разработки C++ MakeStaticReloggerGroup для аналитики сборки.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b74ee778ffafbcb4c292b4b36b309d5ff4d66c27
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224166"
---
# <a name="makestaticreloggergroup"></a>MakeStaticReloggerGroup

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MakeStaticReloggerGroup` используется для создания статической группы повторной записи, которую можно передать в такие функции, как [Relog](relog.md). Члены группы повторной записи в журнал получают события по одному слева направо, пока не будут обработаны все события в трассировке.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename... TReloggerPtrs>
auto MakeStaticReloggerGroup(TReloggerPtrs... reloggers);
```

### <a name="parameters"></a>Параметры

*TReloggerPtrs*\
Этот параметр выводится во всех случаях.

*reloggers*\
Пакет параметров для указателей [`IRelogger`](../other-types/irelogger-class.md), включенных в статическую группу повторной записи. Эти указатели могут иметь следующий формат: необработанный, `std::unique_ptr` или `std::shared_ptr`. Указатели [`IAnalyzer`](../other-types/ianalyzer-class.md) также считаются указателями `IRelogger` в силу отношений наследования.

### <a name="return-value"></a>Возвращаемое значение

Статическая группа повторной записи в журнал. Используйте ключевое слово **`auto`** для захвата возвращаемого значения.

## <a name="remarks"></a>Примечания

В отличие от динамических групп повторной записи, элементы статической группы повторной записи должны быть известны во время компиляции. Кроме того, статическая группа повторной записи содержит указатели [`IRelogger`](../other-types/irelogger-class.md), которые не имеют полиморфизма. При использовании статической группы повторной записи для анализа трассировки событий Windows (ETW) вызовы к интерфейсу `IRelogger` всегда будут разрешаться в объект, на который непосредственно указывает элемент группы повторной записи. Такая утрата гибкости связана с возможностью ускоренной обработки событий. Если элементы группы повторной записи неизвестны во время компиляции или требуется полиморфизм для указателей `IRelogger`, рекомендуется использовать динамическую группу повторной записи. Вы можете использовать динамическую группу повторной записи, вызвав [`MakeDynamicReloggerGroup`](make-dynamic-relogger-group.md).

::: moniker-end
