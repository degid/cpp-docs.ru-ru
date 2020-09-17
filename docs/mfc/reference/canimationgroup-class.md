---
title: Класс CAnimationGroup
ms.date: 03/27/2019
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
helpviewer_keywords:
- CAnimationGroup [MFC], CAnimationGroup
- CAnimationGroup [MFC], Animate
- CAnimationGroup [MFC], ApplyTransitions
- CAnimationGroup [MFC], FindAnimationObject
- CAnimationGroup [MFC], GetGroupID
- CAnimationGroup [MFC], RemoveKeyframes
- CAnimationGroup [MFC], RemoveTransitions
- CAnimationGroup [MFC], Schedule
- CAnimationGroup [MFC], SetAutodestroyTransitions
- CAnimationGroup [MFC], AddKeyframes
- CAnimationGroup [MFC], AddTransitions
- CAnimationGroup [MFC], CreateTransitions
- CAnimationGroup [MFC], m_bAutoclearTransitions
- CAnimationGroup [MFC], m_bAutodestroyAnimationObjects
- CAnimationGroup [MFC], m_bAutodestroyKeyframes
- CAnimationGroup [MFC], m_lstAnimationObjects
- CAnimationGroup [MFC], m_lstKeyFrames
- CAnimationGroup [MFC], m_pStoryboard
- CAnimationGroup [MFC], m_nGroupID
- CAnimationGroup [MFC], m_pParentController
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
ms.openlocfilehash: 14ac32524436ff46449171ad90599e60f63dff2a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750153"
---
# <a name="canimationgroup-class"></a>Класс CAnimationGroup

