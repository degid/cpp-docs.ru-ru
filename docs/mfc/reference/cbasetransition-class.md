---
title: Класс CBaseTransition
ms.date: 03/27/2019
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
ms.openlocfilehash: 9abe4ae55d9d84ea435cd5d82925ff8b8a544480
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752961"
---
# <a name="cbasetransition-class"></a>Класс CBaseTransition

Представляет базовый переход.

## <a name="syntax"></a>Синтаксис

```
class CBaseTransition : public CObject;
```

## <a name="members"></a>Участники

### <a name="public-enumerations"></a>Открытые перечисления

|Имя|Описание|
|----------|-----------------|
|[CBaseПереход:::TRANSITION_TYPE Иномерация](#transition_type_enumeration)|Определяет типы переходов, поддерживаемые в настоящее время внедрением MFC API анимации Windows.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBaseПереход::CBaseПереход](#cbasetransition)|Строит базовый переходный объект.|
|[CBaseПереход::](#_dtorcbasetransition)|Деструктор Вызывается при уничтожении объекта перехода.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBaseTransition::AddtoStoryboard](#addtostoryboard)|Добавляет переход к раскадровке.|
|[CBaseПереход::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|Добавляет переход к раскадровке.|
|[CBaseПереход::Ясно](#clear)|Выпускает инкапсулированный объект IUIAnimationTransition COM.|
|[CBaseПереход::Создание](#create)|Создает переход COM.|
|[CBaseПереход::GetEndKeyframe](#getendkeyframe)|Возвращает запуск ключевой кадра.|
|[CBaseПереход::GetRelatedVariable](#getrelatedvariable)|Возвращает указатель на соответствующую переменную.|
|[CBaseПереход::GetStartKeyframe](#getstartkeyframe)|Возвращает запуск ключевой кадра.|
|[CBaseПереход::GetTransition](#gettransition)|Перегружен. Возвращает указатель на базовый объект перехода COM.|
|[CBaseПереход::GetType](#gettype)|Возвращает тип перехода.|
|[CBaseПереход::Добавлено](#isadded)|Сообщает, был ли добавлен переход в раскадровку.|
|[CBaseПереход::SetKeyframes](#setkeyframes)|Устанавливает ключевые кадры для перехода.|
|[CBaseПереход::SetСвязанныйПеременный](#setrelatedvariable)|Устанавливает связь между переменной анимации и переходом.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CBaseПереход::m_bAdded](#m_badded)|Уточняется, был ли добавлен переход в раскадровку.|
|[CBaseПереход::m_pEndKeyframe](#m_pendkeyframe)|Хранит указатель на клавиатуру, которая определяет конец перехода.|
|[CBaseПереход::m_pRelatedVariable](#m_prelatedvariable)|Указатель на переменную анимации, которая анимируется с переходом, хранящимся в m_transition.|
|[CBaseПереход:::m_pStartKeyframe](#m_pstartkeyframe)|Хранит указатель на клавиатуру, которая определяет начало перехода.|
|[CBaseПереход::m_transition](#m_transition)|Хранит указатель на IUIAnimationTransition. NULL, если объект перехода COM не создан.|
|[CBaseПереход::m_type](#m_type)|Хранит тип перехода.|

## <a name="remarks"></a>Примечания

Этот класс инкапсулирует интерфейс IUIAnimationTransition и служит базовым классом для всех переходов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CBaseTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="cbasetransitioncbasetransition"></a><a name="_dtorcbasetransition"></a>CBaseПереход::

Деструктор Вызывается при уничтожении объекта перехода.

```
virtual ~CBaseTransition();
```

## <a name="cbasetransitionaddtostoryboard"></a><a name="addtostoryboard"></a>CBaseTransition::AddtoStoryboard

Добавляет переход к раскадровке.

```
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку, которая будет оживить соответствующую переменную.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если переход был успешно добавлен в раскадровку.

### <a name="remarks"></a>Примечания

Применяет переход к соответствующей переменной в раскадровке. Если это первый переход, применяемый к этой переменной в этой раскадровке, переход начинается в начале раскадровки. В противном случае переход прилагается к переходу, добавленному совсем недавно к переменной.

## <a name="cbasetransitionaddtostoryboardatkeyframes"></a><a name="addtostoryboardatkeyframes"></a>CBaseПереход::AddToStoryboardAtKeyframes

Добавляет переход к раскадровке.

```
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку, которая будет оживить соответствующую переменную.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если переход был успешно добавлен в раскадровку.

### <a name="remarks"></a>Примечания

Применяет переход к соответствующей переменной в раскадровке. Если был указан ключевой элемент запуска, переход начинается на этом ключевом кадре. Если конечная клавиатура была указана, переход начинается в начальной клавиатуре и останавливается на конце ключевой. Если переход был создан с указанным параметром продолжительности, эта продолжительность перезаписана с продолжительностью времени между ключами запуска и конца. Если не было указано, переход прилагается к переходу, добавленному совсем недавно к переменной.

## <a name="cbasetransitioncbasetransition"></a><a name="cbasetransition"></a>CBaseПереход::CBaseПереход

Строит базовый переходный объект.

```
CBaseTransition();
```

## <a name="cbasetransitionclear"></a><a name="clear"></a>CBaseПереход::Ясно

Выпускает инкапсулированный объект IUIAnimationTransition COM.

```cpp
void Clear();
```

### <a name="remarks"></a>Примечания

Этот метод следует вызывать из метода создания производного класса, чтобы предотвратить утечку интерфейса IUITransition.

## <a name="cbasetransitioncreate"></a><a name="create"></a>CBaseПереход::Создание

Создает переход COM.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory) = 0;
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на библиотеку перехода, которая создает стандартные переходы. Это может быть NULL для пользовательских переходов.

*pFactory*<br/>
Указатель на фабрику перехода, которая создает пользовательские переходы. Это может быть NULL для стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если объект transition COM был создан успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Это чистая виртуальная функция, которая должна быть переопределена в производном классе. Она называется инфраструктурой для мгновенного мгновенного изменения базового объекта перехода COM.

## <a name="cbasetransitiongetendkeyframe"></a><a name="getendkeyframe"></a>CBaseПереход::GetEndKeyframe

Возвращает запуск ключевой кадра.

```
CBaseKeyFrame* GetEndKeyframe();
```

### <a name="return-value"></a>Возвращаемое значение

Действительный указатель на ключевой кадр, или NULL, если переход не должен быть вставлен между ключевыми кадрами.

### <a name="remarks"></a>Примечания

Этот метод можно использовать для доступа к объекту клавиатуры, который ранее был установлен SetKeyframes. Это называется кодом верхнего уровня, когда переходы добавляются в раскадровку.

## <a name="cbasetransitiongetrelatedvariable"></a><a name="getrelatedvariable"></a>CBaseПереход::GetRelatedVariable

Возвращает указатель на соответствующую переменную.

```
CAnimationVariable* GetRelatedVariable();
```

### <a name="return-value"></a>Возвращаемое значение

Действительный указатель на переменную анимации, или NULL, если переменная анимации не была установлена SetRelatedVariable.

### <a name="remarks"></a>Примечания

Это аксессуар к соответствующей переменной анимации.

## <a name="cbasetransitiongetstartkeyframe"></a><a name="getstartkeyframe"></a>CBaseПереход::GetStartKeyframe

Возвращает запуск ключевой кадра.

```
CBaseKeyFrame* GetStartKeyframe();
```

### <a name="return-value"></a>Возвращаемое значение

Действительный указатель на ключевой кадр, или NULL, если переход не должен начинаться после ключа.

### <a name="remarks"></a>Примечания

Этот метод можно использовать для доступа к объекту клавиатуры, который ранее был установлен SetKeyframes. Это называется кодом верхнего уровня, когда переходы добавляются в раскадровку.

## <a name="cbasetransitiongettransition"></a><a name="gettransition"></a>CBaseПереход::GetTransition

Возвращает указатель на базовый объект перехода COM.

```
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* pFactory);

IUIAnimationTransition* GetTransition();
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на библиотеку перехода, которая создает стандартные переходы. Это может быть NULL для пользовательских переходов.

*pFactory*<br/>
Указатель на фабрику перехода, которая создает пользовательские переходы. Это может быть NULL для стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

Действительный указатель на IUIAnimationTransition или NULL, если базовый переход не может быть создан.

### <a name="remarks"></a>Примечания

Этот метод возвращает указатель на базовый объект перехода COM и при необходимости создает его.

## <a name="cbasetransitiongettype"></a><a name="gettype"></a>CBaseПереход::GetType

Возвращает тип перехода.

```
TRANSITION_TYPE GetType() const;
```

### <a name="return-value"></a>Возвращаемое значение

Одно из TRANSITION_TYPE перечисленных значений.

### <a name="remarks"></a>Примечания

Этот метод можно использовать для определения объекта перехода по его типу. Тип устанавливается в конструкторе в производном классе.

## <a name="cbasetransitionisadded"></a><a name="isadded"></a>CBaseПереход::Добавлено

Сообщает, был ли добавлен переход в раскадровку.

```
BOOL IsAdded();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если переход был добавлен в раскадровку, в противном случае FALSE.

### <a name="remarks"></a>Примечания

Этот флаг устанавливается внутренне, когда код верхнего уровня добавляет переходы к раскадровке.

## <a name="cbasetransitionm_badded"></a><a name="m_badded"></a>CBaseПереход::m_bAdded

Уточняется, был ли добавлен переход в раскадровку.

```
BOOL m_bAdded;
```

## <a name="cbasetransitionm_pendkeyframe"></a><a name="m_pendkeyframe"></a>CBaseПереход::m_pEndKeyframe

Хранит указатель на клавиатуру, которая определяет конец перехода.

```
CBaseKeyFrame* m_pEndKeyframe;
```

## <a name="cbasetransitionm_prelatedvariable"></a><a name="m_prelatedvariable"></a>CBaseПереход::m_pRelatedVariable

Указатель на переменную анимации, которая анимируется с переходом, хранящимся в m_transition.

```
CAnimationVariable* m_pRelatedVariable;
```

## <a name="cbasetransitionm_pstartkeyframe"></a><a name="m_pstartkeyframe"></a>CBaseПереход:::m_pStartKeyframe

Хранит указатель на клавиатуру, которая определяет начало перехода.

```
CBaseKeyFrame* m_pStartKeyframe;
```

## <a name="cbasetransitionm_transition"></a><a name="m_transition"></a>CBaseПереход::m_transition

Хранит указатель на IUIAnimationTransition. NULL, если объект перехода COM не создан.

```
ATL::CComPtr<IUIAnimationTransition> m_transition;
```

## <a name="cbasetransitionm_type"></a><a name="m_type"></a>CBaseПереход::m_type

Хранит тип перехода.

```
TRANSITION_TYPE m_type;
```

## <a name="cbasetransitionsetkeyframes"></a><a name="setkeyframes"></a>CBaseПереход::SetKeyframes

Устанавливает ключевые кадры для перехода.

```cpp
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,
    CBaseKeyFrame* pEnd = NULL);
```

### <a name="parameters"></a>Параметры

*pStart*<br/>
Ключевая рамка, опоначальнащая начало перехода.

*pEnd*<br/>
Ключевая рамка, опоедая конец перехода.

### <a name="remarks"></a>Примечания

Этот метод сообщает о переходе к запуску после указанного ключевого кадра и, по желанию, если pEnd не является NULL, заканчивается до указанного ключевого кадра. Если переход был создан с указанным параметром продолжительности, эта продолжительность перезаписана с продолжительностью времени между ключами запуска и конца.

## <a name="cbasetransitionsetrelatedvariable"></a><a name="setrelatedvariable"></a>CBaseПереход::SetСвязанныйПеременный

Устанавливает связь между переменной анимации и переходом.

```cpp
void SetRelatedVariable(CAnimationVariable* pVariable);
```

### <a name="parameters"></a>Параметры

*pПеременный*<br/>
Указатель на соответствующую переменную анимации.

### <a name="remarks"></a>Примечания

Устанавливает связь между переменной анимации и переходом. Переход может применяться только к одной переменной.

## <a name="cbasetransitiontransition_type-enumeration"></a><a name="transition_type_enumeration"></a>CBaseПереход:::TRANSITION_TYPE Иномерация

Определяет типы переходов, поддерживаемые в настоящее время внедрением MFC API анимации Windows.

```
enum TRANSITION_TYPE;
```

### <a name="remarks"></a>Примечания

Тип перехода устанавливается в конструкторе конкретного перехода. Например, CSinusoidalTransitionFromRange устанавливает свой тип для SINUSOIDAL_FROM_RANGE.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
