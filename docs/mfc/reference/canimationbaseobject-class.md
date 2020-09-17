---
title: Класс CAnimationBaseObject
ms.date: 03/27/2019
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
ms.openlocfilehash: 1874ddfdd26b8dd371e32f7e68ea8f668c47d8e1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750219"
---
# <a name="canimationbaseobject-class"></a>Класс CAnimationBaseObject

Базовый класс для всех объектов анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationBaseObject : public CObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|Перегружен. Строит объект анимации.|
|[CAnimationBaseObject:: »CAnimationBaseObject](#_dtorcanimationbaseobject)|Деструктор Вызывается при уничтожении объекта анимации.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationBaseObject:ApplyПереходы](#applytransitions)|Добавляет переходы к раскадровке с инкапсулированной переменной анимации.|
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|Удаляет все связанные переходы.|
|[CAnimationBaseObject::Содержитпеременный](#containsvariable)|Определяет, содержит ли объект анимации определенную переменную анимации.|
|[CAnimationBaseObject::СозданиеПереходы](#createtransitions)|Создает переходы, связанные с объектом анимации.|
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|Отсоединяет объект анимации от родительского контроллера анимации.|
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Настройка обработчика событий Integer Значение изменено.|
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|Настройка обработчика событий изменения значения.|
|[CAnimationBaseObject:GetAutodestroyПереходы](#getautodestroytransitions)|Сообщает, уничтожается ли связанный переход автоматически.|
|[CAnimationBaseObject:GetGroupID](#getgroupid)|Возвращает текущий идентификатор группы.|
|[CAnimationBaseObject::GetObjectID](#getobjectid)|Возвращает текущий идентификатор объекта.|
|[CAnimationBaseObject::GetUserData](#getuserdata)|Возвращает данные, определяемые пользователем.|
|[CAnimationBaseObject:SetAutodestroyПереходы](#setautodestroytransitions)|Устанавливает флаг для автоматического уничтожения переходов.|
|[CAnimationBaseObject::SetID](#setid)|Устанавливает новые иди.|
|[CAnimationBaseObject::SetUserData](#setuserdata)|Устанавливает данные, определяемые пользователем.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|Собирает указатели на содержащиеся переменные анимации.|
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|Устанавливает связь между переменными анимации, содержащимися в объекте анимации, и их контейнером.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Уточняется, должны ли связанные переходы автоматически уничтожаться.|
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|Хранит данные, определяемые пользователем.|
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|Определяет идентификатор группы объекта анимации.|
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|Определяет идентификатор объекта объекта анимации.|
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|Указатель на контроллер родительской анимации.|

## <a name="remarks"></a>Примечания

Этот класс реализует основные методы для всех объектов анимации. Объект анимации может представлять значение, точку, размер, прямоугольник или цвет в приложении, а также любую пользовательскую сущность. Объекты анимации хранятся в группах анимации (см. CAnimationGroup). Каждая группа может быть анимирована отдельно и может рассматриваться как аналог раскадровки. Объект анимации инкапсулирует одну или несколько переменных анимации (см. CAnimationVariable), в зависимости от его логического представления. Например, CAnimationRect содержит четыре переменные анимации - по одной переменной для каждой стороны прямоугольника. Каждый класс объектов анимации предоставляет перегруженный метод AddTransition, который должен использоваться для применения переходов к инкапсулированным переменным анимации. Объект анимации может быть идентифицирован по идентификатору Object (по желанию) и идентификатору группы. Идентификатор группы необходим для размещения объекта анимации для коррекции группы, но если идентификатор группы не указан, объект помещается в группу по умолчанию с идентификатором 0. Если вы называете SetID с другим GroupID, объект анимации будет перемещен в другую группу (при необходимости создается новая группа).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationBaseObject`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="_dtorcanimationbaseobject"></a>CAnimationBaseObject:: »CAnimationBaseObject

Деструктор Вызывается при уничтожении объекта анимации.

```
virtual ~CAnimationBaseObject();
```

## <a name="canimationbaseobjectapplytransitions"></a><a name="applytransitions"></a>CAnimationBaseObject:ApplyПереходы

Добавляет переходы к раскадровке с инкапсулированной переменной анимации.

```
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку.

*bDependOnKeyframes*<br/>
При FALSE этот метод добавляет только те переходы, которые не зависят от ключевых кадров.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если переходы были добавлены успешно.

### <a name="remarks"></a>Примечания

Добавляет связанные переходы, которые были добавлены с AddTransition (перегруженные методы в производных классах), к раскадровке.

## <a name="canimationbaseobjectcanimationbaseobject"></a><a name="canimationbaseobject"></a>CAnimationBaseObject::CAnimationBaseObject

Строит объект анимации.

```
CAnimationBaseObject();

CAnimationBaseObject(
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*nGroupID*<br/>
Определяет идентификатор группы.

*nObjectID*<br/>
Определяет идентификатор объекта.

*dwUserData*<br/>
Данные, определяемые пользователем, которые могут быть связаны с объектом анимации и извлечены позже во время выполнения.

### <a name="remarks"></a>Примечания

Строит объекты анимации и присваивает идентификатор объекта по умолчанию (0) и идентификатор группы (0).

## <a name="canimationbaseobjectcleartransitions"></a><a name="cleartransitions"></a>CAnimationBaseObject::ClearTransitions

Удаляет все связанные переходы.

```
virtual void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Параметры

*bAutodestroy*<br/>
Определяет, следует ли уничтожать объекты перехода автоматически или просто удалить их из соответствующего списка.

### <a name="remarks"></a>Примечания

Удаляет все связанные переходы и уничтожает их, если bAutodestroy или m_bAutodestroyTransitions флаг является правдой. Переходы должны быть уничтожены автоматически только в том случае, если они не выделены в стеке. Если вышеуказанные флаги FALSE, переходы просто удаляются из внутреннего списка связанных переходов.

## <a name="canimationbaseobjectcontainsvariable"></a><a name="containsvariable"></a>CAnimationBaseObject::Содержитпеременный

Определяет, содержит ли объект анимации определенную переменную анимации.

```
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>Параметры

*pПеременный*<br/>
Указатель на переменную анимации.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если переменная анимации содержится в объекте анимации; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Этот метод может быть использован для определения того, содержится ли переменная анимации, указанная pVariable, в объекте анимации. Объект анимации, в зависимости от его типа, может содержать несколько переменных анимации. Например, CAnimationColor содержит три переменные, по одной для каждого цветного компонента (красный, зеленый и синий). При изменении значения переменной анимации API Windows Animation API отправляет события ValueChanged или IntegerValueChanged (если включено), а параметр этого события является указателем для интерфейса IUIAnimationVariable переменной анимации. Этот метод помогает получить указатель на анимацию от указателя до содержащегося объекта COM.

## <a name="canimationbaseobjectcreatetransitions"></a><a name="createtransitions"></a>CAnimationBaseObject::СозданиеПереходы

Создает переходы, связанные с объектом анимации.

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если переходы были созданы успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Циклы над списком переменных анимации, инкапсулированных в производных объектах анимации и создают переходы, связанные с каждой переменной анимации.

## <a name="canimationbaseobjectdetachfromcontroller"></a><a name="detachfromcontroller"></a>CAnimationBaseObject::DetachFromController

Отсоединяет объект анимации от родительского контроллера анимации.

```cpp
void DetachFromController();
```

### <a name="remarks"></a>Примечания

Этот метод используется внутренне.

## <a name="canimationbaseobjectenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>CAnimationBaseObject::EnableIntegerValueChangedEvent

Настройка обработчика событий Integer Значение изменено.

```
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
Определяет, включать или отключать событие Integer Value Изменено.

### <a name="remarks"></a>Примечания

Если включен обработчик события Integer Value Changed, вы можете справиться с этим событием в CAnimationController::OnAnimationIntegerValue, который должен быть переопределен в классе, полученном cAnimationController. Этот метод вызывается каждый раз, когда значение анимации рядом изменилось.

## <a name="canimationbaseobjectenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>CAnimationBaseObject::EnableValueChangedEvent

Настройка обработчика событий изменения значения.

```
virtual void EnableValueChangedEvent(
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
Упоняет, включать или отключать событие Значение Изменено.

### <a name="remarks"></a>Примечания

Если обработчик события «Изменение значения» включен, можно справиться с этим событием в cAnimationController::OnAnimationValueChanged, который должен быть переопределен в классе, полученном cAnimationController. Этот метод вызывается каждый раз, когда значение анимации изменилось.

## <a name="canimationbaseobjectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationBaseObject::GetAnimationVariableList

Собирает указатели на содержащиеся переменные анимации.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& list) = 0;
```

### <a name="parameters"></a>Параметры

*list*<br/>
Список, который должен быть заполнен переменными анимации, содержащимися в объекте анимации.

### <a name="remarks"></a>Примечания

Этот чистый виртуальный метод должен быть переопределен в производном классе. Объект анимации, в зависимости от его типа, содержит одну или несколько переменных анимации. Например, CAnimationPoint содержит две переменные для координат X и Y соответственно. Базовый класс CAnimationBaseObject реализует некоторые общие методы, которые действуют по списку переменных анимации: ApplyTransitions, ClearTransitions, EnableValueChangedEvent, EnableIntegerValueChangedEvent. Эти методы называют GetAnimationVariableList, который заполняется в производном классе с фактическими переменными анимации, содержащимися в определенном объекте анимации, затем цикл над списком и выполнять необходимые действия. При создании пользовательского объекта анимации необходимо добавить в *список* всех переменных анимации, содержащихся в этом объекте.

## <a name="canimationbaseobjectgetautodestroytransitions"></a><a name="getautodestroytransitions"></a>CAnimationBaseObject:GetAutodestroyПереходы

Сообщает, уничтожается ли связанный переход автоматически.

```
BOOL GetAutodestroyTransitions() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если true, связанные переходы уничтожаются автоматически; если FALSE, объекты перехода должны быть рассмотрены путем вызова приложения.

### <a name="remarks"></a>Примечания

По умолчанию этот флаг является правдой. Установите этот флаг только в том случае, если вы выделили переход в стеке и/или переходы, которые должны быть распределены по вызывающей заявке.

## <a name="canimationbaseobjectgetgroupid"></a><a name="getgroupid"></a>CAnimationBaseObject:GetGroupID

Возвращает текущий идентификатор группы.

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий идентификатор группы.

### <a name="remarks"></a>Примечания

Используйте этот метод для получения идентификатора группы. Это 0, если идентификатор группы не был установлен явно в конструкторе или с SetID.

## <a name="canimationbaseobjectgetobjectid"></a><a name="getobjectid"></a>CAnimationBaseObject::GetObjectID

Возвращает текущий идентификатор объекта.

```
UINT32 GetObjectID() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий идентификатор объекта.

### <a name="remarks"></a>Примечания

Используйте этот метод для получения идентификатора объекта. Это 0, если идентификатор объекта не был установлен явно в конструкторе или с SetID.

## <a name="canimationbaseobjectgetuserdata"></a><a name="getuserdata"></a>CAnimationBaseObject::GetUserData

Возвращает данные, определяемые пользователем.

```
DWORD GetUserData() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение пользовательских данных.

### <a name="remarks"></a>Примечания

Вызовите этот метод для извлечения пользовательских данных во время выполнения. Возвратное значение будет 0, если оно не было явно инициализировано в конструкторе или в SetUserData.

## <a name="canimationbaseobjectm_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>CAnimationBaseObject::m_bAutodestroyTransitions

Уточняется, должны ли связанные переходы автоматически уничтожаться.

```
BOOL m_bAutodestroyTransitions;
```

## <a name="canimationbaseobjectm_dwuserdata"></a><a name="m_dwuserdata"></a>CAnimationBaseObject::m_dwUserData

Хранит данные, определяемые пользователем.

```
DWORD m_dwUserData;
```

## <a name="canimationbaseobjectm_ngroupid"></a><a name="m_ngroupid"></a>CAnimationBaseObject::m_nGroupID

Определяет идентификатор группы объекта анимации.

```
UINT32 m_nGroupID;
```

## <a name="canimationbaseobjectm_nobjectid"></a><a name="m_nobjectid"></a>CAnimationBaseObject::m_nObjectID

Определяет идентификатор объекта объекта анимации.

```
UINT32 m_nObjectID;
```

## <a name="canimationbaseobjectm_pparentcontroller"></a><a name="m_pparentcontroller"></a>CAnimationBaseObject::m_pParentController

Указатель на контроллер родительской анимации.

```
CAnimationController* m_pParentController;
```

## <a name="canimationbaseobjectsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>CAnimationBaseObject:SetAutodestroyПереходы

Устанавливает флаг для автоматического уничтожения переходов.

```cpp
void SetAutodestroyTransitions(BOOL bValue);
```

### <a name="parameters"></a>Параметры

*bValue*<br/>
Определяет автоматический флаг уничтожения.

### <a name="remarks"></a>Примечания

Установите этот флаг только в том случае, если вы выделили объекты перехода с помощью нового оператора. Если по какой-либо причине объекты перехода выделены на стек, автоматический флаг уничтожения должен быть FALSE. По умолчанию этот флаг является правдой.

## <a name="canimationbaseobjectsetid"></a><a name="setid"></a>CAnimationBaseObject::SetID

Устанавливает новые иди.

```cpp
void SetID(
    UINT32 nObjectID,
    UINT32 nGroupID = 0);
```

### <a name="parameters"></a>Параметры

*nObjectID*<br/>
Определяет новый идентификатор объекта.

*nGroupID*<br/>
Упогоняет новый идентификатор группы.

### <a name="remarks"></a>Примечания

Позволяет изменить идентификатор объекта и идентификатор группы. Если новый идентификатор группы отличается от текущего идентификатора, объект анимации перемещается в другую группу (при необходимости будет создана новая группа).

## <a name="canimationbaseobjectsetparentanimationobjects"></a><a name="setparentanimationobjects"></a>CAnimationBaseObject::SetParentAnimationObjects

Устанавливает связь между переменными анимации, содержащимися в объекте анимации, и их контейнером.

```
virtual void SetParentAnimationObjects();
```

### <a name="remarks"></a>Примечания

Этот помощник может быть использован для установления взаимосвязи между переменными анимации, содержащимися в объекте анимации, и их контейнером. Он зацикливает над переменными анимации и устанавливает указатель на объект родительской анимации для каждой переменной анимации. В текущей реализации фактическое отношение устанавливается в CAnimationBaseObject::ApplyTransitions, поэтому указатели возврата не устанавливаются до тех пор, пока вы не позвоните cAnimationGroup::Animate. Знание взаимосвязи может быть полезно при обработке событий и необходимости получения родительского объекта анимации от CAnimationVariable. Используйте CAnimationVariable::GetParentAnimationObject.

## <a name="canimationbaseobjectsetuserdata"></a><a name="setuserdata"></a>CAnimationBaseObject::SetUserData

Устанавливает данные, определяемые пользователем.

```cpp
void SetUserData (DWORD dwUserData);
```

### <a name="parameters"></a>Параметры

*dwUserData*<br/>
Определяет пользовательские данные.

### <a name="remarks"></a>Примечания

Используйте этот метод для ассоциации пользовательских данных с объектом анимации. Эти данные могут быть получены позже во время выполнения GetUserData.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