Реализует анимационную группу, которая сочетает в себе анимационный раскадровку, объекты анимации и переходы для определения анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationGroup;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationGroup:CAnimationGroup](#canimationgroup)|Строит анимационную группу.|
|[CAnimationGroup::](#_dtorcanimationgroup)|Деструктор Вызывается при уничтожении группы анимации.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationGroup:Animate](#animate)|Оживляет группу.|
|[CAnimationGroup:ApplyTransitions](#applytransitions)|Применяет переходы к объектам анимации.|
|[CAnimationGroup:FindAnimationObject](#findanimationobject)|Находит объект анимации, содержащий указанную переменную анимации.|
|[CAnimationGroup:GetGroupID](#getgroupid)|Возвращает GroupID.|
|[CAnimationGroup::RemoveKeyframes](#removekeyframes)|Удаляет и по желанию уничтожает все ключевые кадры, принадлежащие группе анимации.|
|[CAnimationGroup::RemoveTransitions](#removetransitions)|Удаляет переходы из объектов анимации, принадлежащих к группе анимации.|
|[CAnimationGroup:Расписание](#schedule)|Расписание анимации в указанное время.|
|[CAnimationGroup:SetAutodestroyПереходы](#setautodestroytransitions)|Направляет все объекты анимации, принадлежащие группе, автоматически уничтожают переходы.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationGroup:AddKeyframes](#addkeyframes)|Помощник, который добавляет ключевые кадры в раскадровку.|
|[CAnimationGroup:AddTransitions](#addtransitions)|Помощник, который добавляет переходы к раскадровке.|
|[CAnimationGroup::СозданиеПереходы](#createtransitions)|Помощник, создающий объекты перехода COM.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationGroup::m_bAutoclearTransitions](#m_bautocleartransitions)|Определяет, как очистить переходы от объектов анимации, которые принадлежат группе. Если этот элемент является правдой, переходы удаляются автоматически, когда анимация была запланирована. В противном случае необходимо удалить переходы вручную.|
|[CAnimationGroup::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|Определяет, как уничтожать объекты анимации. Если этот параметр является истинным, объекты анимации будут автоматически уничтожены при уничтожении группы. В противном случае объекты анимации должны быть уничтожены вручную. Значение по умолчанию — FALSE. Установите это значение к TRUE только в том случае, если все объекты анимации, принадлежащие группе, динамически распределены с новым оператором.|
|[CAnimationGroup::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|Определяет, как уничтожить ключевые кадры. Если это значение соответствует действительности, все ключевые кадры удаляются и уничтожаются; в противном случае они удаляются только из списка. Значение по умолчанию — TRUE.|
|[CAnimationGroup::m_lstAnimationObjects](#m_lstanimationobjects)|Содержит список объектов анимации.|
|[CAnimationGroup::m_lstKeyFrames](#m_lstkeyframes)|Содержит список ключевых кадров.|
|[CAnimationGroup::m_pStoryboard](#m_pstoryboard)|Указывает на раскадровку анимации. Этот указатель действителен только после вызова на Animate.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationGroup::m_nGroupID](#m_ngroupid)|Уникальный идентификатор анимационной группы.|
|[CAnimationGroup::m_pParentController](#m_pparentcontroller)|Указатель на контроллер анимации эта группа принадлежит.|

## <a name="remarks"></a>Примечания

Группы анимации создаются автоматически контроллером анимации (CAnimationController) при добавлении объектов анимации с помощью CAnimationController::AddAnimationObject. Группа анимации идентифицируется GroupID, который обычно принимается в качестве параметра для манипулирования группами анимации. GroupID взят из первого анимационного объекта, добавленного в новую группу анимации. Инкапсулированная анимация раскадровка создается после вызова CAnimationController::AnimateGroup и может быть доступна через общественный m_pStoryboard членов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAnimationGroup`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationgroupcanimationgroup"></a><a name="_dtorcanimationgroup"></a>CAnimationGroup::

Деструктор Вызывается при уничтожении группы анимации.

```
~CAnimationGroup();
```

## <a name="canimationgroupaddkeyframes"></a><a name="addkeyframes"></a>CAnimationGroup:AddKeyframes

Помощник, который добавляет ключевые кадры в раскадровку.

```cpp
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку объекта COM.

*bAddDeep*<br/>
Уточняется, следует ли добавить этот метод к ключевым кадрам раскадровки, которые зависят от других ключевых кадров.

## <a name="canimationgroupaddtransitions"></a><a name="addtransitions"></a>CAnimationGroup:AddTransitions

Помощник, который добавляет переходы к раскадровке.

```cpp
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку объекта COM.

*bDependOnKeyframes*

## <a name="canimationgroupanimate"></a><a name="animate"></a>CAnimationGroup:Animate

Оживляет группу.

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>Параметры

*pManager*<br/>
*pTimer*
*bScheduleNow*

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод удается; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Этот метод создает внутреннюю раскадровку, создает и применяет переходы и запланировал анимацию, если bScheduleNow является правдой. Если bScheduleNow является FALSE, вам необходимо вызвать Расписание, чтобы начать анимацию в указанное время.

## <a name="canimationgroupapplytransitions"></a><a name="applytransitions"></a>CAnimationGroup:ApplyTransitions

Применяет переходы к объектам анимации.

```cpp
void ApplyTransitions();
```

### <a name="remarks"></a>Примечания

Этот метод ASSERTS в режиме отладки, если раскадровка не была создана. Сначала он создает все переходы, затем добавляет "статические" ключевые кадры (ключевые кадры, зависящие от смещений), добавляет переходы, которые не зависят от ключевых кадров, добавляет ключевые кадры в зависимости от переходов и других ключевых кадров и, наконец, добавляет переходы, зависящие от ключевых кадров.

## <a name="canimationgroupcanimationgroup"></a><a name="canimationgroup"></a>CAnimationGroup:CAnimationGroup

Строит анимационную группу.

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>Параметры

*pParentController*<br/>
Указатель на контроллер анимации, который создает группу.

*nGroupID*<br/>
Уточняет GroupID.

## <a name="canimationgroupcreatetransitions"></a><a name="createtransitions"></a>CAnimationGroup::СозданиеПереходы

Помощник, создающий объекты перехода COM.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА метод удается, в противном случае FALSE.

## <a name="canimationgroupfindanimationobject"></a><a name="findanimationobject"></a>CAnimationGroup:FindAnimationObject

Находит объект анимации, содержащий указанную переменную анимации.

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Параметры

*pПеременный*<br/>
Указатель на переменную анимации.

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект анимации, или NULL, если объект анимации не найден.

## <a name="canimationgroupgetgroupid"></a><a name="getgroupid"></a>CAnimationGroup:GetGroupID

Возвращает GroupID.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Идентификатор группы.

## <a name="canimationgroupm_bautocleartransitions"></a><a name="m_bautocleartransitions"></a>CAnimationGroup::m_bAutoclearTransitions

Определяет, как очистить переходы от объектов анимации, которые принадлежат группе. Если этот элемент является правдой, переходы удаляются автоматически, когда анимация была запланирована. В противном случае необходимо удалить переходы вручную.

```
BOOL m_bAutoclearTransitions;
```

## <a name="canimationgroupm_bautodestroyanimationobjects"></a><a name="m_bautodestroyanimationobjects"></a>CAnimationGroup::m_bAutodestroyAnimationObjects

Определяет, как уничтожать объекты анимации. Если этот параметр является истинным, объекты анимации будут автоматически уничтожены при уничтожении группы. В противном случае объекты анимации должны быть уничтожены вручную. Значение по умолчанию — FALSE. Установите это значение к TRUE только в том случае, если все объекты анимации, принадлежащие группе, динамически распределены с новым оператором.

```
BOOL m_bAutodestroyAnimationObjects;
```

## <a name="canimationgroupm_bautodestroykeyframes"></a><a name="m_bautodestroykeyframes"></a>CAnimationGroup::m_bAutodestroyKeyframes

Определяет, как уничтожить ключевые кадры. Если это значение соответствует действительности, все ключевые кадры удаляются и уничтожаются; в противном случае они удаляются только из списка. Значение по умолчанию — TRUE.

```
BOOL m_bAutodestroyKeyframes;
```

## <a name="canimationgroupm_lstanimationobjects"></a><a name="m_lstanimationobjects"></a>CAnimationGroup::m_lstAnimationObjects

Содержит список объектов анимации.

```
CObList m_lstAnimationObjects;
```

## <a name="canimationgroupm_lstkeyframes"></a><a name="m_lstkeyframes"></a>CAnimationGroup::m_lstKeyFrames

Содержит список ключевых кадров.

```
CObList m_lstKeyFrames;
```

## <a name="canimationgroupm_ngroupid"></a><a name="m_ngroupid"></a>CAnimationGroup::m_nGroupID

Уникальный идентификатор анимационной группы.

```
UINT32 m_nGroupID;
```

## <a name="canimationgroupm_pparentcontroller"></a><a name="m_pparentcontroller"></a>CAnimationGroup::m_pParentController

Указатель на контроллер анимации эта группа принадлежит.

```
CAnimationController* m_pParentController;
```

## <a name="canimationgroupm_pstoryboard"></a><a name="m_pstoryboard"></a>CAnimationGroup::m_pStoryboard

Указывает на раскадровку анимации. Этот указатель действителен только после вызова на Animate.

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

## <a name="canimationgroupremovekeyframes"></a><a name="removekeyframes"></a>CAnimationGroup::RemoveKeyframes

Удаляет и по желанию уничтожает все ключевые кадры, принадлежащие группе анимации.

```cpp
void RemoveKeyframes();
```

### <a name="remarks"></a>Примечания

Если m_bAutodestroyKeyframes член является правдой, то ключевые кадры удаляются и уничтожаются, в противном случае ключевые кадры просто удаляются из внутреннего списка ключевых кадров.

## <a name="canimationgroupremovetransitions"></a><a name="removetransitions"></a>CAnimationGroup::RemoveTransitions

Удаляет переходы из объектов анимации, принадлежащих к группе анимации.

```cpp
void RemoveTransitions();
```

### <a name="remarks"></a>Примечания

Если m_bAutoclearTransitions флаг установлен на ИСТИНу, этот метод циклов над всеми объектами анимации, которые принадлежат к группе и называет CAnimationObject::ClearTransitions (FALSE).

## <a name="canimationgroupschedule"></a><a name="schedule"></a>CAnimationGroup:Расписание

Расписание анимации в указанное время.

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>Параметры

*pTimer*<br/>
Указатель на анимационный таймер.

*time*<br/>
Определяет время для планирования анимации.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если метод удается; FALSE, если метод не удается или если Animate не был вызван с bScheduleNow установлен false.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы запланировать анимацию в указанное время. Вы должны позвонить Animate с bScheduleNow установлен на FALSE в первую очередь.

## <a name="canimationgroupsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>CAnimationGroup:SetAutodestroyПереходы

Направляет все объекты анимации, принадлежащие группе, автоматически уничтожают переходы.

```cpp
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Параметры

*bAutoDestroy*<br/>
Определяет, как уничтожить переходы.

### <a name="remarks"></a>Примечания

Установите это значение false только в том случае, если вы выделяете переходы в стеке. Значение по умолчанию является правдой, поэтому настоятельно рекомендуется выделять объекты перехода с помощью нового оператора.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
