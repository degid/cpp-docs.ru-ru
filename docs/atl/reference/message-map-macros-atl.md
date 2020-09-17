---
title: Макросы схемы сообщений (ATL)
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::ALT_MSG_MAP
- atlwin/ATL::BEGIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_ALT
- atlwin/ATL::CHAIN_MSG_MAP_ALT_MEMBER
- atlwin/ATL::CHAIN_MSG_MAP
- atlwin/ATL::CHAIN_MSG_MAP_DYNAMIC
- atlwin/ATL::CHAIN_MSG_MAP_MEMBER
- atlwin/ATL::COMMAND_CODE_HANDLER
- atlwin/ATL::COMMAND_HANDLER
- atlwin/ATL::COMMAND_ID_HANDLER
- atlwin/ATL::COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::COMMAND_RANGE_HANDLER
- atlwin/ATL::DECLARE_EMPTY_MSG_MAP
- atlwin/ATL::DEFAULT_REFLECTION_HANDLER
- atlwin/ATL::END_MSG_MAP
- atlwin/ATL::FORWARD_NOTIFICATIONS
- atlwin/ATL::MESSAGE_HANDLER
- atlwin/ATL::MESSAGE_RANGE_HANDLER
- atlwin/ATL::NOTIFY_CODE_HANDLER
- atlwin/ATL::NOTIFY_HANDLER
- atlwin/ATL::NOTIFY_ID_HANDLER
- atlwin/ATL::NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::NOTIFY_RANGE_HANDLER
- atlwin/ATL::REFLECT_NOTIFICATIONS
- atlwin/ATL::REFLECTED_COMMAND_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_ID_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_COMMAND_RANGE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_ID_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_CODE_HANDLER
- atlwin/ATL::REFLECTED_NOTIFY_RANGE_HANDLER
ms.assetid: eefdd546-8934-4a30-b263-9c06a8addcbd
ms.openlocfilehash: 9917f31dbb115552cf9dc9bde24f7b6921611750
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835302"
---
# <a name="message-map-macros-atl"></a>Макросы схемы сообщений (ATL)

Эти макросы определяют схемы и записи сообщений.

