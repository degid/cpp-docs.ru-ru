---
title: Класс CCmdUI
ms.date: 09/06/2019
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
ms.openlocfilehash: 3e167d9e305481e05808f5e553222c10abbc88de
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752724"
---
# <a name="ccmdui-class"></a>Класс CCmdUI

Используется только в `ON_UPDATE_COMMAND_UI` обработчике в классе `CCmdTarget`производных.

## <a name="syntax"></a>Синтаксис

```
class CCmdUI
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCmdUI:Продолжить](#continuerouting)|Сообщает механизму командной расети продолжить движение текущего сообщения по цепочке обработчиков.|
|[CCmdUI:Включить](#enable)|Позволяет или отсвапотребляет элемент пользователь-интерфейс для этой команды.|
|[CCmdUI:SetCheck](#setcheck)|Устанавливает состояние проверки элемента пользователь-интерфейс для этой команды.|
|[CCmdUI::SetRadio](#setradio)|Как `SetCheck` функция члена, но работает на радио-групп.|
|[CCmdUI::SetText](#settext)|Устанавливает текст для элемента пользователь-интерфейс для этой команды.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CCmdUI::m_nID](#m_nid)|Идентификатор объекта пользователь-интерфейса.|
|[CCmdUI::m_nIndex](#m_nindex)|Индекс объекта пользователь-интерфейса.|
|[CCmdUI::m_pMenu](#m_pmenu)|Очки в меню, представленное объектом. `CCmdUI`|
|[CCmdUI::m_pOther](#m_pother)|Указывает на объект окна, отправивший уведомление.|
|[CCmdUI::m_pSubMenu](#m_psubmenu)|Указывает на содержащееся подменю, представленное объектом. `CCmdUI`|

## <a name="remarks"></a>Примечания

`CCmdUI`не имеет базового класса.

Когда пользователь приложения снимает меню, каждый элемент меню должен знать, следует ли отображать его как включенное или отключенное. Цель команды меню предоставляет эту информацию, реализуя обработчик ON_UPDATE_COMMAND_UI. Для каждого из объектов пользовательского интерфейса команды в приложении используйте окно [Класса Мастер](mfc-class-wizard.md) или **Свойства** (в **классе View)** для создания входа и прототипа функции сообщения для каждого обработчика.

Когда меню стягивается, фреймворк выполняет поиск и `CCmdUI` вызывает каждый `Enable` `Check`ON_UPDATE_COMMAND_UI обработчик, каждый обработчик вызывает функции участника, такие как и, и, затем платформа надлежащим образом отображает каждый элемент меню.

Элемент меню может быть заменен кнопкой управления баром или другим объектом `ON_UPDATE_COMMAND_UI` пользовательского интерфейса команды без изменения кода в обработчике.

В следующей таблице `CCmdUI`кратко излагается влияние функций членов на различные элементы командного пользовательского интерфейса.

|Элемент пользователь-интерфейс|Включить|SetCheck|SetRadio|Settext|
|--------------------------|------------|--------------|--------------|-------------|
|Элемент меню|Включает или отдает|Проверки или непроверки|Проверки с помощью точки|Наборы текста элемента|
|Кнопка на панели инструментов|Включает или отдает|Выбирает, не выбирает или неопределенным|То же, что `SetCheck`|(Неприменимо)|
|Стенейка статус-бар|Делает текст видимым или невидимым|Устанавливает всплывающее окно или нормальную границу|То же, что `SetCheck`|Наборы текста панели|
|Обычная кнопка в`CDialogBar`|Включает или отдает|Чеки или расчек флажок|То же, что `SetCheck`|Устанавливает текст кнопки|
|Нормальный контроль в`CDialogBar`|Включает или отдает|(Неприменимо)|(Неприменимо)|Устанавливает текст окна|

Для получения дополнительной информации об использовании этого класса [см.](../../mfc/how-to-update-user-interface-objects.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CCmdUI`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="ccmduicontinuerouting"></a><a name="continuerouting"></a>CCmdUI:Продолжить

