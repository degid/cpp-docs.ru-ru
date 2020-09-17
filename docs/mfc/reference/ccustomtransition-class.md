---
title: Класс CCustomTransition
ms.date: 11/04/2016
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
ms.openlocfilehash: 76e0d12308ad579e4bdf9866dfcf1cde231a2d0c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749152"
---
# <a name="ccustomtransition-class"></a>Класс CCustomTransition

Реализует пользовательский переход.

## <a name="syntax"></a>Синтаксис

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CCustomTransition::CCustomTransition](#ccustomtransition)|Строит пользовательский объект перехода.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CCustomTransition::Создание](#create)|Вызывает библиотеку перехода для создания инкапсулированного объекта переходного COM. (Переопределяет [CBaseПереход::Создание](../../mfc/reference/cbasetransition-class.md#create).)|
|[CCustomTransition::SetInitialValue](#setinitialvalue)|Устанавливает начальное значение, которое будет применено к переменной анимации, связанной с этим переходом.|
|[CCustomTransition::SetInitialVelocity](#setinitialvelocity)|Устанавливает начальную скорость, которая будет применена к переменной анимации, связанной с этим переходом.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CCustomTransition::m_bInitialValueSpecified](#m_binitialvaluespecified)|Уточняется, было ли первоначальное значение определено с SetInitialValue.|
|[CCustomTransition::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|Уточняется, была ли указана начальная скорость с помощью SetInitialVelocity.|
|[CCustomTransition::m_initialValue](#m_initialvalue)|Хранит начальное значение.|
|[CCustomTransition::m_initialVelocity](#m_initialvelocity)|Хранит начальную скорость.|
|[CCustomTransition::m_pInterpolator](#m_pinterpolator)|Хранит указатель для пользовательского интерполятора.|

## <a name="remarks"></a>Примечания

Класс CCustomTransitions позволяет разработчикам внедрять пользовательские переходы. Он создан и используется в качестве стандартного перехода, но его конструктор принимает в качестве параметра указатель для пользовательского интерполятора. Выполните следующие шаги для использования пользовательских переходов: 1. Выполнить класс от CCustomInterpolator и реализовать по крайней мере метод InterpolateValue. 2. Убедитесь, что срок службы пользовательского объекта интерполятора должен быть больше, чем продолжительность анимации, где он используется. 3. Мгновенное (с помощью нового оператора) объект CCustomTransition и передать указатель пользовательскому интерполятору в конструкторе. 4. Вызов CCustomTransition::SetInitialValue и CCustomTransition::SetInitialVelocity, если эти параметры необходимы для таможенной интерполяции. 5. Передайте указатель на пользовательский переход к методу AddTransition объекта анимации, значение которого должно быть анимировано с пользовательским алгоритмом. 6. При изменении значения объекта анимации Windows Animation API вызовет InterpolateValue (и другие соответствующие методы) в CCustomInterpolator.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseПереход](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="ccustomtransitionccustomtransition"></a><a name="ccustomtransition"></a>CCustomTransition::CCustomTransition

Строит пользовательский объект перехода.

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>Параметры

*pInterpolator*<br/>
Указатель на пользовательский интерполятор.

## <a name="ccustomtransitioncreate"></a><a name="create"></a>CCustomTransition::Создание

Вызывает библиотеку перехода для создания инкапсулированного объекта переходного COM.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>Параметры

*pFactory*<br/>
Указатель на переходную фабрику, которая отвечает за создание пользовательских переходов.

### <a name="return-value"></a>Возвращаемое значение

### <a name="remarks"></a>Примечания

Этот метод также может установить начальное значение и начальную скорость, которые должны быть применены к переменной анимации, которая связана с этим переходом. Для этого необходимо вызвать SetInitialValue и SetInitialVelocity, прежде чем фреймворк создает инкапсулированный переходный COM объект (это происходит при вызове CAnimationController::AnimateGroup).

## <a name="ccustomtransitionm_binitialvaluespecified"></a><a name="m_binitialvaluespecified"></a>CCustomTransition::m_bInitialValueSpecified

Уточняется, было ли первоначальное значение определено с SetInitialValue.

```
BOOL m_bInitialValueSpecified;
```

## <a name="ccustomtransitionm_binitialvelocityspecified"></a><a name="m_binitialvelocityspecified"></a>CCustomTransition::m_bInitialVelocitySpecified

Уточняется, была ли указана начальная скорость с помощью SetInitialVelocity.

```
BOOL m_bInitialVelocitySpecified;
```

## <a name="ccustomtransitionm_initialvalue"></a><a name="m_initialvalue"></a>CCustomTransition::m_initialValue

Хранит начальное значение.

```
DOUBLE m_initialValue;
```

## <a name="ccustomtransitionm_initialvelocity"></a><a name="m_initialvelocity"></a>CCustomTransition::m_initialVelocity

Хранит начальную скорость.

```
DOUBLE m_initialVelocity;
```

## <a name="ccustomtransitionm_pinterpolator"></a><a name="m_pinterpolator"></a>CCustomTransition::m_pInterpolator

Хранит указатель для пользовательского интерполятора.

```
CCustomInterpolator* m_pInterpolator;
```

## <a name="ccustomtransitionsetinitialvalue"></a><a name="setinitialvalue"></a>CCustomTransition::SetInitialValue

Устанавливает начальное значение, которое будет применено к переменной анимации, связанной с этим переходом.

```cpp
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>Параметры

*начальнаястоимость*

## <a name="ccustomtransitionsetinitialvelocity"></a><a name="setinitialvelocity"></a>CCustomTransition::SetInitialVelocity

Устанавливает начальную скорость, которая будет применена к переменной анимации, связанной с этим переходом.

```cpp
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>Параметры

*ПервоначальныйВелосити*

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
