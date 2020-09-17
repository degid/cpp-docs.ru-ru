---
title: Класс CAnimationSize
ms.date: 11/04/2016
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
helpviewer_keywords:
- CAnimationSize [MFC], CAnimationSize
- CAnimationSize [MFC], AddTransition
- CAnimationSize [MFC], GetCX
- CAnimationSize [MFC], GetCY
- CAnimationSize [MFC], GetDefaultValue
- CAnimationSize [MFC], GetValue
- CAnimationSize [MFC], SetDefaultValue
- CAnimationSize [MFC], GetAnimationVariableList
- CAnimationSize [MFC], m_cxValue
- CAnimationSize [MFC], m_cyValue
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
ms.openlocfilehash: 1f4a5b8b52d8bd37d1ed83618e7451dd85f84c32
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755118"
---
# <a name="canimationsize-class"></a>Класс CAnimationSize

Реализует функции объекта размера, размеры которого могут быть анимированы.

## <a name="syntax"></a>Синтаксис

```
class CAnimationSize : public CAnimationBaseObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationSize::CAnimationSize](#canimationsize)|Перегружен. Строит объект размера анимации.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationSize::AddTransition](#addtransition)|Добавляет переходы для ширины и высоты.|
|[CAnimationSize::GetCX](#getcx)|Предоставляет доступ к CAnimationVariable, представляющей Width.|
|[CAnimationSize::GetCY](#getcy)|Предоставляет доступ к CAnimationVariable, представляющей Высоту.|
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для ширины и высоты.|
|[CAnimationSize::GetValue](#getvalue)|Возвращает текущее значение.|
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|Устанавливает значение по умолчанию.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированные переменные анимации в список. (Оверлет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationSize::оператор CSize](#operator_csize)|Преобразует CAnimationSize в CSize.|
|[CAnimationSize::оператор](#operator_eq)|Присваивает szSrc CAnimationSize.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationSize::m_cxValue](#m_cxvalue)|Инкапсулированная переменная анимации, представляющая ширину размера анимации.|
|[CAnimationSize::m_cyValue](#m_cyvalue)|Инкапсулированная переменная анимации, представляющая высоту размера анимации.|

## <a name="remarks"></a>Примечания

Класс CAnimationSize инкапсулирует два объекта CAnimationVariable и может представлять в приложениях размер. Например, этот класс можно использовать для анимировать размер любого двумерного объекта на экране (например, прямоугольник, контроль и т.д.). Чтобы использовать этот класс в приложении, просто мгновенно объект этого класса, добавьте его в контроллер анимации с помощью CAnimationController::AddAnimationObject и вызов AddTransition для каждого перехода, который будет применяться к ширине и / или высоты.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationSize`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationsizeaddtransition"></a><a name="addtransition"></a>CAnimationSize::AddTransition

Добавляет переходы для ширины и высоты.

```cpp
void AddTransition(
    CBaseTransition* pCXTransition,
    CBaseTransition* pCYTransition);
```

### <a name="parameters"></a>Параметры

*pCXПереход*<br/>
Указатель на переход для Ширины.

*pCYTransition*<br/>
Указатель на переход для высоты.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы добавить указанные переходы во внутренний список переходов, которые будут применяться к переменным анимации для Ширины и Высоты. При добавлении переходов они не применяются немедленно и хранятся во внутреннем списке. Переходы применяются (добавлены к раскадровке для определенного значения) при вызове CAnimationController::AnimateGroup. Если вам не нужно применять переход к одному из измерений, вы можете пройти NULL.

## <a name="canimationsizecanimationsize"></a><a name="canimationsize"></a>CAnimationSize::CAnimationSize

Строит объект размера анимации.

```
CAnimationSize();

CAnimationSize(
    const CSize& szDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*szDefault*<br/>
Определяет размер по умолчанию.

*nGroupID*<br/>
Определяет идентификатор группы.

*nObjectID*<br/>
Определяет идентификатор объекта.

*dwUserData*<br/>
Определяет данные, определяемые пользователем.

### <a name="remarks"></a>Примечания

Объект построен со значениями по умолчанию для ширины, высоты, идентификатора объекта и идентификатора группы, которые будут установлены на 0. Они могут быть изменены позже во время выполнения с помощью SetDefaultValue и SetID.

## <a name="canimationsizegetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationSize::GetAnimationVariableList

Помещает инкапсулированные переменные анимации в список.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Параметры

*Lst*<br/>
Когда функция возвращается, она содержит указатели на два CAnimationПеременные объекты, представляющие ширину и высоту.

## <a name="canimationsizegetcx"></a><a name="getcx"></a>CAnimationSize::GetCX

Предоставляет доступ к CAnimationVariable, представляющей Width.

```
CAnimationVariable& GetCX();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий Width.

