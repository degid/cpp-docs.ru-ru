---
title: Общие сведения о C++ AMP
ms.date: 11/19/2018
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, requirements
- C++ Accelerated Massive Parallelism, architecture
- C++ AMP
- C++ Accelerated Massive Parallelism, overview
- C++ Accelerated Massive Parallelism
ms.assetid: 9e593b06-6e3c-43e9-8bae-6d89efdd39fc
ms.openlocfilehash: 2629f243f3db3b8fabbd87ee0a211380ac3d45a2
ms.sourcegitcommit: 093f49b8b69daf86661adc125b1d2d7b1f0e0650
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "89427729"
---
# <a name="c-amp-overview"></a>Общие сведения о C++ AMP

C++ Accelerated Massive Parallelism (C++ AMP) ускоряет выполнение кода C++, используя преимущества аппаратно-ориентированного оборудования, такого как графический процессор (GPU), на дискретной графической карте. С помощью C++ AMP можно создавать алгоритмы многомерных данных, чтобы можно было ускорить выполнение с помощью параллелизма на разнородном оборудовании. Модель программирования C++ AMP включает многомерные массивы, индексирование, перенос памяти, мозаичное заполнение и библиотеку математических функций. С помощью расширений языка C++ AMP можно управлять перемещением данных из ЦП в GPU и обратно, что позволяет повысить производительность.

## <a name="system-requirements"></a>Требования к системе

- Windows 7 и более поздние версии

- Windows Server 2008 R2 и более поздние версии

- DirectX 11, уровень компонентов 11,0 или более поздней версии

- Для отладки в эмуляторе программного обеспечения требуется Windows 8 или Windows Server 2012. Для отладки на оборудовании необходимо установить драйверы для видеокарты. Дополнительные сведения см. в разделе [Отладка кода GPU](/visualstudio/debugger/debugging-gpu-code).

- Примечание. AMP в настоящее время не поддерживается в ARM64.

## <a name="introduction"></a>Введение

В следующих двух примерах показаны основные компоненты C++ AMP. Предположим, что необходимо добавить соответствующие элементы для массивов из 2 1 измерений. Например, может потребоваться добавить `{1, 2, 3, 4, 5}` и `{6, 7, 8, 9, 10}` получить `{7, 9, 11, 13, 15}` . Без использования C++ AMP вы можете написать следующий код, чтобы добавить числа и отобразить результаты.

```cpp
#include <iostream>

void StandardMethod() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5];

    for (int idx = 0; idx < 5; idx++)
    {
        sumCPP[idx] = aCPP[idx] + bCPP[idx];
    }

    for (int idx = 0; idx < 5; idx++)
    {
        std::cout << sumCPP[idx] << "\n";
    }
}
```

Ниже описаны важные части этого кода.

- Данные. данные состоят из трех массивов. Все имеют одинаковый ранг (один) и длину (пять).

- Итерация: первый **`for`** цикл предоставляет механизм для итерации элементов в массивах. Код, который необходимо выполнить для вычисления сумм, содержится в первом **`for`** блоке.

- Index: `idx` переменная обращается к отдельным элементам массивов.

С помощью C++ AMP можно написать следующий код.

```cpp
#include <amp.h>
#include <iostream>
using namespace concurrency;

const int size = 5;

void CppAmpMethod() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[size];

    // Create C++ AMP objects.
    array_view<const int, 1> a(size, aCPP);
    array_view<const int, 1> b(size, bCPP);
    array_view<int, 1> sum(size, sumCPP);
    sum.discard_data();

    parallel_for_each(
        // Define the compute domain, which is the set of threads that are created.
        sum.extent,
        // Define the code to run on each thread on the accelerator.
        [=](index<1> idx) restrict(amp) {
            sum[idx] = a[idx] + b[idx];
        }
    );

    // Print the results. The expected output is "7, 9, 11, 13, 15".
    for (int i = 0; i < size; i++) {
        std::cout << sum[i] << "\n";
    }
}
```

Имеются те же основные элементы, но используются C++ AMP конструкции:

