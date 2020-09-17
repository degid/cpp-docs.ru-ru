---
title: _U_RECT класс
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: 8a4d5b2a770b3f0ecfe10be0fbad22a702aa0531
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325812"
---
# <a name="_u_rect-class"></a>_U_RECT класс

Этот класс адаптера аргумента позволяет передавать указатели `RECT` или ссылки функции, которая реализуется с точки зрения указателей.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class _U_RECT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[_U_RECT::_U_RECT](#_u_rect___u_rect)|Конструктор.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[_U_RECT::m_lpRect](#_u_rect__m_lprect)|Указатель на `RECT`.|

## <a name="remarks"></a>Примечания

Класс определяет две перегрузки конструктора: один принимает **аргумент RECT&,** а другой принимает `LPRECT` аргумент. Первый конструктор хранит адрес эталонного аргумента в едином члене данных класса, [m_lpRect](#_u_rect__m_lprect). Аргумент к конструктору указателя хранится сразу без преобразования.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="_u_rectm_lprect"></a><a name="_u_rect__m_lprect"></a>_U_RECT::m_lpRect

Класс сохраняет значение, передаваемые одному из `LPRECT` его конструкторов в качестве публичного члена данных.

```
LPRECT m_lpRect;
```

## <a name="_u_rect_u_rect"></a><a name="_u_rect___u_rect"></a>_U_RECT::_U_RECT

Адрес эталонного аргумента хранится в едином члене данных класса, [m_lpRect](#_u_rect__m_lprect).

```
_U_RECT(RECT& rc);
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*Rc*<br/>
Ссылка `RECT`.

*lpRect*<br/>
Указатель. `RECT`

### <a name="remarks"></a>Примечания

Аргумент к конструктору указателя хранится сразу без преобразования.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
