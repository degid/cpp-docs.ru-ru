---
title: event_receiver (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.event_receiver
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
ms.openlocfilehash: 7280729a9ae3a054468e1f11bdcc4a563b32effe
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845293"
---
# <a name="event_receiver"></a>event_receiver

Создает приемник событий (получатель).

## <a name="syntax"></a>Синтаксис

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>Параметры

*type*<br/>
Перечисление одного из следующих значений:

- `native` для неуправляемого кода C/C++ (по умолчанию для собственных классов).

- `com` для кода COM. Это значение требует включить следующие файлы заголовка:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
Укажите *layout_dependent* , только если `type` = **com**. *layout_dependent* является логическим значением:

- **`true`** означает, что сигнатуры делегатов в приемнике событий должны точно соответствовать тем, к которым они привязаны в источнике событий. Имена обработчиков приемников событий должны совпадать с именами, указанными в соответствующем исходном интерфейсе события. Необходимо использовать, `coclass` если *layout_dependent* имеет **`true`** . Это несколько более эффективно для указания **`true`** .

- **`false`** (по умолчанию) означает, что соглашение о вызовах и класс хранения (виртуальный, статический и другие) не должны совпадать с методом события и обработчиками. Кроме того, имена обработчиков не должны совпадать с именами методов интерфейса источника событий.

## <a name="remarks"></a>Примечания

Атрибут **event_receiver** C++ указывает, что класс или структура, к которой он применяется, будет приемником событий, используя модель унифицированных событий Visual C++.

**event_receiver** используется с атрибутом [event_source](event-source.md) , а также с ключевыми словами [__hook](../../cpp/hook.md) и [__unhook](../../cpp/unhook.md) . Используйте `event_source` для создания источников событий. Используйте **`__hook`** в методах приемника событий, чтобы связать методы приемника событий с событиями источника событий. Используйте **`__unhook`** , чтобы отменить связь между ними.

*layout_dependent* указывается только для приемников событий COM ( `type` = **com**). Значение по умолчанию для *layout_dependent* — **`false`** .

> [!NOTE]
> Класс-шаблон или структура не могут содержать события.

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|`coclass` При *layout_dependent*=**`true`**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[event_source](event-source.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Атрибуты класса](class-attributes.md)