|Имя|Описание|
|-|-|
|[ALT_MSG_MAP](#alt_msg_map)|Помечает начало альтернативной схемы сообщения.|
|[BEGIN_MSG_MAP](#begin_msg_map)|Помечает начало схемы сообщения по умолчанию.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Цепочка для альтернативной схемы сообщений в базовом классе.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Цепочка для альтернативной схемы сообщений в элементе данных класса.|
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочка для схемы сообщений по умолчанию в базовом классе.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Цепочка для схемы сообщений в другом классе во время выполнения.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочка для схемы сообщений по умолчанию в члене данных класса.|
|[COMMAND_CODE_HANDLER](#command_code_handler)|Сопоставляет WM_COMMAND сообщение с функцией обработчика на основе кода уведомления.|
|[COMMAND_HANDLER](#command_handler)|Сопоставляет WM_COMMAND сообщение с функцией обработчика на основе кода уведомления и идентификатора элемента меню, элемента управления или ускорителя.|
|[COMMAND_ID_HANDLER](#command_id_handler)|Сопоставляет WM_COMMAND сообщение с функцией обработчика на основе идентификатора элемента меню, элемента управления или ускорителя.|
|[COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler)|Сопоставляет WM_COMMAND сообщение с функцией обработчика на основе кода уведомления и непрерывного диапазона идентификаторов элементов управления.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Сопоставляет WM_COMMAND сообщение с функцией обработчика на основе непрерывного диапазона идентификаторов элементов управления.|
|[DECLARE_EMPTY_MSG_MAP](#declare_empty_msg_map)|Реализует пустую схему сообщения.|
|[DEFAULT_REFLECTION_HANDLER](#default_reflection_handler)|Предоставляет обработчик по умолчанию для отраженных сообщений, которые в противном случае не обрабатываются.|
|[END_MSG_MAP](#end_msg_map)|Помечает конец схемы сообщения.|
|[FORWARD_NOTIFICATIONS](#forward_notifications)|Пересылает сообщения уведомления родительскому окну.|
|[MESSAGE_HANDLER](#message_handler)|Сопоставляет сообщение Windows с функцией обработчика.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Сопоставляет непрерывный диапазон сообщений Windows функции обработчика.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Сопоставляет WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления.|
|[NOTIFY_HANDLER](#notify_handler)|Сопоставляет WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления и идентификатора элемента управления.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Сопоставляет WM_NOTIFY сообщение с функцией обработчика на основе идентификатора элемента управления.|
|[NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler)|Сопоставляет WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления и непрерывного диапазона идентификаторов элементов управления.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Сопоставляет WM_NOTIFY сообщение с функцией обработчика на основе непрерывного диапазона идентификаторов элементов управления.|
|[REFLECT_NOTIFICATIONS](#reflect_notifications)|Отображает сообщения уведомления обратно в окно, которое их отправило.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе кода уведомления.|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе кода уведомления и идентификатора элемента меню, элемента управления или ускорителя.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе идентификатора элемента меню, элемента управления или ускорителя.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе кода уведомления и непрерывного диапазона идентификаторов элементов управления.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе непрерывного диапазона идентификаторов элементов управления.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления и идентификатора элемента управления.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе идентификатора элемента управления.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления и непрерывного диапазона идентификаторов элементов управления.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе непрерывного диапазона идентификаторов элементов управления.|

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="alt_msg_map"></a><a name="alt_msg_map"></a> ALT_MSG_MAP

Помечает начало альтернативной схемы сообщения.

```
ALT_MSG_MAP(msgMapID)
```

### <a name="parameters"></a>Параметры

*мсгмапид*<br/>
окне Идентификатор схемы сообщения.

### <a name="remarks"></a>Примечания

ATL идентифицирует каждую карту сообщений по числу. Схема сообщений по умолчанию (объявленная с помощью макроса BEGIN_MSG_MAP) определяется значением 0. Альтернативная схема сообщения определяется *мсгмапид*.

Схемы сообщений используются для обработки сообщений, отправляемых в окно. Например, [кконтаинедвиндов](../../atl/reference/ccontainedwindowt-class.md) позволяет указать идентификатор схемы сообщений в содержащем объекте. [Кконтаинедвиндов:: WindowProc](ccontainedwindowt-class.md#windowproc) использует эту схему сообщений для направления сообщений в окне в соответствующую функцию обработчика или в другую схему сообщений. Список макросов, объявляющих функции обработчика, см. в разделе [BEGIN_MSG_MAP](#begin_msg_map).

Всегда начинать схему сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные схемы сообщений.

Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Обратите внимание, что всегда существует только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="example"></a>Пример

В следующем примере показана схема сообщений по умолчанию и одна альтернативная схема сообщений, каждая из которых содержит одну функцию обработчика:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

В следующем примере показаны две альтернативные схемы сообщений. Схема сообщений по умолчанию пуста.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="begin_msg_map"></a><a name="begin_msg_map"></a> BEGIN_MSG_MAP

Помечает начало схемы сообщения по умолчанию.

```
BEGIN_MSG_MAP(theClass)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
окне Имя класса, содержащего схему сообщений.

### <a name="remarks"></a>Примечания

[Квиндовимпл:: WindowProc](cwindowimpl-class.md#windowproc) использует схему сообщений по умолчанию для обработки сообщений, отправляемых в окно. Схема сообщений направляет сообщения либо в соответствующую функцию обработчика, либо на другую схему сообщений.

Следующие макросы сопоставляют сообщение с функцией обработчика. Эта функция должна быть определена в *секласс*.

|Макрос|Описание|
|-----------|-----------------|
|[MESSAGE_HANDLER](#message_handler)|Сопоставляет сообщение Windows с функцией обработчика.|
|[MESSAGE_RANGE_HANDLER](#message_range_handler)|Сопоставляет непрерывный диапазон сообщений Windows функции обработчика.|
|[COMMAND_HANDLER](#command_handler)|Сопоставляет WM_COMMAND сообщение с функцией обработчика на основе кода уведомления и идентификатора элемента меню, элемента управления или ускорителя.|
|[COMMAND_ID_HANDLER](#command_id_handler)|Сопоставляет WM_COMMAND сообщение с функцией обработчика на основе идентификатора элемента меню, элемента управления или ускорителя.|
|[COMMAND_CODE_HANDLER](#command_handler)|Сопоставляет WM_COMMAND сообщение с функцией обработчика на основе кода уведомления.|
|[COMMAND_RANGE_HANDLER](#command_range_handler)|Сопоставляет непрерывный диапазон WM_COMMAND сообщений функции обработчика на основе идентификатора элемента меню, элемента управления или ускорителя.|
|[NOTIFY_HANDLER](#notify_handler)|Сопоставляет WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления и идентификатора элемента управления.|
|[NOTIFY_ID_HANDLER](#notify_id_handler)|Сопоставляет WM_NOTIFY сообщение с функцией обработчика на основе идентификатора элемента управления.|
|[NOTIFY_CODE_HANDLER](#notify_code_handler)|Сопоставляет WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления.|
|[NOTIFY_RANGE_HANDLER](#notify_range_handler)|Сопоставляет непрерывный диапазон WM_NOTIFY сообщений функции обработчика на основе идентификатора элемента управления.|

Следующие макросы направляют сообщения в другую схему сообщений. Этот процесс называется "цепочка".

|Макрос|Описание|
|-----------|-----------------|
|[CHAIN_MSG_MAP](#chain_msg_map)|Цепочка для схемы сообщений по умолчанию в базовом классе.|
|[CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member)|Цепочка для схемы сообщений по умолчанию в члене данных класса.|
|[CHAIN_MSG_MAP_ALT](#chain_msg_map_alt)|Цепочка для альтернативной схемы сообщений в базовом классе.|
|[CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member)|Цепочка для альтернативной схемы сообщений в элементе данных класса.|
|[CHAIN_MSG_MAP_DYNAMIC](#chain_msg_map_dynamic)|Привязывает к схеме сообщений по умолчанию в другом классе во время выполнения.|

Следующие макросы направляют «отраженные» сообщения из родительского окна. Например, элемент управления обычно отправляет сообщения уведомления родительскому окну для обработки, но родительское окно может отразить сообщение обратно в элемент управления.

|Макрос|Описание|
|-----------|-----------------|
|[REFLECTED_COMMAND_HANDLER](#reflected_command_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе кода уведомления и идентификатора элемента меню, элемента управления или ускорителя.|
|[REFLECTED_COMMAND_ID_HANDLER](#reflected_command_id_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе идентификатора элемента меню, элемента управления или ускорителя.|
|[REFLECTED_COMMAND_CODE_HANDLER](#reflected_command_code_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе кода уведомления.|
|[REFLECTED_COMMAND_RANGE_HANDLER](#reflected_command_range_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе непрерывного диапазона идентификаторов элементов управления.|
|[REFLECTED_COMMAND_RANGE_CODE_HANDLER](#reflected_command_range_code_handler)|Сопоставляет отраженное WM_COMMAND сообщение с функцией обработчика на основе кода уведомления и непрерывного диапазона идентификаторов элементов управления.|
|[REFLECTED_NOTIFY_HANDLER](#reflected_notify_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления и идентификатора элемента управления.|
|[REFLECTED_NOTIFY_ID_HANDLER](#reflected_notify_id_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе идентификатора элемента управления.|
|[REFLECTED_NOTIFY_CODE_HANDLER](#reflected_notify_code_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления.|
|[REFLECTED_NOTIFY_RANGE_HANDLER](#reflected_notify_range_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе непрерывного диапазона идентификаторов элементов управления.|
|[REFLECTED_NOTIFY_RANGE_CODE_HANDLER](#reflected_notify_range_code_handler)|Сопоставляет отраженное WM_NOTIFY сообщение с функцией обработчика на основе кода уведомления и непрерывного диапазона идентификаторов элементов управления.|

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#102](../../atl/codesnippet/cpp/message-map-macros-atl_3.h)]

Когда `CMyExtWindow` объект получает WM_PAINT сообщение, сообщение направляется в `CMyExtWindow::OnPaint` для фактической обработки. Если `OnPaint` указывает, что сообщение требует дальнейшей обработки, сообщение будет направлено на схему сообщений по умолчанию в `CMyBaseWindow` .

Кроме схемы сообщений по умолчанию, можно определить альтернативную схему сообщений с помощью [ALT_MSG_MAP](#alt_msg_map). Всегда начинать схему сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные схемы сообщений. В следующем примере показана схема сообщений по умолчанию и одна альтернативная схема сообщений, каждая из которых содержит одну функцию обработчика:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

В следующем примере показаны две альтернативные схемы сообщений. Схема сообщений по умолчанию пуста.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Обратите внимание, что всегда существует только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map_alt"></a><a name="chain_msg_map_alt"></a> CHAIN_MSG_MAP_ALT

Определяет запись в схеме сообщений.

```
CHAIN_MSG_MAP_ALT(theChainClass, msgMapID)
```

### <a name="parameters"></a>Параметры

*сечаинкласс*<br/>
окне Имя базового класса, содержащего схему сообщений.

*мсгмапид*<br/>
окне Идентификатор схемы сообщения.

### <a name="remarks"></a>Примечания

CHAIN_MSG_MAP_ALT направляет сообщения на альтернативную карту сообщений в базовом классе. Необходимо объявить эту альтернативную схему сообщений с помощью [ALT_MSG_MAP (мсгмапид)](#alt_msg_map). Чтобы направить сообщения в схему сообщений по умолчанию базового класса (объявленную с помощью [BEGIN_MSG_MAP](#begin_msg_map)), используйте CHAIN_MSG_MAP. Пример см. в разделе [CHAIN_MSG_MAP](#chain_msg_map).

> [!NOTE]
> Всегда начинать схему сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные схемы сообщений с помощью ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Каждая схема сообщений должна содержать только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map_alt_member"></a><a name="chain_msg_map_alt_member"></a> CHAIN_MSG_MAP_ALT_MEMBER

Определяет запись в схеме сообщений.

```
CHAIN_MSG_MAP_ALT_MEMBER(theChainMember, msgMapID)
```

### <a name="parameters"></a>Параметры

*сечаинмембер*<br/>
окне Имя элемента данных, содержащего схему сообщения.

*мсгмапид*<br/>
окне Идентификатор схемы сообщения.

### <a name="remarks"></a>Примечания

CHAIN_MSG_MAP_ALT_MEMBER направляет сообщения на альтернативную карту сообщений в элементе данных. Необходимо объявить эту альтернативную схему сообщений с помощью [ALT_MSG_MAP (мсгмапид)](#alt_msg_map). Чтобы направить сообщения в схему сообщений элемента данных по умолчанию (объявленную с помощью [BEGIN_MSG_MAP](#begin_msg_map)), используйте CHAIN_MSG_MAP_MEMBER. Пример см. в разделе [CHAIN_MSG_MAP_MEMBER](#chain_msg_map_member).

> [!NOTE]
> Всегда начинать схему сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные схемы сообщений с помощью ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Каждая схема сообщений должна содержать только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map"></a><a name="chain_msg_map"></a> CHAIN_MSG_MAP

Определяет запись в схеме сообщений.

```
CHAIN_MSG_MAP(theChainClass)
```

### <a name="parameters"></a>Параметры

*сечаинкласс*<br/>
окне Имя базового класса, содержащего схему сообщений.

### <a name="remarks"></a>Примечания

CHAIN_MSG_MAP направляет сообщения в схему сообщений по умолчанию базового класса (объявленную с помощью [BEGIN_MSG_MAP](#begin_msg_map)). Чтобы направить сообщения на альтернативную карту сообщений базового класса (объявленной с помощью [ALT_MSG_MAP](#alt_msg_map)), используйте [CHAIN_MSG_MAP_ALT](#chain_msg_map_alt).

> [!NOTE]
> Всегда начинать схему сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные схемы сообщений с помощью ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Каждая схема сообщений должна содержать только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#107](../../atl/codesnippet/cpp/message-map-macros-atl_4.h)]

В этом примере показаны следующие примеры.

- Если процедура окна использует `CMyClass` схему сообщений по умолчанию и `OnPaint` не обрабатывает сообщение, сообщение перенаправляется в `CMyBaseClass` схему сообщений по умолчанию для обработки.

- Если в процедуре окна используется первая альтернативная схема сообщений в `CMyClass` , все сообщения перенаправляются в `CMyBaseClass` схему сообщений по умолчанию.

- Если процедура окна использует `CMyClass` вторую альтернативную схему сообщения и `OnChar` не обрабатывает сообщение, сообщение направляется на указанную альтернативную схему сообщения в `CMyBaseClass` . `CMyBaseClass` Эта схема сообщений должна быть объявлена с ALT_MSG_MAP (1).

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map_dynamic"></a><a name="chain_msg_map_dynamic"></a> CHAIN_MSG_MAP_DYNAMIC

Определяет запись в схеме сообщений.

```
CHAIN_MSG_MAP_DYNAMIC(dynaChainID)
```

### <a name="parameters"></a>Параметры

*диначаинид*<br/>
окне Уникальный идентификатор для схемы сообщений объекта.

### <a name="remarks"></a>Примечания

CHAIN_MSG_MAP_DYNAMIC направляет сообщения во время выполнения в схему сообщений по умолчанию в другом объекте. Объект и его схема сообщений связаны с *диначаинид*, определяемым с помощью [Кдинамикчаин:: сетчаинентри](cdynamicchain-class.md#setchainentry). Для использования CHAIN_MSG_MAP_DYNAMIC необходимо создать производный класс от `CDynamicChain` . Пример см. в обзоре [кдинамикчаин](../../atl/reference/cdynamicchain-class.md) .

> [!NOTE]
> Всегда начинать схему сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие альтернативные схемы сообщений с помощью ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Каждая схема сообщений должна содержать только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="chain_msg_map_member"></a><a name="chain_msg_map_member"></a> CHAIN_MSG_MAP_MEMBER

Определяет запись в схеме сообщений.

```
CHAIN_MSG_MAP_MEMBER(theChainMember)
```

### <a name="parameters"></a>Параметры

*сечаинмембер*<br/>
окне Имя элемента данных, содержащего схему сообщения.

### <a name="remarks"></a>Примечания

CHAIN_MSG_MAP_MEMBER направляет сообщения в схему сообщений элемента данных по умолчанию (объявленную с помощью [BEGIN_MSG_MAP](#begin_msg_map)). Чтобы направить сообщения на альтернативную карту сообщений элемента данных (объявленную с помощью [ALT_MSG_MAP](#alt_msg_map)), используйте [CHAIN_MSG_MAP_ALT_MEMBER](#chain_msg_map_alt_member).

> [!NOTE]
> Всегда начинать схему сообщений с BEGIN_MSG_MAP. Затем можно объявить последующие альтернативные схемы сообщений с помощью ALT_MSG_MAP. Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Каждая схема сообщений должна содержать только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#108](../../atl/codesnippet/cpp/message-map-macros-atl_5.h)]

В этом примере показаны следующие примеры.

- Если процедура окна использует `CMyClass` схему сообщений по умолчанию и `OnPaint` не обрабатывает сообщение, сообщение перенаправляется в `m_obj` схему сообщений по умолчанию для обработки.

- Если в процедуре окна используется первая альтернативная схема сообщений в `CMyClass` , все сообщения перенаправляются в `m_obj` схему сообщений по умолчанию.

- Если процедура окна использует `CMyClass` вторую альтернативную схему сообщения и `OnChar` не обрабатывает сообщение, сообщение направляется на указанную альтернативную схему сообщения `m_obj` . Класс `CMyContainedClass` должен объявлять эту схему сообщений ALT_MSG_MAP (1).

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_code_handler"></a><a name="command_code_handler"></a> COMMAND_CODE_HANDLER

Аналогичен [COMMAND_HANDLER](#command_handler), но сопоставляет [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение только на основе кода уведомления.

```
COMMAND_CODE_HANDLER(code, func)
```

### <a name="parameters"></a>Параметры

*code*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_handler"></a><a name="command_handler"></a> COMMAND_HANDLER

Определяет запись в схеме сообщений.

```
COMMAND_HANDLER(id, code, func)
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Идентификатор элемента меню, элемента управления или ускорителя.

*code*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="remarks"></a>Примечания

COMMAND_HANDLER сопоставляет [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение с указанной функцией обработчика на основе кода уведомления и идентификатора элемента управления. Пример:

[!code-cpp[NVC_ATL_Windowing#119](../../atl/codesnippet/cpp/message-map-macros-atl_6.h)]

Любая функция, указанная в макросе COMMAND_HANDLER, должна быть определена следующим образом:

`LRESULT CommandHandler(WORD wNotifyCode, WORD wID, HWND hWndCtl, BOOL& bHandled);`

`bHandled`Перед вызовом схема сообщения устанавливает значение true `CommandHandler` . Если `CommandHandler` не обрабатывает сообщение полностью, оно должно иметь значение `bHandled` false, чтобы указать, что сообщение нуждается в дальнейшей обработке.

> [!NOTE]
> Всегда начинать схему сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие альтернативные схемы сообщений с помощью [ALT_MSG_MAP](#alt_msg_map). Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Каждая схема сообщений должна содержать только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

В дополнение к COMMAND_HANDLER можно использовать [MESSAGE_HANDLER](#message_handler) для отображения WM_COMMAND сообщения без учета идентификатора или кода. В этом случае `MESSAGE_HANDLER(WM_COMMAND, OnHandlerFunction)` будет направлять все WM_COMMAND сообщения в `OnHandlerFunction` .

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_id_handler"></a><a name="command_id_handler"></a> COMMAND_ID_HANDLER

Аналогичен [COMMAND_HANDLER](#command_handler), но сопоставляет [WM_COMMAND](/windows/win32/menurc/wm-command) сообщение только на основе идентификатора элемента меню, элемента управления или ускорителя.

```
COMMAND_ID_HANDLER(id, func)
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Идентификатор элемента меню, элемента управления или ускорителя отправки сообщения.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_range_code_handler"></a><a name="command_range_code_handler"></a> COMMAND_RANGE_CODE_HANDLER

Аналогичен [COMMAND_RANGE_HANDLER](#command_range_handler), но сопоставляется [WM_COMMAND](/windows/win32/menurc/wm-command) сообщения с конкретным кодом уведомления из диапазона элементов управления в одну функцию обработчика.

```
COMMAND_RANGE_CODE_HANDLER(idFirst, idLast, code, func)
```

### <a name="parameters"></a>Параметры

*идфирст*<br/>
окне Помечает начало непрерывного диапазона идентификаторов элементов управления.

*идласт*<br/>
окне Помечает конец непрерывного диапазона идентификаторов элементов управления.

*code*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="remarks"></a>Примечания

Этот диапазон основан на идентификаторе элемента меню, элемента управления или ускорителе отправки сообщения.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="command_range_handler"></a><a name="command_range_handler"></a> COMMAND_RANGE_HANDLER

Аналогичен [COMMAND_HANDLER](#command_handler), но сопоставляет сообщения [WM_COMMAND](/windows/win32/menurc/wm-command) из диапазона элементов управления с одной функцией обработчика.

```
COMMAND_RANGE_HANDLER( idFirst, idLast, func)
```

### <a name="parameters"></a>Параметры

*идфирст*<br/>
окне Помечает начало непрерывного диапазона идентификаторов элементов управления.

*идласт*<br/>
окне Помечает конец непрерывного диапазона идентификаторов элементов управления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="remarks"></a>Примечания

Этот диапазон основан на идентификаторе элемента меню, элемента управления или ускорителе отправки сообщения.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="declare_empty_msg_map"></a><a name="declare_empty_msg_map"></a> DECLARE_EMPTY_MSG_MAP

Объявляет пустую схему сообщения.

```
DECLARE_EMPTY_MSG_MAP()
```

### <a name="remarks"></a>Примечания

DECLARE_EMPTY_MSG_MAP — это удобный макрос, вызывающий макросы [BEGIN_MSG_MAP](#begin_msg_map) и [END_MSG_MAP](#end_msg_map) для создания пустой схемы сообщения:

[!code-cpp[NVC_ATL_Windowing#122](../../atl/codesnippet/cpp/message-map-macros-atl_7.h)]

## <a name="default_reflection_handler"></a><a name="default_reflection_handler"></a> DEFAULT_REFLECTION_HANDLER

Предоставляет обработчик по умолчанию для дочернего окна (элемента управления), который получит отраженные сообщения; обработчик будет правильно передавать необработанные сообщения в `DefWindowProc` .

```
DEFAULT_REFLECTION_HANDLER()
```

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="end_msg_map"></a><a name="end_msg_map"></a> END_MSG_MAP

Помечает конец схемы сообщения.

```
END_MSG_MAP()
```

### <a name="remarks"></a>Примечания

Для пометки начала схемы сообщения всегда используйте макрос [BEGIN_MSG_MAP](#begin_msg_map) . Используйте [ALT_MSG_MAP](#alt_msg_map) для объявления последующих альтернативных схем сообщений.

Обратите внимание, что всегда существует только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="example"></a>Пример

В следующем примере показана схема сообщений по умолчанию и одна альтернативная схема сообщений, каждая из которых содержит одну функцию обработчика:

[!code-cpp[NVC_ATL_Windowing#98](../../atl/codesnippet/cpp/message-map-macros-atl_1.h)]

В следующем примере показаны две альтернативные схемы сообщений. Схема сообщений по умолчанию пуста.

[!code-cpp[NVC_ATL_Windowing#99](../../atl/codesnippet/cpp/message-map-macros-atl_2.h)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="forward_notifications"></a><a name="forward_notifications"></a> FORWARD_NOTIFICATIONS

Пересылает сообщения уведомления родительскому окну.

```
FORWARD_NOTIFICATIONS()
```

### <a name="remarks"></a>Примечания

Укажите этот макрос в составе схемы сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="message_handler"></a><a name="message_handler"></a> MESSAGE_HANDLER

Определяет запись в схеме сообщений.

```
MESSAGE_HANDLER( msg, func )
```

### <a name="parameters"></a>Параметры

*msg*<br/>
окне Сообщение Windows.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="remarks"></a>Примечания

MESSAGE_HANDLER сопоставляет сообщение Windows с указанной функцией обработчика.

Любая функция, указанная в макросе MESSAGE_HANDLER, должна быть определена следующим образом:

`LRESULT MessageHandler(UINT uMsg, WPARAM wParam, LPARAM lParam, BOOL& bHandled);`

`bHandled`Перед вызовом схема сообщения устанавливает значение true `MessageHandler` . Если `MessageHandler` не обрабатывает сообщение полностью, оно должно иметь значение `bHandled` false, чтобы указать, что сообщение нуждается в дальнейшей обработке.

> [!NOTE]
> Всегда начинать схему сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие альтернативные схемы сообщений с помощью [ALT_MSG_MAP](#alt_msg_map). Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Каждая схема сообщений должна содержать только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

В дополнение к MESSAGE_HANDLER можно использовать [COMMAND_HANDLER](#command_handler) и [NOTIFY_HANDLER](#notify_handler) , чтобы сопоставлять [WM_COMMAND](/windows/win32/menurc/wm-command) и [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщения соответственно.

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#129](../../atl/codesnippet/cpp/message-map-macros-atl_8.h)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="message_range_handler"></a><a name="message_range_handler"></a> MESSAGE_RANGE_HANDLER

Аналогичен [MESSAGE_HANDLER](#message_handler), но сопоставляет диапазон сообщений Windows с одной функцией обработчика.

```
MESSAGE_RANGE_HANDLER( msgFirst, msgLast, func )
```

### <a name="parameters"></a>Параметры

*мсгфирст*<br/>
окне Помечает начало непрерывного диапазона сообщений.

*мсгласт*<br/>
окне Помечает конец непрерывного диапазона сообщений.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_code_handler"></a><a name="notify_code_handler"></a> NOTIFY_CODE_HANDLER

Аналогичен [NOTIFY_HANDLER](#notify_handler), но сопоставляет [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение только на основе кода уведомления.

```
NOTIFY_CODE_HANDLER(cd, func)
```

### <a name="parameters"></a>Параметры

*cd*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_handler"></a><a name="notify_handler"></a> NOTIFY_HANDLER

Определяет запись в схеме сообщений.

```
NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Идентификатор элемента управления, отправляющего сообщение.

*cd*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="remarks"></a>Примечания

NOTIFY_HANDLER сопоставляет [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение с указанной функцией обработчика на основе кода уведомления и идентификатора элемента управления.

Любая функция, указанная в макросе NOTIFY_HANDLER, должна быть определена следующим образом:

`LRESULT NotifyHandler(int idCtrl, LPNMHDR pnmh, BOOL& bHandled);`

`bHandled`Перед вызовом схема сообщения устанавливает значение true `NotifyHandler` . Если `NotifyHandler` не обрабатывает сообщение полностью, оно должно иметь значение `bHandled` false, чтобы указать, что сообщение нуждается в дальнейшей обработке.

> [!NOTE]
> Всегда начинать схему сообщений с [BEGIN_MSG_MAP](#begin_msg_map). Затем можно объявить последующие альтернативные схемы сообщений с помощью [ALT_MSG_MAP](#alt_msg_map). Макрос [END_MSG_MAP](#end_msg_map) отмечает конец схемы сообщения. Каждая схема сообщений должна содержать только один экземпляр BEGIN_MSG_MAP и END_MSG_MAP.

В дополнение к NOTIFY_HANDLER можно использовать [MESSAGE_HANDLER](#message_handler) для отображения WM_NOTIFY сообщения без учета идентификатора или кода. В этом случае `MESSAGE_HANDLER(WM_NOTIFY, OnHandlerFunction)` будет направлять все WM_NOTIFY сообщения в `OnHandlerFunction` .

Дополнительные сведения об использовании карт сообщений в ATL см. в разделе [схемы сообщений](../../atl/message-maps-atl.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#130](../../atl/codesnippet/cpp/message-map-macros-atl_9.h)]

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_id_handler"></a><a name="notify_id_handler"></a> NOTIFY_ID_HANDLER

Аналогичен [NOTIFY_HANDLER](#notify_handler), но сопоставляет [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщение только на основе идентификатора элемента управления.

```
NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Идентификатор элемента управления, отправляющего сообщение.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_range_code_handler"></a><a name="notify_range_code_handler"></a> NOTIFY_RANGE_CODE_HANDLER

Аналогичен [NOTIFY_RANGE_HANDLER](#notify_range_handler), но сопоставляется [WM_NOTIFY](/windows/win32/controls/wm-notify) сообщения с конкретным кодом уведомления из диапазона элементов управления в одну функцию обработчика.

```
NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Параметры

*идфирст*<br/>
окне Помечает начало непрерывного диапазона идентификаторов элементов управления.

*идласт*<br/>
окне Помечает конец непрерывного диапазона идентификаторов элементов управления.

*cd*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="remarks"></a>Примечания

Этот диапазон основан на идентификаторе элемента управления, отправляющего сообщение.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="notify_range_handler"></a><a name="notify_range_handler"></a> NOTIFY_RANGE_HANDLER

Аналогичен [NOTIFY_HANDLER](#notify_handler), но сопоставляет сообщения [WM_NOTIFY](/windows/win32/controls/wm-notify) из диапазона элементов управления с одной функцией обработчика.

```
NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Параметры

*идфирст*<br/>
окне Помечает начало непрерывного диапазона идентификаторов элементов управления.

*идласт*<br/>
окне Помечает конец непрерывного диапазона идентификаторов элементов управления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="remarks"></a>Примечания

Этот диапазон основан на идентификаторе элемента управления, отправляющего сообщение.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflect_notifications"></a><a name="reflect_notifications"></a> REFLECT_NOTIFICATIONS

Отображает сообщения уведомления обратно в дочернее окно (элемент управления), которое их отправило.

```
REFLECT_NOTIFICATIONS()
```

### <a name="remarks"></a>Примечания

Укажите этот макрос как часть схемы сообщения родительского окна.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_code_handler"></a><a name="reflected_command_code_handler"></a> REFLECTED_COMMAND_CODE_HANDLER

Аналогичен [COMMAND_CODE_HANDLER](#command_code_handler), но отображает команды, отображаемые в родительском окне.

```
REFLECTED_COMMAND_CODE_HANDLER( code, func )
```

### <a name="parameters"></a>Параметры

*code*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_handler"></a><a name="reflected_command_handler"></a> REFLECTED_COMMAND_HANDLER

Аналогичен [COMMAND_HANDLER](#command_handler), но отображает команды, отображаемые в родительском окне.

```
REFLECTED_COMMAND_HANDLER( id, code, func )
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Идентификатор элемента меню, элемента управления или ускорителя.

*code*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_id_handler"></a><a name="reflected_command_id_handler"></a> REFLECTED_COMMAND_ID_HANDLER

Аналогичен [COMMAND_ID_HANDLER](#command_id_handler), но отображает команды, отображаемые в родительском окне.

```
REFLECTED_COMMAND_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Идентификатор элемента меню, элемента управления или ускорителя.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_range_code_handler"></a><a name="reflected_command_range_code_handler"></a> REFLECTED_COMMAND_RANGE_CODE_HANDLER

Аналогичен [COMMAND_RANGE_CODE_HANDLER](#command_range_code_handler), но отображает команды, отображаемые в родительском окне.

```
REFLECTED_COMMAND_RANGE_CODE_HANDLER( idFirst, idLast, code, func )
```

### <a name="parameters"></a>Параметры

*идфирст*<br/>
окне Помечает начало непрерывного диапазона идентификаторов элементов управления.

*идласт*<br/>
окне Помечает конец непрерывного диапазона идентификаторов элементов управления.

*code*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_command_range_handler"></a><a name="reflected_command_range_handler"></a> REFLECTED_COMMAND_RANGE_HANDLER

Аналогичен [COMMAND_RANGE_HANDLER](#command_range_handler), но отображает команды, отображаемые в родительском окне.

```
REFLECTED_COMMAND_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Параметры

*идфирст*<br/>
окне Помечает начало непрерывного диапазона идентификаторов элементов управления.

*идласт*<br/>
окне Помечает конец непрерывного диапазона идентификаторов элементов управления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_code_handler"></a><a name="reflected_notify_code_handler"></a> REFLECTED_NOTIFY_CODE_HANDLER

Аналогичен [NOTIFY_CODE_HANDLER](#notify_code_handler), но сопоставляет уведомления, отраженные в родительском окне.

```
REFLECTED_NOTIFY_CODE_HANDLER_EX( cd, func )
```

### <a name="parameters"></a>Параметры

*cd*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_handler"></a><a name="reflected_notify_handler"></a> REFLECTED_NOTIFY_HANDLER

Аналогичен [NOTIFY_HANDLER](#notify_handler), но сопоставляет уведомления, отраженные в родительском окне.

```
REFLECTED_NOTIFY_HANDLER( id, cd, func )
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Идентификатор элемента меню, элемента управления или ускорителя.

*cd*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_id_handler"></a><a name="reflected_notify_id_handler"></a> REFLECTED_NOTIFY_ID_HANDLER

Аналогичен [NOTIFY_ID_HANDLER](#notify_id_handler), но сопоставляет уведомления, отраженные в родительском окне.

```
REFLECTED_NOTIFY_ID_HANDLER( id, func )
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
окне Идентификатор элемента меню, элемента управления или ускорителя.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_range_code_handler"></a><a name="reflected_notify_range_code_handler"></a> REFLECTED_NOTIFY_RANGE_CODE_HANDLER

Аналогичен [NOTIFY_RANGE_CODE_HANDLER](#notify_range_code_handler), но сопоставляет уведомления, отраженные в родительском окне.

```
REFLECTED_NOTIFY_RANGE_CODE_HANDLER( idFirst, idLast, cd, func )
```

### <a name="parameters"></a>Параметры

*идфирст*<br/>
окне Помечает начало непрерывного диапазона идентификаторов элементов управления.

*идласт*<br/>
окне Помечает конец непрерывного диапазона идентификаторов элементов управления.

*cd*<br/>
окне Код уведомления.

*func*<br/>
окне Имя функции обработчика сообщений.

### <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="reflected_notify_range_handler"></a><a name="reflected_notify_range_handler"></a> REFLECTED_NOTIFY_RANGE_HANDLER

Аналогичен [NOTIFY_RANGE_HANDLER](#notify_range_handler), но сопоставляет уведомления, отраженные в родительском окне.

```
REFLECTED_NOTIFY_RANGE_HANDLER( idFirst, idLast, func )
```

### <a name="parameters"></a>Параметры

*идфирст*<br/>
окне Помечает начало непрерывного диапазона идентификаторов элементов управления.

*идласт*<br/>
окне Помечает конец непрерывного диапазона идентификаторов элементов управления.

*func*<br/>
окне Имя функции обработчика сообщений.

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
