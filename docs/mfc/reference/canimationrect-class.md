---
title: Класс CAnimationRect
ms.date: 11/04/2016
f1_keywords:
- CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::CAnimationRect
- AFXANIMATIONCONTROLLER/CAnimationRect::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationRect::GetBottom
- AFXANIMATIONCONTROLLER/CAnimationRect::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetLeft
- AFXANIMATIONCONTROLLER/CAnimationRect::GetRight
- AFXANIMATIONCONTROLLER/CAnimationRect::GetTop
- AFXANIMATIONCONTROLLER/CAnimationRect::GetValue
- AFXANIMATIONCONTROLLER/CAnimationRect::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationRect::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bFixedSize
- AFXANIMATIONCONTROLLER/CAnimationRect::m_bottomValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_leftValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_rightValue
- AFXANIMATIONCONTROLLER/CAnimationRect::m_szInitial
- AFXANIMATIONCONTROLLER/CAnimationRect::m_topValue
helpviewer_keywords:
- CAnimationRect [MFC], CAnimationRect
- CAnimationRect [MFC], AddTransition
- CAnimationRect [MFC], GetBottom
- CAnimationRect [MFC], GetDefaultValue
- CAnimationRect [MFC], GetLeft
- CAnimationRect [MFC], GetRight
- CAnimationRect [MFC], GetTop
- CAnimationRect [MFC], GetValue
- CAnimationRect [MFC], SetDefaultValue
- CAnimationRect [MFC], GetAnimationVariableList
- CAnimationRect [MFC], m_bFixedSize
- CAnimationRect [MFC], m_bottomValue
- CAnimationRect [MFC], m_leftValue
- CAnimationRect [MFC], m_rightValue
- CAnimationRect [MFC], m_szInitial
- CAnimationRect [MFC], m_topValue
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
ms.openlocfilehash: 273ea2b548d35722ebf937d2db2b589fef5e69fa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755133"
---
# <a name="canimationrect-class"></a>Класс CAnimationRect

Реализует функции прямоугольника, стороны которого могут быть анимированы.

## <a name="syntax"></a>Синтаксис

```
class CAnimationRect : public CAnimationBaseObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationRect::CAnimationRect](#canimationrect)|Перегружен. Строит объект прямой кишки анимации.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationRect::AddTransition](#addtransition)|Добавляет переходы для левых, верхних, правых и нижних координат.|
|[CAnimationRect::GetBottom](#getbottom)|Обеспечивает доступ к CAnimationVariable, представляющей нижние координаты.|
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для границ прямоугольника.|
|[CAnimationRect::GetLeft](#getleft)|Обеспечивает доступ к CAnimationVariable, представляющей левую координату.|
|[CAnimationRect::GetRight](#getright)|Предоставляет доступ к CAnimationVariable, представляющей правильную координату.|
|[CAnimationRect::GetTop](#gettop)|Обеспечивает доступ к CAnimationVariable, представляющей верхние координаты.|
|[CAnimationRect::GetValue](#getvalue)|Возвращает текущее значение.|
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|Устанавливает значение по умолчанию.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированные переменные анимации в список. (Оверлет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationRect::оператор RECT](#operator_rect)|Преобразует CAnimationRect в RECT.|
|[CAnimationRect::оператор](#operator_eq)|Присваивает прямой к CAnimationRect.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|Определяет, имеет ли прямоугольник фиксированный размер.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|Инкапсулированная переменная анимации, представляющая нижнюю границу прямоугольника анимации.|
|[CAnimationRect::m_leftValue](#m_leftvalue)|Инкапсулированная переменная анимации, представляющая левую границу прямоугольника анимации.|
|[CAnimationRect::m_rightValue](#m_rightvalue)|Инкапсулированная переменная анимации, представляющая правую границу прямоугольника анимации.|
|[CAnimationRect::m_szInitial](#m_szinitial)|Определяет начальный размер прямоугольника анимации.|
|[CAnimationRect::m_topValue](#m_topvalue)|Инкапсулированная переменная анимации, представляющая верхнюю границу прямоугольника анимации.|

## <a name="remarks"></a>Примечания

Класс CAnimationRect инкапсулирует четыре объекта CAnimationVariable и может представлять в приложениях прямоугольник. Чтобы использовать этот класс в приложении, просто мгновенно объект этого класса, добавьте его в контроллер анимации с помощью CAnimationController::AddAnimationObject и вызов AddTransition для каждого перехода, который будет применяться к левой, правой верхней и нижней координат.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationRect`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationrectaddtransition"></a><a name="addtransition"></a>CAnimationRect::AddTransition

