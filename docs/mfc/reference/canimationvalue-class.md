---
title: Класс CAnimationValue
ms.date: 11/04/2016
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
ms.openlocfilehash: e020e3e123bb5dc96a623e7a41896d75c611b81e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755085"
---
# <a name="canimationvalue-class"></a>Класс CAnimationValue

Реализует функции объекта анимации, имеющего одно значение.

## <a name="syntax"></a>Синтаксис

```
class CAnimationValue : public CAnimationBaseObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationValue::CAnimationValue](#canimationvalue)|Перегружен. Строит объект CAnimationValue.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationValue::AddTransition](#addtransition)|Добавляет переход, который должен быть применен к значению.|
|[CAnimationValue::GetValue](#getvalue)|Перегружен. Извлекает текущее значение.|
|[CAnimationValue::GetVariable](#getvariable)|Обеспечивает доступ к инкапсулированной переменной анимации.|
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|Устанавливает значение по умолчанию.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированную переменную анимации в список. (Оверлет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationValue::оператор DOUBLE](#operator_double)|Обеспечивает преобразование между CAnimationValue и DOUBLE.|
|[CAnimationValue::оператор INT32](#operator_int32)|Обеспечивает конверсию между CAnimationValue и INT32.|
|[CAnimationValue::оператор](#operator_eq)|Перегружен. Присваивает значение INT32 CAnimationValue.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationValue::m_value](#m_value)|Инкапсулированная переменная анимации, представляющая значение анимации.|

## <a name="remarks"></a>Примечания

Класс CAnimationValue инкапсулирует один объект CAnimationVariable и может представлять в приложениях одно анимированное значение. Например, этот класс можно использовать для анимированной прозрачности (эффект увядания), угла (для поворота объектов) или для любого другого случая, когда необходимо создать анимацию в зависимости от одного анимированного значения. Чтобы использовать этот класс в приложении, просто мгновенно объект этого класса, добавьте его в контроллер анимации с помощью CAnimationController::AddAnimationObject и вызов AddTransition для каждого перехода, который будет применяться к значению.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationvalueaddtransition"></a><a name="addtransition"></a>CAnimationValue::AddTransition

Добавляет переход, который должен быть применен к значению.

```cpp
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>Параметры

*pTransition*<br/>
Указатель на объект перехода.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы добавить переход во внутренний список переходов, которые будут применены к переменной анимации. При добавлении переходов они не применяются немедленно и хранятся во внутреннем списке. Переходы применяются (добавлены к раскадровке для определенного значения) при вызове CAnimationController::AnimateGroup.

## <a name="canimationvaluecanimationvalue"></a><a name="canimationvalue"></a>CAnimationValue::CAnimationValue

Строит объект CAnimationValue.

```
CAnimationValue();

CAnimationValue(
    DOUBLE dblDefaultValue,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*dblDefaultValue*<br/>
Определяет значение по умолчанию.

*nGroupID*<br/>
Определяет идентификатор группы.

*nObjectID*<br/>
Определяет идентификатор объекта.

*dwUserData*<br/>
определяет данные, определяемые пользователем.

### <a name="remarks"></a>Примечания

Строит объект CAnimationValue с свойствами по умолчанию: значение по умолчанию, идентификатор группы и идентификатор объекта настроены до 0.

## <a name="canimationvaluegetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationValue::GetAnimationVariableList

Помещает инкапсулированную переменную анимации в список.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Параметры

*Lst*<br/>
Когда функция возвращается, она содержит указатель на CAnimationVariable, представляющий анимированное значение.

## <a name="canimationvaluegetvalue"></a><a name="getvalue"></a>CAnimationValue::GetValue

Извлекает текущее значение.

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>Параметры

*dblValue*<br/>
Выходные данные. При возврате функции она содержит текущее значение переменной анимации.

*nValue*<br/>
Выходные данные. При возврате функции она содержит текущее значение переменной анимации.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если текущее значение было извлечено успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Вызов ими функции для получения текущего значения. Эта реализация вызывает инкапсулированный объект COM, и если вызов завершается неудачей, этот метод возвращает значение по умолчанию, которое ранее было установлено в конструкторе или в SetDefaultValue.

## <a name="canimationvaluegetvariable"></a><a name="getvariable"></a>CAnimationValue::GetVariable

Обеспечивает доступ к инкапсулированной переменной анимации.

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированную переменную анимации.

### <a name="remarks"></a>Примечания

Используйте этот метод для доступа к инкапсулированной переменной анимации. От CAnimationVariable вы получаете доступ к базовому объекту IUIAnimationVariable, указатель которого может быть NULL, если переменная анимации не была создана.

## <a name="canimationvaluem_value"></a><a name="m_value"></a>CAnimationValue::m_value

Инкапсулированная переменная анимации, представляющая значение анимации.

```
CAnimationVariable m_value;
```

## <a name="canimationvalueoperator-double"></a><a name="operator_double"></a>CAnimationValue::оператор DOUBLE

Обеспечивает преобразование между CAnimationValue и DOUBLE.

```
operator DOUBLE();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение значения анимации.

### <a name="remarks"></a>Примечания

Обеспечивает преобразование между CAnimationValue и DOUBLE. Этот метод внутренне вызывает GetValue и не проверяет на наличие ошибок. Если GetValue выходит из строя, возвращенное значение будет содержать значение по умолчанию, ранее установленное в конструкторе или с SetDefaultValue.

## <a name="canimationvalueoperator-int32"></a><a name="operator_int32"></a>CAnimationValue::оператор INT32

Обеспечивает конверсию между CAnimationValue и INT32.

```
operator INT32();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение значения анимации как целый.

### <a name="remarks"></a>Примечания

Обеспечивает конверсию между CAnimationValue и INT32. Этот метод внутренне вызывает GetValue и не проверяет на наличие ошибок. Если GetValue выходит из строя, возвращенное значение будет содержать значение по умолчанию, ранее установленное в конструкторе или с SetDefaultValue.

## <a name="canimationvalueoperator"></a><a name="operator_eq"></a>CAnimationValue::оператор

Присваивает значение DOUBLE CAnimationValue.

```cpp
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>Параметры

*dblVal*<br/>
Упогоняет значение, назначенное значению анимации.

*nVal*<br/>
Упогоняет значение, назначенное значению анимации.

### <a name="remarks"></a>Примечания

Присваивает значение DOUBLE CAnimationValue. Это значение устанавливается как значение по умолчанию для инкапсулированной переменной анимации. Если вы подписались на этот объект анимации на события (ValueChanged или IntegerValue), необходимо повторно включить эти события.

## <a name="canimationvaluesetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationValue::SetDefaultValue

Устанавливает значение по умолчанию.

```cpp
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>Параметры

*dblDefaultValue*<br/>
Определяет значение по умолчанию.

### <a name="remarks"></a>Примечания

Используйте этот метод для установки значения по умолчанию. Значение по умолчанию возвращается в приложение, когда анимация не запущена и/или базовый объект COM не создан. Если базовый объект COM, инкапсулированный в CAnimationVarible, уже создан, этот метод воссоздает его, поэтому, возможно, потребуется снова позвонить в enableValueChanged/EnableIntegerValue.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
