---
title: Изменение кода отрисовки (учебник ATL, часть 4)
ms.custom: get-started-article
ms.date: 09/26/2018
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
ms.openlocfilehash: 319a27b55c394349de751546457b0741c0799cfc
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "82167647"
---
# <a name="changing-the-drawing-code-atl-tutorial-part-4"></a>Изменение кода отрисовки (учебник ATL, часть 4)

По умолчанию код рисования элемента управления отображает квадрат и текст **поликтл**. На этом шаге вы измените код, чтобы он отображал нечто более интересное. Участвуют следующие задачи:

- Изменение файла заголовка

- Изменение `OnDraw` функции

- Добавление метода для вычисления точек многоугольников

- Инициализация цвета заливки

## <a name="modifying-the-header-file"></a>Изменение файла заголовка

Для начала добавьте поддержку математических функций `sin` и `cos`, которые будут использоваться для вычисления точек многоугольников, и создайте массив для хранения позиций.

### <a name="to-modify-the-header-file"></a>Изменение файла заголовка

1. Добавьте строку `#include <math.h>` в начало поликтл.h. Начало файла должно выглядеть следующим образом:

    [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]

1. Реализуйте `IProvideClassInfo` интерфейс, чтобы предоставить сведения о методе для элемента управления, добавив следующий код в поликтл.h. В `CPolyCtl` классе замените Line:

    ```cpp
    public CComControl<CPolyCtl>
    ```

    на

    ```cpp
    public CComControl<CPolyCtl>,
    public IProvideClassInfo2Impl<&CLSID_PolyCtl, &DIID__IPolyCtlEvents, &LIBID_PolygonLib>
    ```

    и в `BEGIN_COM_MAP(CPolyCtl)`добавьте строки:

    ```cpp
    COM_INTERFACE_ENTRY(IProvideClassInfo)
    COM_INTERFACE_ENTRY(IProvideClassInfo2)
    ```

1. После вычисления точек многоугольников они будут храниться в массиве типа `POINT`, поэтому добавьте массив после оператора `short m_nSides;` определения в поликтл.h:

    [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_2.h)]

## <a name="modifying-the-ondraw-method"></a>Изменение метода OnDraw

Теперь необходимо изменить `OnDraw` метод в поликтл.h. Код, который вы добавите, создает новое перо и кисть для рисования многоугольника, а затем вызывает функции `Ellipse` и `Polygon` API Win32 для выполнения фактического рисования.

### <a name="to-modify-the-ondraw-function"></a>Изменение функции OnDraw

1. Замените существующий `OnDraw` метод в поликтл.h следующим кодом:

    [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]

## <a name="adding-a-method-to-calculate-the-polygon-points"></a>Добавление метода для вычисления точек многоугольников

Добавьте метод с именем `CalcPoints`, который будет вычислять координаты точек, составляющих периметр многоугольника. Эти вычисления будут основываться на переменной RECT, передаваемой в функцию.

### <a name="to-add-the-calcpoints-method"></a>Добавление метода Калкпоинтс

1. Добавьте объявление `CalcPoints` в `IPolyCtl` общедоступный раздел `CPolyCtl` класса в поликтл.h:

    [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_4.h)]

    Последняя часть общедоступного раздела `CPolyCtl` класса будет выглядеть следующим образом:

    [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_5.h)]

1. Добавьте эту реализацию `CalcPoints` функции в конец поликтл. cpp:

    [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]

## <a name="initializing-the-fill-color"></a>Инициализация цвета заливки

Инициализация `m_clrFillColor` с использованием цвета по умолчанию.

### <a name="to-initialize-the-fill-color"></a>Инициализация цвета заливки

1. Используйте зеленый как цвет по умолчанию, добавив следующую строку `CPolyCtl` в конструктор в поликтл.h:

    [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_7.h)]

Теперь конструктор выглядит следующим образом:

[!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_8.h)]

## <a name="building-and-testing-the-control"></a>Сборка и тестирование элемента управления

