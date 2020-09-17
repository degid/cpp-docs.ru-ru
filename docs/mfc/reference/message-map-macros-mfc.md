---
title: Макросы схемы сообщений (MFC)
ms.date: 03/27/2019
f1_keywords:
- AFXWIN/DECLARE_MESSAGE_MAP
- AFXWIN/BEGIN_MESSAGE_MAP
- AFXWIN/BEGIN_TEMPLATE_MESSAGE_MAP
- AFXWIN/END_MESSAGE_MAP
- AFXWIN/ON_COMMAND
- AFXWIN/ON_COMMAND_EX
- AFXWIN/ON_CONTROL
- AFXWIN/ON_MESSAGE
- AFXWIN/ON_OLECMD
- AFXWIN/ON_REGISTERED_MESSAGE
- AFXWIN/ON_REGISTERED_THREAD_MESSAGE
- AFXWIN/ON_THREAD_MESSAGE
- AFXWIN/ON_UPDATE_COMMAND_UI
- AFXWIN/ON_COMMAND_RANGE
- AFXWIN/ON_UPDATE_COMMAND_UI_RANGE
- AFXWIN/ON_CONTROL_RANGE
helpviewer_keywords:
- message map macros
- Windows messages [MFC], declaration
- demarcating Windows messages
- message maps [MFC], macros
- message maps [MFC], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
ms.openlocfilehash: 33b5d2eaefa11f9ccf6459aa05b4e24138731e80
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840275"
---
# <a name="message-map-macros-mfc"></a>Макросы схемы сообщений (MFC)

Для поддержки схем сообщений MFC предоставляет следующие макросы:

### <a name="message-map-declaration-and-demarcation-macros"></a>Объявление схемы сообщений и макросы разделительной