### <a name="remarks"></a>Примечания

Этот метод можно назвать прямым доступом к базовому CAnimationVariable, представляющему Width.

## <a name="canimationsizegetcy"></a><a name="getcy"></a>CAnimationSize::GetCY

Предоставляет доступ к CAnimationVariable, представляющей Высоту.

```
CAnimationVariable& GetCY();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий Высоту.

### <a name="remarks"></a>Примечания

Вы можете вызвать этот метод, чтобы получить прямой доступ к основной CAnimationVariable, представляющей высоту.

## <a name="canimationsizegetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationSize::GetDefaultValue

Возвращает значения по умолчанию для ширины и высоты.

```
CSize GetDefaultValue();
```

### <a name="return-value"></a>Возвращаемое значение

Объект CSize, содержащий значения по умолчанию.

### <a name="remarks"></a>Примечания

Вызовите эту функцию для получения значения по умолчанию, которое ранее было установлено конструктором или SetDefaultValue.

## <a name="canimationsizegetvalue"></a><a name="getvalue"></a>CAnimationSize::GetValue

Возвращает текущее значение.

```
BOOL GetValue(CSize& szValue);
```

### <a name="parameters"></a>Параметры

*szValue*<br/>
Выходные данные. Содержит текущее значение при возврате этого метода.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если текущее значение было успешно извлечено; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы получить текущее значение размера анимации. Если этот метод выходит из строя или базовые объекты COM для ширины и размера не были инициализированы, szValue содержит значение по умолчанию, которое ранее было установлено в конструкторе или SetDefaultValue.

## <a name="canimationsizem_cxvalue"></a><a name="m_cxvalue"></a>CAnimationSize::m_cxValue

Инкапсулированная переменная анимации, представляющая ширину размера анимации.

```
CAnimationVariable m_cxValue;
```

## <a name="canimationsizem_cyvalue"></a><a name="m_cyvalue"></a>CAnimationSize::m_cyValue

Инкапсулированная переменная анимации, представляющая высоту размера анимации.

```
CAnimationVariable m_cyValue;
```

## <a name="canimationsizeoperator-csize"></a><a name="operator_csize"></a>CAnimationSize::оператор CSize

Преобразует CAnimationSize в CSize.

```
operator CSize();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение размера анимации как CSize.

### <a name="remarks"></a>Примечания

Эта функция внутренне вызывает GetValue. Если GetValue по какой-либо причине выходит из строя, возвращенный размер будет содержать значения по умолчанию для ширины и высоты.

## <a name="canimationsizeoperator"></a><a name="operator_eq"></a>CAnimationSize::оператор

Присваивает szSrc CAnimationSize.

```cpp
void operator=(const CSize& szSrc);
```

### <a name="parameters"></a>Параметры

*szSrc*<br/>
Относится к CSize или СИЗЕ.

### <a name="remarks"></a>Примечания

Присваивает szSrc CAnimationSize. Рекомендуется сделать это до начала анимации, потому что этот оператор вызывает SetDefaultValue, который воссоздает основные объекты COM для ширины и высоты, если они были созданы. Если вы подписались на этот объект анимации на события (ValueChanged или IntegerValue), необходимо повторно включить эти события.

## <a name="canimationsizesetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationSize::SetDefaultValue

Устанавливает значение по умолчанию.

```cpp
void SetDefaultValue(const CSize& szDefault);
```

### <a name="parameters"></a>Параметры

*szDefault*<br/>
Определяет новый размер по умолчанию.

### <a name="remarks"></a>Примечания

Используйте эту функцию для установки значения по умолчанию для объекта анимации. Этот метод присваивает значения по умолчанию ширине и высоте размера анимации. Он также воссоздает основные объекты COM, если они были созданы. Если вы подписались на этот объект анимации на события (ValueChanged или IntegerValue), необходимо повторно включить эти события.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
