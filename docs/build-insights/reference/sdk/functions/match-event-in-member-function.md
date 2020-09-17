---
title: MatchEventInMemberFunction
description: Справочник по функции MatchEventInMemberFunction пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d3fdc015b0744cb5d0f98a1c9025343b93489ed9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224153"
---
# <a name="matcheventinmemberfunction"></a>MatchEventInMemberFunction

::: moniker range="<=vs-2015"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Функция `MatchEventInMemberFunction` используется для сопоставления событий с типом, который описывается в первом параметре функции-члена. Подходящее событие пересылается функции-члену для дальнейшей обработки.

## <a name="syntax"></a>Синтаксис

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     TEvent,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventInMemberFunction(
    const RawEvent&          event,
    TInterface*              objectPtr,
    TReturn (TInterface::*   memberFunc)(TEvent, TExtraParams...),
    TExtraArgs&&...          extraArgs);
```

### <a name="parameters"></a>Параметры

*TInterface*\
Тип, который содержит функцию-член.

*TReturn*\
Возвращаемый тип функции-члена.

*TEvent*\
Тип события для сопоставления.

*TExtraParams*\
Типы дополнительных параметров, принимаемых функцией-членом, а также тип события для сопоставления.

*TExtraArgs*\
Типы дополнительных аргументов, переданных в `MatchEventInMemberFunction`.

*event*\
Событие для сопоставления с типом события, который описан в *TEvent*.

*objectPtr*\
Указатель на объект, для которого вызывается *memberFunc*.

*memberFunc*\
Функция-член, которая описывает тип события для сопоставления.

*extraArgs*\
Аргументы, которые без изменений перенаправляются в *memberFunc* вместе с параметром типа события.

### <a name="return-value"></a>Возвращаемое значение

Параметр типа **`bool`** , который принимает значение **`true`** в случае успешного сопоставления или **`false`** в противном случае.

## <a name="remarks"></a>Примечания

Тип события для параметра *TEvent*, можно выбрать из списка *классов захвата*. Список событий и классы захвата, которые можно использовать для сопоставления, см. в [таблице событий](../event-table.md).

## <a name="example"></a>Пример

```cpp
void MyClass::Foo1(Function f) {}

void MyClass::Foo2(Compiler cl) {}

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo1);

    bool b2 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo2);

    // b1: true because the first parameter of Foo1 is Function.
    // b2: false because the first parameter of Foo2 isn't Function.
}
```

::: moniker-end
