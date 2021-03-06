---
title: 'Элементы управления MFC ActiveX: использование шрифтов'
ms.date: 11/19/2018
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
helpviewer_keywords:
- notifications [MFC], MFC ActiveX controls fonts
- OnDraw method, MFC ActiveX controls
- InternalFont method [MFC]
- SetFont method [MFC]
- OnFontChanged method [MFC]
- IPropertyNotifySink class [MFC]
- MFC ActiveX controls [MFC], fonts
- Stock Font property [MFC]
- HeadingFont property [MFC]
- GetFont method [MFC]
- SelectStockFont method [MFC]
- fonts [MFC], ActiveX controls
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
ms.openlocfilehash: 58f387ba6f4d7cdffb3ffc1f7be6f9acde8314f4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618169"
---
# <a name="mfc-activex-controls-using-fonts"></a>Элементы управления MFC ActiveX: использование шрифтов

Если элемент управления ActiveX отображает текст, можно разрешить пользователю элемента управления изменить внешний вид текста, изменив свойство Font. Свойства шрифта реализуются как объекты шрифтов и могут быть одного из двух типов: акции или пользовательские. Свойства шрифта акции — это предреализуемые свойства шрифта, которые можно добавить с помощью мастера добавления свойства. Свойства пользовательского шрифта не реализуются, а разработчик элемента управления определяет поведение и использование свойства.

В этой статье рассматриваются следующие темы:

