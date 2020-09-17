---
title: Класс CCustomInterpolator
ms.date: 11/04/2016
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
helpviewer_keywords:
- CCustomInterpolator [MFC], CCustomInterpolator
- CCustomInterpolator [MFC], GetDependencies
- CCustomInterpolator [MFC], GetDuration
- CCustomInterpolator [MFC], GetFinalValue
- CCustomInterpolator [MFC], Init
- CCustomInterpolator [MFC], InterpolateValue
- CCustomInterpolator [MFC], InterpolateVelocity
- CCustomInterpolator [MFC], SetDuration
- CCustomInterpolator [MFC], SetInitialValueAndVelocity
- CCustomInterpolator [MFC], m_currentValue
- CCustomInterpolator [MFC], m_currentVelocity
- CCustomInterpolator [MFC], m_duration
- CCustomInterpolator [MFC], m_finalValue
- CCustomInterpolator [MFC], m_initialValue
- CCustomInterpolator [MFC], m_initialVelocity
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
ms.openlocfilehash: 00ce0661fa3fbde714a7299ecbbd54df7c9bcc36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749171"
---
# <a name="ccustominterpolator-class"></a>Класс CCustomInterpolator

Реализует базовый интерполятор.

## <a name="syntax"></a>Синтаксис

```
class CCustomInterpolator;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCustomИнтерполатор::CCustomИнтерполатор](#ccustominterpolator)|Перегружен. Строит пользовательский объект интерполятора и инициализирует продолжительность и скорость к указанным значениям.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCustomИнтерполатор::GetDependencies](#getdependencies)|Получает зависимости интерполятора.|
|[CCustomИнтерполатор::GetDuration](#getduration)|Получает продолжительность интерполятора.|
|[CCustomИнтерполатор::GetFinalValue](#getfinalvalue)|Получает окончательное значение, к которому ведет интерполятор.|
|[CCustomИнтерполатор::Init](#init)|Инициализирует продолжительность и окончательное значение.|
|[CCustomИнтерполатор::InterpolateValue](#interpolatevalue)|Интерполиративирует значение в заданном смещении.|
|[CCustomИнтерполатор::Интерполоусть](#interpolatevelocity)|Интерполиративирует скорость в заданном смещении|
|[CCustomИнтерполатор::SetDuration](#setduration)|Устанавливает продолжительность интерполятора.|
|[CCustomИнтерполатор::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Устанавливает исходное значение и скорость интерполятора.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CCustomИнтерполатор::m_currentValue](#m_currentvalue)|Интерполированное значение.|
|[CCustomИнтерполатор::m_currentVelocity](#m_currentvelocity)|Интерполированная скорость.|
|[CCustomИнтерполатор::m_duration](#m_duration)|Продолжительность перехода.|
|[CCustomИнтерполатор::m_finalValue](#m_finalvalue)|Окончательное значение переменной в конце перехода.|
|[CCustomИнтерполатор::m_initialValue](#m_initialvalue)|Значение переменной в начале перехода.|
|[CCustomИнтерполатор::m_initialVelocity](#m_initialvelocity)|Скорость переменной в начале перехода.|

## <a name="remarks"></a>Примечания

Вывести класс из CCustomInterpolator и переопределить все необходимые методы для реализации пользовательского алгоритма интерполяции. Указатель к этому классу должен быть передан в качестве параметра CCustomTransition.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CCustomInterpolator`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="ccustominterpolatorccustominterpolator"></a><a name="ccustominterpolator"></a>CCustomИнтерполатор::CCustomИнтерполатор

Конструирует пользовательский объект интерполятора и устанавливает все значения по умолчанию 0.

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Параметры

*duration*<br/>
Продолжительность перехода.

*finalValue*

### <a name="remarks"></a>Примечания

Используйте CCustomInterpolator::Init для инициализации продолжительности и окончательного значения позже в коде.

## <a name="ccustominterpolatorgetdependencies"></a><a name="getdependencies"></a>CCustomИнтерполатор::GetDependencies

Получает зависимости интерполятора.

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Параметры

*initialValueDependencies*<br/>
Выходные данные. Аспекты интерполятора, зависят от первоначального значения, переданного SetInitialValueAndVelocity.

*initialVelocityЗависимость*<br/>
Выходные данные. Аспекты интерполятора, зависят от начальной скорости, перешли к SetInitialValueAndVelocity.