- Данные. для создания трех C++ AMP [array_view](../../parallel/amp/reference/array-view-class.md) объектов используются массивы C++. Для создания объекта необходимо указать четыре значения `array_view` : значения данных, ранг, тип элемента и длина `array_view` объекта в каждом измерении. Ранг и тип передаются как параметры типа. Данные и длина передаются как параметры конструктора. В этом примере массив C++, передаваемый в конструктор, является одномерным. Ранг и длина используются для создания прямоугольной формы данных в `array_view` объекте, а значения данных используются для заполнения массива. Библиотека времени выполнения также включает [класс Array](../../parallel/amp/reference/array-class.md), который имеет интерфейс, похожий на класс, `array_view` и рассматривается далее в этой статье.

- Итерация. [функция parallel_for_each (C++ amp)](reference/concurrency-namespace-functions-amp.md#parallel_for_each) предоставляет механизм для прохода по элементам данных или *домену вычислений*. В этом примере домен вычислений указывается с помощью `sum.extent` . Код, который требуется выполнить, содержится в лямбда-выражении или *функции ядра*. `restrict(amp)`Указывает, что используется только подмножество языка C++, которое C++ amp может ускорить использование.

- Index: переменная [класса индекса](../../parallel/amp/reference/index-class.md) , `idx` , объявленная с рангом 1 для соответствия рангу `array_view` объекта. С помощью индекса можно получить доступ к отдельным элементам `array_view` объектов.

## <a name="shaping-and-indexing-data-index-and-extent"></a>Формирование и индексирование данных: индекс и экстент

Необходимо определить значения данных и объявить форму данных, прежде чем можно будет запустить код ядра. Все данные определяются как массив (прямоугольный), и можно определить массив для любого ранга (число измерений). Данные могут иметь любой размер в любом из измерений.

### <a name="index-class"></a>Класс index

[Класс index](../../parallel/amp/reference/index-class.md) задает расположение в `array` `array_view` объекте или, включая смещение от источника в каждом измерении в один объект. При доступе к расположению в массиве объект передается `index` оператору индексирования, `[]` а не списку целочисленных индексов. Доступ к элементам в каждом измерении можно получить с помощью [оператора Array::operator ()](reference/array-class.md#operator_call) или [оператора array_view::operator ()](reference/array-view-class.md#operator_call).

В следующем примере создается одномерный индекс, указывающий третий элемент в одномерном `array_view` объекте. Индекс используется для печати третьего элемента в `array_view` объекте. Выходные данные имеют значение 3.

```cpp
int aCPP[] = {1, 2, 3, 4, 5};
array_view<int, 1> a(5, aCPP);

index<1> idx(2);

std::cout << a[idx] << "\n";
// Output: 3
```

В следующем примере создается двухмерный индекс, указывающий элемент, где строка = 1 и столбец = 2 в двухмерном `array_view` объекте. Первым параметром в `index` конструкторе является компонент Row, а вторым параметром является компонент Column. Выходные данные имеют значение 6.

```cpp
int aCPP[] = {1, 2, 3, 4, 5, 6};
array_view<int, 2> a(2, 3, aCPP);

index<2> idx(1, 2);

std::cout <<a[idx] << "\n";
// Output: 6
```

В следующем примере создается трехмерный индекс, указывающий элемент, где глубина = 0, строка = 1, и столбец = 3 в трехмерном `array_view` объекте. Обратите внимание, что первый параметр является компонентом глубины, вторым параметром является компонент Row, а третий параметр — компонент столбца. Выходные данные — 8.

```cpp
int aCPP[] = {
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};

array_view<int, 3> a(2, 3, 4, aCPP);

// Specifies the element at 3, 1, 0.
index<3> idx(0, 1, 3);

std::cout << a[idx] << "\n";
// Output: 8
```

### <a name="extent-class"></a>Класс extent

[Класс экстента](../../parallel/amp/reference/extent-class.md) задает длину данных в каждом измерении `array` `array_view` объекта или. Можно создать экстент и использовать его для создания `array` `array_view` объекта или. Кроме того, можно получить экстент существующего `array` `array_view` объекта или. В следующем примере выводится длина экстента в каждом измерении `array_view` объекта.

```cpp
int aCPP[] = {
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};
// There are 3 rows and 4 columns, and the depth is two.
array_view<int, 3> a(2, 3, 4, aCPP);

std::cout << "The number of columns is " << a.extent[2] << "\n";
std::cout << "The number of rows is " << a.extent[1] << "\n";
std::cout << "The depth is " << a.extent[0] << "\n";
std::cout << "Length in most significant dimension is " << a.extent[0] << "\n";
```

В следующем примере создается `array_view` объект, который имеет те же измерения, что и объект в предыдущем примере, но в этом примере `extent` вместо явных параметров в `array_view` конструкторе используется объект.

```cpp
int aCPP[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};
extent<3> e(2, 3, 4);

array_view<int, 3> a(e, aCPP);

std::cout << "The number of columns is " << a.extent[2] << "\n";
std::cout << "The number of rows is " << a.extent[1] << "\n";
std::cout << "The depth is " << a.extent[0] << "\n";
```

## <a name="moving-data-to-the-accelerator-array-and-array_view"></a>Перемещение данных в ускоритель: массив и array_view

Два контейнера данных, используемых для перемещения данных в ускоритель, определяются в библиотеке времени выполнения. Они являются [классом Array](../../parallel/amp/reference/array-class.md) и [классом array_view](../../parallel/amp/reference/array-view-class.md). `array`Класс является классом контейнера, который создает глубокую копию данных при создании объекта. `array_view`Класс является классом-оболочкой, который копирует данные, когда функция ядра обращается к данным. Если данные необходимы на исходном устройстве, данные копируются обратно.

### <a name="array-class"></a>Класс array

При создании `array` объекта в ускорителе создается глубокая копия данных, если используется конструктор, включающий указатель на набор данных. Функция ядра изменяет копию в ускорителе. После завершения выполнения функции ядра необходимо скопировать данные обратно в исходную структуру данных. В следующем примере каждый элемент в векторе умножается на 10. После завершения работы функции ядра `vector conversion operator` используется для копирования данных обратно в объект Vector.

```cpp
std::vector<int> data(5);

for (int count = 0; count <5; count++)
{
    data[count] = count;
}

array<int, 1> a(5, data.begin(), data.end());

parallel_for_each(
    a.extent,
    [=, &a](index<1> idx) restrict(amp) {
        a[idx] = a[idx]* 10;
    });

data = a;
for (int i = 0; i < 5; i++)
{
    std::cout << data[i] << "\n";
}
```

### <a name="array_view-class"></a>Класс array_view

`array_view`Имеет почти те же члены, что и `array` класс, но базовое поведение отличается. Данные, переданные в `array_view` конструктор, не реплицируются на GPU, так как они существуют с `array` конструктором. Вместо этого данные копируются в ускоритель при выполнении функции ядра. Поэтому при создании двух объектов, `array_view` использующих одни и те же данные, оба `array_view` объекта ссылаются на одно и то же пространство памяти. При этом необходимо синхронизировать любой многопоточный доступ. Основным преимуществом использования `array_view` класса является то, что данные перемещаются только в том случае, если это необходимо.

### <a name="comparison-of-array-and-array_view"></a>Сравнение массивов и array_view

В следующей таблице перечислены сходства и различия между `array` `array_view` классами и.

|Описание|array - класс|array_view - класс|
|-----------------|-----------------|-----------------------|
|Когда определяется ранг|Во время компиляции.|Во время компиляции.|
|Когда определяется экстент|Во время выполнения.|Во время выполнения.|
|Фигурная|Прямоуголь.|Прямоуголь.|
|Хранилище данных|Является контейнером данных.|— Это оболочка данных.|
|Копировать|Явная и глубокая копия в определении.|Неявная копия при обращении к ней функцией ядра.|
|Получение данных|Путем копирования данных массива обратно в объект в потоке ЦП.|Путем прямого доступа к `array_view` объекту или путем вызова [метода array_view:: Synchronize](reference/array-view-class.md#synchronize) для продолжения доступа к данным в исходном контейнере.|

### <a name="shared-memory-with-array-and-array_view"></a>Общая память с массивом и array_view

Общая память — это память, доступ к которой может осуществляться как ЦП, так и ускорителем. Использование общей памяти устраняет или значительно сокращает затраты на копирование данных между ЦП и ускорителем. Несмотря на то, что память является общей, она недоступна одновременно с ЦП и ускорителем, и это приводит к неопределенному поведению.

`array` объекты можно использовать для задания точного управления использованием общей памяти, если соответствующий ускоритель поддерживает его. Поддерживает ли ускоритель совместно используемой памяти свойство [supports_cpu_shared_memory](reference/accelerator-class.md#supports_cpu_shared_memory) ускорителя, которое возвращает, **`true`** когда поддерживается общая память. Если общая память поддерживается, [Перечисление access_type](reference/concurrency-namespace-enums-amp.md#access_type) по умолчанию для выделения памяти на ускорителе определяется `default_cpu_access_type` свойством. По умолчанию `array` `array_view` объекты и принимают то же значение, `access_type` что и основной связанный объект `accelerator` .

Устанавливая явно свойство [массива Array:: Cpu_access_type данных](reference/array-class.md#cpu_access_type) `array` , вы можете точно контролировать, как используется общая память, чтобы оптимизировать приложение для характеристик производительности оборудования на основе шаблонов доступа к памяти в вычислительных ядрах. Объект соответствует тому же, что и `array_view` `cpu_access_type` объект `array` , с которым он связан; или, если array_view создается без источника данных, он `access_type` отражает среду, которая сначала вызывает выделение хранилища. То есть при первом обращении к узлу (ЦП) он ведет себя так, как если бы он был создан на основе источника данных ЦП, и совместно с объектом, `access_type` `accelerator_view` связанным с захватом, но если он первый доступ к `accelerator_view` , то он ведет себя так, как если бы он был создан `array` на основе созданного объекта `accelerator_view` и совместно использует `array` `access_type` .

В следующем примере кода показано, как определить, поддерживает ли ускоритель по умолчанию общую память, а затем создает несколько массивов с разными конфигурациями cpu_access_type.

```cpp
#include <amp.h>
#include <iostream>

using namespace Concurrency;

int main()
{
    accelerator acc = accelerator(accelerator::default_accelerator);

    // Early out if the default accelerator doesn’t support shared memory.
    if (!acc.supports_cpu_shared_memory)
    {
        std::cout << "The default accelerator does not support shared memory" << std::endl;
        return 1;
    }

    // Override the default CPU access type.
    acc.default_cpu_access_type = access_type_read_write

    // Create an accelerator_view from the default accelerator. The
    // accelerator_view inherits its default_cpu_access_type from acc.
    accelerator_view acc_v = acc.default_view;

    // Create an extent object to size the arrays.
    extent<1> ex(10);

    // Input array that can be written on the CPU.
    array<int, 1> arr_w(ex, acc_v, access_type_write);

    // Output array that can be read on the CPU.
    array<int, 1> arr_r(ex, acc_v, access_type_read);

    // Read-write array that can be both written to and read from on the CPU.
    array<int, 1> arr_rw(ex, acc_v, access_type_read_write);
}
```

## <a name="executing-code-over-data-parallel_for_each"></a>Исполнение кода над данными: parallel_for_each

Функция [parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each) определяет код, который необходимо выполнить на ускорителе, на основе данных в `array` `array_view` объекте или. Рассмотрим следующий код, приведенный в этом разделе.

```cpp
#include <amp.h>
#include <iostream>
using namespace concurrency;

void AddArrays() {
    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5] = {0, 0, 0, 0, 0};

    array_view<int, 1> a(5, aCPP);
    array_view<int, 1> b(5, bCPP);
    array_view<int, 1> sum(5, sumCPP);

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp)
        {
            sum[idx] = a[idx] + b[idx];
        }
    );

    for (int i = 0; i < 5; i++) {
        std::cout << sum[i] << "\n";
    }
}
```

`parallel_for_each`Метод принимает два аргумента: домен вычислений и лямбда-выражение.

*Домен вычислений* — это `extent` объект или `tiled_extent` объект, определяющий набор потоков, создаваемых для параллельного выполнения. Для каждого элемента в домене вычислений создается один поток. В этом случае `extent` объект является одномерным и имеет пять элементов. Поэтому запускаются пять потоков.

*Лямбда-выражение* определяет код для выполнения в каждом потоке. Предложение Capture указывает, `[=]` что текст лямбда-выражения получает доступ ко всем захваченным переменным по значению, в данном случае —, `a` `b` и `sum` . В этом примере список параметров создает одномерный `index` переменную с именем `idx` . Значение параметра `idx[0]` равно 0 в первом потоке и увеличивается по одному в каждом последующем потоке. `restrict(amp)`Указывает, что используется только подмножество языка C++, которое C++ amp может ускорить использование.  Ограничения функций, имеющих модификатор restrict, описаны в разделе [restrict (C++ amp)](../../cpp/restrict-cpp-amp.md). Дополнительные сведения см. в разделе [синтаксис лямбда-выражения](../../cpp/lambda-expression-syntax.md).

Лямбда-выражение может включать код для выполнения или может вызывать отдельную функцию ядра. Функция ядра должна включать `restrict(amp)` модификатор. Следующий пример эквивалентен предыдущему примеру, но он вызывает отдельную функцию ядра.

```cpp
#include <amp.h>
#include <iostream>
using namespace concurrency;

void AddElements(
    index<1> idx,
    array_view<int, 1> sum,
    array_view<int, 1> a,
    array_view<int, 1> b) restrict(amp) {
    sum[idx] = a[idx] + b[idx];
}

void AddArraysWithFunction() {

    int aCPP[] = {1, 2, 3, 4, 5};
    int bCPP[] = {6, 7, 8, 9, 10};
    int sumCPP[5] = {0, 0, 0, 0, 0};

    array_view<int, 1> a(5, aCPP);
    array_view<int, 1> b(5, bCPP);
    array_view<int, 1> sum(5, sumCPP);

    parallel_for_each(
        sum.extent,
        [=](index<1> idx) restrict(amp) {
            AddElements(idx, sum, a, b);
        }
    );

    for (int i = 0; i < 5; i++) {
        std::cout << sum[i] << "\n";
    }
}
```

## <a name="accelerating-code-tiles-and-barriers"></a>Ускорение кода: плитки и барьеры

Можно получить дополнительное ускорение, используя мозаичное заполнение. Мозаичное заполнение разделяет потоки на равные прямоугольные подмножества или *плитки*. Вы определяете соответствующий размер плитки на основе набора данных и алгоритма, который вы кодируете. Для каждого потока у вас есть доступ к *глобальному* расположению элемента данных относительно целого `array` или `array_view` к *локальному* расположению относительно плитки. Использование значения локального индекса упрощает код, так как вам не нужно писать код для преобразования значений индекса из глобального в локальный. Чтобы использовать мозаичное заполнение, вызовите [метод экстента:: Tile](reference/extent-class.md#tile) в домене вычислений в `parallel_for_each` методе и используйте объект [tiled_index](../../parallel/amp/reference/tiled-index-class.md) в лямбда-выражении.

В типичных приложениях элементы в плитке связаны каким-либо образом, и код должен иметь доступ и отследить значения в плитке. Для этого используйте ключевое слово [tile_static](../../cpp/tile-static-keyword.md) и [метод tile_barrier:: wait](reference/tile-barrier-class.md#wait) . Переменная, имеющая ключевое слово **tile_static** , имеет область по всей плитке, а экземпляр переменной создается для каждой плитки. Необходимо выполнять синхронизацию доступа к переменной в потоке мозаики. [Метод tile_barrier:: wait](reference/tile-barrier-class.md#wait) останавливает выполнение текущего потока до тех пор, пока все потоки на плитке не достигают вызова `tile_barrier::wait` . Таким образом, можно накапливать значения по плитке с помощью переменных **tile_static** . Затем можно завершить любые вычисления, которым требуется доступ ко всем значениям.

На следующей диаграмме представлен двумерный массив данных выборки, упорядоченный по плиткам.

![Значения индекса в пространстве, разбитом на плитки](../../parallel/amp/media/camptiledgridexample.png "Значения индекса в пространстве, разбитом на плитки")

В следующем примере кода используются данные выборки из предыдущей диаграммы. Код заменяет каждое значение на плитке средним значением в плитке.

```cpp
// Sample data:
int sampledata[] = {
    2, 2, 9, 7, 1, 4,
    4, 4, 8, 8, 3, 4,
    1, 5, 1, 2, 5, 2,
    6, 8, 3, 2, 7, 2};

// The tiles:
// 2 2    9 7    1 4
// 4 4    8 8    3 4
//
// 1 5    1 2    5 2
// 6 8    3 2    7 2

// Averages:
int averagedata[] = {
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
    0, 0, 0, 0, 0, 0,
};

array_view<int, 2> sample(4, 6, sampledata);

array_view<int, 2> average(4, 6, averagedata);

parallel_for_each(
    // Create threads for sample.extent and divide the extent into 2 x 2 tiles.
    sample.extent.tile<2,2>(),
        [=](tiled_index<2,2> idx) restrict(amp) {
        // Create a 2 x 2 array to hold the values in this tile.
        tile_static int nums[2][2];

        // Copy the values for the tile into the 2 x 2 array.
        nums[idx.local[1]][idx.local[0]] = sample[idx.global];

        // When all the threads have executed and the 2 x 2 array is complete, find the average.
        idx.barrier.wait();
        int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1];

        // Copy the average into the array_view.
        average[idx.global] = sum / 4;
    });

for (int i = 0; i <4; i++) {
    for (int j = 0; j <6; j++) {
        std::cout << average(i,j) << " ";
    }
    std::cout << "\n";
}

// Output:
// 3 3 8 8 3 3
// 3 3 8 8 3 3
// 5 5 2 2 4 4
// 5 5 2 2 4 4
```

## <a name="math-libraries"></a>Математические библиотеки

C++ AMP содержит две математические библиотеки. Библиотека двойной точности в [пространстве имен Concurrency::p recise_math](../../parallel/amp/reference/concurrency-precise-math-namespace.md) обеспечивает поддержку функций двойной точности. Он также обеспечивает поддержку функций с одной точностью, хотя по-прежнему требуется поддержка двойной точности на оборудовании. Он соответствует [спецификации C99 (ISO/IEC 9899)](https://go.microsoft.com/fwlink/p/?linkid=225887). Ускоритель должен поддерживать полную двойную точность. Чтобы определить, выполняется ли оно, проверьте значение [элемента данных Accelerator:: supports_double_precision](reference/accelerator-class.md#supports_double_precision). Библиотека Fast Math в [пространстве имен Concurrency:: fast_math](../../parallel/amp/reference/concurrency-fast-math-namespace.md)содержит еще один набор математических функций. Эти функции, которые поддерживают только **`float`** операнды, выполняются быстрее, но не так точны, как в математической библиотеке с двойной точностью. Функции содержатся в \<amp_math.h> файле заголовка, а все объявляются с помощью `restrict(amp)` . Функции в \<cmath> файле заголовка импортируются в `fast_math` `precise_math` пространства имен и. **`restrict`** Ключевое слово используется для различения \<cmath> версии и C++ amp версии. Следующий код вычисляет десятичный логарифм с помощью метода FAST для каждого значения, начисленного в домене вычислений.

```cpp
#include <amp.h>
#include <amp_math.h>
#include <iostream>
using namespace concurrency;

void MathExample() {

    double numbers[] = { 1.0, 10.0, 60.0, 100.0, 600.0, 1000.0 };
    array_view<double, 1> logs(6, numbers);

    parallel_for_each(
        logs.extent,
        [=] (index<1> idx) restrict(amp) {
            logs[idx] = concurrency::fast_math::log10(numbers[idx]);
        }
    );

    for (int i = 0; i < 6; i++) {
        std::cout << logs[i] << "\n";
    }
}
```

## <a name="graphics-library"></a>Библиотека графики

C++ AMP содержит библиотеку графики, предназначенную для ускоренного программирования графики. Эта библиотека используется только на устройствах, поддерживающих собственные графические функции. Методы находятся в [пространстве имен concurrency::graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md) и содержатся в \<amp_graphics.h> файле заголовка. Ключевые компоненты графической библиотеки:

- [класс текстуры](../../parallel/amp/reference/texture-class.md). класс текстуры можно использовать для создания текстур из памяти или из файла. Текстуры похожи на массивы, так как они содержат данные, и они похожи на контейнеры в стандартной библиотеке C++ по отношению к конструкции присваивания и копирования. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../../standard-library/stl-containers.md). Параметры шаблона для `texture` класса являются типом элемента и рангом. Ранг может быть равен 1, 2 или 3. Тип элемента может быть одним из коротких векторных типов, которые описаны далее в этой статье.

- [Writeonly_texture_view класс](../../parallel/amp/reference/writeonly-texture-view-class.md): предоставляет доступ только для записи к любой текстуры.

- Краткая векторная библиотека: определяет набор коротких векторных типов длиной 2, 3 и 4, основанный на **`int`** , `uint` ,, **`float`** **`double`** , [норме](../../parallel/amp/reference/norm-class.md)или [unorm](../../parallel/amp/reference/unorm-class.md).

## <a name="universal-windows-platform-uwp-apps"></a>Приложения универсальной платформы Windows (UWP)

Как и другие библиотеки C++, в приложениях UWP можно использовать C++ AMP. В этих статьях описывается, как включить код C++ AMP в приложения, созданные с помощью C++, C#, Visual Basic или JavaScript.

- [Использование C++ AMP в приложениях UWP](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)

- [Пошаговое руководство. Создание базового среда выполнения Windows компонента в C++ и вызов его из JavaScript](https://go.microsoft.com/fwlink/p/?linkid=249077)

- [Оптимизатор веб-карт Bing, приложение для Магазина Windows на JavaScript и C++](https://go.microsoft.com/fwlink/p/?linkid=249078)

- [Использование C++ AMP из C# с помощью среда выполнения Windows](https://devblogs.microsoft.com/pfxteam/how-to-use-c-amp-from-c-using-winrt/)

- [Использование C++ AMP из C #](https://devblogs.microsoft.com/pfxteam/how-to-use-c-amp-from-c/)

- [Вызов собственных функций из управляемого кода](../../dotnet/calling-native-functions-from-managed-code.md)

## <a name="c-amp-and-concurrency-visualizer"></a>C++ AMP и визуализатор параллелизма

Визуализатор параллелизма включает поддержку для анализа производительности кода C++ AMP. В этих статьях описываются следующие функции:

- [Граф активности GPU](/visualstudio/profiling/gpu-activity-graph)

- [Активность GPU (подкачка)](/visualstudio/profiling/gpu-activity-paging)

- [Активность GPU (этот процесс)](/visualstudio/profiling/gpu-activity-this-process)

- [Активность GPU (другие процессы)](/visualstudio/profiling/gpu-activity-other-processes)

- [Каналы (представление "Потоки")](/visualstudio/profiling/channels-threads-view)

- [Анализ кода C++ AMP с помощью визуализатора параллелизма](/archive/blogs/nativeconcurrency/analyzing-c-amp-code-with-the-concurrency-visualizer)

## <a name="performance-recommendations"></a>Рекомендации по производительности

Модуль и деление целых чисел без знака значительно улучшили производительность, чем модуль и деление целых чисел со знаком. Рекомендуется использовать целые числа без знака, если это возможно.

## <a name="see-also"></a>См. также раздел

[C++ AMP (C++ Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
[Синтаксис лямбда-выражений](../../cpp/lambda-expression-syntax.md)<br/>
[Справочник (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)<br/>
[Блог о параллельном программировании в машинном коде](/archive/blogs/nativeconcurrency/)
