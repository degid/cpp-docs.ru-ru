---
title: "Добавление события (ATL учебника, часть 5) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8cef973849a9af88cd952be69ce9d33e7a516d7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Добавление события (учебник ATL, часть 5)
На этом шаге вы добавите `ClickIn` и `ClickOut` событий для элемента управления ATL. Будет срабатывать `ClickIn` событие, если пользователь щелкает внутри многоугольника и противопожарного `ClickOut` при щелчке за пределами. Ниже приведены задачи, чтобы добавить событие.  
  
-   Добавление `ClickIn` и `ClickOut` методов  
  
-   Создание библиотеки типов  
  
-   Реализация точки подключения интерфейсов  
  
## <a name="adding-the-clickin-and-clickout-methods"></a>Добавление ClickIn и ClickOut методов  
 При создании элемента управления ATL на предыдущем шаге вы выбрали **точки подключения** флажок. Это создан `_IPolyCtlEvents` интерфейс в файле Polygon.idl. Обратите внимание, что имя интерфейса начинается со знака подчеркивания. Это соглашение для указания, что интерфейс является внутренним интерфейсом. Таким образом программы, которые позволяют просматривать COM-объекты можно не отображать интерфейс пользователя. Также Обратите внимание, что **точки подключения** добавьте следующую строку в файле Polygon.idl, чтобы указать, что `_IPolyCtlEvents` исходный интерфейс по умолчанию:  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 Атрибут source указывает управления является источник уведомления, поэтому он будет вызывать этот интерфейс в контейнере.  
  
 Теперь добавьте `ClickIn` и `ClickOut` методы `_IPolyCtlEvents` интерфейса.  
  
#### <a name="to-add-the-clickin-and-clickout-methods"></a>Добавление методов ClickIn и ClickOut  
  
1.  В представлении класса разверните многоугольников и PolygonLib для отображения _IPolyCtlEvents.  
  
2.  Щелкните правой кнопкой мыши _IPolyCtlEvents. В контекстном меню выберите **добавить**, а затем нажмите кнопку **добавить метод**.  
  
3.  Выберите **тип возвращаемого значения** из `void`.  
  
4.  Введите `ClickIn` в **имя метода** поле.  
  
5.  В разделе **атрибуты параметра**выберите **в** поле.  
  
6.  Выберите **тип параметра** из `LONG`.  
  
7.  Тип `x` как **имя параметра**и нажмите кнопку **добавить**.  
  
8.  Повторите шаги с 5 по 7, в настоящее время для **имя параметра** из `y`.  
  
9. Нажмите кнопку **Далее**.  
  
10. Тип `method ClickIn` как **helpstring**.  
  
11. Нажмите кнопку **Готово**.  
  
12. Шаги, описанные выше, чтобы определить `ClickOut` метод с тем же `LONG` параметры `x` и `y`, то **атрибуты параметра** и тот же `void` тип возвращаемого значения.  
  
 Проверьте файл Polygon.idl, чтобы увидеть, что код был добавлен `_IPolyCtlEvents` disp-интерфейса.  
  
 `_IPolyCtlEvents` Disp-интерфейса в файле Polygon.idl теперь должна выглядеть следующим образом:  
  
 [!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_1.idl)]  
  
 `ClickIn` И `ClickOut` методы принимают x и y координаты выбранной точки в качестве параметров.  
  
## <a name="generating-the-type-library"></a>Создание библиотеки типов  
 На этом этапе создавайте библиотеку типов, так как мастер точки подключения будет использоваться для получения сведения, необходимые для создания интерфейса точки подключения и интерфейс контейнера точки подключения для элемента управления.  
  
#### <a name="to-generate-the-type-library"></a>Для создания библиотеки типов  
  
1.  Перестройте проект.  
  
     -или-  
  
2.  Щелкните правой кнопкой мыши файл Polygon.idl в обозревателе решений и выберите **компиляции** в контекстном меню.  
  
 Это создаст файл Polygon.tlb, который имеет свою библиотеку типов. Файл Polygon.tlb не отображается в обозревателе решений, так как он является двоичным файлом и не может быть просмотрены или изменены непосредственно.  
  
## <a name="implementing-the-connection-point-interfaces"></a>Реализация точки подключения интерфейсов  
 Реализуйте интерфейс точки подключения и интерфейс контейнера точки подключения для элемента управления. В модели COM события реализуются посредством механизма точек подключения. Для получения событий из COM-объектом, контейнер устанавливает вспомогательное соединение к точке соединения, который реализует COM-объекта. Так как COM-объект может иметь несколько точек подключения, COM-объекта также реализует интерфейс контейнера точки подключения. Через этот интерфейс контейнера можно определить, какие точки подключения поддерживаются.  
  
 Интерфейс, который реализует точку соединения вызывается `IConnectionPoint`, и интерфейс, реализующий контейнер точки подключения называется `IConnectionPointContainer`.  
  
 Чтобы реализовать `IConnectionPoint`, используется мастер реализации точек подключения. Этот мастер создает `IConnectionPoint` интерфейса путем чтения свою библиотеку типов и реализации функции для каждого события, которое может быть.  
  
