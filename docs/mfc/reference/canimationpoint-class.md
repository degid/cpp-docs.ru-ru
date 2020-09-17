---
title: Класс CAnimationPoint
ms.date: 11/04/2016
f1_keywords:
- CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::CAnimationPoint
- AFXANIMATIONCONTROLLER/CAnimationPoint::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetX
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetY
- AFXANIMATIONCONTROLLER/CAnimationPoint::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_xValue
- AFXANIMATIONCONTROLLER/CAnimationPoint::m_yValue
helpviewer_keywords:
- CAnimationPoint [MFC], CAnimationPoint
- CAnimationPoint [MFC], AddTransition
- CAnimationPoint [MFC], GetDefaultValue
- CAnimationPoint [MFC], GetValue
- CAnimationPoint [MFC], GetX
- CAnimationPoint [MFC], GetY
- CAnimationPoint [MFC], SetDefaultValue
- CAnimationPoint [MFC], GetAnimationVariableList
- CAnimationPoint [MFC], m_xValue
- CAnimationPoint [MFC], m_yValue
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
ms.openlocfilehash: fcdd07efb46c97d27a9f1349c297688b5705f176
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755151"
---
# <a name="canimationpoint-class"></a>Класс CAnimationPoint

Реализует функции точки, координаты которой могут быть анимированы.

## <a name="syntax"></a>Синтаксис

```
class CAnimationPoint : public CAnimationBaseObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationPoint::CAnimationPoint](#canimationpoint)|Перегружен. Строит объект CAnimationPoint.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationPoint::AddTransition](#addtransition)|Добавляет переходы для координат X и Y.|
|[CAnimationPoint::GetDefaultValue](#getdefaultvalue)|Возвращает значения по умолчанию для координат X и Y.|
|[CAnimationPoint::GetValue](#getvalue)|Возвращает текущее значение.|
|[CAnimationPoint::GetX](#getx)|Предоставляет доступ к CAnimationПеременный для X координат.|
|[CAnimationPoint::GetY](#gety)|Предоставляет доступ к CAnimationПеременный для Y координат.|
|[CAnimationPoint::SetDefaultValue](#setdefaultvalue)|Устанавливает значение по умолчанию.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CAnimationPoint::GetAnimationVariableList](#getanimationvariablelist)|Помещает инкапсулированные переменные анимации в список. (Оверлет [CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist).)|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAnimationPoint:оператор CPoint](#operator_cpoint)|Преобразует CAnimationPoint в CPoint.|
|[CAnimationPoint::оператор](#operator_eq)|Присваивает ptSrc CAnimationPoint.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CAnimationPoint::m_xValue](#m_xvalue)|Инкапсулированная переменная анимации, представляющая X-координаты точки анимации.|
|[CAnimationPoint::m_yValue](#m_yvalue)|Инкапсулированная переменная анимации, представляющая y-координаты точки анимации.|

## <a name="remarks"></a>Примечания

Класс CAnimationPoint инкапсулирует два объекта CAnimationVariable и может представлять в приложениях точку. Например, этот класс можно использовать для анимирования положения любого объекта на экране (например, строки текста, круга, точки и т.д.). Чтобы использовать этот класс в приложении, просто мгновенно объект этого класса, добавьте его в контроллер анимации с помощью CAnimationController::AddAnimationObject и вызов AddTransition для каждого перехода, который будет применяться к X и / или Y координаты.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationPoint`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="canimationpointaddtransition"></a><a name="addtransition"></a>CAnimationPoint::AddTransition

Добавляет переходы для координат X и Y.

```cpp
void AddTransition(
    CBaseTransition* pXTransition,
    CBaseTransition* pYTransition);
```

### <a name="parameters"></a>Параметры

*pXПереход*<br/>
Указатель на переход для X координат.

*pYTransition*<br/>
Указатель перехода для Y-координата.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы добавить указанные переходы во внутренний список переходов, которые будут применяться к переменным анимации для координат X и Y. При добавлении переходов они не применяются немедленно и хранятся во внутреннем списке. Переходы применяются (добавлены к раскадровке для определенного значения) при вызове CAnimationController::AnimateGroup. Если вам не нужно применять переход к одной из координат, вы можете пройти NULL.

## <a name="canimationpointcanimationpoint"></a><a name="canimationpoint"></a>CAnimationPoint::CAnimationPoint

Строит объект CAnimationPoint.

