---
title: Класс CLinearTransition
ms.date: 11/04/2016
f1_keywords:
- CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::CLinearTransition
- AFXANIMATIONCONTROLLER/CLinearTransition::Create
- AFXANIMATIONCONTROLLER/CLinearTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransition::m_duration
helpviewer_keywords:
- CLinearTransition [MFC], CLinearTransition
- CLinearTransition [MFC], Create
- CLinearTransition [MFC], m_dblFinalValue
- CLinearTransition [MFC], m_duration
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
ms.openlocfilehash: 1d3bc50255dae93bfa80e8212c2349db66db4eb6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372282"
---
# <a name="clineartransition-class"></a>Класс CLinearTransition

Инкапсулирует линейный переход.

## <a name="syntax"></a>Синтаксис

```
class CLinearTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CLinearTransition::CLinearTransition](#clineartransition)|Строит линейный переходный объект и инициализирует его с длительностью и конечным значением.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CLinearTransition::Создание](#create)|Вызывает библиотеку перехода для создания инкапсулированного объекта переходного COM. (Переопределяет [CBaseПереход::Создание](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CLinearTransition::m_dblFinalValue](#m_dblfinalvalue)|Значение переменной анимации в конце перехода.|
|[CLinearTransition::m_duration](#m_duration)|Продолжительность перехода.|

## <a name="remarks"></a>Примечания

Во время линейного перехода значение переменной анимации линейно переходит от исходного значения к определенному конечному значению. Поскольку все переходы очищаются автоматически, рекомендуется выделять их с помощью нового оператора. Инкапсулированный объект IUIAnimationTransition COM создается CAnimationController::AnimateGroup, до тех пор это NULL. Изменение переменных членов после создания этого объекта COM не имеет эффекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseПереход](../../mfc/reference/cbasetransition-class.md)

[CLinearTransition](../../mfc/reference/clineartransition-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="clineartransitionclineartransition"></a><a name="clineartransition"></a>CLinearTransition::CLinearTransition

Строит линейный переходный объект и инициализирует его с длительностью и конечным значением.

```
CLinearTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Продолжительность перехода.

*dblFinalValue*<br/>
Значение переменной анимации в конце перехода.

## <a name="clineartransitioncreate"></a><a name="create"></a>CLinearTransition::Создание

Вызывает библиотеку перехода для создания инкапсулированного объекта переходного COM.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на [интерфейс IUIAnimationTransitionLibrary,](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)который определяет библиотеку стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если переход создан успешно; в противном случае FALSE.

## <a name="clineartransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>CLinearTransition::m_dblFinalValue

Значение переменной анимации в конце перехода.

```
DOUBLE m_dblFinalValue;
```

## <a name="clineartransitionm_duration"></a><a name="m_duration"></a>CLinearTransition::m_duration

Продолжительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
