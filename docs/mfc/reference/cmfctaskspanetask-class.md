---
title: Класс CMFCTasksPaneTask
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
helpviewer_keywords:
- CMFCTasksPaneTask [MFC], CMFCTasksPaneTask
- CMFCTasksPaneTask [MFC], SetACCData
- CMFCTasksPaneTask [MFC], m_bAutoDestroyWindow
- CMFCTasksPaneTask [MFC], m_bIsBold
- CMFCTasksPaneTask [MFC], m_dwUserData
- CMFCTasksPaneTask [MFC], m_hwndTask
- CMFCTasksPaneTask [MFC], m_nIcon
- CMFCTasksPaneTask [MFC], m_nWindowHeight
- CMFCTasksPaneTask [MFC], m_pGroup
- CMFCTasksPaneTask [MFC], m_rect
- CMFCTasksPaneTask [MFC], m_strName
- CMFCTasksPaneTask [MFC], m_uiCommandID
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
ms.openlocfilehash: 49fccdf161da7deb1fd88a12a107df40bafdae92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375866"
---
# <a name="cmfctaskspanetask-class"></a>Класс CMFCTasksPaneTask

Класс `CMFCTasksPaneTask` является классом помощника, который представляет задачи для управления панелью задач [(CMFCTasksPane).](../../mfc/reference/cmfctaskspane-class.md) Объект задачи представляет элемент в целевой группе [(CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)). Каждая задача может иметь команду, которую платформа выполняет, когда пользователь щелкает задачу, и значок, который присутствует слева от имени задачи.

