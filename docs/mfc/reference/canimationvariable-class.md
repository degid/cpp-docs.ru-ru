---
title: Класс CAnimationVariable
ms.date: 03/27/2019
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
ms.openlocfilehash: b53a1338566a329fbdf5b91c41d0411a529afe8d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755068"
---
# <a name="canimationvariable-class"></a>Класс CAnimationVariable

Представляет переменную анимации.

## <a name="syntax"></a>Синтаксис

```
class CAnimationVariable;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationПеременный::CAnimationПеременный](#canimationvariable)|Строит объект переменной анимации.|
|[CAnimationПеременный вариант:::»CAnimationПеременный](#_dtorcanimationvariable)|Деструктор Вызывается при уничтожении объекта CAnimationVariable.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationПеременный::AddПереход](#addtransition)|Добавляет переход.|
|[CAnimationПеременный::ApplyTransitions](#applytransitions)|Добавляет переходы из внутреннего списка в раскадровку.|
|[CAnimationПеременный::ЯсныеПереходы](#cleartransitions)|Очищает переходы.|
|[CAnimationПеременный::Создание](#create)|Создает базовый объект переменной анимации COM.|
|[CAnimationПеременный::СозданиеПереходы](#createtransitions)|Создает все переходы, которые должны быть применены к этой переменной анимации.|
|[CAnimationПеременный:EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|Включает или отменяет событие IntegerValueChanged.|
|[CAnimationПеременный::EnableValueChangedEvent](#enablevaluechangedevent)|Позволяет или отменяет событие ValueChanged.|
|[CAnimationПеременный::GetDefaultValue](#getdefaultvalue)|Возвращает значение по умолчанию.|
|[CAnimationПеременный::GetParentAnimationObject](#getparentanimationobject)|Возвращает родительский объект анимации.|
|[CAnimationПеременный::GetValue](#getvalue)|Перегружен. Возвращает текущее значение переменной анимации.|
|[CAnimationПеременный::GetVariable](#getvariable)|Возвращает указатель на объект IUIAnimationVariable COM.|
|[CAnimationПеременный::SetDefaultValue](#setdefaultvalue)|Устанавливает значение по умолчанию и выпускает объект IUIAnimationVariable COM.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationПеременный::SetParentAnimationObject](#setparentanimationobject)|Устанавливает связь между переменной анимации и объектом анимации.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationПеременный::m_bAutodestroyTransitions](#m_bautodestroytransitions)|Определяет, следует ли удалять связанные объекты перехода.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationПеременный::m_dblDefaultValue](#m_dbldefaultvalue)|Определяет значение по умолчанию, которое распространяется на IUIAnimationVariable.|
|[CAnimationПеременный::m_lstTransitions](#m_lsttransitions)|Содержит список переходов, которые оживляют эту переменную анимации.|
|[CAnimationПеременный::m_pParentObject](#m_pparentobject)|Указатель на объект анимации, который инкапсулирует эту переменную анимации.|
|[CAnimationПеременный::m_variable](#m_variable)|Хранит указатель на объект IUIAnimationVariable COM. NULL, если объект COM еще не создан, или если создание не удалось.|

## <a name="remarks"></a>Примечания

Класс CAnimationVariable инкапсулирует объект IUIAnimationVariable COM. Он также содержит список переходов, которые будут применяться к переменной анимации в раскадровке. CAnimationПеременные объекты встроены в объекты анимации, которые могут представлять в приложении анимированное значение, точку, размер, цвет и прямоугольник.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CAnimationVariable`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationvariablecanimationvariable"></a><a name="_dtorcanimationvariable"></a>CAnimationПеременный вариант:::»CAnimationПеременный

Деструктор Вызывается при уничтожении объекта CAnimationVariable.

```
virtual ~CAnimationVariable();
```

## <a name="canimationvariableaddtransition"></a><a name="addtransition"></a>CAnimationПеременный::AddПереход

Добавляет переход.

