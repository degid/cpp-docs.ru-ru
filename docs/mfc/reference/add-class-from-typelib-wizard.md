---
title: Мастер добавления классов из TypeLib
ms.date: 05/09/2019
helpviewer_keywords:
- COM interfaces, adding classes
ms.assetid: 96152afd-9374-4649-a6ab-b0fa2a5592a3
ms.openlocfilehash: 6fa1dd3985fd5b565bcc4b4727f41960d1f4f5d0
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "86405134"
---
# <a name="add-class-from-typelib-wizard"></a>Мастер добавления классов из TypeLib

::: moniker range="vs-2019"

Этот мастер недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="<=vs-2017"

Этот мастер используется для добавления класса MFC из доступной библиотеки типов. Мастер создает класс для каждого интерфейса, добавляемого из выбранной библиотеки типов.

- **Добавить класс из**

   Указывает расположение библиотеки типов, из которой создается класс.

   |Параметр|Описание|
   |------------|-----------------|
   |**Реестр**|Библиотека типов зарегистрирована в системе. Зарегистрированные библиотеки типов перечислены в разделе **Доступные библиотеки типов**.|
   |**Файл**|Библиотека типов не обязательно зарегистрирована в системе, но содержится в файле. Нужно указать расположение файлов в поле **Расположение**.|

- **Доступные библиотеки типов**

   Перечисляет библиотеки типов, зарегистрированные в системе в настоящее время. Выберите библиотеку типов из этого списка, чтобы отобразить ее интерфейсы в списке **интерфейсы** .

- **Расположение**

   Задает расположение библиотеки типов. Если щелкнуть элемент **Файл** в области **Добавить класс из**, можно указать расположение файла, содержащего библиотеку типов. Чтобы перейти к расположению файла, нажмите кнопку с многоточием.

- **Интерфейсы**

   Перечисляет интерфейсы в библиотеке типов, выбранной в списке **Доступные библиотеки типов** .

   |Кнопка "Перенести"|Описание|
   |---------------------|-----------------|
   |**>**|Добавляет интерфейс, выбранный в списке **Интерфейсы**. Недоступно, если интерфейс не выбран.|
   |**>>**|Добавляет все интерфейсы в библиотеке типов, выбранной в списке **Доступные библиотеки типов** .|
   |**\<**|Удаляет класс, выбранный в списке **Созданные классы**. Недоступно, если в списке **создаваемых классов** не выбран ни один класс.|
   |**\<\<**|Удаляет все классы в списке **Созданные классы**. Недоступно, если список **создаваемых классов** пуст.|

- **Созданные классы**

   Указывает имена классов, которые должны быть созданы из интерфейсов, добавленных с помощью **>** **>>** кнопки или. Можно щелкнуть это поле, чтобы выбрать класс, а затем использовать клавиши со стрелками вверх или вниз для прокрутки списка, просмотреть имя каждого класса в поле **класса** и имя файла в поле " **файл** ", создаваемом мастером после нажатия кнопки **"Готово"**. В этом поле можно выбрать только один класс за раз.

   Чтобы удалить класс, выберите его в списке и нажмите кнопку **<** . Вам не нужно выбирать класс в поле Созданные классы для удаления всех классов. Чтобы удалить все классы в поле **Созданные классы**, щелкните **<<**.

- **Класс**

   Задает имя класса, выбранного в поле **Созданные классы**, который мастер добавляет при нажатии кнопки **Готово**. Можно изменить имя в поле **Класс**.

- **Файл**

   Задает имя файла заголовка для нового класса. По умолчанию это имя основано на имени, указанном в поле **Созданные классы**. Нажмите кнопку с многоточием, чтобы сохранить имя файла в выбранном расположении или добавить объявление класса к существующему файлу. При выборе существующего файла мастер не сохраняет его в выбранном расположении, пока вы не нажмете кнопку **Готово** в мастере.

   Мастер не перезаписывает файл. Если выбрать имя существующего файла, при нажатии кнопки **Готово** мастер предложит указать, нужно ли добавить объявление класса к содержимому файла. Чтобы добавить данные в файл, нажмите кнопку **Да**; чтобы вернуться в мастер и указать другое имя файла, нажмите кнопку **Нет**.

::: moniker-end

## <a name="see-also"></a>См. также раздел

[Класс MFC из библиотеки типов](../../mfc/reference/adding-an-mfc-class-from-a-type-library.md)<br/>
[Клиенты автоматизации. Использование библиотек типов](../../mfc/automation-clients-using-type-libraries.md)
