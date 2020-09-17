---
title: класс _U_MENUorID
ms.date: 11/04/2016
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
ms.openlocfilehash: 419c9e79178db12efe278838ec8630e04ac3c461
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325839"
---
# <a name="_u_menuorid-class"></a>класс _U_MENUorID

Этот класс предоставляет обертки для `CreateWindow` и `CreateWindowEx`.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class _U_MENUorID
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Конструктор.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Ручка к меню.|

## <a name="remarks"></a>Примечания

Этот класс адаптера аргументов позволяет передавать либо идентифицаторы (UINT) или ручки меню (HMENUs) функции, не требуя явного отливки со стороны вызывающего абонента.

Этот класс предназначен для реализации оберток для API Windows, в частности функций [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) и [CreateWindowEx,](/windows/win32/api/winuser/nf-winuser-createwindowexw) которые принимают аргумент HMENU, который может быть идентификатором окна ребенка (UINT), а не ручкой меню. Например, вы можете увидеть этот класс в использовании в качестве параметра [для CWindowImpl::Create](cwindowimpl-class.md#create).

Класс определяет две перегрузки конструктора: один принимает аргумент UINT, а другой принимает аргумент HMENU. Аргумент UINT просто отбрасывается в HMENU в конструкторе и результат, хранящийся в единственном элементе данных класса, [m_hMenu](#_u_menuorid__m_hmenu). Аргумент конструктору HMENU хранится непосредственно без преобразования.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="_u_menuoridm_hmenu"></a><a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu

Класс удерживает значение, передаваемые одному из его конструкторов в качестве публичного члена данных HMENU.

```
HMENU m_hMenu;
```

## <a name="_u_menuorid_u_menuorid"></a><a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID

Аргумент UINT просто отбрасывается в HMENU в конструкторе и результат, хранящийся в единственном элементе данных класса, [m_hMenu](#_u_menuorid__m_hmenu).

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор окна ребенка.

*hMenu*<br/>
Ручка меню.

### <a name="remarks"></a>Примечания

Аргумент конструктору HMENU хранится непосредственно без преобразования.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