```cpp
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Параметры

*pTransition*<br/>
Указатель на переход для добавления.

### <a name="remarks"></a>Примечания

Этот метод называется для добавления перехода во внутренний список переходов, которые будут применяться к переменной анимации. Этот список должен быть очищен, когда анимация была запланирована.

## <a name="canimationvariableapplytransitions"></a><a name="applytransitions"></a>CAnimationПеременный::ApplyTransitions

Добавляет переходы из внутреннего списка в раскадровку.

```cpp
void ApplyTransitions(
    CAnimationController* pController,
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на контроллер родительской анимации.

*pStoryboard*<br/>
Указатель на раскадровку.

*bDependOnKeyframes*<br/>
ПРАВДА, если этот метод должен добавить переходы, которые зависят от ключевых кадров.

### <a name="remarks"></a>Примечания

Этот метод добавляет переходы из внутреннего списка в раскадровку. Он несколько раз вызывается из кода верхнего уровня, чтобы добавить переходы, которые не зависят от ключевых кадров, и добавить переходы, зависят от ключевых кадров. Если базовый объект переменной анимации COM не создан, этот метод создает его на этом этапе.

## <a name="canimationvariablecanimationvariable"></a><a name="canimationvariable"></a>CAnimationПеременный::CAnimationПеременный

Строит объект переменной анимации.

```
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```

### <a name="parameters"></a>Параметры

*dblDefaultValue*<br/>
Определяет значение по умолчанию.

### <a name="remarks"></a>Примечания

Строит объект переменной анимации и устанавливает его значение по умолчанию. Значение по умолчанию используется, когда переменная не анимирована или не может быть анимирована.

## <a name="canimationvariablecleartransitions"></a><a name="cleartransitions"></a>CAnimationПеременный::ЯсныеПереходы

Очищает переходы.

```cpp
void ClearTransitions(BOOL bAutodestroy);
```

### <a name="parameters"></a>Параметры

*bAutodestroy*<br/>
Уточняется, следует ли удалять объекты перехода.

### <a name="remarks"></a>Примечания

Этот метод удаляет все переходы из внутреннего списка переходов. Если bAutodestroy является правдой, или m_bAutodestroyTransitions является правдой, то переходы удаляются. В противном случае абонент должен распределить объекты перехода.

## <a name="canimationvariablecreate"></a><a name="create"></a>CAnimationПеременный::Создание

Создает базовый объект переменной анимации COM.

```
virtual BOOL Create(IUIAnimationManager* pManager);
```

### <a name="parameters"></a>Параметры

*pManager*<br/>
Указатель на менеджера анимации.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если переменная анимации была успешно создана; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Этот метод создает базовую переменную анимации COM объекта и устанавливает его значение по умолчанию.

## <a name="canimationvariablecreatetransitions"></a><a name="createtransitions"></a>CAnimationПеременный::СозданиеПереходы

Создает все переходы, которые должны быть применены к этой переменной анимации.

```
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на [интерфейс IUIAnimationTransitionLibrary,](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если переходы были созданы успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Этот метод вызывается инфраструктурой, когда ему необходимо создать переходы, которые были добавлены во внутренний список переходов переменной.

## <a name="canimationvariableenableintegervaluechangedevent"></a><a name="enableintegervaluechangedevent"></a>CAnimationПеременный:EnableIntegerValueChangedEvent

Включает или отменяет событие IntegerValueChanged.

```cpp
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
TRUE - включить событие, FALSE - отключить событие.

### <a name="remarks"></a>Примечания

Когда событие ValueChanged включено, фреймворк вызывает виртуальный метод CAnimationController::OnAnimationIntegerValue. Для обработки этого события необходимо переопределить его в классе, полученном от CAnimationController. Этот метод вызывается каждый раз, когда изменяется значение аналог переменной анимации.

## <a name="canimationvariableenablevaluechangedevent"></a><a name="enablevaluechangedevent"></a>CAnimationПеременный::EnableValueChangedEvent

Позволяет или отменяет событие ValueChanged.

```cpp
void EnableValueChangedEvent (
    CAnimationController* pController,
    BOOL bEnable);
```

### <a name="parameters"></a>Параметры

*pController*<br/>
Указатель на родительский контроллер.

*bEnable*<br/>
TRUE - включить событие, FALSE - отключить событие.

### <a name="remarks"></a>Примечания

Когда событие ValueChanged включено, фреймворк вызывает виртуальный метод CAnimationController::OnAnimationValueChanged. Для обработки этого события необходимо переопределить его в классе, полученном от CAnimationController. Этот метод вызывается каждый раз, когда изменяется переменная анимации.

## <a name="canimationvariablegetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationПеременный::GetDefaultValue

Возвращает значение по умолчанию.

```
DOUBLE GetDefaultValue() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение по умолчанию.

### <a name="remarks"></a>Примечания

Используйте эту функцию для получения значения анимации по умолчанию. Значение по умолчанию может быть установлено в конструкторе или методе SetDefaultValue.

## <a name="canimationvariablegetparentanimationobject"></a><a name="getparentanimationobject"></a>CAnimationПеременный::GetParentAnimationObject

Возвращает родительский объект анимации.

```
CAnimationBaseObject* GetParentAnimationObject();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект родительской анимации, если связь была установлена, в противном случае NULL.

### <a name="remarks"></a>Примечания

Этот метод можно вызвать для получения указателя на объект родительской анимации (контейнер).

## <a name="canimationvariablegetvalue"></a><a name="getvalue"></a>CAnimationПеременный::GetValue

Возвращает текущее значение переменной анимации.

```
HRESULT GetValue(DOUBLE& dblValue);
HRESULT GetValue(INT32& nValue);
```

### <a name="parameters"></a>Параметры

*dblValue*<br/>
Текущее значение переменной анимации.

*nValue*<br/>
Текущее значение переменной анимации.

### <a name="return-value"></a>Возвращаемое значение

S_OK если значение было получено успешно, или базовая переменная анимации не была создана. В противном случае код ошибки HRESULT.

### <a name="remarks"></a>Примечания

Этот метод можно вызвать для получения текущего значения переменной анимации. Если базовый объект COM не создан, dblValue будет содержать значение по умолчанию при возврате функции.

## <a name="canimationvariablegetvariable"></a><a name="getvariable"></a>CAnimationПеременный::GetVariable

Возвращает указатель на объект IUIAnimationVariable COM.

```
IUIAnimationVariable* GetVariable();
```

### <a name="return-value"></a>Возвращаемое значение

Действительный указатель на объект IUIAnimationVariable COM, или NULL, если переменная анимации не была создана или не может быть создана.

### <a name="remarks"></a>Примечания

Используйте эту функцию, чтобы получить доступ к базовому объекту IUIAnimationVariable COM и при необходимости назовем его методы напрямую.

## <a name="canimationvariablem_bautodestroytransitions"></a><a name="m_bautodestroytransitions"></a>CAnimationПеременный::m_bAutodestroyTransitions

Определяет, следует ли удалять связанные объекты перехода.

```
BOOL m_bAutodestroyTransitions;
```

### <a name="remarks"></a>Примечания

Установите это значение для TRUE, чтобы заставить удаление объектов перехода, когда они удаляются из внутреннего списка переходов. Если это значение FALSE, переходы должны быть удалены, вызывая приложение. Список переходов всегда очищается после запланированного анимации. Значение по умолчанию — FALSE.

## <a name="canimationvariablem_dbldefaultvalue"></a><a name="m_dbldefaultvalue"></a>CAnimationПеременный::m_dblDefaultValue

Определяет значение по умолчанию, которое распространяется на IUIAnimationVariable.

```
DOUBLE m_dblDefaultValue;
```

## <a name="canimationvariablem_lsttransitions"></a><a name="m_lsttransitions"></a>CAnimationПеременный::m_lstTransitions

Содержит список переходов, которые оживляют эту переменную анимации.

```
CObList m_lstTransitions;
```

## <a name="canimationvariablem_pparentobject"></a><a name="m_pparentobject"></a>CAnimationПеременный::m_pParentObject

Указатель на объект анимации, который инкапсулирует эту переменную анимации.

```
CAnimationBaseObject* m_pParentObject;
```

## <a name="canimationvariablem_variable"></a><a name="m_variable"></a>CAnimationПеременный::m_variable

Хранит указатель на объект IUIAnimationVariable COM. NULL, если объект COM еще не создан, или если создание не удалось.

```
ATL::CComPtr<IUIAnimationVariable> m_variable;
```

## <a name="canimationvariablesetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationПеременный::SetDefaultValue

Устанавливает значение по умолчанию и выпускает объект IUIAnimationVariable COM.

```cpp
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Параметры

*dblDefaultValue*<br/>
Определяет новое значение по умолчанию.

### <a name="remarks"></a>Примечания

Используйте этот метод для сбросить значение по умолчанию. Этот метод выпускает внутренний объект IUIAnimationVariable COM, поэтому при воссоздании переменной анимации основной объект COM получает новое значение по умолчанию. Значение по умолчанию возвращается GetValue, если объект COM, представляющий переменную анимации, не создан, или если переменная не была анимирована.

## <a name="canimationvariablesetparentanimationobject"></a><a name="setparentanimationobject"></a>CAnimationПеременный::SetParentAnimationObject

Устанавливает связь между переменной анимации и объектом анимации.

```cpp
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```

### <a name="parameters"></a>Параметры

*pParentObject*<br/>
Указатель на объект анимации, содержащий эту переменную.

### <a name="remarks"></a>Примечания

Этот метод называется внутренне, чтобы установить связь один-к-одному между переменной анимации и объектом анимации, который инкапсулирует ее.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
