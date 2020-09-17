---
title: MatchEvent
description: Справочник по функции MatchEvent пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8ec2c6bfcacf28998058dc66b5f363fbf1ea5d70
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224114"
---
# <a name="matchevent"></a>MatchEvent

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEvent` используется для сопоставления событий со списком типов событий. Если событие соответствует типу в этом списке, оно передается обработчику для дальнейшей обработки.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename        TEvent,
    typename...     TEvents,
    typename        TCallable,
    typename...     TExtraArgs>
bool MatchEvent(
    const RawEvent& event,
    TCallable&&     callable,
    TExtraArgs&&... extraArgs);
```

### <a name="parameters"></a>Параметры

*TEvent*\
Первый тип события для сопоставления.

*TEvents*\
Остальные типы события для сопоставления.

*TCallable*\
Тип, который поддерживает `operator()`. Дополнительные сведения о том, какие аргументы передаются этому оператору, см. в описании параметра *callable*.

*TExtraArgs*\
Типы дополнительных аргументов, переданных в `MatchEvent`.

*event*\
Событие для сопоставления с типом события, который описан в *TEvent* и *TEvents*.

*callable*\
`MatchEvent` вызывает *callable* после успешного сопоставления события с любым из типов событий, которые описаны в *TEvent* и *TEvents*. Первый аргумент, передаваемый в *callable*, является значением r для сопоставленного типа события. Пакет параметров *extraArgs* передается в неизменном виде в остальных параметрах *callable*.  

*extraArgs*\
Аргументы, которые без изменений перенаправляются в *callable* вместе с сопоставленным типом события.

### <a name="return-value"></a>Возвращаемое значение

Параметр типа **`bool`** , который принимает значение **`true`** в случае успешного сопоставления или **`false`** в противном случае.

## <a name="remarks"></a>Примечания

Тип события для параметров *TEvent* и *TEvents* можно выбрать из списка *классов захвата*. Список событий и классы захвата, которые можно использовать для сопоставления, см. в [таблице событий](../event-table.md).

## <a name="example"></a>Пример

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEvent<Function, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});

    bool b2 = MatchEvent<CodeGeneration, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});


    // b1: true because the list of types contains Function, which is
    //     the type of the event we are trying to match.
    // b2: false because the list of types doesn't contain Function.
}
```

::: moniker-end
