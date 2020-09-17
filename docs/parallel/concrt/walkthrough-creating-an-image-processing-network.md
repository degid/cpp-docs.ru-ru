---
title: Пошаговое руководство. Создание сети обработки изображений
ms.date: 04/25/2019
helpviewer_keywords:
- image-processing networks, creating [Concurrency Runtime]
- creating image-processing networks [Concurrency Runtime]
ms.assetid: 78ccadc9-5ce2-46cc-bd62-ce0f99d356b8
ms.openlocfilehash: 03d95be8fae3565a51811357ed9553c3a2649674
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140754"
---
# <a name="walkthrough-creating-an-image-processing-network"></a>Пошаговое руководство. Создание сети обработки изображений

В этом документе показано, как создать сеть асинхронных блоков сообщений, выполняющих обработку изображений.

Сеть определяет, какие операции должны выполняться с изображением на основе его характеристик. В этом примере модель *потока* данных используется для маршрутизации изображений по сети. В модели потока данных независимые компоненты программы взаимодействуют друг с другом, отправляя сообщения. Когда компонент получает сообщение, он может выполнить какое-либо действие и передать результат этого действия другому компоненту. Сравните это с моделью *потока управления* , в которой приложение использует структуры элементов управления, например условные операторы, циклы и т. д., для управления порядком операций в программе.

Сеть, основанная на потоке данных, создает *конвейер* задач. Каждый этап конвейера параллельно выполняет часть общей задачи. Можно сравнить это с линией сборки автомобилей. Так как каждый транспортный модуль проходит через строку сборки, одна станция выполняет сборку кадра, другой устанавливает подсистему и т. д. Разрешив одновременное сборку нескольких автомобилей, линия сборки обеспечивает лучшую пропускную способность по сравнению со сборкой полных транспортных средств по одному за раз.

## <a name="prerequisites"></a>предварительные требования

Прежде чем приступить к работе с этим пошаговым руководством, прочитайте следующие документы:

- [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)

- [Практическое руководство. Использование фильтра блоков сообщений](../../parallel/concrt/how-to-use-a-message-block-filter.md)

- [Пошаговое руководство. Создание агента потоков данных](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)

Также рекомендуется понимать основы интерфейса GDI+ перед началом работы с этим пошаговым руководством.

## <a name="top"></a> Разделы

Это пошаговое руководство содержит следующие разделы:

- [Определение функциональных возможностей обработки изображений](#functionality)

- [Создание сети обработки изображений](#network)

- [Полный пример](#complete)

## <a name="functionality"></a>Определение функциональных возможностей обработки изображений

В этом разделе показаны функции поддержки, используемые сетью обработки изображений для работы с образами, которые считываются с диска.

Следующие функции, `GetRGB` и `MakeColor`, извлекают и объединяют отдельные компоненты заданного цвета соответственно.

[!code-cpp[concrt-image-processing-filter#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_1.cpp)]

Следующая функция, `ProcessImage`, вызывает данный объект [std:: Function](../../standard-library/function-class.md) для преобразования значения цвета каждого пикселя в [растровом](/windows/win32/api/gdiplusheaders/nl-gdiplusheaders-bitmap) объекте GDI+. Функция `ProcessImage` использует алгоритм [параллелизма::parallel_for](reference/concurrency-namespace-functions.md#parallel_for) для параллельной обработки каждой строки точечного рисунка.

[!code-cpp[concrt-image-processing-filter#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_2.cpp)]

Следующие функции, `Grayscale`, `Sepiatone`, `ColorMask`и `Darken`, вызывают функцию `ProcessImage` для преобразования значения цвета каждого пикселя в объекте `Bitmap`. Каждая из этих функций использует лямбда-выражение для определения преобразования цвета одного пикселя.

[!code-cpp[concrt-image-processing-filter#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_3.cpp)]

Следующая функция, `GetColorDominance`, также вызывает функцию `ProcessImage`. Однако вместо изменения значения каждого цвета эта функция использует объекты [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) , чтобы вычислить, является ли изображение красным, зеленым или синим цветом частью изображения.

[!code-cpp[concrt-image-processing-filter#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_4.cpp)]

Следующая функция, `GetEncoderClsid`, получает идентификатор класса для заданного типа MIME кодировщика. Приложение использует эту функцию для получения кодировщика для точечного рисунка.

[!code-cpp[concrt-image-processing-filter#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_5.cpp)]

[[В начало](#top)]

## <a name="network"></a>Создание сети обработки изображений

В этом разделе описывается создание сети асинхронных блоков сообщений, выполняющих обработку изображений для каждого изображения JPEG (JPG) в заданном каталоге. Сеть выполняет следующие операции обработки образов:

1. Для любого образа, созданного Tom, преобразуйте его в градации серого.

1. Для любого изображения, которое имеет красный цвет в качестве главного, удалите зеленые и синие компоненты, а затем затемнить их.

1. Для любого другого образа примените выцветшей Тонинг.

Сеть применяет только первую операцию обработки изображения, которая соответствует одному из этих условий. Например, если изображение создано объектом Tom и имеет красный цвет в качестве главного, изображение преобразуется в градации серого.

После того как сеть выполняет каждую операцию обработки изображений, образ сохраняется на диск в виде файла точечного рисунка (BMP).

Ниже показано, как создать функцию, которая реализует эту сеть обработки изображений и применяет эту сеть к каждому изображению JPEG в указанном каталоге.

#### <a name="to-create-the-image-processing-network"></a>Создание сети обработки изображений

1. Создайте функцию `ProcessImages`, которая принимает имя каталога на диске.

   [!code-cpp[concrt-image-processing-filter#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_6.cpp)]

1. В функции `ProcessImages` создайте `countdown_event` переменную. Класс `countdown_event` показан далее в этом пошаговом руководстве.

   [!code-cpp[concrt-image-processing-filter#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_7.cpp)]

1. Создайте объект [std:: Map](../../standard-library/map-class.md) , связывающий объект `Bitmap` с его исходным именем файла.

   [!code-cpp[concrt-image-processing-filter#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_8.cpp)]

1. Добавьте следующий код, чтобы определить элементы сети обработки изображений.

   [!code-cpp[concrt-image-processing-filter#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_9.cpp)]

1. Добавьте следующий код для подключения к сети.

   [!code-cpp[concrt-image-processing-filter#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_10.cpp)]

1. Добавьте следующий код для отправки в заголовок сети полный путь к каждому файлу JPEG в каталоге.

   [!code-cpp[concrt-image-processing-filter#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_11.cpp)]

1. Дождитесь, пока переменная `countdown_event` не достигнет нуля.

   [!code-cpp[concrt-image-processing-filter#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_12.cpp)]

Следующая таблица описывает члены сети.

|Участник|Description|
|------------|-----------------|
|`load_bitmap`|Объект [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) , который загружает объект `Bitmap` с диска и добавляет запись в объект `map`, чтобы связать образ с его исходным именем файла.|
|`loaded_bitmaps`|Объект [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md) , который отправляет загруженные изображения в фильтры обработки изображений.|
|`grayscale`|Объект `transformer`, который преобразует изображения, созданные с помощью тома, в градации серого. Он использует метаданные образа для определения его автора.|
|`colormask`|Объект `transformer`, который удаляет компоненты зеленого и синего цветов из изображений, которые имеют красный цвет в качестве главного.|
|`darken`|Объект `transformer`, который затемняет изображения с красным цветом в качестве главного.|
|`sepiatone`|Объект `transformer`, который применяет выцветшей Тонинг к изображениям, которые не созданы с помощью Tom и не являются преимущественно красными.|
|`save_bitmap`|Объект `transformer`, сохраняющий обработанные `image` на диск в виде точечного рисунка. `save_bitmap` извлекает исходное имя файла из объекта `map` и изменяет расширение имени файла на. bmp.|
|`delete_bitmap`|Объект `transformer`, освобождающий память для изображений.|
|`decrement`|Объект [concurrency::Call](../../parallel/concrt/reference/call-class.md) , который выступает в качестве узла терминала в сети. Он уменьшает объект `countdown_event`, чтобы сообщить основному приложению о том, что изображение обработано.|

Буфер сообщений `loaded_bitmaps` важен, поскольку, как `unbounded_buffer` объект, он предлагает `Bitmap` объекты нескольким получателям. Если целевой блок принимает объект `Bitmap`, объект `unbounded_buffer` не предоставляет этот `Bitmap` объект другим целевым объектам. Поэтому важен порядок, в котором объекты связываются с объектом `unbounded_buffer`. Блоки сообщений `grayscale`, `colormask`и `sepiatone` используют фильтр, чтобы принимать только определенные объекты `Bitmap`. `decrement` буфер сообщений является важной целью `loaded_bitmaps` буфера сообщений, так как он принимает все `Bitmap`ные объекты, отклоненные другими буферами сообщений. Для распространения сообщений по порядку требуется объект `unbounded_buffer`. Таким образом, объект `unbounded_buffer` блокируется до тех пор, пока новый целевой блок не будет связан с ним и не примет сообщение, если текущий целевой блок не принимает это сообщение.

Если приложению требуется, чтобы несколько блоков сообщений обрабатывали сообщение, а не только один блок сообщений, который первым принимает сообщение, можно использовать другой тип блока сообщений, например `overwrite_buffer`. Класс `overwrite_buffer` содержит по одному сообщению за раз, но он распространяет это сообщение на все целевые объекты.

На следующем рисунке показана сеть обработки изображений:

![Сеть обработки изображений](../../parallel/concrt/media/concrt_imageproc.png "Сеть обработки изображений")

Объект `countdown_event` в этом примере позволяет сети обработки изображений сообщать основному приложению о том, что все образы обработаны. Класс `countdown_event` использует объект [concurrency::Event](../../parallel/concrt/reference/event-class.md) для сигнализации, если значение счетчика достигает нуля. Основное приложение увеличивает счетчик каждый раз при отправке имени файла в сеть. Узел терминала сети уменьшает счетчик после обработки каждого образа. Когда основное приложение проходит по указанному каталогу, оно ждет, пока объект `countdown_event` сообщит, что его счетчик достиг нуля.

В следующем примере показан класс `countdown_event`:

[!code-cpp[concrt-image-processing-filter#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_13.cpp)]

[[В начало](#top)]

## <a name="complete"></a>Полный пример

Ниже приведен полный пример кода. Функция `wmain` управляет библиотекой GDI+ и вызывает функцию `ProcessImages` для обработки JPEG файлов в каталоге `Sample Pictures`.

[!code-cpp[concrt-image-processing-filter#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-an-image-processing-network_14.cpp)]

На следующем рисунке показан пример выходных данных. Каждый исходный образ находится выше соответствующего измененного образа.

![Пример выходных данных для примера](../../parallel/concrt/media/concrt_imageout.png "Пример выходных данных для данного примера")

`Lighthouse` создан Алфин Tom, поэтому он преобразуется в градации серого. `Chrysanthemum`, `Desert`, `Koala`и `Tulips` имеют красный цвет, поэтому компоненты синего и зеленого цвета удаляются и становятся темными. `Hydrangeas`, `Jellyfish`и `Penguins` соответствуют критериям по умолчанию, поэтому выцветшей упрощенная.

[[В начало](#top)]

### <a name="compiling-the-code"></a>Компиляция кода

Скопируйте пример кода и вставьте его в проект Visual Studio или вставьте в файл с именем `image-processing-network.cpp`, а затем выполните следующую команду в окне командной строки Visual Studio.

**CL. exe/ДУНИКОДЕ/EHsc имаже-процессинг-Нетворк. cpp/Link GDIPLUS. lib**

## <a name="see-also"></a>См. также раздел

[Пошаговые руководства по среде выполнения с параллелизмом](../../parallel/concrt/concurrency-runtime-walkthroughs.md)