```
CAnimationPoint();

CAnimationPoint(
    const CPoint& ptDefault,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>Параметры

*ptDefault*<br/>
Определяет координаты точек по умолчанию.

*nGroupID*<br/>
Определяет идентификатор группы.

*nObjectID*<br/>
Определяет идентификатор объекта.

*dwUserData*<br/>
Определяет данные, определяемые пользователем.

### <a name="remarks"></a>Примечания

Строит объект CAnimationPoint с свойствами по умолчанию: координаты точки по умолчанию, идентификатор группы и идентификатор объекта настроены до 0.

## <a name="canimationpointgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationPoint::GetAnimationVariableList

Помещает инкапсулированные переменные анимации в список.

```
virtual void GetAnimationVariableList(CList<CAnimationVariable*, CAnimationVariable*>& lst);
```

### <a name="parameters"></a>Параметры

*Lst*<br/>
Когда функция возвращается, она содержит указатели на два CAnimationПеременные объекты, представляющие X и Y координаты.

## <a name="canimationpointgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationPoint::GetDefaultValue

Возвращает значения по умолчанию для координат X и Y.

```
CPoint GetDefaultValue();
```

### <a name="return-value"></a>Возвращаемое значение

Точка, содержащая значение по умолчанию.

### <a name="remarks"></a>Примечания

Вызовите эту функцию для получения значения по умолчанию, которое ранее было установлено конструктором или SetDefaultValue.

## <a name="canimationpointgetvalue"></a><a name="getvalue"></a>CAnimationPoint::GetValue

Возвращает текущее значение.

```
BOOL GetValue(CPoint& ptValue);
```

### <a name="parameters"></a>Параметры

*ptValue*<br/>
Выходные данные. Содержит текущее значение при возврате этого метода.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если текущее значение было успешно извлечено; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Вызов используйте эту функцию, чтобы получить текущее значение точки анимации. Если этот метод выходит из строя или основные объекты COM для координат X и Y не были инициализированы, ptValue содержит значение по умолчанию, которое ранее было установлено в конструкторе или SetDefaultValue.

## <a name="canimationpointgetx"></a><a name="getx"></a>CAnimationPoint::GetX

Предоставляет доступ к CAnimationПеременный для X координат.

```
CAnimationVariable& GetX();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий X-координаты.

### <a name="remarks"></a>Примечания

Вы можете назвать этот метод, чтобы получить прямой доступ к основной CAnimationVariable, представляющей X-координаты.

## <a name="canimationpointgety"></a><a name="gety"></a>CAnimationPoint::GetY

Предоставляет доступ к CAnimationПеременный для Y координат.

```
CAnimationVariable& GetY();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на инкапсулированный CAnimationVariable, представляющий Y координаты.

### <a name="remarks"></a>Примечания

Вы можете вызвать этот метод, чтобы получить прямой доступ к основной CAnimationVariable, представляющей Y координаты.

## <a name="canimationpointm_xvalue"></a><a name="m_xvalue"></a>CAnimationPoint::m_xValue

Инкапсулированная переменная анимации, представляющая X-координаты точки анимации.

```
CAnimationVariable m_xValue;
```

## <a name="canimationpointm_yvalue"></a><a name="m_yvalue"></a>CAnimationPoint::m_yValue

Инкапсулированная переменная анимации, представляющая y-координаты точки анимации.

```
CAnimationVariable m_yValue;
```

## <a name="canimationpointoperator-cpoint"></a><a name="operator_cpoint"></a>CAnimationPoint:оператор CPoint

Преобразует CAnimationPoint в CPoint.

```
operator CPoint();
```

### <a name="return-value"></a>Возвращаемое значение

Текущее значение CAnimationPoint как CPoint.

### <a name="remarks"></a>Примечания

Эта функция внутренне вызывает GetValue. Если GetValue по какой-либо причине выходит из строя, возвращается точка будет содержать значения по умолчанию для координат X и Y.

## <a name="canimationpointoperator"></a><a name="operator_eq"></a>CAnimationPoint::оператор

Присваивает ptSrc CAnimationPoint.

```cpp
void operator=(const CPoint& ptSrc);
```

### <a name="parameters"></a>Параметры

*ptSrc*<br/>
Относится к CPoint или POINT.

### <a name="remarks"></a>Примечания

Присваивает ptSrc CAnimationPoint. Рекомендуется сделать это до начала анимации, потому что этот оператор вызывает SetDefaultValue, который воссоздает основные объекты COM для координат X и Y, если они были созданы. Если вы подписались на этот объект анимации на события (ValueChanged или IntegerValue), необходимо повторно включить эти события.

## <a name="canimationpointsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationPoint::SetDefaultValue

Устанавливает значение по умолчанию.

```cpp
void SetDefaultValue(const POINT& ptDefault);
```

### <a name="parameters"></a>Параметры

*ptDefault*<br/>
Определяет значение точки по умолчанию.

### <a name="remarks"></a>Примечания

Используйте эту функцию для установки значения по умолчанию для объекта анимации. Этот метод присваивает значения по умолчанию координатам Анимации X и Y. Он также воссоздает основные объекты COM, если они были созданы. Если вы подписались на этот объект анимации на события (ValueChanged или IntegerValue), необходимо повторно включить эти события.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
