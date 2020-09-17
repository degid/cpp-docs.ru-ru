---
title: Атрибуты класса (C++ com)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], class attributes
ms.assetid: fad04ea1-d8ff-46d4-bb42-2b4500a6ab60
ms.openlocfilehash: 5e10b7831e59211b73ce947ac21e43bc1a8af1c9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167320"
---
# <a name="class-attributes"></a>Атрибуты классов

К ключевому слову [Class](../../cpp/class-cpp.md) C++ применяются следующие атрибуты.

|attribute|Description|
|---------------|-----------------|
|[aggregatable](aggregatable.md)|Указывает, что класс поддерживает агрегирование.|
|[aggregates](aggregates.md)|Указывает, что элемент управления выполняет статистическую обработку целевого класса.|
|[appobject](appobject.md)|Определяет компонент в качестве объекта приложения, связанного с полным exe-приложением, и указывает, что функции и свойства компонентного класса глобально доступны в этой библиотеке типов.|
|[case](case-cpp.md)|Используется с атрибутом [switch_type](switch-type.md) в объединении.|
|[кокласс](coclass.md)|Создает элемент управления ActiveX.|
|[com_interface_entry](com-interface-entry-cpp.md)|Добавляет запись интерфейса в карту COM.|
|[control](control.md)|Указывает, что определяемый пользователем тип является элементом управления.|
|[custom](custom-cpp.md)|Позволяет определить собственный атрибут.|
|[db_command](db-command.md)|Создает команду OLE DB.|
|[db_param](db-param.md)|Связывает указанную переменную элемента с входным или выходным параметром и разделяет переменную.|
|[db_source](db-source.md)|Создает соединение с источником данных.|
|[db_table](db-table.md)|Открывает таблицу OLE DB.|
|[значение по умолчанию](default-cpp.md)|Указывает, что настраиваемый или disp-интерфейс, определенный в коклассе, представляет интерфейс программирования по умолчанию.|
|[defaultvtable](defaultvtable.md)|Определяет интерфейс как интерфейс vtable по умолчанию для элемента управления.|
|[event_receiver](event-receiver.md)|Создает приемник событий.|
|[event_source](event-source.md)|Создает источник событий.|
|[helpcontext](helpcontext.md)|Указывает идентификатор контекста, позволяющий пользователю просматривать сведения об этом элементе в файле **справки** .|
|[helpfile](helpfile.md)|Задает имя файла справки для библиотеки типов.|
|[helpstringcontext](helpstringcontext.md)|Указывает идентификатор раздела справки в файле.hlp или. chm.|
|[helpstring](helpstring.md)|Определяет строку символов, используемую для описания элемента, к которому оно применяется.|
|[hidden](hidden.md)|Указывает, что элемент существует, но не должен отображаться в браузере, ориентированном на пользователя.|
|[implements](implements-cpp.md)|Указывает интерфейсы диспетчеризации, которые должны быть членами coclass-класса IDL.|
|[implements_category](implements-category.md)|Задает категории реализованного компонента для класса.|
|[module](module-cpp.md)|Определяет блок библиотеки в IDL-файле.|
|[noncreatable](noncreatable.md)|Определяет объект, который не может быть создан самим по себе.|
|[progid](progid.md)|Определяет ProgID для элемента управления.|
|[registration_script](registration-script.md)|Выполняет указанный скрипт регистрации.|
|[requestedit](requestedit.md)|Указывает, что свойство поддерживает уведомление `OnRequestEdit`.|
|[источник](source-cpp.md)|Указывает исходные интерфейсы элемента управления для точек соединения в классе. В свойстве или методе атрибут `source` указывает, что член возвращает объект или `VARIANT`, являющийся источником событий.|
|[support_error_info](support-error-info.md)|Поддерживает отчеты об ошибках для целевого объекта.|
|[threading](threading-cpp.md)|Задает потоковую модель для элемента управления.|
|[uuid](uuid-cpp-attributes.md)|Задает уникальный идентификатор класса или интерфейса.|
|[version](version-cpp.md)|Определяет определенную версию для нескольких версий класса.|
|[vi_progid](vi-progid.md)|Указывает независимую от версии форму ProgID.|

## <a name="see-also"></a>См. также раздел

[Список атрибутов по использованию](attributes-by-usage.md)