## <a name="syntax"></a>Синтаксис

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCTasksPaneTask::CMFCTasksPaneTask](#cmfctaskspanetask)|Создает и инициализирует объект `CMFCTasksPaneTask`.|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCTasksPaneTask::SetACCData](#setaccdata)|Определяет данные о доступности для текущей задачи.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCTasksPaneTask::m_bAutoDestroyWindow](#m_bautodestroywindow)|Определяет, автоматически ли уничтожается окно задачи.|
|[CMFCTasksPaneTask::m_bIsBold](#m_bisbold)|Определяет, рисует ли фреймворк жирным текстом метку задачи.|
|[CMFCTasksPaneTask::m_dwUserData](#m_dwuserdata)|Содержит данные, определяемые пользователем, которые фреймворк связывает с задачей. Установите к нулю, если задача не имеет связанных данных.|
|[CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)|Ручка к окну задачи.|
|[CMFCTasksPaneTask::m_nIcon](#m_nicon)|Индекс в списке изображений изображения, отображаемого фреймворком рядом с задачей.|
|[CMFCTasksPaneTask::m_nWindowHeight](#m_nwindowheight)|Высота окна задачи. Если в задаче нет окна задачи, это значение равно нулю.|
|[CMFCTasksPaneTask::m_pGroup](#m_pgroup)|Указатель на `CMFCTasksPaneTaskGroup` то, что эта задача принадлежит.|
|[CMFCTasksPaneTask::m_rect](#m_rect)|Определяет ограничивающий прямоугольник задачи.|
|[CMFCTasksPaneTask::m_strName](#m_strname)|Имя данной задачи.|
|[CMFCTasksPaneTask::m_uiCommandID](#m_uicommandid)|Уотеляет идентификатор команды команды, который выполняет сяокард при нажатии задачи пользователем. Если это значение не является действительным идентификатором команды, задача рассматривается как простая метка.|

## <a name="remarks"></a>Примечания

На следующей иллюстрации показана целевая группа, содержащая три задачи:

![Целевая группа, расширенная](../../mfc/reference/media/nexttaskgrpexpand.png "Развернутая группа задач")

> [!NOTE]
> Если задача не имеет действительного идентификатора команды, она рассматривается как простая метка.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxTasksPane.h

## <a name="cmfctaskspanetaskcmfctaskspanetask"></a><a name="cmfctaskspanetask"></a>CMFCTasksPaneTask::CMFCTasksPaneTask

Создает и инициализирует объект `CMFCTasksPaneTask`.

```
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,
    LPCTSTR lpszName,
    int nIcon,
    UINT uiCommandID,
    DWORD dwUserData = 0,
    HWND hwndTask = NULL,
    BOOL bAutoDestroyWindow = FALSE,
    int nWindowHeight = 0);
```

### <a name="parameters"></a>Параметры

*pGroup*<br/>
Определяет [CMFCTasksPaneTaskGroup,](../../mfc/reference/cmfctaskspanetaskgroup-class.md) к которому принадлежит задача.

*lpszName*<br/>
Указание названия задачи.

*nIcon*<br/>
Определяет индекс изображения задачи в списке изображений.

*uiCommandID*<br/>
Уотеляет идентификатор команды команды, выполняемый при нажатии задачи.

*dwUserData*<br/>
Данные, определяемые пользователем.

*hwndTask*<br/>
Определяет ручку к окну задачи.

*bAutoDestroyWindow*<br/>
Если TRUE, окно задачи будет уничтожено автоматически.

*nWindowHeight*<br/>
Определяет высоту окна задачи.

### <a name="remarks"></a>Примечания

## <a name="cmfctaskspanetaskm_bautodestroywindow"></a><a name="m_bautodestroywindow"></a>CMFCTasksPaneTask::m_bAutoDestroyWindow

Определяет, автоматически ли уничтожается окно задачи.

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>Примечания

Установить, чтобы true указать, что окно задачи [(CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) должны быть уничтожены автоматически; в противном случае, FALSE.

## <a name="cmfctaskspanetaskm_bisbold"></a><a name="m_bisbold"></a>CMFCTasksPaneTask::m_bIsBold

Определяет, нарисована ли метка задачи жирным текстом.

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>Примечания

Установите этот член к TRUE для отображения смелого текста для метки задачи.

## <a name="cmfctaskspanetaskm_dwuserdata"></a><a name="m_dwuserdata"></a>CMFCTasksPaneTask::m_dwUserData

Содержит данные, определяемые пользователем, связанные с задачей. Установите к нулю, если данные не связаны с задачей.

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>Примечания

## <a name="cmfctaskspanetaskm_hwndtask"></a><a name="m_hwndtask"></a>CMFCTasksPaneTask::m_hwndTask

Ручка к окну задачи.

```
HWND m_hwndTask;
```

### <a name="remarks"></a>Примечания

Чтобы добавить окно задачи, позвоните [cmFCTasksPane::AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow).

## <a name="cmfctaskspanetaskm_nicon"></a><a name="m_nicon"></a>CMFCTasksPaneTask::m_nIcon

Положение индекса в списке изображений, которое определяет изображение, отображаемые рядом с указанной задачей.

```
int m_nIcon;
```

### <a name="remarks"></a>Примечания

Список изображений устанавливается [CMFCTasksPane::SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist).

Установите `m_nIcon` задачу -1, если вы хотите отобразить задачу без изображения.

## <a name="cmfctaskspanetaskm_nwindowheight"></a><a name="m_nwindowheight"></a>CMFCTasksPaneTask::m_nWindowHeight

Высота окна задачи. Если в задаче нет окна задачи, это значение равно нулю.

```
int m_nWindowHeight;
```

### <a name="remarks"></a>Примечания

## <a name="cmfctaskspanetaskm_pgroup"></a><a name="m_pgroup"></a>CMFCTasksPaneTask::m_pGroup

Указатель на [CMFCTasksPaneTaskGroup,](../../mfc/reference/cmfctaskspanetaskgroup-class.md) к которому принадлежит эта задача.

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>Примечания

Каждая задача должна иметь родительскую группу. Вы добавляете группы в панель задач, [позвонив по телефону CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).

## <a name="cmfctaskspanetaskm_rect"></a><a name="m_rect"></a>CMFCTasksPaneTask::m_rect

Определяет ограничивающий прямоугольник задачи.

```
CRect m_rect;
```

### <a name="remarks"></a>Примечания

Это значение рассчитывается по системе при нарисовании задачи.

## <a name="cmfctaskspanetaskm_strname"></a><a name="m_strname"></a>CMFCTasksPaneTask::m_strName

Имя данной задачи.

```
CString m_strName;
```

### <a name="remarks"></a>Примечания

## <a name="cmfctaskspanetaskm_uicommandid"></a><a name="m_uicommandid"></a>CMFCTasksPaneTask::m_uiCommandID

Уотеляет идентификатор команды команды, выполняемый при нажатии задачи. Если это значение не является действительным идентификатором команды, задача рассматривается как простая метка.

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>Примечания

## <a name="cmfctaskspanetasksetaccdata"></a><a name="setaccdata"></a>CMFCTasksPaneTask::SetACCData

Определяет данные о доступности для текущей задачи.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*pРодитель*<br/>
(в) Представляет родительское окно текущей задачи.

*данные*<br/>
(ваут) Объект типа, `CAccessibilityData` населенный данными о доступности текущей задачи.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если параметр *данных* был успешно заселен данными о доступности текущей задачи; в противном случае, FALSE.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)
