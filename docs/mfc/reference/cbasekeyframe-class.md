---
title: Класс CBaseKeyFrame
ms.date: 11/04/2016
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
helpviewer_keywords:
- CBaseKeyFrame [MFC], CBaseKeyFrame
- CBaseKeyFrame [MFC], AddToStoryboard
- CBaseKeyFrame [MFC], GetAnimationKeyframe
- CBaseKeyFrame [MFC], IsAdded
- CBaseKeyFrame [MFC], IsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_bAdded
- CBaseKeyFrame [MFC], m_bIsKeyframeAtOffset
- CBaseKeyFrame [MFC], m_keyframe
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
ms.openlocfilehash: 3fcd55f6a157f4b837090a3608fb509b870aae5d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81352990"
---
# <a name="cbasekeyframe-class"></a>Класс CBaseKeyFrame

Реализует базовую функциональность ключевого кадра.

## <a name="syntax"></a>Синтаксис

```
class CBaseKeyFrame : public CObject;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|Строит объект ключевой рамы.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CBaseKeyFrame:AddtoStoryboard](#addtostoryboard)|Добавляет клавиатуру в раскадровку.|
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|Возвращает базовое значение ключевой частоты.|
|[CBaseKeyFrame::Добавлено](#isadded)|Сообщает, был ли добавлен ключ-панель в раскадровку.|
|[CBaseKeyFrame::IsKeyframeatOffset](#iskeyframeatoffset)|Определяет, следует ли добавлять ключ-рамку в раскадровку в смещении или после перехода.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CBaseKeyFrame::m_bAdded](#m_badded)|Определяет, был ли этот ключ-рамка добавлен в раскадровку.|
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|Определяется, следует ли добавлять этот ключевой элемент в раскадровку в смещении с другого существующего ключевого кадра или в конце некоторого перехода.|
|[CBaseKeyFrame:::m_keyframe](#m_keyframe)|Представляет aKeyframe API анимации Windows. Когда клавиатура не инициализирована, она устанавливается на предопределенное значение UI_ANIMATION_KEYFRAME_STORYBOARD_START.|

## <a name="remarks"></a>Примечания

Инкапсулирует UI_ANIMATION_KEYFRAME переменной. Служит базовым классом для любой реализации ключевых кадров. Ключевой элемент представляет момент времени в раскадровке и может использоваться для указания времени начала и окончания переходов. Есть два типа ключевых кадров - ключевые кадры, добавленные в раскадровку в указанном смещении (в срок) или ключевые кадры, добавленные после указанного перехода. Поскольку продолжительность некоторых переходов не может быть известна до начала анимации, фактические значения некоторых ключевых кадров определяются только во времени выполнения. Поскольку ключевые кадры могут зависеть от переходов, которые, в свою очередь, зависят от ключевых кадров, важно предотвратить бесконечные рекурсии при построении цепочек ключей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CBaseKeyFrame`

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="cbasekeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>CBaseKeyFrame:AddtoStoryboard

Добавляет клавиатуру в раскадровку.

```
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку.

*bDeepAdd*<br/>
Если этот параметр является истинным и добавленный ключевой параметр зависит от некоторых других ключевых рамок или перехода, этот метод пытается добавить этот ключевой кадр или переход к раскадровке в первую очередь.

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ключ был добавлен в раскадровку успешно; в противном случае FALSE.

### <a name="remarks"></a>Примечания

Этот метод называется для добавления клавиатуры в раскадровку.

## <a name="cbasekeyframecbasekeyframe"></a><a name="cbasekeyframe"></a>CBaseKeyFrame::CBaseKeyFrame

Строит объект ключевой рамы.

```
CBaseKeyFrame();
```

## <a name="cbasekeyframegetanimationkeyframe"></a><a name="getanimationkeyframe"></a>CBaseKeyFrame::GetAnimationKeyframe

Возвращает базовое значение ключевой частоты.

```
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий ключевой кадр. Значение по умолчанию является UI_ANIMATION_KEYFRAME_STORYBOARD_START.

### <a name="remarks"></a>Примечания

Это элемент доступа к базовому значению ключевых кадров.

## <a name="cbasekeyframeisadded"></a><a name="isadded"></a>CBaseKeyFrame::Добавлено

Сообщает, был ли добавлен ключ-панель в раскадровку.

```
BOOL IsAdded() const;
```

### <a name="return-value"></a>Возвращаемое значение

TRUE, если ключ добавляется в раскадровку; otehrwise FALSE.

### <a name="remarks"></a>Примечания

В базовом классе IsAdded всегда возвращается TRUE, но он переопределяется в производных классах.

## <a name="cbasekeyframeiskeyframeatoffset"></a><a name="iskeyframeatoffset"></a>CBaseKeyFrame::IsKeyframeatOffset

Определяет, следует ли добавлять ключ-рамку в раскадровку в смещении или после перехода.

```
BOOL IsKeyframeAtOffset() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ключ должен быть добавлен к раскадровке в некоторых указанных смещения. FALSE, если ключ должен быть добавлен в раскадровку после некоторого перехода.

### <a name="remarks"></a>Примечания

Определяет, следует ли добавлять ключ-рамку в раскадровку в смещении. Смещение или переход должны быть указаны в производном классе.

## <a name="cbasekeyframem_badded"></a><a name="m_badded"></a>CBaseKeyFrame::m_bAdded

Определяет, был ли этот ключ-рамка добавлен в раскадровку.

```
BOOL m_bAdded;
```

## <a name="cbasekeyframem_biskeyframeatoffset"></a><a name="m_biskeyframeatoffset"></a>CBaseKeyFrame::m_bIsKeyframeAtOffset

Определяется, следует ли добавлять этот ключевой элемент в раскадровку в смещении с другого существующего ключевого кадра или в конце некоторого перехода.

```
BOOL m_bIsKeyframeAtOffset;
```

## <a name="cbasekeyframem_keyframe"></a><a name="m_keyframe"></a>CBaseKeyFrame:::m_keyframe

Представляет aKeyframe API анимации Windows. Когда клавиатура не инициализирована, она устанавливается на предопределенное значение UI_ANIMATION_KEYFRAME_STORYBOARD_START.

```
UI_ANIMATION_KEYFRAME m_keyframe;
```

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