|Имя|Описание|
|-|-|
|[DECLARE_MESSAGE_MAP](#declare_message_map)|Объявляет, что схема сообщений будет использоваться в классе для преобразования сообщений в функции (необходимо использовать в объявлении класса).|
|[BEGIN_MESSAGE_MAP](#begin_message_map)|Начинает определение схемы сообщения (необходимо использовать в реализации класса).|
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_message_map)|Начинает определение схемы сообщений для типа класса, содержащего один аргумент шаблона. |
|[END_MESSAGE_MAP](#end_message_map)|Завершает определение схемы сообщения (необходимо использовать в реализации класса).|

### <a name="message-mapping-macros"></a>Макросы сопоставления сообщений

|Имя|Описание|
|-|-|
|[ON_COMMAND](#on_command)|Указывает, какая функция будет выполнять обработку указанного сообщения команды.|
|[ON_COMMAND_EX](#on_command_ex)|Указывает, какая функция будет выполнять обработку указанного сообщения команды.|
|[ON_CONTROL](#on_control)|Указывает, какая функция будет выполнять обработку указанного сообщения уведомления об элементе управления.|
|[ON_MESSAGE](#on_message)|Указывает, какая функция будет выполнять обработку определяемого пользователем сообщения.|
|[ON_OLECMD](#on_olecmd)|Указывает, какая функция будет выполнять команду меню из DocObject или ее контейнера.|
|[ON_REGISTERED_MESSAGE](#on_registered_message)|Указывает, какая функция будет выполнять обработку зарегистрированного определяемого пользователем сообщения.|
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|Указывает, какая функция будет обрабатывает зарегистрированное пользовательское сообщение при наличии `CWinThread` класса.|
|[ON_THREAD_MESSAGE](#on_thread_message)|Указывает, какая функция будет обрабатывает определяемое пользователем сообщение при наличии `CWinThread` класса.|
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|Указывает, какая функция будет выполнять обработку указанного сообщения команды обновления пользовательского интерфейса.|

### <a name="message-map-range-macros"></a>Макросы диапазона схемы сообщения

|Имя|Описание|
|-|-|
|[ON_COMMAND_RANGE](#on_command_range)|Указывает, какая функция будет поддерживать диапазон идентификаторов команд, указанных в первых двух параметрах макроса.|
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|Указывает, какой обработчик обновлений будет выполнять в макросе диапазон идентификаторов команд, указанный в первых двух параметрах.|
|[ON_CONTROL_RANGE](#on_control_range)|Указывает, какая функция будет выполнять обработку уведомлений из диапазона идентификаторов элементов управления, указанных во втором и третьем параметрах макроса. Первый параметр — это сообщение уведомления элемента управления, например BN_CLICKED.|

Дополнительные сведения о схемах сообщений, объявлениях и макросах разделительной, а также о макросах сопоставления сообщений см. в разделах [схемы сообщений](../../mfc/reference/message-maps-mfc.md) и [Обработка сообщений и сопоставление](../../mfc/message-handling-and-mapping.md). Дополнительные сведения о диапазонах карт сообщений см. в разделе [обработчики для диапазонов карт сообщений](../../mfc/handlers-for-message-map-ranges.md).

## <a name="begin_message_map"></a><a name="begin_message_map"></a> BEGIN_MESSAGE_MAP

Начинает определение схемы сообщений.

### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_MESSAGE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Указывает имя класса, для которого сопоставлено сообщение.

*baseClass*<br/>
Задает имя базового класса *секласс*.

### <a name="remarks"></a>Примечания

В файле реализации (. cpp), который определяет функции-члены для класса, запустите схему сообщений с помощью макроса BEGIN_MESSAGE_MAP, добавьте записи макросов для каждой функции обработчика сообщений и завершите схему сообщений с помощью макроса END_MESSAGE_MAP.

Дополнительные сведения о картах сообщений см. в разделе [схемы сообщений](message-maps-mfc.md) .

### <a name="example"></a>Пример

```cpp
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="begin_template_message_map"></a><a name="begin_template_message_map"></a> BEGIN_TEMPLATE_MESSAGE_MAP

Начинает определение схемы сообщений для типа класса, содержащего один аргумент шаблона.

### <a name="syntax"></a>Синтаксис

```cpp
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Указывает имя класса, для которого сопоставлено сообщение.

*type_name*<br/>
Имя параметра шаблона, указанного для класса.

*baseClass*<br/>
Задает имя базового класса *секласс*.

### <a name="remarks"></a>Примечания

Этот макрос аналогичен макросу [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map) . Однако этот макрос предназначен для классов, содержащих один аргумент шаблона.

В разделе Реализация метода класса запустите схему сообщений с помощью макроса BEGIN_TEMPLATE_MESSAGE_MAP. Затем добавьте записи макросов для каждого метода обработчика сообщений, как в стандартной схеме сообщений. Как и в случае с макросом BEGIN_MESSAGE_MAP, завершите схему сообщений шаблона с помощью макроса [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map) .

Дополнительные сведения о реализации карт сообщений для классов шаблонов см. в разделе [инструкции. Создание схемы сообщений для класса шаблона](../how-to-create-a-message-map-for-a-template-class.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="declare_message_map"></a><a name="declare_message_map"></a> DECLARE_MESSAGE_MAP

Объявляет, что класс определяет схему сообщения. Каждый `CCmdTarget` производный класс в программе должен предоставить схему сообщений для работы с сообщениями.

### <a name="syntax"></a>Синтаксис

```cpp
DECLARE_MESSAGE_MAP( )
```

### <a name="remarks"></a>Примечания

Используйте макрос DECLARE_MESSAGE_MAP в конце объявления класса. Затем в cpp-файле, который определяет функции-члены для класса, используйте макрос BEGIN_MESSAGE_MAP, записи макросов для каждой функции обработчика сообщений и макрос END_MESSAGE_MAP.

> [!NOTE]
> При объявлении любого члена после DECLARE_MESSAGE_MAP необходимо указать для них новый тип доступа ( **`public`** , **`private`** или **`protected`** ).

Дополнительные сведения о картах сообщений и макросах DECLARE_MESSAGE_MAP см. в [разделах обработка сообщений и сопоставление](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Пример

```cpp
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
```

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="end_message_map"></a><a name="end_message_map"></a> END_MESSAGE_MAP

Завершает определение схемы сообщений.

### <a name="syntax"></a>Синтаксис

```cpp
END_MESSAGE_MAP( )
```

### <a name="remarks"></a>Примечания

Дополнительные сведения о картах сообщений и макросах END_MESSAGE_MAP см. в [разделах обработка сообщений и сопоставление](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="on_command"></a><a name="on_command"></a> ON_COMMAND

Этот макрос сопоставляет командное сообщение с функцией-членом.

### <a name="syntax"></a>Синтаксис

```cpp
ON_COMMAND( commandId, memberFxn )
```

### <a name="parameters"></a>Параметры

*commandId*<br/>
Идентификатор команды.

*мемберфксн*<br/>
Имя функции обработчика сообщений, с которой сопоставляется команда.

### <a name="remarks"></a>Примечания

Указывает, какая функция будет обработано сообщение команды от объекта пользовательского интерфейса команды, такого как элемент меню или кнопка панели инструментов.

Когда целевой объект Command получает сообщение Windows WM_COMMAND с указанным ИДЕНТИФИКАТОРом, ON_COMMAND вызовет функцию-член `memberFxn` для его обработки.

Используйте ON_COMMAND, чтобы связать одну команду с функцией-членом. Используйте [ON_COMMAND_RANGE](#on_command_range) , чтобы связать диапазон идентификаторов команд с одной функцией-членом. Только одна запись схемы сообщений может соответствовать указанному ИДЕНТИФИКАТОРу команды. То есть нельзя сопоставлять команду более чем с одним обработчиком. Дополнительные сведения и примеры см. в [разделах обработка сообщений и сопоставление](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Пример

```cpp
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_command_ex"></a><a name="on_command_ex"></a> ON_COMMAND_EX

Расширенная функция-член обработчика команд.

### <a name="syntax"></a>Синтаксис

```cpp
ON_COMMAND_EX(commandId, memberFxn);
```

### <a name="parameters"></a>Параметры

*commandId*<br/>
Идентификатор команды.

*мемберфксн*<br/>
Имя функции обработчика сообщений, с которой сопоставляется команда.

### <a name="remarks"></a>Примечания

Расширенная форма обработчиков командных сообщений доступна для расширенных применений. Макрос ON_COMMAND_EX используется для таких обработчиков сообщений и предоставляет надмножество функциональных возможностей [ON_COMMAND](message-map-macros-mfc.md#on_command) . Расширенные функции-члены обработчика команд принимают один параметр, UINT, содержащий идентификатор команды, и возвращают логическое значение. Чтобы указать, что команда была обработана, возвращаемое значение должно быть равно TRUE. в противном случае маршрутизация продолжит другие целевые объекты команды.

Дополнительные сведения см. в техническом примечании [TN006: сопоставления сообщений] tm006-Message-maps.md).

### <a name="requirements"></a>Требования

Заголовочный файл: afxmsg_.h

## <a name="on_control"></a><a name="on_control"></a> ON_CONTROL

Указывает, какая функция будет выполнять обработку сообщения уведомления пользовательского элемента управления.

### <a name="syntax"></a>Синтаксис

```cpp
ON_CONTROL( wNotifyCode, commandId, memberFxn )
```

### <a name="parameters"></a>Параметры

*wNotifyCode*<br/>
Код уведомления элемента управления.

*commandId*<br/>
Идентификатор команды.

*мемберфксн*<br/>
Имя функции обработчика сообщений, с которой сопоставляется команда.

### <a name="remarks"></a>Примечания

Сообщения управления уведомлениями отправляются из элемента управления в его родительское окно.

В схеме сообщений должен быть ровно один ON_CONTROL оператор макроса для каждого управляющего сообщения уведомления, которое должно быть сопоставлено функции обработчика сообщений.

Дополнительные сведения и примеры см. в [разделах обработка сообщений и сопоставление](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_message"></a><a name="on_message"></a> ON_MESSAGE

Указывает, какая функция будет выполнять обработку определяемого пользователем сообщения.

### <a name="syntax"></a>Синтаксис

```cpp
ON_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Параметры

*message*<br/>
Идентификатор сообщения.

*мемберфксн*<br/>
Имя функции обработчика сообщений, с которой сопоставлено сообщение.

Тип функции должен быть `afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)` .

### <a name="remarks"></a>Примечания

Определяемые пользователем сообщения — это любые сообщения, не являющиеся стандартными сообщениями Windows WM_MESSAGE. При выборе идентификатора сообщения необходимо использовать значения в диапазоне от WM_USER (0x0400) до 0x7FFF или WM_APP (0x8000) в 0xBFFF. Дополнительные сведения об идентификаторах сообщений см. в разделе [WM_APP](/windows/win32/winmsg/wm-app).

В схеме сообщений для каждого определяемого пользователем сообщения, которое должно быть сопоставлено функции обработчика сообщений, должен быть ровно один ON_MESSAGE макрос.

> [!NOTE]
> В дополнение к определяемым пользователем сообщениям ON_MESSAGE обрабатывает менее распространенные сообщения Windows. Дополнительные сведения см. в разделе [схемы сообщений](../../mfc/tn006-message-maps.md).

Дополнительные сведения и примеры см. в [разделах обработка сообщений и сопоставление](../../mfc/message-handling-and-mapping.md) и пользовательские [обработчики](user-defined-handlers.md) .

### <a name="example"></a>Пример

```cpp
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here.

   return 0;
}
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_olecmd"></a><a name="on_olecmd"></a> ON_OLECMD

Маршрутизирует команды через интерфейс диспетчеризации команд `IOleCommandTarget` .

### <a name="syntax"></a>Синтаксис

```cpp
ON_OLECMD( pguid, olecmdid, commandId )
```

### <a name="parameters"></a>Параметры

*пгуид*<br/>
Идентификатор группы команд, которой принадлежит команда. Для стандартной группы используйте значение NULL.

*олекмдид*<br/>
Идентификатор команды OLE.

*commandId*<br/>
ИДЕНТИФИКАТОР меню, идентификатор панели инструментов, идентификатор кнопки или другой идентификатор ресурса или объекта, выдавшего команду.

### <a name="remarks"></a>Примечания

`IOleCommandTarget` позволяет контейнеру получать команды, которые происходят в пользовательском интерфейсе DocObject, и позволяет контейнеру отправлять одни и те же команды (такие как New, Open, SaveAs и Print в меню файл, а также копировать, вставлять, отменять и т. д. в меню Правка) в DocObject.

`IOleCommandTarget` проще, чем OLE Automation `IDispatch` . `IOleCommandTarget` полностью опирается на стандартный набор команд, которые редко имеют аргументы, и сведения о типе не участвуют (безопасность типов также уменьшается для аргументов команды). Если нужно отправить команды с аргументами, используйте [колесервердок:: онексеколекмд](coleserverdoc-class.md#onexecolecmd).

`IOleCommandTarget`Стандартные команды меню реализованы в MFC в следующих макросах:

**ON_OLECMD_CLEARSELECTION ()**

Отправляет команду Edit Clear. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`

**ON_OLECMD_COPY ()**

Отправляет команду изменить копию. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`

**ON_OLECMD_CUT ()**

Отправляет команду "изменить Вырезать". Реализовано как:

`ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`

**ON_OLECMD_NEW ()**

Отправляет команду File New. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`

**ON_OLECMD_OPEN ()**

Отправляет команду открытия файла. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`

**ON_OLECMD_PAGESETUP ()**

Отправляет команду настройки страницы файла. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`

**ON_OLECMD_PASTE ()**

Отправляет команду "изменить вставку". Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`

**ON_OLECMD_PASTESPECIAL ()**

Отправляет команду Правка Специальная вставка. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`

**ON_OLECMD_PRINT ()**

Отправляет команду File Print. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`

**ON_OLECMD_PRINTPREVIEW ()**

Отправляет команду предварительного просмотра файла. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`

**ON_OLECMD_REDO ()**

Отправляет команду "изменить Повтор". Реализовано как:

`ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`

**ON_OLECMD_SAVE ()**

Отправляет команду сохранения файла. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`

**ON_OLECMD_SAVE_AS ()**

Отправляет команду "Сохранить как" в файле. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`

**ON_OLECMD_SAVE_COPY_AS ()**

Отправляет файл сохранить копию как команду. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`

**ON_OLECMD_SELECTALL ()**

Отправляет команду Изменить выделить все. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`

**ON_OLECMD_UNDO ()**

Отправляет команду Изменить отмену. Реализовано как:

`ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`

### <a name="requirements"></a>Требования

**Заголовок:** афксдокоб.h

## <a name="on_registered_message"></a><a name="on_registered_message"></a> ON_REGISTERED_MESSAGE

Функция Windows `RegisterWindowMessage` используется для определения нового сообщения окна, которое гарантированно уникально в пределах всей системы.

### <a name="syntax"></a>Синтаксис

```cpp
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Параметры

*нмессажевариабле*<br/>
Зарегистрированная переменная идентификатора сообщения окна.

*мемберфксн*<br/>
Имя функции обработчика сообщений, с которой сопоставлено сообщение.

### <a name="remarks"></a>Примечания

Этот макрос указывает, какая функция будет выполнять обработку зарегистрированного сообщения.

Дополнительные сведения и примеры см. в [разделах обработка сообщений и сопоставление](../../mfc/message-handling-and-mapping.md).

### <a name="example"></a>Пример

```cpp
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));

BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_registered_thread_message"></a><a name="on_registered_thread_message"></a> ON_REGISTERED_THREAD_MESSAGE

Указывает, какая функция будет выполнять обработку сообщения, зарегистрированного функцией Windows Регистервиндовмессаже.

### <a name="syntax"></a>Синтаксис

```cpp
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )
```

### <a name="parameters"></a>Параметры

*нмессажевариабле*<br/>
Зарегистрированная переменная идентификатора сообщения окна.

*мемберфксн*<br/>
Имя функции, с которой сопоставлено сообщение.

### <a name="remarks"></a>Примечания

Регистервиндовмессаже используется для определения нового сообщения окна, которое гарантированно уникально в пределах всей системы. ON_REGISTERED_THREAD_MESSAGE необходимо использовать вместо ON_REGISTERED_MESSAGE при наличии класса CWinThread.

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_thread_message"></a><a name="on_thread_message"></a> ON_THREAD_MESSAGE

Указывает, какая функция будет выполнять обработку определяемого пользователем сообщения.

### <a name="syntax"></a>Синтаксис

```cpp
ON_THREAD_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>Параметры

*message*<br/>
Идентификатор сообщения.

*мемберфксн*<br/>
Имя `CWinThread` функции обработчика сообщений, с которой сопоставляется сообщение.

### <a name="remarks"></a>Примечания

ON_THREAD_MESSAGE необходимо использовать вместо ON_MESSAGE при наличии `CWinThread` класса. Определяемые пользователем сообщения — это любые сообщения, не являющиеся стандартными сообщениями Windows WM_MESSAGE. В схеме сообщений для каждого определяемого пользователем сообщения, которое должно быть сопоставлено функции обработчика сообщений, должен быть ровно один ON_THREAD_MESSAGE макрос.

### <a name="requirements"></a>Требования

**Заголовок:** афксоле.h

## <a name="on_update_command_ui"></a><a name="on_update_command_ui"></a> ON_UPDATE_COMMAND_UI

Этот макрос указывает, какая функция будет управлять сообщением команды обновления пользовательского интерфейса.

### <a name="syntax"></a>Синтаксис

```cpp
ON_UPDATE_COMMAND_UI( messageId, memberFxn )
```

### <a name="parameters"></a>Параметры

*messageId*<br/>
Идентификатор сообщения.

*мемберфксн*<br/>
Имя функции обработчика сообщений, с которой сопоставлено сообщение.

### <a name="remarks"></a>Примечания

В схеме сообщений для каждой команды обновления пользовательского интерфейса, которая должна быть сопоставлена с функцией обработчика сообщений, должен быть ровно один ON_UPDATE_COMMAND_UI макрос.

Дополнительные сведения и примеры см. в [разделах обработка сообщений и сопоставление](../../mfc/message-handling-and-mapping.md).

### <a name="requirements"></a>Требования

**Заголовок:** афксоле.h

## <a name="on_command_range"></a><a name="on_command_range"></a> ON_COMMAND_RANGE

Используйте этот макрос для преобразования непрерывного диапазона идентификаторов команд в одну функцию обработчика сообщений.

### <a name="syntax"></a>Синтаксис

```cpp
ON_COMMAND_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Параметры

*id1*<br/>
Идентификатор команды в начале непрерывного диапазона идентификаторов команд.

*id2*<br/>
Идентификатор команды в конце непрерывного диапазона идентификаторов команд.

*мемберфксн*<br/>
Имя функции обработчика сообщений, с которой сопоставлены команды.

### <a name="remarks"></a>Примечания

Диапазон идентификаторов начинается с *id1* и заканчивается на *id2*.

Используйте ON_COMMAND_RANGE, чтобы связать диапазон идентификаторов команд с одной функцией-членом. Используйте [ON_COMMAND](#on_command) , чтобы связать одну команду с функцией-членом. Только одна запись схемы сообщений может соответствовать указанному ИДЕНТИФИКАТОРу команды. То есть нельзя сопоставлять команду более чем с одним обработчиком. Дополнительные сведения о сопоставлении диапазонов сообщений см. в разделе [обработчики для диапазонов карт сообщений](../../mfc/handlers-for-message-map-ranges.md).

Не существует автоматической поддержки диапазонов схемы сообщений, поэтому необходимо поместить макрос самостоятельно.

### <a name="example"></a>Пример

```cpp
// The code fragment below shows how to use ON_COMMAND_RANGE macro
// to map a contiguous range of command IDs to a single message
// handler function (i.e. OnRangeCmds() in the sample below). In
// addition, it also shows how to use CheckMenuRadioItem() to check a
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3,
      nID, MF_BYCOMMAND);
}
```

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_update_command_ui_range"></a><a name="on_update_command_ui_range"></a> ON_UPDATE_COMMAND_UI_RANGE

Сопоставляет непрерывный диапазон идентификаторов команд с одной функцией обработчика сообщений об обновлении.

### <a name="syntax"></a>Синтаксис

```cpp
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>Параметры

*id1*<br/>
Идентификатор команды в начале непрерывного диапазона идентификаторов команд.

*id2*<br/>
Идентификатор команды в конце непрерывного диапазона идентификаторов команд.

*мемберфксн*<br/>
Имя функции обработчика сообщений обновления, с которой сопоставлены команды.

### <a name="remarks"></a>Примечания

Обработчики сообщений обновления обновляют состояние пунктов меню и кнопок панели инструментов, связанных с командой. Диапазон идентификаторов начинается с *id1* и заканчивается на *id2*.

Не существует автоматической поддержки диапазонов схемы сообщений, поэтому необходимо поместить макрос самостоятельно.

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="on_control_range"></a><a name="on_control_range"></a> ON_CONTROL_RANGE

Используйте этот макрос для отображения непрерывного диапазона идентификаторов элементов управления для одной функции обработчика сообщений для указанного сообщения уведомления Windows, например BN_CLICKED.

### <a name="syntax"></a>Синтаксис

```cpp
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )
```

### <a name="parameters"></a>Параметры

*wNotifyCode*<br/>
Код уведомления, на который отвечает обработчик.

*id1*<br/>
Идентификатор команды в начале непрерывного диапазона идентификаторов элементов управления.

*id2*<br/>
Идентификатор команды в конце непрерывного диапазона идентификаторов элементов управления.

*мемберфксн*<br/>
Имя функции обработчика сообщений, с которой сопоставляются элементы управления.

### <a name="remarks"></a>Примечания

Диапазон идентификаторов начинается с *id1* и заканчивается на *id2*. Обработчик вызывается для указанного уведомления, поступающего из любого сопоставленного элемента управления.

Не существует автоматической поддержки диапазонов схемы сообщений, поэтому необходимо поместить макрос самостоятельно.

Дополнительные сведения о реализации функций обработчика для диапазона идентификаторов элементов управления см. в разделе [обработчики для диапазонов карт сообщений](../../mfc/handlers-for-message-map-ranges.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxmsg_.h

## <a name="see-also"></a>См. также раздел

[ON_COMMAND](message-map-macros-mfc.md#on_command)<br/>
[TN006: схемы сообщений](../tn006-message-maps.md)<br/>
[Класс Колекмдуи](colecmdui-class.md)<br/>
[Колесервердок:: Онексеколекмд](coleserverdoc-class.md#onexecolecmd)<br/>
[регистервиндовмессаже](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew)<br/>
[Пользовательские обработчики](user-defined-handlers.md)<br/>
[Класс поддержка CCmdUI](ccmdui-class.md)
