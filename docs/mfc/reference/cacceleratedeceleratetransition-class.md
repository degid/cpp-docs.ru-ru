---
title: Класс CAccelerateDecelerateTransition
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: 356ba30e6d9a638672d2c356676735ebfaed8f3e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371150"
---
# <a name="cacceleratedeceleratetransition-class"></a>Класс CAccelerateDecelerateTransition

Реализует переход между ускорением и замедлением.

## <a name="syntax"></a>Синтаксис

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAccelerateDecDecelerateПереход::УскорениеDecDecDecDecDecDecelerateTransition](#cacceleratedeceleratetransition)|Строит переходный объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAccelerateDecDecElerateПереход::Создание](#create)|Вызывает библиотеку перехода для создания инкапсулированного объекта переходного COM. (Переопределяет [CBaseПереход::Создание](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAccelerateDecDecDecelerateПереход::m_accelerationRatio](#m_accelerationratio)|Соотношение времени, затраченного на ускорение к продолжительности.|
|[CAccelerateDecDecDecelerateПереход::m_decelerationRatio](#m_decelerationratio)|Соотношение времени, затрачиваемого на замедление к продолжительности.|
|[CAccelerateDecDecElerateПереход::m_duration](#m_duration)|Продолжительность перехода.|
|[CAccelerateDecDecElerateПереход::m_finalValue](#m_finalvalue)|Значение переменной анимации в конце перехода.|

## <a name="remarks"></a>Примечания

Во время перехода ускоренного замедления переменная анимации ускоряется, а затем замедляется в течение всего периода перехода, заканчивающегося в определенном значении. Вы можете контролировать, как быстро переменная ускоряется и замедляется самостоятельно, указывая различные коэффициенты ускорения и замедления. Когда начальная скорость равна нулю, коэффициент ускорения — это доля продолжительности, которую переменная потратит на ускорение; также с коэффициентом замедления. Если начальная скорость неравнейна, то это доля времени между скоростью, достигающей нуля, и концом перехода. Коэффициент ускорения и коэффициент замедления должны составить максимум 1,0. Поскольку все переходы очищаются автоматически, рекомендуется выделять их с помощью нового оператора. Инкапсулированный объект IUIAnimationTransition COM создается CAnimationController::AnimateGroup, до тех пор это NULL. Изменение переменных членов после создания этого объекта COM не имеет эффекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseПереход](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="cacceleratedeceleratetransitioncacceleratedeceleratetransition"></a><a name="cacceleratedeceleratetransition"></a>CAccelerateDecDecelerateПереход::УскорениеDecDecDecDecDecDecelerateTransition

Строит переходный объект.

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Продолжительность перехода.

*finalValue*<br/>
Значение переменной анимации в конце перехода.

*ускорениеКоэффициент*<br/>
Соотношение времени, затраченного на ускорение к продолжительности.

*замедлениеКоэффициент*<br/>
Соотношение времени, затрачиваемого на замедление к продолжительности.

## <a name="cacceleratedeceleratetransitioncreate"></a><a name="create"></a>CAccelerateDecDecElerateПереход::Создание

Вызывает библиотеку перехода для создания инкапсулированного объекта переходного COM.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на [интерфейс IUIAnimationTransitionLibrary,](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если переход создан успешно; в противном случае FALSE.

## <a name="cacceleratedeceleratetransitionm_accelerationratio"></a><a name="m_accelerationratio"></a>CAccelerateDecDecDecelerateПереход::m_accelerationRatio

Соотношение времени, затраченного на ускорение к продолжительности.

```
DOUBLE m_accelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_decelerationratio"></a><a name="m_decelerationratio"></a>CAccelerateDecDecDecelerateПереход::m_decelerationRatio

Соотношение времени, затрачиваемого на замедление к продолжительности.

```
DOUBLE m_decelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_duration"></a><a name="m_duration"></a>CAccelerateDecDecElerateПереход::m_duration

Продолжительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="cacceleratedeceleratetransitionm_finalvalue"></a><a name="m_finalvalue"></a>CAccelerateDecDecElerateПереход::m_finalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
