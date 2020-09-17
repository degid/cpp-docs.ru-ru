---
title: Класс CAnimationColor
ms.date: 11/04/2016
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
helpviewer_keywords:
- CAnimationColor [MFC], CAnimationColor
- CAnimationColor [MFC], AddTransition
- CAnimationColor [MFC], GetB
- CAnimationColor [MFC], GetDefaultValue
- CAnimationColor [MFC], GetG
- CAnimationColor [MFC], GetR
- CAnimationColor [MFC], GetValue
- CAnimationColor [MFC], SetDefaultValue
- CAnimationColor [MFC], GetAnimationVariableList
- CAnimationColor [MFC], m_bValue
- CAnimationColor [MFC], m_gValue
- CAnimationColor [MFC], m_rValue
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
ms.openlocfilehash: 7c1c98d739aa1c17bb30df2d9d4ce8c41558c76d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750194"
---
# <a name="canimationcolor-class"></a>Класс CAnimationColor

Реализует функции цвета, красный, зеленый и синий компоненты которого могут быть анимированы.

## <a name="syntax"></a>Синтаксис

```
class CAnimationColor : public CAnimationBaseObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationColor::CAnimationColor](#canimationcolor)|Перегружен. Строит объект цвета анимации.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationColor::AddTransition](#addtransition)|Добавляет переходы для красных, зеленых и синих компонентов.|
|[CAnimationColor::GetB](#getb)|Обеспечивает доступ к CAnimationVariable, представляющей синий компонент.|
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для цветовых компонентов.|
|[CAnimationColor::GetG](#getg)|Обеспечивает доступ к CAnimationVariable, представляющей зеленый компонент.|
|[CAnimationColor::GetR](#getr)|Обеспечивает доступ к CAnimationVariable, представляющей красный компонент.|
|[CAnimationColor::GetValue](#getvalue)|Возвращает текущее значение.|
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|Устанавливает значение по умолчанию.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированные переменные анимации в список. (Оверлет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationColor::оператор КОЛОРРЕФ](#operator_colorref)||
|[CAnimationColor::оператор](#operator_eq)|Присваивает цвет CAnimationColor.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationColor::m_bValue](#m_bvalue)|Инкапсулированная переменная анимации, представляющая синий компонент цвета анимации.|
|[CAnimationColor::m_gValue](#m_gvalue)|Инкапсулированная переменная анимации, представляющая зеленый компонент цвета анимации.|
|[CAnimationColor::m_rValue](#m_rvalue)|Инкапсулированная переменная анимации, представляющая красный компонент цвета анимации.|

## <a name="remarks"></a>Примечания

Класс CAnimationColor инкапсулирует три объекта CAnimationVariable и может представлять в приложениях цвет. Например, вы можете использовать этот класс для анимировать цвета любого объекта на экране (например, цвет текста, цвет фона и т.д.). Чтобы использовать этот класс в приложении, просто мгновенно объект этого класса, добавьте его в контроллер анимации с помощью CAnimationController::AddAnimationObject и вызов AddTransition для каждого перехода, который будет применяться к красным, зеленым и синим компонентам.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationColor`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationcoloraddtransition"></a><a name="addtransition"></a>CAnimationColor::AddTransition

Добавляет переходы для красных, зеленых и синих компонентов.

```cpp
void AddTransition(
    CBaseTransition* pRTransition,
    CBaseTransition* pGTransition,
    CBaseTransition* pBTransition);
```

### <a name="parameters"></a>Параметры

*pRTransition*<br/>
Переход для красного компонента.

*pGПереход*<br/>
Переход для зеленого компонента.

*pBПереход*<br/>
Переход для компонента Blue.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы добавить указанные переходы во внутренний список переходов, которые будут применяться к переменным анимации, представляющим цветовые компоненты. При добавлении переходов они не применяются немедленно и хранятся во внутреннем списке. Переходы применяются (добавлены к раскадровке для определенного значения) при вызове CAnimationController::AnimateGroup. Если вам не нужно применять переход к одному из цветовых компонентов, вы можете пройти NULL.

## <a name="canimationcolorcanimationcolor"></a><a name="canimationcolor"></a>CAnimationColor::CAnimationColor

Строит объект CAnimationColor.

