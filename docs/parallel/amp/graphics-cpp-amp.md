---
title: Графика (C++ AMP)
ms.date: 11/04/2016
ms.assetid: 190a98a4-5f7d-442e-866b-b374ca74c16f
ms.openlocfilehash: 3f68766c2c38b74df6e57aaa52419baf5d1151a3
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041462"
---
# <a name="graphics-c-amp"></a>Графика (C++ AMP)

C++ AMP содержит несколько интерфейсов API в пространстве имен [concurrency::graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md) , которые можно использовать для доступа к поддержке текстур на графических процессорах. Ниже описываются наиболее типичные сценарии применения:

- Класс [текстуры](../../parallel/amp/reference/texture-class.md) можно использовать в качестве контейнера данных для вычисления и использования *пространственной локализации* кэша текстуры и макетов оборудования GPU. Пространственная локальность — это свойство элементов данных, заключающееся в их близком физическом расположении друг к другу;

- среда выполнения обеспечивает эффективное взаимодействие с невычислительными шейдерами. Шейдеры пикселей, вершин, тесселяции и поверхностей часто используют или создают текстуры, которые можно использовать в вычислениях C++ AMP;

- графические API в C++ AMP предоставляет альтернативные способы доступа к буферам, упакованным в подслова. Текстуры с форматами, представляющими *пикселей текстуры* (элементы текстуры), состоящие из 8-разрядных или 16-разрядных скаляров, обеспечивают доступ к такому хранилищу данных.

## <a name="the-norm-and-unorm-types"></a>Типы norm и unorm

`norm`Типы и `unorm` являются скалярными типами, ограничивающими диапазон **`float`** значений. это называется *фиксацией*. Эти типы могут быть созданы из других скалярных типов явным образом. При приведении значение сначала приводится к, **`float`** а затем преобразуется в соответствующий регион, допустимый нормой [-1,0, 1,0] или unorm [0,0, 1,0]. Приведение из +/- бесконечности возвращает +/-1. Приведение из NaN не определено. Тип norm может быть неявно создан из unorm без потери данных. В этих типах определен неявный оператор приведения к float. Бинарные операторы определяются между этими типами и другими встроенными скалярными типами, такими как **`float`** и **`int`** : +,-, \* ,/, = =,! =, >, \<, > =, <=. Также поддерживаются составные операторы присваивания: + =,-=, \* =,/=. Для типов norm определен унарный оператор отрицания (-).

## <a name="short-vector-library"></a>Библиотека коротких векторов

