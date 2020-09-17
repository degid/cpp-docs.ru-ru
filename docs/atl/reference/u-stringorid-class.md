---
title: класс _U_STRINGorID
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: 4e46ceec077b8daf8ef2a76110d2fc19dd39ae26
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325826"
---
# <a name="_u_stringorid-class"></a>класс _U_STRINGorID

Этот класс адаптера аргументов позволяет передавать идентификаторы ресурсов (LPCTSTRs) или идентификаторы ресурсов (UINT), не требуя от вызывающего абонента преобразования идентификатора в строку с помощью макроса MAKEINTRESOURCE.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class _U_STRINGorID
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|Конструктор.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|Идентификатор ресурса.|

## <a name="remarks"></a>Примечания

Этот класс предназначен для реализации оберток для API управления ресурсами Windows, таких как [функции FindResource,](/windows/win32/api/winbase/nf-winbase-findresourcea) [LoadIcon](/windows/win32/api/winuser/nf-winuser-loadiconw)и [LoadMenu,](/windows/win32/api/winuser/nf-winuser-loadmenuw) которые принимают аргумент LPCTSTR, который может быть либо названием ресурса, либо его идентификатором.

Класс определяет две перегрузки конструктора: один принимает аргумент LPCTSTR, а другой принимает аргумент UINT. Аргумент UINT преобразуется в тип ресурса, совместимый с функциями управления ресурсами Windows, используя макрос MAKEINTRESOURCE и результат, хранящийся в едином элементе данных класса, [m_lpstr.](#_u_stringorid__m_lpstr) Аргумент конструктору LPCTSTR хранится непосредственно без преобразования.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="_u_stringoridm_lpstr"></a><a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID::m_lpstr

Класс содержит значение, передаваемые одному из его конструкторов в качестве публичного члена данных LPCTSTR.

```
LPCTSTR m_lpstr;
```

## <a name="_u_stringorid_u_stringorid"></a><a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID::_U_STRINGorID

Конструктор UINT преобразует свой аргумент в тип ресурса, совместимый с функциями управления ресурсами Windows, используя макрос MAKEINTRESOURCE, и результат хранится в едином элементе данных класса, [m_lpstr](#_u_stringorid__m_lpstr).

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор ресурса.

*lpString*<br/>
Имя ресурса.

### <a name="remarks"></a>Примечания

Аргумент конструктору LPCTSTR хранится непосредственно без преобразования.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](../../atl/atl-class-overview.md)
