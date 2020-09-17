---
title: Класс CConstantTransition
ms.date: 11/04/2016
f1_keywords:
- CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::Create
- AFXANIMATIONCONTROLLER/CConstantTransition::m_duration
helpviewer_keywords:
- CConstantTransition [MFC], CConstantTransition
- CConstantTransition [MFC], Create
- CConstantTransition [MFC], m_duration
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
ms.openlocfilehash: 0d5d92f02cc3b56268966f1cd79451578a5cc390
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369410"
---
# <a name="cconstanttransition-class"></a>Класс CConstantTransition

Инкапсулирует постоянный переход.

## <a name="syntax"></a>Синтаксис

```
class CConstantTransition : public CBaseTransition;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CConstantTransition::CConstantTransition](#cconstanttransition)|Строит переходный объект и инициализирует его продолжительность.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CConstantTransition::Создание](#create)|Вызывает библиотеку перехода для создания инкапсулированного объекта переходного COM. (Переопределяет [CBaseПереход::Создание](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CConstantTransition:::m_duration](#m_duration)|Продолжительность перехода.|

## <a name="remarks"></a>Примечания

Во время постоянного перехода значение переменной анимации остается на начальном значении в течение всего периода перехода. Поскольку все переходы очищаются автоматически, рекомендуется выделять их с помощью нового оператора. Инкапсулированный объект IUIAnimationTransition COM создается CAnimationController::AnimateGroup, до тех пор это NULL. Изменение переменных членов после создания этого объекта COM не имеет эффекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseПереход](../../mfc/reference/cbasetransition-class.md)

`CConstantTransition`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="cconstanttransitioncconstanttransition"></a><a name="cconstanttransition"></a>CConstantTransition::CConstantTransition

Строит переходный объект и инициализирует его продолжительность.

```
CConstantTransition (UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Продолжительность перехода.

## <a name="cconstanttransitioncreate"></a><a name="create"></a>CConstantTransition::Создание

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

## <a name="cconstanttransitionm_duration"></a><a name="m_duration"></a>CConstantTransition:::m_duration

Продолжительность перехода.

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