Перестройте элемент управления. Убедитесь, что файл Поликтл.htm закрыт, если он все еще открыт, а затем нажмите кнопку **построить многоугольник** в меню **Сборка** . Вы можете снова просмотреть элемент управления на странице Поликтл.htm, но на этот раз используйте тестовый контейнер элемента управления ActiveX.

### <a name="to-use-the-activex-control-test-container"></a>Использование тестового контейнера элемента управления ActiveX

1. Создайте и запустите тестовый контейнер элемента управления ActiveX. [Пример тсткон. контейнер теста элемента управления ActiveX](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/ole/TstCon) можно найти на сайте GitHub.

    > [!NOTE]
    > `ATL::CW2AEX`Для ошибок, содержащихся в скрипте script. cpp, `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT );` замените `TRACE( "XActiveScriptSite::GetItemInfo( %s )\n", pszNameT.m_psz );`строку на, `TRACE( "Source Text: %s\n", COLE2CT( bstrSourceLineText ) );` а `TRACE( "Source Text: %s\n", bstrSourceLineText );`строку на.<br/>
    > При возникновении ошибок `HMONITOR`откройте файл stdafx.h в `TCProps` проекте и замените:
    >
    > ```cpp
    > #ifndef WINVER
    > #define WINVER 0x0400
    > #endif
    > ```
    >
    > на
    >
    > ```cpp
    > #ifndef WINVER
    > #define WINVER 0x0500
    > #define _WIN32_WINNT 0x0500
    > #endif
    > ```

1. В **тестовом контейнере**в меню **Правка** выберите пункт **Вставить новый элемент управления**.

1. Выберите элемент управления, который будет вызываться `PolyCtl class`, и нажмите кнопку **ОК**. Вы увидите зеленый треугольник в окружности.

Попробуйте изменить количество сторон, выполнив следующую процедуру. Чтобы изменить свойства сдвоенного интерфейса в **тестовом контейнере**, используйте **методы Invoke**.

### <a name="to-modify-a-controls-property-from-within-the-test-container"></a>Изменение свойства элемента управления из тестового контейнера

1. В **тестовом контейнере**в меню **Управление** выберите команду **вызвать методы** .

    Откроется диалоговое окно **вызов метода** .

1. Выберите версию **propput** свойства **стороны** из раскрывающегося списка **имя метода** .

1. Введите `5` в поле **значение параметра** , щелкните **задать значение**и нажмите кнопку **вызвать**.

Обратите внимание, что элемент управления не изменяется. Несмотря на то, что число внутренних сторон было изменено внутренне путем задания `m_nSides` переменной, это не приводит к перерисовке элемента управления. Если переключиться на другое приложение, а затем вернуться к **тестовому контейнеру**, вы обнаружите, что элемент управления был перерисован и имеет правильное количество сторон.

Чтобы устранить эту проблему, добавьте вызов `FireViewChange` функции, определенной в `IViewObjectExImpl`, после задания числа сторон. Если элемент управления выполняется в отдельном окне, `FireViewChange` вызов `InvalidateRect` метода осуществляется напрямую. Если элемент управления работает без окон, `InvalidateRect` метод будет вызываться в интерфейсе сайта контейнера. Это заставляет элемент управления перерисовывать сам себя.

### <a name="to-add-a-call-to-fireviewchange"></a>Добавление вызова Фиревиевчанже

1. Обновите Поликтл. cpp, добавив вызов `FireViewChange` в `put_Sides` метод. По завершении `put_Sides` метод должен выглядеть следующим образом:

    [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/cpp/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]

После добавления `FireViewChange`, перестройте и снова попробуйте элемент управления в тестовом контейнере элемента управления ActiveX. На этот раз при изменении числа сторон и нажатии кнопки `Invoke`вы увидите, что элемент управления будет изменен немедленно.

На следующем шаге будет добавлено событие.

[Вернитесь к шагу 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [на шаг 5](../atl/adding-an-event-atl-tutorial-part-5.md) .

## <a name="see-also"></a>См. также

[Руководство](../atl/active-template-library-atl-tutorial.md)<br/>
[Тестирование свойств и событий с использованием тестового контейнера](../mfc/testing-properties-and-events-with-test-container.md)
