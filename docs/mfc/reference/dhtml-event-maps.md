---
title: Схемы событий DHTML
ms.date: 11/04/2016
f1_keywords:
- vc.macros.shared
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
ms.openlocfilehash: 099a08298357d99a3d09ed6fc1209d463f6a4526
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837428"
---
# <a name="dhtml-event-maps"></a>Схемы событий DHTML

Для управления событиями DHTML можно использовать следующие макросы.

## <a name="dhtml-event-map-macros"></a>Макросы схемы событий DHTML

Следующие макросы можно использовать для управления событиями DHTML в классах, производных от [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md).

|Имя|Описание|
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|Помечает начало схемы событий DHTML.|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|Помечает начало схемы событий DHTML.|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|Объявляет таблицу событий DHTML.|
|[DHTML_EVENT](#dhtml_event)|Используется для управления событием на уровне документа для одного HTML-элемента.|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Используется для работы с событием, запущенным элементом управления ActiveX.|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Используется для управления событием на уровне документа для всех HTML-элементов с определенным классом CSS.|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Используется для управления событием на уровне элемента.|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|Используется для обработки `onafterupdate` события из HTML-элемента.|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|Используется для обработки `onbeforeupdate` события из HTML-элемента.|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|Используется для обработки `onblur` события из HTML-элемента.|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|Используется для обработки `onchange` события из HTML-элемента.|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|Используется для обработки `onclick` события из HTML-элемента.|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|Используется для обработки `ondataavailable` события из HTML-элемента.|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|Используется для обработки `ondatasetchanged` события из HTML-элемента.|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|Используется для обработки `ondatasetcomplete` события из HTML-элемента.|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|Используется для обработки `ondblclick` события из HTML-элемента.|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|Используется для обработки `ondragstart` события из HTML-элемента.|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|Используется для обработки `onerrorupdate` события из HTML-элемента.|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|Используется для обработки `onfilterchange` события из HTML-элемента.|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|Используется для обработки `onfocus` события из HTML-элемента.|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|Используется для обработки `onhelp` события из HTML-элемента.|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|Используется для обработки `onkeydown` события из HTML-элемента.|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|Используется для обработки `onkeypress` события из HTML-элемента.|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|Используется для обработки `onkeyup` события из HTML-элемента.|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|Используется для обработки `onmousedown` события из HTML-элемента.|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|Используется для обработки `onmousemove` события из HTML-элемента.|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|Используется для обработки `onmouseout` события из HTML-элемента.|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|Используется для обработки `onmouseover` события из HTML-элемента.|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|Используется для обработки `onmouseup` события из HTML-элемента.|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|Используется для обработки `onresize` события из HTML-элемента.|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|Используется для обработки `onrowenter` события из HTML-элемента.|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|Используется для обработки `onrowexit` события из HTML-элемента.|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|Используется для обработки `onselectstart` события из HTML-элемента.|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Используется для управления событием на уровне документа для всех элементов с определенным HTML-тегом.|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|Помечает конец схемы событий DHTML.|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|Помечает конец схемы событий DHTML. |

## <a name="url-event-map-macros"></a>Макросы схемы событий URL-адреса

Следующие макросы можно использовать для управления событиями DHTML в классах, производных от [кмултипажедхтмлдиалог](../../mfc/reference/cmultipagedhtmldialog-class.md).

|Имя|Описание|
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Помечает начало многостраничной схемы событий DHTML и URL.|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Помечает начало внедренной схемы событий DHTML.|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Помечает начало таблицы входа события URL-адреса.|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Объявляет схему сопоставлений DHTML и URL-адреса многостраничных событий.|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Помечает конец многостраничной схемы событий DHTML и URL.|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Помечает конец внедренной схемы событий DHTML.|
|[END_URL_ENTRIES](#end_url_entries)|Помечает конец таблицы входа события URL-адреса.|
|[URL_EVENT_ENTRY](#url_event_entry)|Сопоставляет URL-адрес или ресурс HTML со страницей многостраничного диалогового окна.|

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="begin_dhtml_event_map"></a><a name="begin_dhtml_event_map"></a> BEGIN_DHTML_EVENT_MAP

Помечает начало схемы событий DHTML при помещении в исходный файл для класса, определенного параметром `className` .

```cpp
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего таблицу событий DHTML. Этот класс должен прямо или косвенно наследовать от [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включать макрос [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) в его определение класса.

### <a name="remarks"></a>Примечания

Добавьте в класс таблицу сопоставлений DHTML, чтобы предоставить сведения `CDHtmlDialog` , которые можно использовать для маршрутизации событий, инициированных ЭЛЕМЕНТАМИ HTML или элементами управления ActiveX на веб-странице, в функции обработчика в классе.

Поместите макрос BEGIN_DHTML_EVENT_MAP в файл реализации класса (. cpp), а затем DHTML_EVENT макросы для событий, которые класс обрабатывает (например, DHTML_EVENT_ONMOUSEOVER для событий onmouseover). Используйте макрос [END_DHTML_EVENT_MAP](#end_dhtml_event_map) , чтобы отметить окончание схемы событий. Эти макросы реализуют следующую функцию:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="begin_dhtml_event_map_inline"></a><a name="begin_dhtml_event_map_inline"></a> BEGIN_DHTML_EVENT_MAP_INLINE

Помечает начало таблицы событий DHTML в определении класса для *className*.

```cpp
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего таблицу событий DHTML. Этот класс должен прямо или косвенно наследовать от [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включать макрос [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) в его определение класса.

### <a name="remarks"></a>Примечания

Добавьте в класс таблицу сопоставлений DHTML, чтобы предоставить сведения `CDHtmlDialog` , которые можно использовать для маршрутизации событий, инициированных ЭЛЕМЕНТАМИ HTML или элементами управления ActiveX на веб-странице, в функции обработчика в классе.

Поместите макрос BEGIN_DHTML_EVENT_MAP в файл определения класса (.h), а затем DHTML_EVENT макросы для событий, которые класс обрабатывает (например, DHTML_EVENT_ONMOUSEOVER для событий onmouseover). Используйте макрос [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) , чтобы отметить окончание схемы событий. Эти макросы реализуют следующую функцию:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="declare_dhtml_event_map"></a><a name="declare_dhtml_event_map"></a> DECLARE_DHTML_EVENT_MAP

Объявляет таблицу событий DHTML в определении класса.

```cpp
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Примечания

Этот макрос используется в определении классов, производных от [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md).

Для реализации этой схемы используйте [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) или [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) .

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) объявляет следующую функцию:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event"></a><a name="dhtml_event"></a> DHTML_EVENT

Дескрипторы (на уровне документа) событие, определяемое *идентификатором DISPID* , порождено элементом HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор DISPID обрабатываемого события.

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который исследует событие, или значение NULL для управления событиями документа.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_axcontrol"></a><a name="dhtml_event_axcontrol"></a> DHTML_EVENT_AXCONTROL

Обрабатывает событие, определяемое *идентификатором DISPID* , запущенным элементом управления ActiveX, идентифицируемым *контролнаме*.

```cpp
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор диспетчеризации обрабатываемого события.

*контролнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML элемента управления, вызывающего событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_class"></a><a name="dhtml_event_class"></a> DHTML_EVENT_CLASS

Дескрипторы (на уровне документа) события, идентифицируемые *идентификатором DISPID* , порождены любым HTML-элементом с КЛАССом CSS, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор диспетчеризации обрабатываемого события.

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий класс CSS HTML-элементов, исполняющий событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_element"></a><a name="dhtml_event_element"></a> DHTML_EVENT_ELEMENT

Дескрипторы (в элементе, идентифицируемом *елемнаме*) — событие, определяемое *DISPID*.

```cpp
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор диспетчеризации обрабатываемого события.

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

Если этот макрос используется для управления событиями, не восходящей маршрутизацией, источником события будет элемент, идентифицируемый *елемнаме*.

Если этот макрос используется для управления событиями восходящей маршрутизации, элемент, идентифицируемый *елемнаме* , может не быть источником события (источником может быть любой элемент, содержащийся в *елемнаме*).

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onafterupdate"></a><a name="dhtml_event_onafterupdate"></a> DHTML_EVENT_ONAFTERUPDATE

Обрабатывает (на уровне документа) событие, `onafterupdate` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a> DHTML_EVENT_ONBEFOREUPDATE

Обрабатывает (на уровне документа) событие, `onbeforeupdate` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onblur"></a><a name="dhtml_event_onblur"></a> DHTML_EVENT_ONBLUR

Обрабатывает событие (на уровне элемента) `onblur` . Это событие с восходящей маршрутизацией.

```cpp
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onchange"></a><a name="dhtml_event_onchange"></a> DHTML_EVENT_ONCHANGE

Обрабатывает событие (на уровне элемента) `onchange` . Это событие с восходящей маршрутизацией.

```cpp
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onclick"></a><a name="dhtml_event_onclick"></a> DHTML_EVENT_ONCLICK

Обрабатывает (на уровне документа) событие, `onclick` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_ondataavailable"></a><a name="dhtml_event_ondataavailable"></a> DHTML_EVENT_ONDATAAVAILABLE

Обрабатывает (на уровне документа) событие, `ondataavailable` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_ondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a> DHTML_EVENT_ONDATASETCHANGED

Обрабатывает (на уровне документа) событие, `ondatasetchanged` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_ondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a> DHTML_EVENT_ONDATASETCOMPLETE

Обрабатывает (на уровне документа) событие, `ondatasetcomplete` созданное ЭЛЕМЕНТОМ HTML, определенным `elemName` .

```cpp
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_ondblclick"></a><a name="dhtml_event_ondblclick"></a> DHTML_EVENT_ONDBLCLICK

Обрабатывает (на уровне документа) событие, `ondblclick` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_ondragstart"></a><a name="dhtml_event_ondragstart"></a> DHTML_EVENT_ONDRAGSTART

Обрабатывает (на уровне документа) событие, `ondragstart` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a> DHTML_EVENT_ONERRORUPDATE

Обрабатывает (на уровне документа) событие, `onerrorupdate` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onfilterchange"></a><a name="dhtml_event_onfilterchange"></a> DHTML_EVENT_ONFILTERCHANGE

Обрабатывает (на уровне документа) событие, `onfilterchange` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onfocus"></a><a name="dhtml_event_onfocus"></a> DHTML_EVENT_ONFOCUS

Обрабатывает событие (на уровне элемента) `onfocus` . Это событие с восходящей маршрутизацией.

```cpp
DHTML_EVENT_ONFOCUS(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onhelp"></a><a name="dhtml_event_onhelp"></a> DHTML_EVENT_ONHELP

Обрабатывает (на уровне документа) событие, `onhelp` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONHELP(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onkeydown"></a><a name="dhtml_event_onkeydown"></a> DHTML_EVENT_ONKEYDOWN

Обрабатывает (на уровне документа) событие, `onkeydown` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onkeypress"></a><a name="dhtml_event_onkeypress"></a> DHTML_EVENT_ONKEYPRESS

Обрабатывает (на уровне документа) событие, `onkeypress` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onkeyup"></a><a name="dhtml_event_onkeyup"></a> DHTML_EVENT_ONKEYUP

Обрабатывает (на уровне документа) событие, `onkeyup` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONKEYUP(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onmousedown"></a><a name="dhtml_event_onmousedown"></a> DHTML_EVENT_ONMOUSEDOWN

Обрабатывает (на уровне документа) событие, `onmousedown` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onmousemove"></a><a name="dhtml_event_onmousemove"></a> DHTML_EVENT_ONMOUSEMOVE

Обрабатывает (на уровне документа) событие, `onmousemove` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onmouseout"></a><a name="dhtml_event_onmouseout"></a> DHTML_EVENT_ONMOUSEOUT

Обрабатывает (на уровне документа) событие, `onmouseout` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onmouseover"></a><a name="dhtml_event_onmouseover"></a> DHTML_EVENT_ONMOUSEOVER

Обрабатывает (на уровне документа) событие, `onmouseover` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onmouseup"></a><a name="dhtml_event_onmouseup"></a> DHTML_EVENT_ONMOUSEUP

Обрабатывает (на уровне документа) событие, `onmouseup` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onresize"></a><a name="dhtml_event_onresize"></a> DHTML_EVENT_ONRESIZE

Обрабатывает событие (на уровне элемента) `onresize` . Это событие с восходящей маршрутизацией.

```cpp
DHTML_EVENT_ONRESIZE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onrowenter"></a><a name="dhtml_event_onrowenter"></a> DHTML_EVENT_ONROWENTER

Обрабатывает (на уровне документа) событие, `onrowenter` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONROWENTER(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onrowexit"></a><a name="dhtml_event_onrowexit"></a> DHTML_EVENT_ONROWEXIT

Обрабатывает (на уровне документа) событие, `onrowexit` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_onselectstart"></a><a name="dhtml_event_onselectstart"></a> DHTML_EVENT_ONSELECTSTART

Обрабатывает (на уровне документа) событие, `onselectstart` созданное ЭЛЕМЕНТОМ HTML, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*елемнаме*<br/>
Объект ЛПКВСТР, содержащий идентификатор HTML-элемента, который содержит событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="dhtml_event_tag"></a><a name="dhtml_event_tag"></a> DHTML_EVENT_TAG

Дескрипторы (на уровне документа) события, идентифицируемые `dispid` любым HTML-элементом с HTML-тегом, идентифицируемым *елемнаме*.

```cpp
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор диспетчеризации обрабатываемого события.

*елемнаме*<br/>
Тег HTML HTML-элементов, искоторому событие.

*мемберфксн*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись в [таблицу событий DHTML](#begin_dhtml_event_map_inline) в своем классе.

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="end_dhtml_event_map"></a><a name="end_dhtml_event_map"></a> END_DHTML_EVENT_MAP

Помечает конец схемы событий DHTML.

```cpp
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Примечания

Должен использоваться в сочетании с [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="begin_dhtml_url_event_map"></a><a name="begin_dhtml_url_event_map"></a> BEGIN_DHTML_URL_EVENT_MAP

Запускает определение схемы событий DHTML и URL в многостраничном диалоговом окне.

```cpp
BEGIN_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>Примечания

Поставьте BEGIN_DHTML_URL_EVENT_MAP в файл реализации класса, производного от [кмултипажедхтмлдиалог](../../mfc/reference/cmultipagedhtmldialog-class.md). Используйте [встроенные сопоставления событий DHTML](#begin_embed_dhtml_event_map) и [записи URL-адресов](#begin_url_entries), а затем закройте его с помощью [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Включите макрос [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) в определение класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="begin_embed_dhtml_event_map"></a><a name="begin_embed_dhtml_event_map"></a> BEGIN_EMBED_DHTML_EVENT_MAP

Запускает определение встроенной схемы событий DHTML в многостраничном диалоговом окне.

```cpp
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карту событий. Этот класс должен быть прямо или косвенно производным от [кмултипажедхтмлдиалог](../../mfc/reference/cmultipagedhtmldialog-class.md). Внедренная схема событий DHTML должна находиться в [таблице событий DHTML и URL-адреса](#begin_dhtml_url_event_map).

*мапнаме*<br/>
Указывает страницу, в которой сопоставлены события. Это соответствует *мапнаме* в макросе [URL_EVENT_ENTRY](#url_event_entry) , который фактически определяет URL-адрес или HTML-ресурс.

### <a name="remarks"></a>Примечания

Поскольку многостраничное диалоговое окно DHTML состоит из нескольких HTML-страниц, каждая из которых может вызывать события DHTML, встроенные карты событий используются для сопоставления событий с обработчиками на каждой странице.

Сопоставление внедренных событий в таблице событий DHTML и URL состоит из BEGIN_EMBED_DHTML_EVENT_MAP макроса, за которым следует [DHTML_EVENT](#dhtml_event) макросы и макрос [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) .

Для каждой внедренной схемы событий требуется соответствующая [запись в URL-адресе](#url_event_entry) для соответствия *мапнаме* (указанной в BEGIN_EMBED_DHTML_EVENT_MAP) URL-адресу или ресурсу HTML.

### <a name="example"></a>Пример

См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="begin_url_entries"></a><a name="begin_url_entries"></a> BEGIN_URL_ENTRIES

Запускает определение схемы записи события URL-адреса в многостраничном диалоговом окне.

```cpp
BEGIN_URL_ENTRIES(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карту входа события URL-адреса. Этот класс должен быть прямо или косвенно производным от [кмултипажедхтмлдиалог](../../mfc/reference/cmultipagedhtmldialog-class.md). Схема записи события URL-адреса должна находиться в [таблице событий DHTML и URL-адреса](#begin_dhtml_url_event_map).

### <a name="remarks"></a>Примечания

Поскольку многостраничное диалоговое окно DHTML состоит из нескольких страниц HTML, для сопоставления URL-адресов или ресурсов HTML с соответствующими [внедренными картами событий DHTML](#begin_embed_dhtml_event_map)используются записи событий URL-адресов. Помещайте URL_EVENT_ENTRY макросы между BEGIN_URL_ENTRIES и [END_URL_ENTRIES](#end_url_entries) макросами.

### <a name="example"></a>Пример

См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="declare_dhtml_url_event_map"></a><a name="declare_dhtml_url_event_map"></a> DECLARE_DHTML_URL_EVENT_MAP

Объявляет карту событий DHTML и URL в определении класса.

```cpp
DECLARE_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>Примечания

Этот макрос используется в определении классов, производных от [кмултипажедхтмлдиалог](../../mfc/reference/cmultipagedhtmldialog-class.md).

Сопоставление событий DHTML и URL-адресов содержит [внедренные сопоставления событий DHTML](#begin_embed_dhtml_event_map) и [записи событий URL-адресов](#begin_url_entries) для сопоставления событий DHTML с обработчиками для отдельных страниц. Для реализации этой схемы используйте [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) .

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="end_dhtml_url_event_map"></a><a name="end_dhtml_url_event_map"></a> END_DHTML_URL_EVENT_MAP

Помечает окончание схемы событий DHTML и URL.

```cpp
END_DHTML_URL_EVENT_MAP(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карту событий. Этот класс должен быть прямо или косвенно производным от [кмултипажедхтмлдиалог](../../mfc/reference/cmultipagedhtmldialog-class.md). Он должен соответствовать *className* в соответствующем макросе [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) .

### <a name="example"></a>Пример

См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="end_embed_dhtml_event_map"></a><a name="end_embed_dhtml_event_map"></a> END_EMBED_DHTML_EVENT_MAP

Помечает конец внедренной схемы событий DHTML.

```cpp
END_EMBED_DHTML_EVENT_MAP()
```

### <a name="example"></a>Пример

См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="end_url_entries"></a><a name="end_url_entries"></a> END_URL_ENTRIES

Помечает конец таблицы входа события URL-адреса.

```cpp
END_URL_ENTRIES()
```

### <a name="example"></a>Пример

См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="url_event_entry"></a><a name="url_event_entry"></a> URL_EVENT_ENTRY

Сопоставляет URL-адрес или ресурс HTML со страницей многостраничного диалогового окна.

```cpp
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карту входа события URL-адреса. Этот класс должен быть прямо или косвенно производным от [кмултипажедхтмлдиалог](../../mfc/reference/cmultipagedhtmldialog-class.md). Схема записи события URL-адреса должна находиться в [таблице событий DHTML и URL-адреса](#begin_dhtml_url_event_map).

*url*<br/>
URL-адрес или ресурс HTML для страницы.

*мапнаме*<br/>
Указывает страницу, URL-адрес которой является *URL*. Это соответствует *мапнаме* в макросе [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) , который сопоставляет события на этой странице.

### <a name="remarks"></a>Примечания

Если страница является ресурсом HTML, *URL-адрес* должен представлять собой строковое представление идентификационного номера ресурса (то есть "123", а не 123 или ID_HTMLRES1).

Идентификатор страницы, *мапнаме*, — это произвольный символ, используемый для связывания встроенных сопоставлений событий DHTML с картами входа событий URL-адресов. Она ограничена областью действия для отображения DHTML и URL-адреса.

### <a name="example"></a>Пример

См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** афксдхтмл.h

## <a name="end_dhtml_event_map_inline"></a><a name="end_dhtml_event_map_inline"></a> END_DHTML_EVENT_MAP_INLINE

Помечает конец схемы событий DHTML.

### <a name="syntax"></a>Синтаксис

```cpp
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>Примечания

Должен использоваться в сочетании с [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline).

### <a name="requirements"></a>Требования

**Заголовок:** афксдхтмл.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)
