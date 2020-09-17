---
title: Класс CReversalTransition
ms.date: 11/04/2016
f1_keywords:
- CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::Create
- AFXANIMATIONCONTROLLER/CReversalTransition::m_duration
helpviewer_keywords:
- CReversalTransition [MFC], CReversalTransition
- CReversalTransition [MFC], Create
- CReversalTransition [MFC], m_duration
ms.assetid: e89516be-2d07-4885-95a8-fc278f46e3ad
ms.openlocfilehash: 73d12fb6bbaefcfac1437248ebe11f3a5c24c45b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368315"
---
# <a name="creversaltransition-class"></a>Класс CReversalTransition

Инкапсулирует обратный переход.

## <a name="syntax"></a>Синтаксис

```
class CReversalTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CReversalTransition::CReversalTransition](#creversaltransition)|Строит объект разворотного перехода и инициализирует его продолжительность.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CReversalTransition::Создание](#create)|Вызывает библиотеку перехода для создания инкапсулированного объекта переходного COM. (Переопределяет [CBaseПереход::Создание](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CReversalTransition:::m_duration](#m_duration)|Продолжительность перехода.|

## <a name="remarks"></a>Примечания

Разворотный переход плавно меняет направление в течение заданной продолжительности. Окончательное значение будет таким же, как начальное значение, а конечная скорость будет отрицательной начальной скорости. Поскольку все переходы очищаются автоматически, рекомендуется выделять их с помощью нового оператора. Инкапсулированный объект IUIAnimationTransition COM создается CAnimationController::AnimateGroup, до тех пор это NULL. Изменение переменных членов после создания этого объекта COM не имеет эффекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseПереход](../../mfc/reference/cbasetransition-class.md)

[CReversalПереход](../../mfc/reference/creversaltransition-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="creversaltransitioncreate"></a><a name="create"></a>CReversalTransition::Создание

Вызывает библиотеку перехода для создания инкапсулированного объекта переходного COM.

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>Параметры

*pLibrary*<br/>
Указатель на библиотеку перехода, которая отвечает за создание стандартных переходов.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если переход создан успешно; в противном случае FALSE.

## <a name="creversaltransitioncreversaltransition"></a><a name="creversaltransition"></a>CReversalTransition::CReversalTransition

Строит объект разворотного перехода и инициализирует его продолжительность.

```
CReversalTransition(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Продолжительность перехода.

## <a name="creversaltransitionm_duration"></a><a name="m_duration"></a>CReversalTransition:::m_duration

Продолжительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
