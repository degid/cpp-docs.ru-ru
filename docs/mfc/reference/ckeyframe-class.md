---
title: Класс CKeyFrame
ms.date: 11/04/2016
f1_keywords:
- CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::CKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAfterTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::AddToStoryboardAtOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetExistingKeyframe
- AFXANIMATIONCONTROLLER/CKeyFrame::GetOffset
- AFXANIMATIONCONTROLLER/CKeyFrame::GetTransition
- AFXANIMATIONCONTROLLER/CKeyFrame::m_offset
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pExistingKeyFrame
- AFXANIMATIONCONTROLLER/CKeyFrame::m_pTransition
helpviewer_keywords:
- CKeyFrame [MFC], CKeyFrame
- CKeyFrame [MFC], AddToStoryboard
- CKeyFrame [MFC], AddToStoryboardAfterTransition
- CKeyFrame [MFC], AddToStoryboardAtOffset
- CKeyFrame [MFC], GetExistingKeyframe
- CKeyFrame [MFC], GetOffset
- CKeyFrame [MFC], GetTransition
- CKeyFrame [MFC], m_offset
- CKeyFrame [MFC], m_pExistingKeyFrame
- CKeyFrame [MFC], m_pTransition
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
ms.openlocfilehash: f535503338a82c7cc70455ae6a08cdab0f13c624
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372295"
---
# <a name="ckeyframe-class"></a>Класс CKeyFrame

Представляет ключевой кадр анимации.

## <a name="syntax"></a>Синтаксис

