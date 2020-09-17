---
title: Добавление события (учебник ATL, часть 5)
ms.custom: get-started-article
ms.date: 09/27/2018
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
ms.openlocfilehash: c9a7c6f38a2f47ec808081e440a200737ad1928a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127578"
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Добавление события (учебник ATL, часть 5)

На этом шаге вы добавите `ClickIn` и `ClickOut` событие в элемент управления ATL. Событие `ClickIn` будет срабатывать, если пользователь щелкнет в пределах многоугольника и выпустит `ClickOut`, если пользователь щелкнет за пределами. Ниже приведены задачи по добавлению события.

- Добавление методов `ClickIn` и `ClickOut`

- Создание библиотеки типов

- Реализация интерфейсов точек подключения

## <a name="adding-the-clickin-and-clickout-methods"></a>Добавление методов Click и Click

При создании элемента управления ATL на шаге 2 установлен флажок **точки соединения** . При этом был создан интерфейс `_IPolyCtlEvents` в файле Polygon. idl. Обратите внимание, что имя интерфейса начинается с символа подчеркивания. Это соглашение указывает, что интерфейс является внутренним интерфейсом. Таким же программам, которые позволяют просматривать COM-объекты, можно не отображать интерфейс для пользователя. Также обратите внимание, что при выборе **точек подключения** в файле Polygon. idl была добавлена следующая строка, указывающая, что `_IPolyCtlEvents` является исходным интерфейсом по умолчанию:

`[default, source] dispinterface _IPolyCtlEvents;`

Атрибут Source указывает, что элемент управления является источником уведомлений, поэтому он будет вызывать этот интерфейс в контейнере.

Теперь добавьте методы `ClickIn` и `ClickOut` в интерфейс `_IPolyCtlEvents`.

### <a name="to-add-the-clickin-and-clickout-methods"></a>Добавление методов Click и Click

1. В **Обозреватель решений**откройте Polygon. idl и добавьте следующий код в раздел `methods:` в объявлении `dispInterface_IPolyCtlEvents` библиотеки полигонлиб:

    ```cpp
   [id(1), helpstring("method ClickIn")] void ClickIn([in] LONG x,[in] LONG y);
   [id(2), helpstring("method ClickOut")] void ClickOut([in] LONG x,[in] LONG y);
    ```

Методы `ClickIn` и `ClickOut` принимают координаты x и y нажатой точки в качестве параметров.

## <a name="generating-the-type-library"></a>Создание библиотеки типов

Создание библиотеки типов на этом этапе, поскольку проект будет использовать его для получения сведений, необходимых для создания интерфейса точки подключения и интерфейса контейнера точки подключения для элемента управления.

### <a name="to-generate-the-type-library"></a>Создание библиотеки типов

1. Перестройте свой проект.

     -или-

1. Щелкните правой кнопкой мыши файл Polygon. idl в **Обозреватель решений** и в контекстном меню выберите команду **компилировать** .

Будет создан файл Polygon. tlb, который является библиотекой типов. Файл Polygon. tlb не отображается в **Обозреватель решений**, так как он является двоичным файлом и не может быть просмотрен или изменен напрямую.

## <a name="implementing-the-connection-point-interfaces"></a>Реализация интерфейсов точек подключения

Реализуйте интерфейс точки подключения и интерфейс контейнера точки подключения для элемента управления. В COM события реализуются с помощью механизма точек соединения. Для получения событий из COM-объекта контейнер устанавливает связь с точкой соединения, которую реализует COM-объект. Так как COM-объект может иметь несколько точек подключения, COM-объект также реализует интерфейс контейнера точки подключения. С помощью этого интерфейса контейнер может определить, какие точки подключения поддерживаются.

Интерфейс, реализующий точку подключения, называется `IConnectionPoint`, а интерфейс, реализующий контейнер точки подключения, называется `IConnectionPointContainer`.

Чтобы реализовать `IConnectionPoint`, вы будете использовать мастер реализации точки подключения. Этот мастер создает интерфейс `IConnectionPoint`, считывая библиотеку типов и реализуя функцию для каждого события, которое может быть запущено.

### <a name="to-implement-the-connection-points"></a>Реализация точек подключения

