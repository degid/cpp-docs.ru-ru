---
title: Практическое руководство. Преобразование из коллекции .NET в контейнер STL/CLR
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR, converting from .NET collections
- STL/CLR Containers [STL/CLR]
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
ms.openlocfilehash: a7b2ee94f02e663690287ecfa6bc8a7230830a95
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686461"
---
# <a name="how-to-convert-from-a-net-collection-to-a-stlclr-container"></a>Практическое руководство. Преобразование из коллекции .NET в контейнер STL/CLR

В этом разделе показано, как преобразовать коллекции .NET в эквивалентные контейнеры STL/CLR. В качестве примера мы покажем, как преобразовать .NET <xref:System.Collections.Generic.List%601> в [вектор](../dotnet/vector-stl-clr.md) STL/CLR и как преобразовать .NET <xref:System.Collections.Generic.Dictionary%602> в [карту](../dotnet/map-stl-clr.md)STL/CLR, но процедура аналогична для всех коллекций и контейнеров.

### <a name="to-create-a-container-from-a-collection"></a>Создание контейнера из коллекции

1. Чтобы преобразовать целую коллекцию, создайте контейнер STL/CLR и передайте коллекцию в конструктор.

   В первом примере демонстрируется эта процедура.

-или-

1. Создайте универсальный контейнер STL/CLR, создав объект [collection_adapter](../dotnet/collection-adapter-stl-clr.md) . Этот класс шаблона принимает в качестве аргумента интерфейс коллекции .NET. Сведения о том, какие интерфейсы поддерживаются, см. в разделе [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md).

1. Скопируйте содержимое коллекции .NET в контейнер. Это можно сделать с помощью [алгоритма](../dotnet/algorithm-stl-clr.md)STL/CLR или путем прохода по коллекции .NET и вставки копии каждого элемента в контейнер STL/CLR.

   Во втором примере демонстрируется эта процедура.

## <a name="examples"></a>Примеры

В этом примере мы создадим универсальный объект <xref:System.Collections.Generic.List%601> и добавим в него 5 элементов. Затем мы создадим `vector` с помощью конструктора, который принимает в <xref:System.Collections.Generic.IEnumerable%601> качестве аргумента.

```cpp
// cliext_convert_list_to_vector.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/vector>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    List<int> ^primeNumbersColl = gcnew List<int>();
    primeNumbersColl->Add(2);
    primeNumbersColl->Add(3);
    primeNumbersColl->Add(5);
    primeNumbersColl->Add(7);
    primeNumbersColl->Add(11);

    cliext::vector<int> ^primeNumbersCont =
        gcnew cliext::vector<int>(primeNumbersColl);

    Console::WriteLine("The contents of the cliext::vector are:");
    cliext::vector<int>::const_iterator it;
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)
    {
        Console::WriteLine(*it);
    }
}
```

```Output
The contents of the cliext::vector are:
2
3
5
7
11
```

В этом примере мы создадим универсальный объект <xref:System.Collections.Generic.Dictionary%602> и добавим в него 5 элементов. Затем мы создадим, `collection_adapter` чтобы создать оболочку для <xref:System.Collections.Generic.Dictionary%602> простого контейнера STL/CLR. Наконец, мы создаем `map` и копируем содержимое объекта в, <xref:System.Collections.Generic.Dictionary%602> `map` пересматривая `collection_adapter` . Во время этого процесса мы создадим новую пару с помощью `make_pair` функции и вставляем новую пару непосредственно в `map` .

```cpp
// cliext_convert_dictionary_to_map.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/map>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    System::Collections::Generic::Dictionary<float, int> ^dict =
        gcnew System::Collections::Generic::Dictionary<float, int>();
    dict->Add(42.0, 42);
    dict->Add(13.0, 13);
    dict->Add(74.0, 74);
    dict->Add(22.0, 22);
    dict->Add(0.0, 0);

    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);
    cliext::map<float, int> aMap;
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)
    {
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);
        aMap.insert(aPair);
    }

    Console::WriteLine("The contents of the cliext::map are:");
    cliext::map<float, int>::const_iterator it;
    for (it = aMap.begin(); it != aMap.end(); it++)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);
    }
}
```

```Output
The contents of the cliext::map are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>См. также

[Справочник по библиотеке STL/CLR](../dotnet/stl-clr-library-reference.md)<br/>
[adapter (STL/CLR)](../dotnet/adapter-stl-clr.md)<br/>
[Как преобразовать контейнер STL/CLR в коллекцию .NET](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)
