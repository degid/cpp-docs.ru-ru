---
title: Коллекции (C++/CX)
ms.date: 11/19/2018
ms.assetid: 914da30b-aac5-4cd7-9da3-a5ac08cdd72c
ms.openlocfilehash: 84c6ecad5ffb4920972faf5aa564103ec1f5b5df
ms.sourcegitcommit: 65fead53d56d531d71be42216056aca5f44def11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2020
ms.locfileid: "88610950"
---
# <a name="collections-ccx"></a>Коллекции (C++/CX)

В программе C++/CX можно свободно использовать контейнеры библиотеки стандартных шаблонов (STL) или любой другой определяемый пользователем тип коллекции. Однако при передаче коллекций между и обратно в среда выполнения Windows двоичном интерфейсе приложения (ABI), например в элемент управления XAML или на клиент JavaScript, необходимо использовать типы коллекций среда выполнения Windows.

Среда выполнения Windows определяет интерфейсы для коллекций и связанных типов, а C++/CX предоставляет конкретные реализации C++ в файле заголовка Collection.h. На этой иллюстрации показаны связи между типами коллекций:

![Дерево наследования C&#43;&#43;&#47;CX для типов коллекций](../cppcx/media/cppcxcollectionsinheritancetree.png "Дерево наследования C&#43;&#43;&#47;CX для типов коллекций")

- [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) похож на [класс std::vector](../standard-library/vector-class.md).

- [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md) похож на [класс std::map](../standard-library/map-class.md).

- [Класс Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md) и[класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md) являются доступными только для чтения версиями `Vector` и `Map`.

- Итераторы определяются в [пространстве имен Platform::Collections](../cppcx/platform-collections-namespace.md). Эти итераторы удовлетворяют требованиям итераторов STL и позволяют использовать алгоритмы [std::find](../standard-library/algorithm-functions.md#find),  [std::count_if](../standard-library/algorithm-functions.md#count_if)и другие алгоритмы STL в любом типе интерфейса [Windows::Foundation::Collections](/uwp/api/windows.foundation.collections) или конкретном типе [Platform::Collections](../cppcx/platform-collections-namespace.md) . Например, это означает, что можно выполнить итерацию коллекции в среда выполнения Windows компоненте, созданном в C#, и применить к нему алгоритм STL.

   > [!IMPORTANT]
   > Итераторы прокси-сервера `VectorIterator` и `VectorViewIterator` используют прокси-объекты `VectoryProxy<T>` и `ArrowProxy<T>` для включения использования с контейнерами STL. Дополнительные сведения см. в теме "Элементы VectorProxy" далее в этой статье.

- Типы коллекций C++/CX поддерживают те же гарантии безопасности потоков, что и контейнеры STL.

- [Windows::Foundation::Collections::IObservableVector](/uwp/api/windows.foundation.collections.iobservablevector-1) и [Windows::Foundation::Collections::IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) определяют события, инициируемые при разнообразных изменениях коллекции. Реализуя эти интерфейсы, объекты  [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) и [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) поддерживают привязку данных с коллекциями XAML. Например, если имеется объект `Vector` , данные которого связаны с `Grid`, то при добавлении данных в коллекцию их изменения отражаются в пользовательском интерфейсе таблицы.

## <a name="vector-usage"></a>Использование класса Vector

Когда класс должен передать контейнер последовательности другому компоненту среда выполнения Windows, используйте [Windows:: Foundation:: Collections:: IVector \<T> ](/uwp/api/windows.foundation.collections.ivector-1) в качестве параметра или возвращаемого типа, а [Platform:: Collections:: vector \<T> ](../cppcx/platform-collections-vector-class.md) — в качестве конкретной реализации. При попытке использования типа `Vector` в качестве открытого возвращаемого значения или параметра возникнет ошибка компилятора C3986. Эту ошибку можно исправить, заменив `Vector` объектом `IVector`.

> [!IMPORTANT]
> В случае передачи последовательности внутри разрабатываемой программы используйте `Vector` или `std::vector` , поскольку они более эффективны по сравнению с `IVector`. Используйте `IVector` только при передаче контейнера с помощью ABI.
>
> Система типов среда выполнения Windows не поддерживает концепцию массива массивов и, следовательно, нельзя передавать в `IVector<Platform::Array<T>>` качестве возвращаемого значения или параметра метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.

Класс`Vector<T>` предоставляет методы, необходимые для добавления и удаления элементов коллекции и доступа к ним. Его можно неявно преобразовать в класс `IVector<T>`. Алгоритмы STL также можно применять к экземплярам `Vector<T>`. В следующем примере демонстрируются некоторые простейшие варианты использования. [Функция начала](../cppcx/begin-function.md) и [функция окончания](../cppcx/end-function.md) , используемые здесь, — из пространства имен `Platform::Collections` , а не `std` .

[!code-cpp[cx_collections#01](../cppcx/codesnippet/CPP/collections/class1.cpp#01)]

Если у вас есть код, который использует, `std::vector` и вы хотите повторно использовать его в среда выполнения Windows компоненте, просто используйте один из `Vector` конструкторов, который принимает `std::vector` или пару итераторов для создания в `Vector` точке, где вы передаете коллекцию по интерфейсу ABI. В следующем примере показано использование конструктора класса `Vector` для эффективной инициализации из объекта `std::vector`. После операции перемещения исходная переменная `vec` более не является допустимой.

[!code-cpp[cx_collections#02](../cppcx/codesnippet/CPP/collections/class1.cpp#02)]

Если имеется вектор строк, которые должны будут передаваться через интерфейс ABI, необходимо решить, следует ли изначально создавать строки как типы `std::wstring` или как типы `Platform::String^` . Если предполагается выполнение большого объема операций с этими строками, используйте тип `wstring`. В противном случае создайте строки типа `Platform::String^` , чтобы избежать издержек, связанных с их последующим преобразованием. Кроме того, необходимо определить, куда лучше поместить строки для внутреннего использования — в `std:vector` или в `Platform::Collections::Vector` . В общем случае рекомендуется использовать объект `std::vector` и создавать из него `Platform::Vector` только при передаче контейнера через интерфейс ABI.

## <a name="value-types-in-vector"></a>Типы значений в объекте Vector

Любой элемент, который необходимо сохранить в объекте [Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md) , должен поддерживать сравнение на равенство (неявно или с помощью пользовательского алгоритма сравнения [std::equal_to](../standard-library/equal-to-struct.md) ). Все ссылочные типы и все скалярные типы неявно поддерживают сравнение на равенство. Для нескалярных типов значений, таких как [Windows::FoundationDateTime](/uwp/api/windows.foundation.datetime), или для пользовательских сравнений (например, `objA->UniqueID == objB->UniqueID`) необходимо предоставить специальный объект функции.

## <a name="vectorproxy-elements"></a>Элементы VectorProxy

[Platform:: Collections:: VectorIterator](../cppcx/platform-collections-vectoriterator-class.md) and [Platform:: Collections:: VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md) позволяют использовать `range for` циклы и алгоритмы, такие как [std:: Sort](../standard-library/algorithm-functions.md#sort) с контейнером [IVector \<T> ](/uwp/api/windows.foundation.collections.ivector-1) . Однако невозможно получить доступ к элементам `IVector` через отмену ссылки на указатель C++; доступ к ним можно получить только с использованием методов [GetAt](/uwp/api/windows.foundation.collections.ivector-1.getat) и [SetAt](/uwp/api/windows.foundation.collections.ivector-1.setat) . Таким образом, эти итераторы используют прокси-классы `Platform::Details::VectorProxy<T>` и `Platform::Details::ArrowProxy<T>` для предоставления доступа к отдельным элементам с __\*__ помощью __->__ операторов,, и __ \[ ]__ , как это требуется для стандартной библиотеки. Строго говоря, при использовании `IVector<Person^> vec`типом `*begin(vec)` является `VectorProxy<Person^>`. Однако прокси-объект практически всегда прозрачен для кода. Эти прокси-объекты не документируются, поскольку предназначены исключительно для внутреннего пользования итераторами, однако полезно иметь представление о самом механизме работы.

При использовании цикла `range for` с контейнерами `IVector` используйте `auto&&` для включения переменной итератора для правильной привязки к элементам `VectorProxy` . Если используется **`auto`** или `auto&` , предупреждение компилятора C4239 вызывается и `VectoryProxy` упоминается в тексте предупреждения.

На следующем рисунке показан цикл `range for` с контейнерами `IVector<Person^>`. Обратите внимание, что выполнение прекращается в точке останова на строке 64. В окне **Быстрая проверка** показано, что переменная итератора `p` , по сути, является объектом `VectorProxy<Person^>` с переменными-членами `m_v` и `m_i` . Однако при вызове `GetType` для этой переменной она возвращает идентичный тип в экземпляр `Person``p2`. Отсюда вывод: несмотря на то что `VectorProxy` и `ArrowProxy` могут отображаться в разделе **Быстрая проверка**, отладчик устраняет некоторые ошибки в компиляторе или других местах, для которых, как правило, не нужно явно создавать код.

![VectorProxy в диапазоне&#45;на основе цикла for](../cppcx/media/vectorproxy-1.png "VectorProxy в диапазоне&#45;на основе цикла for")

Одним из сценариев, в которых необходимо создавать код для прокси-объекта, является то, что необходимо выполнить **`dynamic_cast`** для элементов, например, при поиске объектов XAML определенного типа в `UIElement` коллекции элементов. В этом случае необходимо сначала привести элемент к [Platform::Object](../cppcx/platform-object-class.md)^, а затем выполнить динамическое приведение.

```cpp
void FindButton(UIElementCollection^ col)
{
    // Use auto&& to avoid warning C4239
    for (auto&& elem : col)
    {
        Button^ temp = dynamic_cast<Button^>(static_cast<Object^>(elem));
        if (nullptr != temp)
        {
            // Use temp...
        }
    }
}
```

## <a name="map-usage"></a>Использование класса Map

В этом примере показано, как вставлять элементы и находить их в объекте [Platform::Collections::Map](../cppcx/platform-collections-map-class.md), а затем возвращать объект `Map` в качестве доступного только для чтения типа [Windows::Foundation::Collections::IMapView](/uwp/api/windows.foundation.collections.imapview-2) .

[!code-cpp[cx_collections#04](../cppcx/codesnippet/CPP/collections/class1.cpp#04)]

Как правило, для реализации внутренних возможностей сопоставления предпочтительно использовать тип `std::map` (из соображений производительности). Если необходимо передать контейнер с помощью интерфейса ABI, создайте объект [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) из [std::map](../standard-library/map-class.md) и верните `Map` в качестве [Windows::Foundation::Collections::IMap](/uwp/api/windows.foundation.collections.imap-2). При попытке использования типа `Map` в качестве открытого возвращаемого значения или параметра возникнет ошибка компилятора C3986. Эту ошибку можно исправить, заменив `Map` объектом `IMap`. В некоторых случаях (например, если вы не выполняете большого количества операций поиска или вставки и часто передаете коллекцию через интерфейс ABI) более рационально использовать класс `Platform::Collections::Map` с самого начала, не затрачивая ресурсы на преобразование типа объекта `std::map`. В любом случае следует избегать операций поиска и вставки в объектах `IMap` , поскольку из всех трех типов он обладает самой низкой производительностью. Преобразование в `IMap` следует выполнять только в момент передачи контейнера через интерфейс ABI.

## <a name="value-types-in-map"></a>Типы значений в объекте Map

Элементы в [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) упорядочены. Любой элемент, который необходимо сохранить в объекте `Map` , должен поддерживать сравнение "меньше" для строгого слабого порядка (неявно или с помощью пользовательского алгоритма сравнения [stl::less](../standard-library/less-struct.md) ). Скалярные типы поддерживают сравнение неявно. Для нескалярных типов значений, таких как `Windows::Foundation::DateTime`, или для пользовательских вариантов сравнения (например, `objA->UniqueID < objB->UniqueID`) необходимо определять специальный алгоритм сравнения.

## <a name="collection-types"></a>Типы коллекций

Коллекции подразделяются на четыре категории: изменяемые и доступные только для чтения версии последовательных и ассоциативных коллекций. Кроме того, C++/CX расширяет коллекции, предоставляя три класса итераторов, которые упрощают доступ к коллекциям.

Элементы изменяемой коллекции можно изменять, тогда как к элементам коллекции, доступной только для чтения (также называемой *представлением*), можно обращаться только для чтения. Для доступа к элементам коллекции [Platform:: Collections:: Vector](../cppcx/platform-collections-vector-class.md) или[Platform:: Collections:: VectorView](../cppcx/platform-collections-vectorview-class.md) можно использовать итератор или [vector:: GetAt](../cppcx/platform-collections-vector-class.md#getat) коллекции и индекс. Доступ к элементам ассоциативной коллекции можно получить с помощью [Map:: Lookup](../cppcx/platform-collections-map-class.md#lookup) и ключа в коллекции.

[Класс Platform:: Collections:: Map](../cppcx/platform-collections-map-class.md)<br/>
Изменяемая ассоциативная коллекция. Элементы объекта Map представляют собой пары "ключ-значение". Поддерживается как поиск значения по связанному с ним ключу, так и перебор всех пар "ключ-значение".

В классах`Map` и `MapView` используется шаблон `<K, V, C = std::less<K>>`; таким образом, алгоритм сравнения можно изменять.  Кроме того, в классах `Vector` и `VectorView` используется шаблон `<T, E = std::equal_to<T>>` , поэтому поведение метода `IndexOf()`можно изменять. Это важно в основном для объектов `Vector` и `VectorView` , содержащих структуры значения. Например, чтобы создать вектор \<Windows::Foundation::DateTime> , необходимо предоставить настраиваемое средство сравнения, так как DateTime не перегружает оператор = =.

[Класс Platform:: Collections:: MapView](../cppcx/platform-collections-mapview-class.md)<br/>
Версия объекта `Map`только для чтения.

[Класс Platform:: Collections:: Vector](../cppcx/platform-collections-vector-class.md)<br/>
Изменяемая коллекция последовательностей. Класс`Vector<T>` поддерживает операции произвольного доступа, занимающие фиксированное время, и операции [добавления](../cppcx/platform-collections-vector-class.md#append) , занимающие фиксированное время с поправкой на амортизацию.

[Класс Platform:: Collections:: VectorView](../cppcx/platform-collections-vectorview-class.md)<br/>
Версия объекта `Vector`только для чтения.

[Класс Platform:: Collections:: InputIterator](../cppcx/platform-collections-inputiterator-class.md)<br/>
Итератор STL, отвечающий требованиям итератора ввода STL.

[Класс Platform:: Collections:: VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)<br/>
Итератор STL, отвечающий требованиям изменяемого итератора произвольного доступа STL.

[Класс Platform:: Collections:: VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)<br/>
Итератор STL, удовлетворяющий требованиям  **`const`** итератора случайного доступа STL.

### <a name="begin-and-end-functions"></a>Функции begin() и end()

Чтобы упростить использование STL для обработки,,, `Vector` `VectorView` `Map` `MapView` и произвольных `Windows::Foundation::Collections` объектов, C++/CX поддерживает перегрузки функций [Begin](../cppcx/begin-function.md) и [End Function](../cppcx/end-function.md) , не являющихся членами.

В следующей таблице перечислены все доступные итераторы и функции.

|Iterators|Функции|
|---------------|---------------|
|[Platform:: Collections:: VectorIterator\<T>](../cppcx/platform-collections-vectoriterator-class.md)<br /><br /> (Внутренне сохраняет [Windows:: Foundation:: Collections:: \<T> IVector](/uwp/api/windows.foundation.collections.ivector-1) и int.)|[Начало](../cppcx/begin-function.md) /  [End](../cppcx/end-function.md)([Windows:: Foundation:: Collections:: \<T> IVector](/uwp/api/windows.foundation.collections.ivector-1))|
|[Platform:: Collections:: VectorViewIterator\<T>](../cppcx/platform-collections-vectorviewiterator-class.md)<br /><br /> (Внутренне сохраняет [IVectorView \<T> ](/uwp/api/windows.foundation.collections.ivectorview-1)^ и int.)|[Начало](../cppcx/begin-function.md) /  [конец](../cppcx/end-function.md) ([IVectorView \<T> ](/uwp/api/windows.foundation.collections.ivectorview-1)^)|
|[Platform:: Collections:: InputIterator\<T>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Внутренне сохраняет [иитератор \<T> ](/uwp/api/windows.foundation.collections.iiterator-1)^ и T.)|[Начало](../cppcx/begin-function.md) /  [конец](../cppcx/end-function.md) ([иитерабле \<T> ](/uwp/api/windows.foundation.collections.iiterable-1))|
|[Platform:: Collections:: InputIterator<IKeyValuePair\<K, V>^>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Внутренне сохраняет [иитератор \<T> ](/uwp/api/windows.foundation.collections.iiterator-1)^ и T.)|[Начало](../cppcx/begin-function.md) /  [конец](../cppcx/end-function.md) ([IMAP \<K,V> ](/uwp/api/windows.foundation.collections.imap-2).|
|[Platform:: Collections:: InputIterator<IKeyValuePair\<K, V>^>](../cppcx/platform-collections-inputiterator-class.md)<br /><br /> (Внутренне сохраняет [иитератор \<T> ](/uwp/api/windows.foundation.collections.iiterator-1)^ и T.)|[Начало](../cppcx/begin-function.md) /  [End](../cppcx/end-function.md) ([Windows:: Foundation:: Collections:: IMapView](/uwp/api/windows.foundation.collections.imapview-2))|

### <a name="collection-change-events"></a>События изменения коллекций

Классы`Vector` и `Map` поддерживают привязку данных в коллекциях XAML за счет реализации событий, которые возникают при изменении или сбросе объекта коллекции, а также при вставке, удалении или изменении любого элемента коллекции. Можно разрабатывать собственные типы, поддерживающие привязку данных, но нельзя наследовать от типов `Map` и `Vector` , так как эти типы запечатаны.

Делегаты [Windows::Foundation::Collections::VectorChangedEventHandler](/uwp/api/windows.foundation.collections.vectorchangedeventhandler-1) и [Windows::Foundation::Collections::MapChangedEventHandler](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) определяют сигнатуры для обработчиков событий для событий изменения коллекции. Открытый класс перечисления [Windows::Foundation::Collections::CollectionChange](/uwp/api/windows.foundation.collections.collectionchange) и ссылочные классы `Platform::Collection::Details::MapChangedEventArgs` и `Platform::Collections::Details::VectorChangedEventArgs` хранят аргументы события, по которым можно определить его причину. `*EventArgs`Типы определяются в `Details` пространстве имен, так как их не нужно создавать и использовать явным образом при использовании `Map` или `Vector` .

## <a name="see-also"></a>См. также

[Система типов](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
