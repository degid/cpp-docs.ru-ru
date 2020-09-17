---
title: Схемы команд редактирования DHTML
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: f4bbfb500e8de9594bbaa334b4e227caeaa845da
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837415"
---
# <a name="dhtml-editing-command-maps"></a>Схемы команд редактирования DHTML

Следующие макросы можно использовать для отображения команд редактирования DHTML в классах, производных от [CHtmlEditView](../../mfc/reference/chtmleditview-class.md). Пример использования см. в разделе [Хтмледит Sample](../../overview/visual-cpp-samples.md).

### <a name="dhtml-editing-command-map-macros"></a>Макросы схемы команд редактирования DHTML

|Имя|Описание|
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Объявляет карту команд редактирования DHTML в классе.|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Запускает определение схемы команды редактирования DHTML в классе.|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|Помечает конец схемы команды редактирования DHTML.|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Сопоставляет идентификатор команды с HTML-командой редактирования.|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Сопоставляет идентификатор команды с HTML-командой редактирования и обработчиком сообщений.|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Сопоставляет идентификатор команды с HTML-командой редактирования и элементом интерфейса пользователя.|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Сопоставляет идентификатор команды с командой редактирования HTML, обработчиком сообщений и элементом пользовательского интерфейса.|

## <a name="declare_dhtmlediting_cmdmap"></a><a name="declare_dhtmlediting_cmdmap"></a> DECLARE_DHTMLEDITING_CMDMAP

Объявляет карту команд редактирования DHTML в классе.

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса.

### <a name="remarks"></a>Примечания

Этот макрос используется в определении классов, производных от [CHtmlEditView](../../mfc/reference/chtmleditview-class.md).

Для реализации этой схемы используйте [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) .

### <a name="example"></a>Пример

См. [Пример хтмледит](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="begin_dhtmlediting_cmdmap"></a><a name="begin_dhtmlediting_cmdmap"></a> BEGIN_DHTMLEDITING_CMDMAP

Запускает определение схемы команды редактирования DHTML в классе.

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карту команд редактирования DHTML. Этот класс должен прямо или косвенно наследовать от [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) и включать макрос [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) в его определение класса.

### <a name="remarks"></a>Примечания

Добавьте в класс карту команды редактирования DHTML, чтобы сопоставлять команды пользовательского интерфейса с командами редактирования HTML.

Поместите макрос BEGIN_DHTMLEDITING_CMDMAP в файл реализации класса (. cpp), а затем [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) макросы для команд, с которыми должен сопоставляться класс (например, от ID_EDIT_CUT до IDM_CUT). Используйте макрос [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) , чтобы отметить окончание схемы событий.

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="end_dhtmlediting_cmdmap"></a><a name="end_dhtmlediting_cmdmap"></a> END_DHTMLEDITING_CMDMAP

Помечает конец схемы команды редактирования DHTML.

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>Примечания

Используйте в сочетании с [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap).

### <a name="example"></a>Пример

См. [Пример хтмледит](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="dhtmlediting_cmd_entry"></a><a name="dhtmlediting_cmd_entry"></a> DHTMLEDITING_CMD_ENTRY

Сопоставляет идентификатор команды с HTML-командой редактирования.

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*дхтмлкмдид*<br/>
Команда редактирования HTML, к которой сопоставлены *cmdID* (например, IDM_COPY).

### <a name="example"></a>Пример

См. [Пример хтмледит](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func"></a><a name="dhtmlediting_cmd_entry_func"></a> DHTMLEDITING_CMD_ENTRY_FUNC

Сопоставляет идентификатор команды с HTML-командой редактирования и обработчиком сообщений.

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*дхтмлкмдид*<br/>
Команда редактирования HTML, к которой сопоставлены *cmdID* (например, IDM_COPY).

*member_func_name*<br/>
Имя функции обработчика сообщений, с которой сопоставляется команда.

### <a name="example"></a>Пример

См. [Пример хтмледит](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="dhtmlediting_cmd_entry_type"></a><a name="dhtmlediting_cmd_entry_type"></a> DHTMLEDITING_CMD_ENTRY_TYPE

Сопоставляет идентификатор команды с HTML-командой редактирования и элементом интерфейса пользователя.

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*дхтмлкмдид*<br/>
Команда редактирования HTML, к которой сопоставлены *cmdID* (например, IDM_COPY).

*елемтипе*<br/>
Тип элемента пользовательского интерфейса; один из AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX или AFX_UI_ELEMTYPE_RADIO.

### <a name="example"></a>Пример

См. [Пример хтмледит](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func_type"></a><a name="dhtmlediting_cmd_entry_func_type"></a> DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

Сопоставляет идентификатор команды с командой редактирования HTML, обработчиком сообщений и элементом пользовательского интерфейса.

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>Параметры

*cmdID*<br/>
Идентификатор команды (например, ID_EDIT_COPY).

*дхтмлкмдид*<br/>
Команда редактирования HTML, к которой сопоставлены *cmdID* (например, IDM_COPY).

*member_func_name*<br/>
Имя функции обработчика сообщений, с которой сопоставляется команда.

*елемтипе*<br/>
Тип элемента пользовательского интерфейса; один из AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX или AFX_UI_ELEMTYPE_RADIO.

### <a name="example"></a>Пример

См. [Пример хтмледит](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Требования

  **Заголовок** afxhtml.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