1. В **Обозреватель решений**откройте _IPolyCtlEvents_CP.h и добавьте следующий код в инструкцию `public:` в классе `CProxy_IPolyCtlEvents`:

    ```cpp
    VOID Fire_ClickIn(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x1, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    VOID Fire_ClickOut(LONG x, LONG y)
    {
        T* pT = static_cast<T*>(this);
        int nConnectionIndex;
        CComVariant* pvars = new CComVariant[2];
        int nConnections = m_vec.GetSize();

        for (nConnectionIndex = 0; nConnectionIndex < nConnections; nConnectionIndex++)
        {
            pT->Lock();
            CComPtr<IUnknown> sp = m_vec.GetAt(nConnectionIndex);
            pT->Unlock();
            IDispatch* pDispatch = reinterpret_cast<IDispatch*>(sp.p);
            if (pDispatch != NULL)
            {
                pvars[1].vt = VT_I4;
                pvars[1].lVal = x;
                pvars[0].vt = VT_I4;
                pvars[0].lVal = y;
                DISPPARAMS disp = { pvars, NULL, 2, 0 };
                pDispatch->Invoke(0x2, IID_NULL, LOCALE_USER_DEFAULT, DISPATCH_METHOD, &disp, NULL, NULL, NULL);
            }
        }
        delete[] pvars;

    }
    ```

Вы увидите, что этот файл содержит класс с именем `CProxy_IPolyCtlEvents`, производный от `IConnectionPointImpl`. _IPolyCtlEvents_CP.h теперь определяет два метода `Fire_ClickIn` и `Fire_ClickOut`, которые принимают два параметра координат. Эти методы вызываются, когда требуется запустить событие из элемента управления.

При создании выбранного параметра «элемент управления с **точками соединения** » файл _IPolyCtlEvents_CP.h был создан автоматически. Она также добавила `CProxy_PolyEvents` и `IConnectionPointContainerImpl` в список множественного наследования элемента управления и предоставляла `IConnectionPointContainer`, добавляя соответствующие записи в карту COM.

Реализация кода для поддержки событий завершена. Теперь добавьте код для запуска событий в соответствующий момент времени. Помните, что событие `ClickIn` или `ClickOut` будет срабатывать, когда пользователь нажимает на элемент управления левую кнопку мыши. Чтобы узнать, когда пользователь нажимает кнопку, добавьте обработчик для сообщения `WM_LBUTTONDOWN`.

### <a name="to-add-a-handler-for-the-wm_lbuttondown-message"></a>Добавление обработчика для сообщения WM_LBUTTONDOWN

1. В **представление классов**щелкните правой кнопкой мыши класс `CPolyCtl` и в контекстном меню выберите пункт **свойства** .

1. В окне **Свойства** щелкните значок **сообщения** , а затем выберите `WM_LBUTTONDOWN` из списка слева.

1. В появившемся раскрывающемся списке щелкните **\<добавить > онлбуттондовн**. Объявление обработчика `OnLButtonDown` будет добавлено в Поликтл.h, и реализация обработчика будет добавлена в Поликтл. cpp.

Затем измените обработчик.

### <a name="to-modify-the-onlbuttondown-method"></a>Изменение метода Онлбуттондовн

1. Измените код, который включает метод `OnLButtonDown` в Поликтл. cpp (удаление любого кода, помещенного мастером), чтобы он выглядел следующим образом:

    [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]

Этот код использует точки, вычисленные в функции `OnDraw`, для создания региона, который обнаруживает щелчки мыши пользователя с помощью вызова `PtInRegion`.

Параметр *uiacp* является идентификатором обрабатываемого сообщения Windows. Это позволяет использовать одну функцию, обрабатывающую диапазон сообщений. Параметры *wParam* и *lParam* являются стандартными значениями обрабатываемого сообщения. Параметр *бхандлед* позволяет указать, должна ли функция обрабатывать сообщение. По умолчанию значение равно TRUE, чтобы указать, что функция обработала сообщение, но можно задать для него значение FALSE. Это приведет к тому, что библиотека ATL продолжит поиск другой функции обработчика сообщений для отправки сообщения.

## <a name="building-and-testing-the-control"></a>Сборка и тестирование элемента управления

Теперь попробуйте свои события. Постройте элемент управления и снова запустите тестовый контейнер элемента управления ActiveX. На этот раз просмотрите окно Журнал событий. Чтобы направить события в окно вывода, выберите пункт **ведение журнала** в меню **Параметры** и выберите пункт **Журнал в окне вывода**. Вставьте элемент управления и попробуйте щелкнуть его в окне. Обратите внимание, что `ClickIn` срабатывает, если щелкнуть в закрашенном многоугольнике, и `ClickOut` срабатывает при щелчке за его пределами.

Далее предстоит добавить страницу свойств.

[Вернемся к шагу 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [на шаге 6](../atl/adding-a-property-page-atl-tutorial-part-6.md) .

## <a name="see-also"></a>См. также раздел

[Руководство](../atl/active-template-library-atl-tutorial.md)