*длительностьЗависимости*<br/>
Выходные данные. Аспекты интерполятора, зависят от продолжительности, передаваемые SetDuration.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает TRUE. Возврат FALSE из перезавереденной реализации, если вы хотите провести неудачу события.

## <a name="ccustominterpolatorgetduration"></a><a name="getduration"></a>CCustomИнтерполатор::GetDuration

Получает продолжительность интерполятора.

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Параметры

*duration*<br/>
Выходные данные. Продолжительность перехода, в секундах.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает TRUE. Возврат FALSE из перезавереденной реализации, если вы хотите провести неудачу события.

## <a name="ccustominterpolatorgetfinalvalue"></a><a name="getfinalvalue"></a>CCustomИнтерполатор::GetFinalValue

Получает окончательное значение, к которому ведет интерполятор.

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Выходные данные. Окончательное значение переменной в конце перехода.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает TRUE. Возврат FALSE из перезавереденной реализации, если вы хотите провести неудачу события.

## <a name="ccustominterpolatorinit"></a><a name="init"></a>CCustomИнтерполатор::Init

Инициализирует продолжительность и окончательное значение.

```cpp
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>Параметры

*duration*<br/>
Продолжительность перехода.

*finalValue*<br/>
Окончательное значение переменной в конце перехода.

## <a name="ccustominterpolatorinterpolatevalue"></a><a name="interpolatevalue"></a>CCustomИнтерполатор::InterpolateValue

Интерполиративирует значение в заданном смещении.

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Выходные данные. Интерполированное значение.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает TRUE. Возврат FALSE из перезавереденной реализации, если вы хотите провести неудачу события.

## <a name="ccustominterpolatorinterpolatevelocity"></a><a name="interpolatevelocity"></a>CCustomИнтерполатор::Интерполоусть

Интерполиративирует скорость в заданном смещении

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>Параметры

*velocity*<br/>
Выходные данные. Скорость переменной в смещении.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает TRUE. Возврат FALSE из перезавереденной реализации, если вы хотите провести неудачу события.

## <a name="ccustominterpolatorm_currentvalue"></a><a name="m_currentvalue"></a>CCustomИнтерполатор::m_currentValue

Интерполированное значение.

```
DOUBLE m_currentValue;
```

## <a name="ccustominterpolatorm_currentvelocity"></a><a name="m_currentvelocity"></a>CCustomИнтерполатор::m_currentVelocity

Интерполированная скорость.

```
DOUBLE m_currentVelocity;
```

## <a name="ccustominterpolatorm_duration"></a><a name="m_duration"></a>CCustomИнтерполатор::m_duration

Продолжительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="ccustominterpolatorm_finalvalue"></a><a name="m_finalvalue"></a>CCustomИнтерполатор::m_finalValue

Окончательное значение переменной в конце перехода.

```
DOUBLE m_finalValue;
```

## <a name="ccustominterpolatorm_initialvalue"></a><a name="m_initialvalue"></a>CCustomИнтерполатор::m_initialValue

Значение переменной в начале перехода.

```
DOUBLE m_initialValue;
```

## <a name="ccustominterpolatorm_initialvelocity"></a><a name="m_initialvelocity"></a>CCustomИнтерполатор::m_initialVelocity

Скорость переменной в начале перехода.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustominterpolatorsetduration"></a><a name="setduration"></a>CCustomИнтерполатор::SetDuration

Устанавливает продолжительность интерполятора.

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*duration*<br/>
Продолжительность перехода.

### <a name="return-value"></a>Возвращаемое значение

Базовая реализация всегда возвращает TRUE. Возврат FALSE из перезавереденной реализации, если вы хотите провести неудачу события.

## <a name="ccustominterpolatorsetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a>CCustomИнтерполатор::SetInitialValueAndVelocity

Устанавливает исходное значение и скорость интерполятора.

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>Параметры

*начальнаястоимость*<br/>
Значение переменной в начале перехода.

*ПервоначальныйВелосити*<br/>
Скорость переменной в начале перехода.

### <a name="return-value"></a>Возвращаемое значение

Основная реализация всегда возвращает TRUE. Возврат FALSE из перезавереденной реализации, если вы хотите провести неудачу события.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