```
CAnimationColor();

CAnimationColor(
    COLORREF color,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Определяет цвет по умолчанию.

*nGroupID*<br/>
Определяет идентификатор группы.

*nObjectID*<br/>
Определяет идентификатор объекта.

*dwUserData*<br/>
Определяет данные, определяемые пользователем.

### <a name="remarks"></a>Примечания

Объект построен с значениями по умолчанию для красного, зеленого, синего, идентификатора объекта и идентификатора группы, который будет установлен на 0. Они могут быть изменены позже во время выполнения с помощью SetDefaultValue и SetID.

## <a name="canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList

Помещает инкапсулированные переменные анимации в список.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Параметры

*Lst*<br/>
Когда функция возвращается, она содержит указатели на три CAnimationПеременные объекты, представляющие красный, зеленый и синий компоненты.

## <a name="canimationcolorgetb"></a><a name="getb"></a>CAnimationColor::GetB

Обеспечивает доступ к CAnimationVariable, представляющей синий компонент.

```
CAnimationVariable& GetB();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий синий компонент.

### <a name="remarks"></a>Примечания

Этот метод можно назвать прямым доступом к базовому CAnimationVariable, представляющему синий компонент.

## <a name="canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue

Возвращает значения по умолчанию для цветовых компонентов.

```
COLORREF GetDefaultValue();
```

### <a name="return-value"></a>Возвращаемое значение

Значение COLORREF, содержащее по умолчанию для компонентов RGB.

### <a name="remarks"></a>Примечания

Вызовите эту функцию для получения значения по умолчанию, которое ранее было установлено конструктором или SetDefaultValue.

## <a name="canimationcolorgetg"></a><a name="getg"></a>CAnimationColor::GetG

Обеспечивает доступ к CAnimationVariable, представляющей зеленый компонент.

```
CAnimationVariable& GetG();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий зеленый компонент.

### <a name="remarks"></a>Примечания

Этот метод можно назвать прямым доступом к базовому CAnimationVariable, представляющему зеленый компонент.

## <a name="canimationcolorgetr"></a><a name="getr"></a>CAnimationColor::GetR

Обеспечивает доступ к CAnimationVariable, представляющей красный компонент.

```
CAnimationVariable& GetR();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий красный компонент.

### <a name="remarks"></a>Примечания

Этот метод можно назвать прямым доступом к базовому CAnimationVariable, представляющему красный компонент.

## <a name="canimationcolorgetvalue"></a><a name="getvalue"></a>CAnimationColor::GetValue

Возвращает текущее значение.

```
BOOL GetValue(COLORREF& color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Выходные данные. Содержит текущее значение при возврате этого метода.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если текущее значение было успешно извлечено; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы получить текущее значение цвета анимации. Если этот метод не удается или базовые объекты COM для цветовых компонентов не были инициализированы, цвет содержит значение по умолчанию, которое ранее было установлено в конструкторе или SetDefaultValue.

## <a name="canimationcolorm_bvalue"></a><a name="m_bvalue"></a>CAnimationColor::m_bValue

Инкапсулированная переменная анимации, представляющая синий компонент цвета анимации.

```
CAnimationVariable m_bValue;
```

## <a name="canimationcolorm_gvalue"></a><a name="m_gvalue"></a>CAnimationColor::m_gValue

Инкапсулированная переменная анимации, представляющая зеленый компонент цвета анимации.

```
CAnimationVariable m_gValue;
```

## <a name="canimationcolorm_rvalue"></a><a name="m_rvalue"></a>CAnimationColor::m_rValue

Инкапсулированная переменная анимации, представляющая красный компонент цвета анимации.

```
CAnimationVariable m_rValue;
```

## <a name="canimationcoloroperator-colorref"></a><a name="operator_colorref"></a>CAnimationColor::оператор КОЛОРРЕФ

```
operator COLORREF();
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="canimationcoloroperator"></a><a name="operator_eq"></a>CAnimationColor::оператор

Присваивает цвет CAnimationColor.

```cpp
void operator=(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Определяет новое значение Анимация Цвет.

### <a name="remarks"></a>Примечания

Рекомендуется сделать это до начала анимации, потому что этот оператор вызывает SetDefaultValue, который воссоздает основные объекты COM для цветовых компонентов, если они были созданы. Если вы подписались на этот объект анимации на события (ValueChanged или IntegerValue), необходимо повторно включить эти события.

## <a name="canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue

Устанавливает значение по умолчанию.

```cpp
void SetDefaultValue(COLORREF color);
```

### <a name="parameters"></a>Параметры

*Цвет*<br/>
Определяет новые значения по умолчанию для красных, зеленых и синих компонентов.

### <a name="remarks"></a>Примечания

Используйте эту функцию для установки значения по умолчанию для объекта анимации. Этот метод присваивает значения по умолчанию цветовым компонентам цвета анимации. Он также воссоздает основные объекты COM, если они были созданы. Если вы подписались на этот объект анимации на события (ValueChanged или IntegerValue), необходимо повторно включить эти события.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
