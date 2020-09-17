---
title: Использование IDispEventImpl (ATL)
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: 9684781ba99d96e2c58d450ee0ff892374e33aef
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630600"
---
# <a name="using-idispeventimpl"></a>Использование IDispEventImpl

При использовании `IDispEventImpl` для работы с событиями необходимо выполнить следующие действия:

- Создайте класс, производный от [IDispEventImpl](../atl/reference/idispeventimpl-class.md).

- Добавьте карту приемника событий в класс.

- Добавьте записи в карту приемника событий с помощью макроса [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) или [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) .

- Реализуйте методы, которые вы заинтересованы в обработке.

- Посоветовать и порекомендовать источник событий.

## <a name="example"></a>Пример

В приведенном ниже примере показано, `DocumentChange` как обработано событие, инициированное объектом **приложения** Word. Это событие определяется как метод в `ApplicationEvents` DISP-интерфейсе.

Пример приведен в примере [атлевенсандлинг](../overview/visual-cpp-samples.md).

```cpp
[ uuid(000209F7-0000-0000-C000-000000000046), hidden ]
dispinterface ApplicationEvents {
properties:
methods:
    [id(0x00000001), restricted, hidden]
    void Startup();

    [id(0x00000002)]
    void Quit();

    [id(0x00000003)]
    void DocumentChange();
};
```

В примере используется `#import` для создания необходимых файлов заголовков из библиотеки типов Word. Если вы хотите использовать этот пример с другими версиями Word, необходимо указать правильный DLL-файл Mso. Например, в Office 2000 есть MSO9. dll, а Оффицексп — MSO. dll. Этот код упрощен из *PCH.h* (*stdafx.h* в Visual Studio 2017 и более ранних версиях):

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

Следующий код отображается в Нотсосимпле.h. Соответствующий код отмечается комментариями:

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>См. также

[Обработка событий](../atl/event-handling-and-atl.md)<br/>
[Пример Атлевенсандлинг](../overview/visual-cpp-samples.md)