Добавляет переходы для левых, верхних, правых и нижних координат.

```cpp
void AddTransition(
    CBaseTransition* pLeftTransition,
    CBaseTransition* pTopTransition,
    CBaseTransition* pRightTransition,
    CBaseTransition* pBottomTransition);
```

### <a name="parameters"></a>Параметры

*pLeftTransition*<br/>
Определяет переход на левую сторону.

*pTopПереход*<br/>
Определяет переход для верхней стороны.

*pRightTransition*<br/>
Определяет переход для правой стороны.

*pBottomTransition*<br/>
Определяет переход для нижней стороны.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы добавить указанные переходы во внутренний список переходов, которые будут применяться к переменным анимации для каждой прямоугольника сторон. При добавлении переходов они не применяются немедленно и хранятся во внутреннем списке. Переходы применяются (добавлены к раскадровке для определенного значения) при вызове CAnimationController::AnimateGroup. Если вам не нужно применять переход к одной из сторон прямоугольника, вы можете пройти NULL.

## <a name="canimationrectcanimationrect"></a><a name="canimationrect"></a>CAnimationRect::CAnimationRect

Строит объект CAnimationRect.

```
CAnimationRect();

CAnimationRect(
    const CRect& rect,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    const CPoint& pt,
    const CSize& sz,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);

CAnimationRect(
    int nLeft,
    int nTop,
    int nRight,
    int nBottom,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Определяет прямоугольник по умолчанию.

*nGroupID*<br/>
Определяет идентификатор группы.

*nObjectID*<br/>
Определяет идентификатор объекта.

*dwUserData*<br/>
Определяет данные, определяемые пользователем.

*пт*<br/>
Координация верхнего левого угла.

*Sz*<br/>
Размер прямоугольника.

*nСлева*<br/>
Определяет координаты левой границы.

*Ntop*<br/>
Определяет координаты верхней границы.

*nПраво*<br/>
Определяет координаты правой границы.

*nБоттом*<br/>
Определяет координаты нижней границы.

### <a name="remarks"></a>Примечания

Объект построен с значениями по умолчанию для левого, верхнего, правого и нижнего, идентификатора объекта и идентификатора группы, который будет установлен на 0. Они могут быть изменены позже во время выполнения с помощью SetDefaultValue и SetID.

## <a name="canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationRect::GetAnimationVariableList

Помещает инкапсулированные переменные анимации в список.

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Параметры

*Lst*<br/>
Когда функция возвращается, она содержит указатели на четыре CAnimationПеременные объекты, представляющие координаты прямоугольника.

## <a name="canimationrectgetbottom"></a><a name="getbottom"></a>CAnimationRect::GetBottom

Обеспечивает доступ к CAnimationVariable, представляющей нижние координаты.

```
CAnimationVariable& GetBottom();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий нижние координаты.

### <a name="remarks"></a>Примечания

Этот метод можно назвать прямым доступом к базовому CAnimationVariable, представляющему нижнюю координату.

## <a name="canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationRect::GetDefaultValue

Возвращает значения по умолчанию для границ прямоугольника.

```
CRect GetDefaultValue();
```

### <a name="return-value"></a>Возвращаемое значение

Значение CRect, содержащее значения по умолчанию для левого, правого, верхнего и нижнего.

### <a name="remarks"></a>Примечания

Вызовите эту функцию для получения значения по умолчанию, которое ранее было установлено конструктором или SetDefaultValue.

## <a name="canimationrectgetleft"></a><a name="getleft"></a>CAnimationRect::GetLeft

Обеспечивает доступ к CAnimationVariable, представляющей левую координату.

```
CAnimationVariable& GetLeft();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий левую координату.

### <a name="remarks"></a>Примечания

Вы можете вызвать этот метод, чтобы получить прямой доступ к основной CAnimationVariable, представляющей левую координату.

## <a name="canimationrectgetright"></a><a name="getright"></a>CAnimationRect::GetRight

Предоставляет доступ к CAnimationVariable, представляющей правильную координату.

```
CAnimationVariable& GetRight();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий правильную координату.

### <a name="remarks"></a>Примечания

Вы можете вызвать этот метод, чтобы получить прямой доступ к основной CAnimationVariable, представляющей правильную координатку.

## <a name="canimationrectgettop"></a><a name="gettop"></a>CAnimationRect::GetTop

Обеспечивает доступ к CAnimationVariable, представляющей верхние координаты.