#### <a name="to-use-the-implement-connection-point-wizard"></a>Чтобы использовать мастер реализации точек подключения  
  
1.  В представлении классов щелкните правой кнопкой мыши класс реализации элемента управления `CPolyCtl`.  
  
2.  В контекстном меню щелкните **добавить**, а затем нажмите кнопку **добавить точку подключения**.  
  
3.  Выберите `_IPolyCtlEvents` из **интерфейсов источника** список и дважды щелкните его, чтобы добавить его в **реализованы точки соединения** столбца. Нажмите кнопку **Готово**. Будет создан класс-посредник для точки подключения, в этом случае `CProxy_IPolyCtlEvents`.  
  
 Если взглянуть на созданный _IPolyCtlEvents_CP.h файл в обозревателе решений, вы увидите наличие в нем создается класс с именем `CProxy_IPolyCtlEvents` , производный от `IConnectionPointImpl`. _IPolyCtlEvents_CP.h определяет два метода `Fire_ClickIn` и `Fire_ClickOut`, который принимают два параметра координат. Если вы хотите вызывать события из элемента управления вызывать эти методы.  
  
 Мастер также добавлены `CProxy_PolyEvents` и `IConnectionPointContainerImpl` несколько наследования список элемента управления. Мастер также предоставляется `IConnectionPointContainer` вам, добавив соответствующие записи в сопоставление COM.  
  
 Не требуется реализация кода для поддержки событий. Теперь добавьте некоторый код для вызова событий в соответствующий момент. Помните, что вы собираетесь срабатывание `ClickIn` или `ClickOut` событие, когда пользователь нажимает кнопку мыши в элементе управления. Чтобы определить, когда пользователь нажимает кнопку, добавьте обработчик для `WM_LBUTTONDOWN` сообщения.  
  
#### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>Чтобы добавить обработчик для сообщения WM_LBUTTONDOWN  
  
1.  В представлении классов щелкните правой кнопкой мыши класс CPolyCtl и нажмите кнопку **свойства** в контекстном меню.  
  
2.  В **свойства** окно, нажмите кнопку **сообщений** значок и нажмите кнопку `WM_LBUTTONDOWN` в списке слева.  
  
3.  В раскрывающемся списке выберите  **\<Добавить > OnLButtonDown**. `OnLButtonDown` Объявление обработчика будет добавляться к PolyCtl.h и PolyCtl.cpp будут добавлены на реализацию обработчика.  
  
 Далее измените обработчик.  
  
#### <a name="to-modify-the-onlbuttondown-method"></a>Чтобы изменить OnLButtonDown-метод  
  
1.  Измените код, который состоит из `OnLButtonDown` метода в PolyCtl.cpp (любой код, помещенный в мастере удаления), чтобы он выглядел следующим образом:  
  
     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]  
  
 Это делает код точки вычисляются в `OnDraw` функции для создания области, которое обнаруживает щелчков мыши пользователя при вызове `PtInRegion`.  
  
 `uMsg` Параметр — идентификатор обрабатываемого сообщения Windows. Это позволяет иметь одну функцию, обрабатывающий ряд сообщений. `wParam` И `lParam` параметры — это стандартные значения для обрабатываемого сообщения. Параметр bHandled позволяет указать ли функция обработал сообщение или нет. По умолчанию присвоено значение `TRUE` для указания функция обработал сообщение, что ему можно присвоить `FALSE`. Это приведет к ATL продолжить поиск другой функции обработки сообщений для отправки сообщения.  
  
## <a name="building-and-testing-the-control"></a>Построение и тестирование элемента управления  
 Теперь проверим событий. Создать элемент управления и снова запустите тестовый контейнер элемента управления ActiveX. На этот раз просмотрите окно "журнал событий". Для отправки событий в окне вывода, нажмите кнопку **входа** из **параметры** и выбрать пункт **журнала в окне вывода**. Вставить элемент управления и щелкните правой кнопкой мыши в окне. Обратите внимание, что `ClickIn` срабатывает при нажатии кнопки в пределах закрашенный многоугольник и `ClickOut` срабатывает при нажатии кнопки за ее пределами.  
  
 Далее вы добавите страницу свойств.  
  
 [Вернитесь к шагу 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [На шаге 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="see-also"></a>См. также  
 [Учебник](../atl/active-template-library-atl-tutorial.md)
