---
title: Класс CMFCTasksPaneTaskGroup
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
ms.openlocfilehash: 4c24eba646bede462a5f3cfb85715278cfa7daee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366255"
---
# <a name="cmfctaskspanetaskgroup-class"></a>Класс CMFCTasksPaneTaskGroup

Класс `CMFCTasksPaneTaskGroup` является классом помощников, используемым в управлении [CMFCTasksPane.](../../mfc/reference/cmfctaskspane-class.md) Объекты типа `CMFCTasksPaneTaskGroup` представляют *группу задач*. Группа задач — это список элементов, отображаемых структурой в отдельном поле с кнопкой "Свернуть". Поле может иметь необязательный заголовок (имя группы). Если группа свернута, список задач не отображается.

## <a name="syntax"></a>Синтаксис

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup:CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|Формирует объект `CMFCTasksPaneTaskGroup`.|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Деструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::SetACCData](#setaccdata)|Определяет данные о доступности для текущей целевой группы.|

### <a name="data-members"></a>Элементы данных

|Имя|Описание|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup::m_bIsBottom](#m_bisbottom)|Определяет, выравнивается ли рабочая группа до нижней части элемента управления панели задач.|
|[CMFCTasksPaneTaskGroup::m_bIsCollapsed](#m_biscollapsed)|Определяет, является ли задача рухнула.|
|[CMFCTasksPaneTaskGroup::m_bIsSpecial](#m_bisspecial)|Определяет, является ли целевая группа *особенной.* Рамки отображают специальные субтитры в другом цвете.|
|[CMFCTasksPaneTaskGroup::m_lstTasks](#m_lsttasks)|Содержит внутренний список задач.|
|[CMFCTasksPaneTaskGroup::m_rect](#m_rect)|Определяет ограничивающий прямоугольник подписи группы.|
|[CMFCTasksPaneTaskGroup::m_rectGroup](#m_rectgroup)|Определяет ограничивающий прямоугольник группы.|
|[CMFCTasksPaneTaskGroup::m_strName](#m_strname)|Задает имя группы.|

## <a name="remarks"></a>Примечания

На следующей иллюстрации показана расширенная целевая группа:

![Целевая группа, расширенная](../../mfc/reference/media/nexttaskgrpexpand.png "Развернутая группа задач")

На следующей иллюстрации показана рухнувшему целевому группе:

![Свернутая группа задач](../../mfc/reference/media/nexttaskgrpcollapse.png "Свернутая группа задач")

На следующей иллюстрации показана целевая группа без подписи:

![Группа задач без заголовка](../../mfc/reference/media/nexttaskgrpnocapt.png "Группа задач без заголовка")

На следующей иллюстрации показаны две группы задач. Первая целевая группа помечена `m_bIsSpecial` как специальная, установив флаг на ИСТИНу, в то время как вторая целевая группа не является особенной. Обратите внимание, что подпись для первой группы задач темнее второй группы задач:

![Специальная группа задач](../../mfc/reference/media/nexttaskgrpspecial.png "Специальная группа задач")

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxTasksPane.h

## <a name="cmfctaskspanetaskgroupcmfctaskspanetaskgroup"></a><a name="cmfctaskspanetaskgroup"></a>CMFCTasksPaneTaskGroup:CMFCTasksPaneTaskGroup

Формирует объект `CMFCTasksPaneTaskGroup`.

```
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,
    BOOL bIsBottom,
    BOOL bIsSpecial=FALSE,
    BOOL bIsCollapsed=FALSE,
    CMFCTasksPanePropertyPage* pPage=NULL,
    HICON hIcon=NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Упоняет название группы в подписи к группе.

*bIsBottom*<br/>
Определяет, выравнивается ли группа до нижней части элемента управления панелью задач.

*bIsSpecial*<br/>
Определяет, обозначена ли группа как *специальная* и, таким образом, заполняется ли подпись группы другим цветом.

*bIsСконированный*<br/>
Уточняется, рухнула ли группа.

*pPage*<br/>
Уотек страницы свойств, к которой принадлежит эта целевая группа.

*hIcon*<br/>
Упоняет значок, отображаемый в подписи к группе.

### <a name="remarks"></a>Примечания

## <a name="cmfctaskspanetaskgroupm_bisbottom"></a><a name="m_bisbottom"></a>CMFCTasksPaneTaskGroup::m_bIsBottom

Определяет, выравнивается ли рабочая группа до нижней части элемента управления панели задач.

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>Примечания

Только одна группа может быть выровнена в нижней части элемента управления панелью задач. Эта целевая группа должна быть добавлена последней. Для получения дополнительной информации [см. CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup).

## <a name="cmfctaskspanetaskgroupm_biscollapsed"></a><a name="m_biscollapsed"></a>CMFCTasksPaneTaskGroup::m_bIsCollapsed

Определяет, является ли задача рухнула.

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>Примечания

Вы можете включить или отключить возможность коллапса групп на панели задач, [позвонив cmFCTasksPane::EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse).

## <a name="cmfctaskspanetaskgroupm_bisspecial"></a><a name="m_bisspecial"></a>CMFCTasksPaneTaskGroup::m_bIsSpecial

Определяет, *является* ли специальная группа задач и должна ли подпись к специальной целевой группе быть идентифицирована другим цветом.

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>Примечания

Если ваше приложение использует визуальную `m_bIsSpecial` тему Windows XP `DrawThemeBackground` и является FALSE, фреймворк вызывает сявок с EBP_NORMALGROUPBACKGROUND флагом. Если `m_bIsSpecial` это правда, `DrawThemeBackground` то фреймворк вызывает с флагом EBP_SPECIALGROUPBACKGROUND.

## <a name="cmfctaskspanetaskgroupm_lsttasks"></a><a name="m_lsttasks"></a>CMFCTasksPaneTaskGroup::m_lstTasks

Содержит внутренний список задач.

```
CObList m_lstTasks;
```

### <a name="remarks"></a>Примечания

Чтобы заполнить этот список, позвоните [CMFCTasksPane::AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask).

## <a name="cmfctaskspanetaskgroupm_rect"></a><a name="m_rect"></a>CMFCTasksPaneTaskGroup::m_rect

Определяет ограничивающий прямоугольник подписи группы.

```
CRect m_rect;
```

### <a name="remarks"></a>Примечания

Это значение автоматически рассчитывается по фреймворку.

## <a name="cmfctaskspanetaskgroupm_rectgroup"></a><a name="m_rectgroup"></a>CMFCTasksPaneTaskGroup::m_rectGroup

Определяет ограничивающий прямоугольник группы.

```
CRect m_rectGroup;
```

### <a name="remarks"></a>Примечания

Это значение автоматически рассчитывается по фреймворку.

## <a name="cmfctaskspanetaskgroupm_strname"></a><a name="m_strname"></a>CMFCTasksPaneTaskGroup::m_strName

Задает имя группы.

```
CString m_strName;
```

### <a name="remarks"></a>Примечания

Если это значение пусто, подпись группы не отображается и группа не может быть свернута.

## <a name="cmfctaskspanetaskgroupsetaccdata"></a><a name="setaccdata"></a>CMFCTasksPaneTaskGroup::SetACCData

Определяет данные о доступности для текущей целевой группы.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Параметры

*pРодитель*<br/>
(в) Представляет родительское окно текущей группы задач.

*данные*<br/>
(ваут) Объект типа, `CAccessibilityData` населенный данными о доступности текущей группы задач.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если параметр *данных* был успешно заселен данными о доступности текущей целевой группы; в противном случае, FALSE.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Классы](../../mfc/reference/mfc-classes.md)<br/>
[Класс CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)<br/>
[Класс CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[Класс CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)