```
class CKeyFrame : public CBaseKeyFrame;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CKeyFrame::CKeyFrame](#ckeyframe)|Перегружен. Строит ключевой кадр, который зависит от других ключевых рамок.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CKeyFrame::AddtoStoryboard](#addtostoryboard)|Добавляет клавиатуру в раскадровку. (Переопределяет [CbaseKeyFrame::AddtoStoryboard](../../mfc/reference/cbasekeyframe-class.md#addtostoryboard).)|
|[CKeyframe::AddtoStoryboardAfterTransition](#addtostoryboardaftertransition)|Добавляет клавиатуру в раскадровку после перехода.|
|[CKeyFrame::AddtoStoryboardatOffset](#addtostoryboardatoffset)|Добавляет клавиатуру к раскадровке в смещении.|
|[CKeyFrame::GetExistingKeyframe](#getexistingkeyframe)|Возвращает указатель на ключевой кадр, от чего зависит этот ключевой момент.|
|[CKeyFrame::GetOffset](#getoffset)|Возвращает смещение с другого ключевого кадра.|
|[CKeyFrame::GetTransition](#gettransition)|Возвращает указатель на переход, от этого зависит этот ключевой момент.|

### <a name="protected-data-members"></a>Защищенные члены данных

|Имя|Описание|
|----------|-----------------|
|[CKeyFrame::m_offset](#m_offset)|Определяет смещение этого ключевого кадра с ключа, хранящегося в m_pExistingKeyFrame.|
|[CKeyFrame::m_pExistingKeyFrame](#m_pexistingkeyframe)|Хранит указатель на существующий кефрейм. Этот ключ добавляется в раскадровку с m_offset к существующему ключу.|
|[CKeyFrame::m_pTransition](#m_ptransition)|Хранит указатель на транситивание, которое начинается на этом ключевом кадре.|

## <a name="remarks"></a>Примечания

Этот класс реализует клавиатуру анимации. Ключевой элемент представляет момент времени в раскадровке и может использоваться для указания времени начала и окончания переходов. Ключевой кадр может быть основан на другом ключевом кадре и иметь смещение (в секундах) от него, или может быть основан на переходе и представлять момент времени, когда этот переход заканчивается.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CBaseKeyFrame](../../mfc/reference/cbasekeyframe-class.md)

[CKeyFrame](../../mfc/reference/ckeyframe-class.md)

## <a name="requirements"></a>Требования

**Заголовок:** afxanimationcontroller.h

## <a name="ckeyframeaddtostoryboard"></a><a name="addtostoryboard"></a>CKeyFrame::AddtoStoryboard

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
Определяет, следует ли добавлять ключевой кадр или переход рекурсивно.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ключ был добавлен успешно.

### <a name="remarks"></a>Примечания

Этот метод добавляет клавиатуру к раскадровке. Если это зависит от других ключевых рамок или перехода и bDeepAdd является правдой, этот метод пытается добавить их рекурсивно.

## <a name="ckeyframeaddtostoryboardaftertransition"></a><a name="addtostoryboardaftertransition"></a>CKeyframe::AddtoStoryboardAfterTransition

Добавляет клавиатуру в раскадровку после перехода.

```
BOOL AddToStoryboardAfterTransition(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку.

*bDeepAdd*<br/>
Определяет, следует ли добавлять переход рекурсивно.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ключ был добавлен успешно.

### <a name="remarks"></a>Примечания

Эта функция вызывается фректовой для добавления ключевой панели к раскадровке после перехода.

## <a name="ckeyframeaddtostoryboardatoffset"></a><a name="addtostoryboardatoffset"></a>CKeyFrame::AddtoStoryboardatOffset

Добавляет клавиатуру к раскадровке в смещении.

```
virtual BOOL AddToStoryboardAtOffset(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDeepAdd);
```

### <a name="parameters"></a>Параметры

*pStoryboard*<br/>
Указатель на раскадровку.

*bDeepAdd*<br/>
Определяет, следует ли добавлять ключевой кадр, от этого ключевого кадра зависит рекурсивно.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если ключ был добавлен успешно.

### <a name="remarks"></a>Примечания

Эта функция вызывается фректовой для добавления ключевой панели к раскадровке в смещении.

## <a name="ckeyframeckeyframe"></a><a name="ckeyframe"></a>CKeyFrame::CKeyFrame

Строит ключевой элемент, зависят от перехода.

```
CKeyFrame(CBaseTransition* pTransition);

CKeyFrame(
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>Параметры

*pTransition*<br/>
Указатель на переход.

*pKeyframe*<br/>
Указатель на клавиатуру.

*Смещение*<br/>
Смещение, в секундах, от клавиатуры, указанной pKeyframe.

### <a name="remarks"></a>Примечания

Построенный ключевой кадр будет представлять момент времени в раскадровке, когда указанный переход заканчивается.

## <a name="ckeyframegetexistingkeyframe"></a><a name="getexistingkeyframe"></a>CKeyFrame::GetExistingKeyframe

Возвращает указатель на ключевой кадр, от чего зависит этот ключевой момент.

```
CBaseKeyFrame* GetExistingKeyframe();
```

### <a name="return-value"></a>Возвращаемое значение

Действительный указатель на ключевой кадр, или NULL, если этот ключевой кадр не зависит от других ключевых кадров.

### <a name="remarks"></a>Примечания

Это доступ к ключевой кадр, от этого от этого ключа зависит.

## <a name="ckeyframegetoffset"></a><a name="getoffset"></a>CKeyFrame::GetOffset

Возвращает смещение с другого ключевого кадра.

```
UI_ANIMATION_SECONDS GetOffset();
```

### <a name="return-value"></a>Возвращаемое значение

Смещение в секундах от другого ключевого кадра.

### <a name="remarks"></a>Примечания

Этот метод должен быть вызван для определения смещения в секундах от другого ключевого кадра.

## <a name="ckeyframegettransition"></a><a name="gettransition"></a>CKeyFrame::GetTransition

Возвращает указатель на переход, от этого зависит этот ключевой момент.

```
CBaseTransition* GetTransition();
```

### <a name="return-value"></a>Возвращаемое значение

Действительный указатель перехода, или NULL, если этот ключевой элемент не зависит от перехода.

### <a name="remarks"></a>Примечания

Это элемент доступа к переходу, от этого ключа зависит.

## <a name="ckeyframem_offset"></a><a name="m_offset"></a>CKeyFrame::m_offset

Определяет смещение этого ключевого кадра с ключа, хранящегося в m_pExistingKeyFrame.

```
UI_ANIMATION_SECONDS m_offset;
```

## <a name="ckeyframem_pexistingkeyframe"></a><a name="m_pexistingkeyframe"></a>CKeyFrame::m_pExistingKeyFrame

Хранит указатель на существующий кефрейм. Этот ключ добавляется в раскадровку с m_offset к существующему ключу.

```
CBaseKeyFrame* m_pExistingKeyFrame;
```

## <a name="ckeyframem_ptransition"></a><a name="m_ptransition"></a>CKeyFrame::m_pTransition

Хранит указатель на транситивание, которое начинается на этом ключевом кадре.

```
CBaseTransition* m_pTransition;
```

## <a name="see-also"></a>См. также раздел

[Классы](../../mfc/reference/mfc-classes.md)