Библиотека коротких векторов предоставляет некоторые функции [типа Vector](https://go.microsoft.com/fwlink/p/?linkid=248500) , определенные в HLSL и обычно используемые для определения пикселей текстуры. Короткий вектор — это структура данных, которая содержит от одного до четырех значений одного типа. Поддерживаются следующие типы: **`double`** , **`float`** ,,, **`int`** `norm` `uint` и `unorm` . Имена типов показаны в следующей таблице. Для каждого типа также имеется соответствующий элемент **`typedef`** , в имени которого нет символа подчеркивания. Типы с символами подчеркивания находятся в [пространстве имен concurrency::graphics](../../parallel/amp/reference/concurrency-graphics-namespace.md). Типы без подчеркивания находятся в [пространстве имен concurrency::graphics::direct3d](../../parallel/amp/reference/concurrency-graphics-direct3d-namespace.md) , чтобы они были четко отделены от основных типов с аналогичными именами, таких как **`__int8`** и **`__int16`** .

|Тип|Длина 2|Длина 3|Длина 4|
|-|--------------|--------------|--------------|
|double|double_2<br /><br /> double2|double_3<br /><br /> double3|double_4<br /><br /> double4|
|FLOAT|float_2<br /><br /> float2|float_3<br /><br /> float3|float_4<br /><br /> float4|
|INT|int_2<br /><br /> int2|int_3<br /><br /> int3|int_4<br /><br /> int4|
|norm|norm_2<br /><br /> norm2|norm_3<br /><br /> norm3|norm_4<br /><br /> norm4|
|uint|uint_2<br /><br /> uint2|uint_3<br /><br /> uint3|uint_4<br /><br /> uint4|
|unorm|unorm_2<br /><br /> unorm2|unorm_3<br /><br /> unorm3|unorm_4<br /><br /> unorm4|

### <a name="operators"></a>Операторы

Если оператор определен между двумя короткими векторами, то он также определен между коротким вектором и скаляром. Кроме того, должно выполняться одно из следующих утверждений:

- тип скаляра должен быть тем же, что и тип элемента короткого вектора;

- тип скаляра может быть неявно преобразован в тип элемента вектора с помощью только одного определенного пользователем преобразования.

Операция выполняется покомпонентно между каждым компонентом короткого вектора и скаляром. Ниже приведены допустимые операторы.

|Тип оператора|Допустимые типы|
|-------------------|-----------------|
|Бинарные операторы|Допустимо для всех типов: +,-, \* ,/,<br /><br /> Допустимо для целочисленных типов:%, ^, &#124;, &, <\<, >><br /><br /> Два вектора должны иметь одинаковый размер, а результат будет вектором такого же размера.|
|Операторы отношения|Допустимы для всех типов: == и !=|
|Составной оператор присваивания|Допустимо для всех типов: + =,-=, \* =,/=<br /><br /> Допустимо для целочисленных типов:% =, ^ =, &#124;=, &=, <\<=, >>=|
|Операторы инкремента и декремента|Допустимы для всех типов: ++, --<br /><br /> Как префиксная, так и постфиксная формы являются допустимыми.|
|Оператор побитового НЕ (~)|Допустим для целочисленных типов.|
|Унарный оператор -|Допустим для всех типов, за исключением `unorm` и `uint`.|

### <a name="swizzling-expressions"></a>Группирующие выражения

Библиотека коротких векторов поддерживает конструкции метода доступа вида `vector_type.identifier` для обращения к компонентам короткого вектора. `identifier`, Который называется *выражением группирующие*, задает компоненты вектора. Выражение может быть l-значением или r-значением. Отдельные символы в идентификаторе могут быть: x, y, z и w; или r, g, b и a. «x» и «r» означают нуль-й компонент, «y» и «g» означают первый компонент и т. д. (Обратите внимание, что "x" и "r" не могут использоваться в одном и том же идентификаторе.) Таким образом, "RGBA" и "ксизв" возвращают один и тот же результат. Методы доступа из одного компонента, такие как "x" и "y", являются скалярными типами значений. Многокомпонентные методы доступа — типы короткого вектора. Например, если есть вектор `int_4` с именем `fourInts` и значениями 2, 4, 6 и 8, то `fourInts.y` возвращает целое число 4, а `fourInts.rg` — объект `int_2` со значениями 2 и 4.

## <a name="texture-classes"></a>Классы текстуры

Многие графические процессоры имеют аппаратные компоненты и кэши, оптимизированные для получения пикселов и текселей и визуализации изображений и текстур. Класс [текстуры \<T,N> ](../../parallel/amp/reference/texture-class.md) , который является классом контейнера для объектов шаг текселя, предоставляет функции текстуры этих графических процессоров. Тексель может быть:

- **`int`** `uint` **`float`** **`double`** `norm` Скалярная величина,,,,, или `unorm` .

- коротким вектором, который содержит 2 или 4 компонента. Единственное исключение — тип `double_4`, который не разрешен.

Объект `texture` может иметь ранг 1, 2 или 3. Объект `texture` может быть перехвачен только по ссылке в лямбда-выражении в вызове метода `parallel_for_each`. Текстура хранится в GPU в виде объектов текстуры Direct3D. Дополнительные сведения о текстурах и пикселей текстуры в Direct3D см. в статье [Введение в текстуры в Direct3D 11](https://go.microsoft.com/fwlink/p/?linkid=248502).

В качестве типа текселя можно использовать одним из множества различных форматов текстур, которые используются при программировании графики. Например, формат RGBA может использовать 32 бита, по 8 бит на каждый из скалярных элементов R, G, B и A. Текстурные компоненты видеокарты могут обращаться к отдельным элементам текстуры в зависимости от формата. Например, если используется формат RGBA, то текстурные компоненты могут извлекать каждый 8-битный элемент в 32-битное представление. В C++ AMP можно задать количество бит на один скалярный элемент текселя, что позволяет автоматически обращаться к отдельным скалярным элементам в коде без использования битовых сдвигов.

### <a name="instantiating-texture-objects"></a>Создание объектов текстуры

Объект текстуры можно объявить без инициализации. В следующем примере кода объявляется несколько объектов текстуры.

```cpp
#include <amp.h>
#include <amp_graphics.h>
using namespace concurrency;
using namespace concurrency::graphics;

void declareTextures() {
    // Create a 16-texel texture of int.
    texture<int, 1> intTexture1(16);
    texture<int, 1> intTexture2(extent<1>(16));

    // Create a 16 x 32 texture of float_2.
    texture<float_2, 2> floatTexture1(16, 32);
    texture<float_2, 2> floatTexture2(extent<2>(16, 32));

    // Create a 2 x 4 x 8 texture of uint_4.
    texture<uint_4, 3> uintTexture1(2, 4, 8);
    texture<uint_4, 3> uintTexture2(extent<3>(2, 4, 8));
}
```

Кроме того, для объявления и инициализации объектов `texture` можно использовать конструкторы. В следующем примере кода создается объект `texture` из вектора объектов `float_4`. Количество битов на один скалярный элемент установлено по умолчанию. Нельзя использовать этот конструктор с `norm`, `unorm` или с короткими векторами `norm` и `unorm`, поскольку они не имеют количества бит по умолчанию на один скалярный элемент.

```cpp
#include <amp.h>
#include <amp_graphics.h>
#include <vector>
using namespace concurrency;
using namespace concurrency::graphics;

void initializeTexture() {
    std::vector<int_4> texels;
    for (int i = 0; i < 768 * 1024; i++) {
        int_4 i4(i, i, i, i);
        texels.push_back(i4);
    }

    texture<int_4, 2> aTexture(768, 1024, texels.begin(), texels.end());
}
```

Можно также объявить и инициализировать объект `texture` с использованием перегрузки конструктора, которая принимает указатель на исходные данные, размер исходных данных в байтах и количество бит на один скалярный элемент.

```cpp
void createTextureWithBPC() { // Create the source data.
    float source[1024* 2];
    for (int i = 0; i <1024* 2; i++) {
        source[i] = (float)i;
    }
    // Initialize the texture by using the size of source in bytes // and bits per scalar element.
    texture<float_2, 1> floatTexture(1024, source, (unsigned int)sizeof(source), 32U);
}
```

Текстуры в этих примерах созданы в представлении по умолчанию ускорителя по умолчанию. Можно использовать другие перегрузки конструктора, если нужно определить объект `accelerator_view`. Объект текстуры нельзя создать в ускорителе ЦП.

Существуют ограничения на размер каждого измерения объекта `texture`, показанные в следующей таблице. Если пределы превышены, то возникает ошибка времени выполнения.

|Текстура|Ограничение размера на измерение|
|-------------|---------------------|
|поддержки\<T,1>|16384|
|поддержки\<T,2>|16384|
|поддержки\<T,3>|2048|

### <a name="reading-from-texture-objects"></a>Чтение из объектов текстуры

Чтение из объекта можно выполнить с `texture` помощью оператора [текстуры::operator \[ \] ](reference/texture-class.md#operator_at), [текстуры::operator ()](reference/texture-class.md#operator_call)или [метода текстуры:: Get](reference/texture-class.md#get). Два оператора возвращают значение, а не ссылку. Поэтому нельзя осуществлять запись в объект `texture` с помощью `texture::operator\[\]`.

```cpp
void readTexture() {
    std::vector<int_2> src;
    for (int i = 0; i <16 *32; i++) {
        int_2 i2(i, i);

        src.push_back(i2);
    }

    std::vector<int_2> dst(16* 32);

    array_view<int_2, 2> arr(16, 32, dst);

    arr.discard_data();

    const texture<int_2, 2> tex9(16, 32, src.begin(), src.end());

    parallel_for_each(tex9.extent, [=, &tex9] (index<2> idx) restrict(amp) { // Use the subscript operator.
        arr[idx].x += tex9[idx].x; // Use the function () operator.
        arr[idx].x += tex9(idx).x; // Use the get method.
        arr[idx].y += tex9.get(idx).y; // Use the function () operator.
        arr[idx].y += tex9(idx[0], idx[1]).y;
    });

    arr.synchronize();
}
```

В следующем примере кода показано, как сохранить каналы текстуры в коротком векторе, а затем обращаться к отдельным скалярным элементам как к свойствам короткого вектора.

```cpp
void UseBitsPerScalarElement() { // Create the image data. // Each unsigned int (32-bit) represents four 8-bit scalar elements(r,g,b,a values).
    const int image_height = 16;
    const int image_width = 16;
    std::vector<unsigned int> image(image_height* image_width);

    extent<2> image_extent(image_height, image_width);

    // By using uint_4 and 8 bits per channel, each 8-bit channel in the data source is // stored in one 32-bit component of a uint_4.
    texture<uint_4, 2> image_texture(image_extent, image.data(), image_extent.size()* 4U,  8U);

    // Use can access the RGBA values of the source data by using swizzling expressions of the uint_4.
    parallel_for_each(image_extent,
        [&image_texture](index<2> idx) restrict(amp)
        { // 4 bytes are automatically extracted when reading.
            uint_4 color = image_texture[idx];
            unsigned int r = color.r;
            unsigned int g = color.g;
            unsigned int b = color.b;
            unsigned int a = color.a;
        });
}
```

В следующей таблице перечислено допустимое количество бит на канал для каждой разновидности типа вектора.

|Тип данных текстуры|Допустимое количество бит на скалярный элемент|
|-----------------------|-----------------------------------|
|int, int_2, int_4<br /><br /> uint, uint_2, uint_4|8, 16, 32|
|int_3, uint_3|32|
|float, float_2, float_4|16, 32|
|float_3|32|
|double, double_2|64|
|norm, norm_2, norm_4<br /><br /> unorm, unorm_2, unorm_4|8, 16|

### <a name="writing-to-texture-objects"></a>Запись в объекты текстуры

Используйте метод [текстуры:: Set](reference/texture-class.md#set) для записи в `texture` объекты. Объект текстуры может быть доступен только для чтения или для чтения и записи. Для объекта текстуры, который должен быть доступен для чтения и записи, должны выполняться следующие условия:

- T имеет только один скалярный компонент. (Нельзя использовать короткие векторы);

- T не является **`double`** , `norm` или `unorm` .

- значение свойства `texture::bits_per_scalar_element` — 32.

Если все три условия не выполняются, то объект `texture` будет доступен только для чтения. Первые два условия проверяются во время компиляции. Ошибка компиляции генерируется, если имеется код, который пытается писать в `readonly`-объект текстуры. Условие для `texture::bits_per_scalar_element` определяется во время выполнения, и среда выполнения создает исключение [unsupported_feature](../../parallel/amp/reference/unsupported-feature-class.md) при попытке записи в объект, доступный только для чтения `texture` .

В следующем примере кода выполняется запись значений в объект текстуры.

```cpp
void writeTexture() {
    texture<int, 1> tex1(16);

    parallel_for_each(tex1.extent, [&tex1] (index<1> idx) restrict(amp) {
        tex1.set(idx, 0);
    });
}
```

### <a name="copying-texture-objects"></a>Копирование объектов текстуры

Копировать объекты текстуры можно с помощью функции [Copy](reference/concurrency-namespace-functions-amp.md#copy) или функции [copy_async](reference/concurrency-namespace-functions-amp.md#copy_async) , как показано в следующем примере кода.

```cpp
void copyHostArrayToTexture() { // Copy from source array to texture object by using the copy function.
    float floatSource[1024* 2];
    for (int i = 0; i <1024* 2; i++) {
        floatSource[i] = (float)i;
    }
    texture<float_2, 1> floatTexture(1024);

    copy(floatSource, (unsigned int)sizeof(floatSource), floatTexture);

    // Copy from source array to texture object by using the copy function.
    char charSource[16* 16];
    for (int i = 0; i <16* 16; i++) {
        charSource[i] = (char)i;
    }
    texture<int, 2> charTexture(16, 16, 8U);

    copy(charSource, (unsigned int)sizeof(charSource), charTexture);
    // Copy from texture object to source array by using the copy function.
    copy(charTexture, charSource, (unsigned int)sizeof(charSource));
}
```

Также можно скопировать из одной текстуры в другую с помощью метода [текстуры:: copy_to](reference/texture-class.md#copy_to) . Две текстуры могут находиться на разных объектах accelerator_view. При копировании в объект `writeonly_texture_view` данные копируются в нижележащий объект `texture`. Количество бит на один скалярный элемент и размер должны быть одинаковыми на объектах `texture` источника и назначения. Если эти требования не выполнены, то генерируется исключение.

## <a name="texture-view-classes"></a>Классы представления текстуры

C++ AMP вводит [Texture_view класс](../../parallel/amp/reference/texture-view-class.md) в Visual Studio 2013. Представления текстур поддерживают те же типы шаг текселя и ранги, что и [класс текстуры](../../parallel/amp/reference/texture-class.md), но в отличие от текстур они предоставляют доступ к дополнительным аппаратным функциям, таким как выборка текстур и MIP-карты. Представления текстуры поддерживают доступ только для чтения, только для записи и для чтения и записи к соответствующим данным текстуры.

- Доступ только для чтения предоставляется специализацией шаблона `texture_view<const T, N>`, которая поддерживает элементы с 1, 2 или 4 компонентами, дискретизацию текстур и динамический доступ к диапазону уровней MIP-карты, определяемых при создании экземпляра представления.

- Доступ только для записи предоставляется неспециализированным классом шаблона `texture_view<T, N>`, который поддерживает элементы с 2 или 4 компонентами и позволяет обращаться к одному уровню MIP-карты, определяемому при создании экземпляра представления. Оно не поддерживает дискретизацию.

- Доступ для чтения и записи предоставляется неспециализированным классом шаблона `texture_view<T, N>`, который, как и текстуры, поддерживает элементы только с одним компонентом; представление может обращаться к одному уровню MIP-карты, определяемому при создании экземпляра этого представления. Оно не поддерживает дискретизацию.

Представления текстур аналогичны представлениям массива, но не предоставляют функции автоматического управления данными и перемещения, которые [класс array_view](../../parallel/amp/reference/array-view-class.md) предоставляет для [класса Array](../../parallel/amp/reference/array-class.md). К `texture_view` можно обращаться только в представлении ускорителя, в котором находятся соответствующие данные текстуры.

### <a name="writeonly_texture_view-deprecated"></a>Использовать класс writeonly_texture_view не рекомендуется

Для Visual Studio 2013 C++ AMP предоставляет улучшенную поддержку аппаратных функций текстуры, таких как выборка и MIP-карты, которые не поддерживаются [классом writeonly_texture_view](../../parallel/amp/reference/writeonly-texture-view-class.md). Новый класс `texture_view` поддерживает надмножество функций в `writeonly_texture_view`; поэтому использовать `writeonly_texture_view` больше не рекомендуется.

Рекомендуется (по крайней мере в новом коде) использовать `texture_view` для доступа к функциям, которые раньше реализовывались с помощью `writeonly_texture_view`. Сравните следующие два примера кода, в которых осуществляется запись в объект текстуры, состоящий из двух компонентов (int_2). Обратите внимание, что в обоих случаях представление `wo_tv4` должно захватываться по значению в лямбда-выражении. Ниже приведен пример, в котором используется новый класс `texture_view`:

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> tex4(16);

    texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {
        wo_tv4.set(idx, int_2(1, 1));
    });
}
```

А здесь показан нерекомендуемый класс `writeonly_texture_view`:

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> tex4(16);

    writeonly_texture_view<int_2, 1> wo_tv4(tex4);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {
        wo_tv4.set(idx, int_2(1, 1));
    });
}
```

Можно видеть, что оба примера кода практически идентичны, когда требуется выполнить запись в базовый уровень MIP-карты. Если в вашем коде используется класс `writeonly_texture_view` и вы не планируете улучшать его, код можно не менять. Если же вы думаете о расширении кода, рекомендуется переписать его с использованием класса `texture_view`, поскольку усовершенствования в нем поддерживают новые аппаратные возможности для работы с текстурами. Ниже эти новые возможности описаны более подробно.

Дополнительные сведения о нерекомендуемых параметрах `writeonly_texture_view` см. [в разделе Общие сведения о структуре представления текстуры в C++ amp](/archive/blogs/nativeconcurrency/overview-of-the-texture-view-design-in-c-amp) на параллельном программировании в блоге машинного кода.

### <a name="instantiating-texture-view-objects"></a>Создание экземпляров объектов представлений текстуры

Объявление объекта `texture_view` аналогично объявлению `array_view` , связанному с **массивом**. В следующем примере кода объявляются несколько объектов `texture` и связанных с ними объектов `texture_view`.

```cpp
#include <amp.h>
#include <amp_graphics.h>
using namespace concurrency;
using namespace concurrency::graphics;

void declareTextureViews()
{
    // Create a 16-texel texture of int, with associated texture_views.
    texture<int, 1> intTexture(16);
    texture_view<const int, 1> intTextureViewRO(intTexture);  // read-only
    texture_view<int, 1> intTextureViewRW(intTexture);        // read-write

    // Create a 16 x 32 texture of float_2, with associated texture_views.
    texture<float_2, 2> floatTexture(16, 32);
    texture_view<const float_2, 2> floatTextureViewRO(floatTexture);  // read-only
    texture_view<float_2, 2> floatTextureViewRO(floatTexture);        // write-only

    // Create a 2 x 4 x 8 texture of uint_4, with associated texture_views.
    texture<uint_4, 3> uintTexture(2, 4, 8);
    texture_view<const uint_4, 3> uintTextureViewRO(uintTexture);  // read-only
    texture_view<uint_4, 3> uintTextureViewWO(uintTexture);        // write-only
}
```

Обратите внимание, что представление текстуры, тип элемента которой не является константным и содержащее один компонент, доступно для чтения и записи, а представление текстуры, тип элемента которой не является константным, но содержащее более одного компонента, доступно только для записи. Представления текстуры с константными типами элемента всегда доступны только для чтения, но если тип элемента не является константным, число компонентов в этом элементе определяют режим доступа к текстуре — чтение и запись (один компонент) или только запись (несколько компонентов).

Тип элемента `texture_view` (его "константность" и количество компонентов в нем) также определяют, поддерживает ли представление дискретизацию текстуры и способ доступа к уровням MIP-карт.

|Тип|Компоненты|Чтение|запись|Выборка|Доступ к MIP-карте|
|----------|----------------|----------|-----------|--------------|-------------------|
|texture_view\<const T, N>|1, 2, 4|Да|Нет (1)|Да|Да, индексируемый. Диапазон определяется при создании экземпляра.|
|Texture_view\<T, N>|1<br /><br /> 2, 4|Да<br /><br /> Нет (2)|Да<br /><br /> Да|Нет (1)<br /><br /> Нет (1)|Да, один уровень. Уровень определяется при создании экземпляра.<br /><br /> Да, один уровень. Уровень определяется при создании экземпляра.|

Из этой таблицы можно увидеть, что представления текстур, доступные только для чтения, полностью поддерживают новые возможности в обмен на невозможность записи в в представление. Доступные для записи представления текстуры ограничены тем, что они поддерживают доступ только к одному уровню MIP-карт. Представления текстуры для чтения и записи являются более специализированным по сравнению с поддерживающими только запись, поскольку они содержат дополнительное требование о том, что тип элемента в таком представлении текстуры должен содержать только один компонент. Обратите внимание, что дискретизация не поддерживается для записываемых представлений текстур, поскольку эта операция предполагает чтение.

### <a name="reading-from-texture-view-objects"></a>Чтение из объектов представления текстуры

Чтение недискретизированных данных текстуры через представление текстуры похоже на чтение из самой текстуры за тем исключением, что текстуры передаются по ссылке, а представления текстуры — по значению. В следующих двух примерах кода демонстрируется это. В первом — с использованием только `texture`:

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> text_data(16);

    parallel_for_each(extent<1>(16), [&] (index<1> idx) restrict(amp) {
        tex_data.set(idx, int_2(1, 1));
    });
}
```

А ниже приведен тот же пример, но с использованием класса `texture_view`:

```cpp
void write2ComponentTexture() {
    texture<int_2, 1> tex_data(16);

    texture_view<int_2, 1> tex_view(tex_data);

    parallel_for_each(extent<1>(16), [=] (index<1> idx) restrict(amp) {
        tex_view.set(idx, int_2(1, 1));
    });
}
```

Представления текстур, элементы которых основаны на типах с плавающей запятой, например float, float_2 или float_4, также могут считываться с помощью дискретизации текстур, чтобы можно было использовать аппаратную поддержку различных режимов фильтрации и адресации. C++ AMP поддерживает два режима фильтрации, которые чаще всего используются в вычислениях — точечная фильтрация (ближайший сосед) и линейная фильтрации (средневзвешенный показатель), а также четыре режима адресации — с переносом, зеркальный, ограниченный и граничный. Дополнительные сведения о режимах адресации см. в разделе [Перечисление address_mode](reference/concurrency-graphics-namespace-enums.md#address_mode).

Помимо режимов, поддерживаемых в C++ AMP напрямую, можно использовать другие режимы фильтрации и адресации базовой платформы через API взаимодействия, чтобы применять дискретизатор текстур, созданный непосредственно API. Например, Direct3D поддерживает другие режимы фильтрации, такие как анизотропная фильтрация, и может применять к каждому измерению текстуры свой режим адресации. С помощью API Direct3D можно создать дискретизатор текстур, координаты которого будут переноситься по вертикали, зеркально отражаться по горизонтали и дискретизироваться с помощью анизотропного фильтра, после чего использовать этот дискретизатор в коде C++ AMP с помощью API взаимодействия `make_sampler`. Дополнительные сведения см. [в разделе Выбор текстуры в C++ amp](/archive/blogs/nativeconcurrency/texture-sampling-in-c-amp) для параллельного программирования в блоге машинного кода.

Представления текстуры также поддерживают чтение MIP-карт. Доступные только для чтения представления текстуры (имеющие константный тип элемента) обеспечивают наибольшую гибкость, поскольку диапазон MIP-уровней, определяемых при создании экземпляра, может дискретизироваться динамически и потому что поддерживаются элементы с 1, 2 или 4 компонентами. Представления текстуры для чтения и записи, содержащие элементы с одним компонентом, также поддерживают MIP-карты, но только один уровень определяется при создании экземпляра. Дополнительные сведения см. в разделе [текстура с помощью MIP-карты](/archive/blogs/nativeconcurrency/texture-with-mipmaps) в блоге по параллельному программированию в машинном коде.

### <a name="writing-to-texture-view-objects"></a>Запись в объекты представлений текстуры

Используйте [метод texture_view:: Get](reference/texture-view-class.md#get) для записи в базовый `texture` объект с помощью `texture_view` объекта. Представление текстуры могут быть доступным только для чтения, для чтения и записи или только для записи. Чтобы представление текстуры было доступно для записи, оно должно иметь неконстантный тип элемента; чтобы представление текстуры было доступным для чтения и записи, его тип элемента должен также иметь только один компонент. В противном случае представление текстуры доступно только для чтения. Через представление текстуры одновременно можно обращаться только к одному уровню MIP-карты текстуры, и этот уровень задается при создании экземпляра представления.

В этом примере показано, как осуществлять запись во второй по детализации уровень текстуры, имеющей 4 уровня MIP-карт. Самый подробный уровень MIP-карт — уровень 0.

```cpp
// Create a texture that has 4 mipmap levels : 16x16, 8x8, 4x4, 2x2
texture<int, 2> tex(extent<2>(16, 16), 16U, 4);

// Create a writable texture view to the second mipmap level :4x4
texture_view<int, 2> w_view(tex, 1);

parallel_for_each(w_view.extent, [=](index<2> idx) restrict(amp)
{
    w_view.set(idx, 123);
});
```

## <a name="interoperability"></a>Совместимость

Среда выполнения C++ AMP поддерживает взаимодействие между `texture<T,1>` и [интерфейсом ID3D11Texture1D](https://go.microsoft.com/fwlink/p/?linkId=248503), между и интерфейсом `texture<T,2>` [ID3D11Texture2D](https://go.microsoft.com/fwlink/p/?linkId=255317), а также между `texture<T,3>` и [интерфейсом ID3D11Texture3D](https://go.microsoft.com/fwlink/p/?linkId=255377). Метод [get_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#get_texture) принимает `texture` объект и возвращает `IUnknown` интерфейс. Метод [make_texture](reference/concurrency-graphics-direct3d-namespace-functions.md#make_texture) принимает `IUnknown` интерфейс и `accelerator_view` объект и возвращает `texture` объект.

## <a name="see-also"></a>См. также раздел

[Класс double_2](../../parallel/amp/reference/double-2-class.md)<br/>
[Класс double_3](../../parallel/amp/reference/double-3-class.md)<br/>
[Класс double_4](../../parallel/amp/reference/double-4-class.md)<br/>
[Класс float_2](../../parallel/amp/reference/float-2-class.md)<br/>
[Класс float_3](../../parallel/amp/reference/float-3-class.md)<br/>
[Класс float_4](../../parallel/amp/reference/float-4-class.md)<br/>
[Класс int_2](../../parallel/amp/reference/int-2-class.md)<br/>
[Класс int_3](../../parallel/amp/reference/int-3-class.md)<br/>
[Класс int_4](../../parallel/amp/reference/int-4-class.md)<br/>
[Класс norm_2](../../parallel/amp/reference/norm-2-class.md)<br/>
[Класс norm_3](../../parallel/amp/reference/norm-3-class.md)<br/>
[Класс norm_4](../../parallel/amp/reference/norm-4-class.md)<br/>
[Структура short_vector](../../parallel/amp/reference/short-vector-structure.md)<br/>
[Структура short_vector_traits](../../parallel/amp/reference/short-vector-traits-structure.md)<br/>
[Класс uint_2](../../parallel/amp/reference/uint-2-class.md)<br/>
[Класс uint_3](../../parallel/amp/reference/uint-3-class.md)<br/>
[Класс uint_4](../../parallel/amp/reference/uint-4-class.md)<br/>
[Класс unorm_2](../../parallel/amp/reference/unorm-2-class.md)<br/>
[Класс unorm_3](../../parallel/amp/reference/unorm-3-class.md)<br/>
[Класс unorm_4](../../parallel/amp/reference/unorm-4-class.md)
