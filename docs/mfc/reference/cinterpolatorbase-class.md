---
title: Класс CInterpolatorBase
ms.date: 11/04/2016
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
ms.openlocfilehash: efa08aa5dd556d7e136323c31451a9f33bd72ec6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754955"
---
# <a name="cinterpolatorbase-class"></a>Класс CInterpolatorBase

Реализует обратный вызов, используемый API анимации, когда требуется рассчитать новое значение переменной анимации.

## <a name="syntax"></a>Синтаксис

```
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CInterpolatorBase::КИнтерполаторБаза](#cinterpolatorbase)|Строит `CInterpolatorBase` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CInterpolatorBase::СозданиеInstance](#createinstance)|Создает экземпляр `CInterpolatorBase` и хранит указатель на пользовательский интерполятор, который будет обрабатывать события.|
|[CInterpolatorBase::GetDependencies](#getdependencies)|Получает зависимости интерполятора. (Переопределяет `CUIAnimationInterpolatorBase::GetDependencies`.)|
|[CInterpolatorBase::GetDuration](#getduration)|Получает продолжительность интерполятора. (Переопределяет `CUIAnimationInterpolatorBase::GetDuration`.)|
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Получает окончательное значение, к которому ведет интерполятор. (Переопределяет `CUIAnimationInterpolatorBase::GetFinalValue`.)|
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|Интерполиративирует значение в заданном смещении (Overrides `CUIAnimationInterpolatorBase::InterpolateValue`.)|
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|Интерполирует скорость при заданном смещении `CUIAnimationInterpolatorBase::InterpolateVelocity`(Overrides .)|
|[CInterpolatorBase::SetCustomИнтерполатор](#setcustominterpolator)|Хранит указатель на пользовательский интерполятор, который будет обрабатывать события.|
|[CInterpolatorBase::SetDuration](#setduration)|Устанавливает продолжительность интерполятора (Переопределения `CUIAnimationInterpolatorBase::SetDuration`.)|
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Устанавливает исходное значение и скорость интерполятора. (Переопределяет `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.)|

## <a name="remarks"></a>Примечания

Этот обработчик создается и передается `IUIAnimationTransitionFactory::CreateTransition` при создании `CCustomTransition` объекта в рамках `CAnimationController::AnimateGroup`процесса инициализации анимации (запущенного). Обычно вам не нужно использовать этот класс напрямую, он `CCustomInterpolator`просто разогнат все события на `CCustomTransition`-производный класс, указатель которого передается конструктору .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="cinterpolatorbasecinterpolatorbase"></a><a name="cinterpolatorbase"></a>CInterpolatorBase::КИнтерполаторБаза

Строит объект CInterpolatorBase.

```
CInterpolatorBase();
```

## <a name="cinterpolatorbasecreateinstance"></a><a name="createinstance"></a>CInterpolatorBase::СозданиеInstance

Создает экземпляр CInterpolatorBase и хранит указатель на пользовательский интерполятор, который будет обрабатывать события.

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>Параметры

*pInterpolator*<br/>
Указатель на пользовательский интерполятор.

*ppHandler*<br/>
Выходные данные. Содержит указатель на экземпляр CInterpolatorBase при возврате функции.

### <a name="return-value"></a>Возвращаемое значение

## <a name="cinterpolatorbasegetdependencies"></a><a name="getdependencies"></a>CInterpolatorBase::GetDependencies

Получает зависимости интерполятора.

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>Параметры

*initialValueDependencies*<br/>
Выходные данные. Аспекты интерполятора, зависят от первоначального значения, переданного SetInitialValueAndVelocity.

*initialVelocityЗависимость*<br/>
Выходные данные. Аспекты интерполятора, зависят от начальной скорости, перешли к SetInitialValueAndVelocity.

*длительностьЗависимости*<br/>
Выходные данные. Аспекты интерполятора, зависят от продолжительности, передаваемые SetDuration.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не установлен, или пользовательская реализация возвращает FALSE из метода GetDependencies.

## <a name="cinterpolatorbasegetduration"></a><a name="getduration"></a>CInterpolatorBase::GetDuration

Получает продолжительность интерполятора.

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>Параметры

*duration*<br/>
Выходные данные. Продолжительность перехода, в секундах.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. Он возвращает E_FAIL если CCustomInterpolator не установлен, или пользовательская реализация возвращает FALSE из метода GetDuration.

## <a name="cinterpolatorbasegetfinalvalue"></a><a name="getfinalvalue"></a>CInterpolatorBase::GetFinalValue

Получает окончательное значение, к которому ведет интерполятор.

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*value*<br/>
Выходные данные. Окончательное значение переменной в конце перехода.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не установлен, или пользовательская реализация возвращает FALSE из метода GetFinalValue.

## <a name="cinterpolatorbaseinterpolatevalue"></a><a name="interpolatevalue"></a>CInterpolatorBase::InterpolateValue

Интерполиративирует значение в заданном смещении

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>Параметры

*Смещение*<br/>
Смещение с начала перехода. Смещение всегда больше или равно нулю и меньше, чем продолжительность перехода. Этот метод не вызывается, если продолжительность перехода равна нулю.

*value*<br/>
Выходные данные. Интерполированное значение.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. Он возвращает E_FAIL если CCustomInterpolator не установлен, или пользовательская реализация возвращает FALSE из метода InterpolateValue.

## <a name="cinterpolatorbaseinterpolatevelocity"></a><a name="interpolatevelocity"></a>CInterpolatorBase::InterpolateVelocity

Интерполиративирует скорость в заданном смещении

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>Параметры

*Смещение*<br/>
Смещение с начала перехода. Смещение всегда больше или равно нулю и меньше или равно продолжительности перехода. Этот метод не вызывается, если продолжительность перехода равна нулю.

*velocity*<br/>
Выходные данные. Скорость переменной в смещении.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. Он возвращает E_FAIL, если CCustomInterpolator не установлен, или пользовательская реализация возвращает FALSE из метода InterpolateVelocity.

## <a name="cinterpolatorbasesetcustominterpolator"></a><a name="setcustominterpolator"></a>CInterpolatorBase::SetCustomИнтерполатор

Хранит указатель на пользовательский интерполятор, который будет обрабатывать события.

```cpp
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Параметры

*pInterpolator*<br/>
Указатель на пользовательский интерполятор.

## <a name="cinterpolatorbasesetduration"></a><a name="setduration"></a>CInterpolatorBase::SetDuration

Устанавливает продолжительность интерполятора

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*duration*<br/>
Продолжительность перехода.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. Он возвращает E_FAIL если CCustomInterpolator не установлен, или пользовательская реализация возвращает FALSE из метода SetDuration.

## <a name="cinterpolatorbasesetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a>CInterpolatorBase::SetInitialValueAndVelocity

Устанавливает исходное значение и скорость интерполятора.

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>Параметры

*начальнаястоимость*<br/>
Значение переменной в начале перехода.

*ПервоначальныйВелосити*<br/>
Скорость переменной в начале перехода.

### <a name="return-value"></a>Возвращаемое значение

Если метод завершается успешно, возвращает значение S_OK. Он возвращает E_FAIL если CCustomInterpolator не установлен, или пользовательская реализация возвращает FALSE из метода SetInitialValueAndVelocity.

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