- [Использование свойства "шрифт акции"](#_core_using_the_stock_font_property)

- [Использование настраиваемых свойств шрифта в элементе управления](#_core_implementing_a_custom_font_property)

## <a name="using-the-stock-font-property"></a><a name="_core_using_the_stock_font_property"></a>Использование свойства "шрифт акции"

Свойства шрифта акции реализуются с помощью класса [COleControl](reference/colecontrol-class.md). Кроме того, доступна стандартная страница свойств шрифта, позволяющая пользователю изменять различные атрибуты объекта Font, например его имя, размер и стиль.

Доступ к объекту Font осуществляется с помощью функций [Font](reference/colecontrol-class.md#getfont), [сетфонт](reference/colecontrol-class.md#setfont)и [интерналжетфонт](reference/colecontrol-class.md#internalgetfont) `COleControl` . Пользователь элемента управления будет обращаться к объекту Font через `GetFont` `SetFont` функции и точно так же, как и любое другое свойство get/set. Если доступ к объекту Font требуется в элементе управления, используйте `InternalGetFont` функцию.

Как обсуждалось в [элементах управления ActiveX MFC: свойства](mfc-activex-controls-properties.md), Добавление свойств хранения с помощью [мастера добавления свойств](../ide/names-add-property-wizard.md)— это просто. Вы выбираете свойство Font, и мастер добавления свойств автоматически вставляет запись о шрифте акции в карту диспетчеризации элемента управления.

#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>Добавление свойства «стандартный шрифт» с помощью мастера добавления свойства

1. Загрузите проект элемента управления.

1. В представлении класса разверните узел библиотеки элемента управления.

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.

1. В контекстном меню выберите **Добавить** , а затем — **Добавить свойство**.

   Откроется мастер добавления свойств.

1. В поле **имя свойства** щелкните **Шрифт**.

1. Нажмите кнопку **Готово**.

Мастер добавления свойств добавляет следующую строку в карту диспетчеризации элемента управления, расположенную в файле реализации класса элемента управления:

[!code-cpp[NVC_MFC_AxFont#1](codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]

Кроме того, мастер добавления свойств добавляет следующую строку в элемент управления. IDL-файл:

[!code-cpp[NVC_MFC_AxFont#2](codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]

Свойство «заголовок акции» является примером свойства текста, которое можно изобразить с помощью сведений о свойстве «шрифт акции». Добавление свойства "заголовок акции" в элемент управления использует шаги, аналогичные тем, которые используются для свойства "шрифт акции".

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Добавление свойства «заголовок акции» с помощью мастера добавления свойства

1. Загрузите проект элемента управления.

1. В представлении класса разверните узел библиотеки элемента управления.

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.

1. В контекстном меню выберите **Добавить** , а затем — **Добавить свойство**.

   Откроется мастер добавления свойств.

1. В поле **имя свойства** щелкните **заголовок**.

1. Нажмите кнопку **Готово**.

Мастер добавления свойств добавляет следующую строку в карту диспетчеризации элемента управления, расположенную в файле реализации класса элемента управления:

[!code-cpp[NVC_MFC_AxFont#3](codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]

## <a name="modifying-the-ondraw-function"></a><a name="_core_modifying_the_ondraw_function"></a>Изменение функции OnDraw

Реализация по умолчанию `OnDraw` использует системный шрифт Windows для всего текста, отображаемого в элементе управления. Это означает, что необходимо изменить `OnDraw` код, выбрав объект Font в контексте устройства. Для этого вызовите [COleControl:: селектстоккфонт](reference/colecontrol-class.md#selectstockfont) и передайте контекст устройства элемента управления, как показано в следующем примере:

[!code-cpp[NVC_MFC_AxFont#4](codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]

После того как `OnDraw` функция будет изменена для использования объекта Font, любой текст в элементе управления будет отображаться с характеристиками из свойства «стандартный шрифт» элемента управления.

## <a name="using-custom-font-properties-in-your-control"></a><a name="_core_using_custom_font_properties_in_your_control"></a>Использование настраиваемых свойств шрифта в элементе управления

Помимо свойства «стандартный шрифт», элемент управления ActiveX может иметь свойства пользовательского шрифта. Чтобы добавить свойство пользовательского шрифта, необходимо выполнить следующие действия.

- Используйте мастер добавления свойств для реализации свойства пользовательского шрифта.

- [Обработка уведомлений шрифтов](#_core_processing_font_notifications).

- [Реализация нового интерфейса уведомления шрифтов](#_core_implementing_a_new_font_notification_interface).

### <a name="implementing-a-custom-font-property"></a><a name="_core_implementing_a_custom_font_property"></a>Реализация пользовательского свойства шрифта

Для реализации пользовательского свойства шрифта используйте мастер добавления свойств, чтобы добавить свойство, а затем внесите некоторые изменения в код. В следующих разделах описывается добавление пользовательского `HeadingFont` свойства в образец элемента управления.

##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>Добавление свойства пользовательского шрифта с помощью мастера добавления свойства

1. Загрузите проект элемента управления.

1. В представлении класса разверните узел библиотеки элемента управления.

1. Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.

1. В контекстном меню выберите **Добавить** , а затем — **Добавить свойство**.

   Откроется мастер добавления свойств.

1. В поле **имя свойства** введите имя свойства. В этом примере используйте **хеадингфонт**.

1. В поле **Тип реализации**выберите **Методы Get/Set**.

1. В поле **тип свойства** выберите **IDispatch** <strong>\*</strong> для типа свойства.

1. Нажмите кнопку **Готово**.

Мастер добавления свойств создает код для добавления `HeadingFont` пользовательского свойства в `CSampleCtrl` класс и образец. IDL-файл. Так как `HeadingFont` является типом свойства Get/Set, мастер добавления свойств изменяет `CSampleCtrl` карту диспетчеризации класса для включения DISP_PROPERTY_EX_ID[DISP_PROPERTY_EX](reference/dispatch-maps.md#disp_property_ex) запись макроса:

[!code-cpp[NVC_MFC_AxFont#5](codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]

Макрос DISP_PROPERTY_EX связывает `HeadingFont` имя свойства с соответствующими `CSampleCtrl` методами Get и Set класса, `GetHeadingFont` и `SetHeadingFont` . Также указывается тип значения свойства. в этом случае VT_FONT.

Мастер добавления свойств также добавляет объявление в файл заголовка элемента управления (. H) для `GetHeadingFont` функций и `SetHeadingFont` и добавляет их шаблоны функций в файл реализации элемента управления (. CPP):

[!code-cpp[NVC_MFC_AxFont#6](codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]

Наконец, мастер добавления свойств изменяет элемент управления. IDL-файл, добавив запись для `HeadingFont` Свойства:

[!code-cpp[NVC_MFC_AxFont#7](codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]

### <a name="modifications-to-the-control-code"></a>Изменения управляющего кода

Теперь, когда вы добавили `HeadingFont` свойство в элемент управления, необходимо внести некоторые изменения в заголовок элемента управления и файлы реализации для полной поддержки нового свойства.

В файле заголовка элемента управления (. H) добавьте следующее объявление защищенной переменной-члена:

[!code-cpp[NVC_MFC_AxFont#8](codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]

В файле реализации элемента управления (. CPP), выполните следующие действия.

- Инициализация *m_fontHeading* в конструкторе элемента управления.

   [!code-cpp[NVC_MFC_AxFont#9](codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]

- Объявите статическую структуру ФОНТДЕСК, содержащую атрибуты шрифта по умолчанию.

   [!code-cpp[NVC_MFC_AxFont#10](codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]

- В функции- `DoPropExchange` члене элемента управления добавьте вызов `PX_Font` функции. Это обеспечивает инициализацию и сохраняемость для пользовательского свойства шрифта.

   [!code-cpp[NVC_MFC_AxFont#11](codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]

- Завершите реализацию функции элемента управления `GetHeadingFont` .

   [!code-cpp[NVC_MFC_AxFont#12](codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]

- Завершите реализацию функции элемента управления `SetHeadingFont` .

   [!code-cpp[NVC_MFC_AxFont#13](codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]

- Измените функцию- `OnDraw` член элемента управления, чтобы определить переменную, в которой будет храниться ранее выбранный шрифт.

   [!code-cpp[NVC_MFC_AxFont#14](codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]

- Измените функцию-член элемента управления, `OnDraw` чтобы выбрать пользовательский шрифт в контексте устройства, добавив следующую строку везде, где будет использоваться шрифт.

   [!code-cpp[NVC_MFC_AxFont#15](codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]

- Измените `OnDraw` функцию элемента управления, чтобы выбрать предыдущий шрифт обратно в контекст устройства, добавив следующую строку после использования шрифта.

   [!code-cpp[NVC_MFC_AxFont#16](codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]

После реализации свойства пользовательского шрифта необходимо реализовать стандартную страницу свойств шрифта, позволяющую управлять изменением текущего шрифта элемента управления пользователями. Чтобы добавить идентификатор страницы свойств для страницы свойств стандартного шрифта, вставьте следующую строку после макроса BEGIN_PROPPAGEIDS:

[!code-cpp[NVC_MFC_AxFont#17](codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]

Кроме того, необходимо увеличить значение параметра count макроса BEGIN_PROPPAGEIDS на единицу. Это показано в следующей строке:

[!code-cpp[NVC_MFC_AxFont#18](codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]

После внесения этих изменений перестройте весь проект, чтобы включить дополнительные функции.

### <a name="processing-font-notifications"></a><a name="_core_processing_font_notifications"></a>Обработка уведомлений шрифтов

В большинстве случаев элемент управления должен иметь сведения об изменении характеристик объекта Font. Каждый объект Font способен предоставлять уведомления при изменении путем вызова функции-члена `IFontNotification` интерфейса, реализованной в `COleControl` .

Если элемент управления использует свойство «Шрифт акции», его уведомления обрабатываются `OnFontChanged` функцией члена `COleControl` . При добавлении свойств пользовательского шрифта они могут использовать одну и ту же реализацию. В примере из предыдущего раздела это достигается путем передачи &*m_xFontNotification* при инициализации переменной члена *m_fontHeading* .

![Реализация интерфейсов нескольких объектов шрифта](../mfc/media/vc373q1.gif "Реализация интерфейсов нескольких объектов шрифта") <br/>
Реализация нескольких интерфейсов объектов Font

Сплошные линии на рисунке выше показывают, что оба объекта шрифта используют одну и ту же реализацию `IFontNotification` . Это может вызвать проблемы, если вам нужно будет отличать измененный шрифт.

Одним из способов различения уведомлений объекта шрифта элемента управления является создание отдельной реализации `IFontNotification` интерфейса для каждого объекта Font в элементе управления. Этот метод позволяет оптимизировать код рисования, обновляя только строку или строки, которые используют шрифт, измененный недавно. В следующих разделах демонстрируются шаги, необходимые для реализации отдельных интерфейсов уведомлений для второго свойства Font. Второе свойство font считается `HeadingFont` свойством, которое было добавлено в предыдущем разделе.

### <a name="implementing-a-new-font-notification-interface"></a><a name="_core_implementing_a_new_font_notification_interface"></a>Реализация нового интерфейса уведомления шрифтов

Для различения уведомлений двух или более шрифтов необходимо реализовать новый интерфейс уведомления для каждого шрифта, используемого в элементе управления. В следующих разделах описывается реализация нового интерфейса уведомления шрифтов путем изменения заголовка и файлов реализации элемента управления.

### <a name="additions-to-the-header-file"></a>Дополнения к файлу заголовка

В файле заголовка элемента управления (. H) добавьте следующие строки в объявление класса:

[!code-cpp[NVC_MFC_AxFont#19](codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]

При этом создается реализация интерфейса с `IPropertyNotifySink` именем `HeadingFontNotify` . Этот новый интерфейс содержит метод с именем `OnChanged` .

### <a name="additions-to-the-implementation-file"></a>Дополнения к файлу реализации

В коде, который инициализирует шрифт заголовка (в конструкторе элемента управления), измените &*m_xFontNotification* на &*m_xHeadingFontNotify*. Затем добавьте приведенный ниже код.

[!code-cpp[NVC_MFC_AxFont#20](codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]

`AddRef`Методы и `Release` в `IPropertyNotifySink` интерфейсе отслеживают счетчик ссылок для объекта элемента управления ActiveX. Когда элемент управления получает доступ к указателю интерфейса, элемент управления вызывает метод, `AddRef` чтобы увеличить число ссылок. Когда элемент управления завершается с помощью указателя, он вызывает метод, точно так `Release` же, как он `GlobalFree` может быть вызван для освобождения глобального блока памяти. Когда счетчик ссылок для этого интерфейса переходит к нулю, реализация интерфейса может быть освобождена. В этом примере `QueryInterface` функция возвращает указатель на `IPropertyNotifySink` интерфейс определенного объекта. Эта функция позволяет элементу управления ActiveX запрашивать объект, чтобы определить, какие интерфейсы он поддерживает.

После внесения этих изменений в проект перестройте проект и используйте тестовый контейнер для тестирования интерфейса. Сведения о том, как получить доступ к Контейнеру для тестирования, см. в разделе [Тестирование свойств и событий в Контейнере для тестирования](testing-properties-and-events-with-test-container.md) .

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Использование изображений в элементе ActiveX](mfc-activex-controls-using-pictures-in-an-activex-control.md)<br/>
[Элементы ActiveX в MFC. Использование стандартных страниц свойств](mfc-activex-controls-using-stock-property-pages.md)