```
CAnimationVariable& GetTop();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий верхние координаты.

### <a name="remarks"></a>Примечания

Вы можете назвать этот метод, чтобы получить прямой доступ к основной CAnimationVariable, представляющей верхнюю координат.

## <a name="canimationrectgetvalue"></a><a name="getvalue"></a>CAnimationRect::GetValue

Возвращает текущее значение.

```
BOOL GetValue(CRect& rect);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Выходные данные. Содержит текущее значение при возврате этого метода.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если текущее значение было успешно извлечено; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Вызов используйте эту функцию, чтобы получить текущее значение прямоугольника анимации. Если этот метод не удается или основные объекты COM для левого, верхнего, правого и снизу не были инициализированы, rect содержит значение по умолчанию, которое ранее было установлено в конструкторе или SetDefaultValue.

## <a name="canimationrectm_bfixedsize"></a><a name="m_bfixedsize"></a>CAnimationRect::m_bFixedSize

Определяет, имеет ли прямоугольник фиксированный размер.

```
BOOL m_bFixedSize;
```

### <a name="remarks"></a>Примечания

Если этот участник истинен, то размер прямоугольника фиксируется, а правые и нижние значения пересчитываются каждый раз, когда верхний левый угол перемещается в соответствии с фиксированным размером. Установите это значение для TRUE, чтобы легко перемещать прямоугольник вокруг экрана. В этом случае игнорируются переходы, применяемые к правым и нижним координатам. Размер хранится внутренне при построении объекта и/или вызове SetDefaultValue. По умолчанию этот участник установлен на FALSE.

## <a name="canimationrectm_bottomvalue"></a><a name="m_bottomvalue"></a>CAnimationRect::m_bottomValue

Инкапсулированная переменная анимации, представляющая нижнюю границу прямоугольника анимации.

```
CAnimationVariable m_bottomValue;
```

## <a name="canimationrectm_leftvalue"></a><a name="m_leftvalue"></a>CAnimationRect::m_leftValue

Инкапсулированная переменная анимации, представляющая левую границу прямоугольника анимации.

```
CAnimationVariable m_leftValue;
```

## <a name="canimationrectm_rightvalue"></a><a name="m_rightvalue"></a>CAnimationRect::m_rightValue

Инкапсулированная переменная анимации, представляющая правую границу прямоугольника анимации.

```
CAnimationVariable m_rightValue;
```

## <a name="canimationrectm_szinitial"></a><a name="m_szinitial"></a>CAnimationRect::m_szInitial

Определяет начальный размер прямоугольника анимации.

```
CSize m_szInitial;
```

## <a name="canimationrectm_topvalue"></a><a name="m_topvalue"></a>CAnimationRect::m_topValue

Инкапсулированная переменная анимации, представляющая верхнюю границу прямоугольника анимации.

```
CAnimationVariable m_topValue;
```

## <a name="canimationrectoperator-rect"></a><a name="operator_rect"></a>CAnimationRect::оператор RECT

Преобразует CAnimationRect в RECT.

```
operator RECT();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение прямоугольника анимации как RECT.

### <a name="remarks"></a>Примечания

Эта функция внутренне вызывает GetValue. Если GetValue по какой-либо причине выходит из строя, возвращенный RECT будет содержать значения по умолчанию для всех координат прямоугольника.

## <a name="canimationrectoperator"></a><a name="operator_eq"></a>CAnimationRect::оператор

Присваивает прямой к CAnimationRect.

```cpp
void operator=(const RECT& rect);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Новое значение прямоугольника анимации.

### <a name="remarks"></a>Примечания

Рекомендуется сделать это до начала анимации, потому что этот оператор вызывает SetDefaultValue, который воссоздает основные объекты COM для цветовых компонентов, если они были созданы. Если вы подписались на этот объект анимации на события (ValueChanged или IntegerValue), необходимо повторно включить эти события.

## <a name="canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationRect::SetDefaultValue

Устанавливает значение по умолчанию.

```cpp
void SetDefaultValue(const CRect& rect);
```

### <a name="parameters"></a>Параметры

*rect*<br/>
Определяет новые значения по умолчанию для левого, верхнего, правого и нижнего.

### <a name="remarks"></a>Примечания

Используйте эту функцию для установки значения по умолчанию для объекта анимации. Этот метод присваивает значения по умолчанию границам прямоугольника. Он также воссоздает основные объекты COM, если они были созданы. Если вы подписались на этот объект анимации на события (ValueChanged или IntegerValue), необходимо повторно включить эти события.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