Вызов ими функции участника, чтобы сообщить механизму командной растерянии о продолжении перехивания текущего сообщения по цепочке обработчиков.

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>Примечания

Это расширенная функция члена, которая должна использоваться в сочетании с обработчиком ON_COMMAND_EX, который возвращает FALSE. Для получения дополнительной информации [см.](../../mfc/tn006-message-maps.md)

## <a name="ccmduienable"></a><a name="enable"></a>CCmdUI:Включить

Вызовите эту функцию участника, чтобы включить или отключить элемент пользовательского интерфейса для этой команды.

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Параметры

*Бон*<br/>
ПРАВДА, чтобы позволить пункт, FALSE отключить его.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

## <a name="ccmduim_nid"></a><a name="m_nid"></a>CCmdUI::m_nID

Идентификатор элемента меню, кнопки панели инструментов или `CCmdUI` другого объекта пользовательского интерфейса, представленного объектом.

```
UINT m_nID;
```

## <a name="ccmduim_nindex"></a><a name="m_nindex"></a>CCmdUI::m_nIndex

Индекс элемента меню, кнопки панели инструментов или другого `CCmdUI` объекта пользовательского интерфейса, представленного объектом.

```
UINT m_nIndex;
```

## <a name="ccmduim_pmenu"></a><a name="m_pmenu"></a>CCmdUI::m_pMenu

Указатель `CMenu` (тип) в меню, представленное объектом. `CCmdUI`

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>Примечания

NULL, если элемент не является меню.

## <a name="ccmduim_psubmenu"></a><a name="m_psubmenu"></a>CCmdUI::m_pSubMenu

Указатель `CMenu` (тип) к содержащемуся подменю, представленному объектом. `CCmdUI`

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>Примечания

NULL, если элемент не является меню. Если подменю всплывающее окно, *m_nID* содержит идентификатор первого элемента в всплывающем меню. Для получения дополнительной информации [см.](../../mfc/tn021-command-and-message-routing.md)

## <a name="ccmduim_pother"></a><a name="m_pother"></a>CCmdUI::m_pOther

Указатель (тип) `CWnd`на объект окна, например, инструмент или панель статуса, который отправил уведомление.

```
CWnd* m_pOther;
```

### <a name="remarks"></a>Примечания

NULL, если элемент является меню `CWnd` или не-объект.

## <a name="ccmduisetcheck"></a><a name="setcheck"></a>CCmdUI:SetCheck

Вызовите эту функцию участника, чтобы настроить элемент пользователь-интерфейс для этой команды в соответствующее состояние проверки.

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>Параметры

*Nпроверьте*<br/>
Определяет состояние проверки для установки. Если 0, отскакивая от проверок; если 1, проверяет; и если 2, устанавливает неопределенный.

### <a name="remarks"></a>Примечания

Эта функция члена работает для элементов меню и кнопок панели инструментов. Неопределенное состояние применяется только к кнопкам панели инструментов.

## <a name="ccmduisetradio"></a><a name="setradio"></a>CCmdUI::SetRadio

Вызовите эту функцию участника, чтобы настроить элемент пользователь-интерфейс для этой команды в соответствующее состояние проверки.

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>Параметры

*Бон*<br/>
TRUE для включения элемента; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Эта функция члена `SetCheck`работает как , за исключением того, что она работает на пользовательских интерфейсе элементов, действующих как часть радио-группы. Отсечение других элементов в группе не происходит автоматически, если сами элементы не поддерживают поведение радиогруппы.

## <a name="ccmduisettext"></a><a name="settext"></a>CCmdUI::SetText

Вызовите эту функцию участника, чтобы настроить текст элемента пользовательского интерфейса для этой команды.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>Параметры

*lpszText*<br/>
Указатель на текстовую строку.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец MDI](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CCmdTarget](../../mfc/reference/ccmdtarget-class.md)
