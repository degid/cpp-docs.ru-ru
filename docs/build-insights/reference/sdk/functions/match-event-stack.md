---
title: MatchEventStack
description: Справочник по функции MatchEventStack пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ae476c402c3ea0cad558ce41a979b4233e0f1dd3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224127"
---
# <a name="matcheventstack"></a>MatchEventStack

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEventStack` используется для сопоставления стека событий с определенной иерархией событий. Подходящие иерархии пересылаются обработчику для дальнейшей обработки. Дополнительные сведения о событиях, стеках событий и иерархиях см. в [таблице событий](../event-table.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename          TEvent,
    typename...       TEvents,
    typename          TCallable,
    typename...       TExtraArgs>
bool MatchEventStack(
    const EventStack& eventStack,
    TCallable&&       callable,
    TExtraArgs&&...   extraArgs);
```

### <a name="parameters"></a>Параметры

*TEvent*\
Тип самого старого родительского элемента для сопоставления в стеке событий.

*TEvents*\
Остальные типы, которые вы хотите сопоставить в стеке событий.

*TCallable*\
Тип, который поддерживает `operator()`. Дополнительные сведения о том, какие аргументы передаются этому оператору, см. в описании параметра *callable*.

*TExtraArgs*\
Типы дополнительных аргументов в `MatchEventStack`.

*eventStack*\
Стек событий для сопоставления с иерархией типов событий, описанной в *TEvent*...*TEvents*.

*callable*\
После успешного сопоставления стека событий с иерархией типов событий, описанной в *TEvent* и *TEvents*, `MatchEventStack` вызывает *callable*. Он передает в *callable* один аргумент r-значения для каждого типа в иерархии событий. Пакет параметров *extraArgs* передается в неизменном виде в остальных параметрах *callable*.

*extraArgs*\
Аргументы, которые без изменений перенаправляются в *callable* вместе с сопоставленным типом события.

### <a name="return-value"></a>Возвращаемое значение

Параметр типа **`bool`** , который принимает значение **`true`** в случае успешного сопоставления или **`false`** в противном случае.

## <a name="remarks"></a>Примечания

Последнее событие в *eventStack* всегда сопоставляется с последней записью в сцепленном списке типов \[*TEvent*, *TEvents...* \]. Все остальные элементы в *TEvent* и *TEvents* могут соответствовать любому положению в *eventStack*, за исключением последнего, если расположены в том же порядке.

Тип события для параметров *TEvent* и *TEvents* можно выбрать из списка *классов захвата*. Список событий и классы захвата, которые можно использовать для сопоставления, см. в [таблице событий](../event-table.md).

## <a name="example"></a>Пример

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    bool b1 = MatchEventStack<Compiler, BackEndPass, C2DLL,
                CodeGeneration, Thread, Function>(
        eventStack, [](Compiler cl, BackEndPass bep, C2DLL c2,
            CodeGeneration cg, Thread t, Function f){ /* Do something ... */ });

    bool b2 = MatchEventStack<Compiler, Function>(
        eventStack, [](Compiler cl, Function f){ /* Do something... */ });

    bool b3 = MatchEventStack<Thread, Compiler, Function>(
        eventStack, [](Thread t, Compiler cl Function f){ /* Do something... */ });

    bool b4 = MatchEventStack<Compiler>(
        eventStack, [](Compiler cl){ /* Do something... */ });


    // b1: true because the list of types matches the eventStack exactly.
    // b2: true because Function is the last entry in both the type list
    //     and 'eventStack', and also because Compiler comes before
    //     Function in 'eventStack' and in the type list.
    // b3: false because, even though both Thread and Compiler come
    //     before Function in 'eventStack', they aren't listed in the
    //     right order in the type list.
    // b4: false because the last entry in the type list is Compiler,
    //     which doesn't match the last entry in 'eventStack' (Function).
}
```

::: moniker-end
