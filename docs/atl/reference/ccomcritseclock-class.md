---
title: Класс Ккомкритсеклокк
ms.date: 11/04/2016
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
ms.openlocfilehash: fd2904f67d84db42d6b35aa4e505b063d6ea9a9f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224296"
---
# <a name="ccomcritseclock-class"></a>Класс Ккомкритсеклокк

Этот класс предоставляет методы для блокировки и разблокировки объекта критической секции.

## <a name="syntax"></a>Синтаксис

```
template<class TLock> class CComCritSecLock
```

#### <a name="parameters"></a>Параметры

*тлокк*<br/>
Объект, который должен быть заблокирован и разблокирован.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Ккомкритсеклокк:: Ккомкритсеклокк](#ctor)|Конструктор.|
|[Ккомкритсеклокк:: ~ Ккомкритсеклокк](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Ккомкритсеклокк:: Lock](#lock)|Вызовите этот метод, чтобы заблокировать объект критической секции.|
|[Ккомкритсеклокк:: Unlock](#unlock)|Вызовите этот метод, чтобы разблокировать объект критической секции.|

## <a name="remarks"></a>Примечания

Используйте этот класс для блокировки и разблокирования объектов в более безопасном виде, чем класс [ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md) или [класс ккомаутокритикалсектион](../../atl/reference/ccomautocriticalsection-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="ccomcritseclockccomcritseclock"></a><a name="ctor"></a>Ккомкритсеклокк:: Ккомкритсеклокк

Конструктор.

```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```

### <a name="parameters"></a>Параметры

*сложных*<br/>
Объект критического раздела.

*бинитиаллокк*<br/>
Начальное состояние блокировки: **`true`** означает, что заблокировано.

### <a name="remarks"></a>Примечания

Инициализирует объект критической секции.

## <a name="ccomcritseclockccomcritseclock"></a><a name="dtor"></a>Ккомкритсеклокк:: ~ Ккомкритсеклокк

Деструктор

```
~CComCritSecLock() throw();
```

### <a name="remarks"></a>Примечания

Разблокирует объект критической секции.

## <a name="ccomcritseclocklock"></a><a name="lock"></a>Ккомкритсеклокк:: Lock

Вызовите этот метод, чтобы заблокировать объект критической секции.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK, если объект был успешно заблокирован, или ошибка HRESULT при сбое.

### <a name="remarks"></a>Примечания

Если объект уже заблокирован, в отладочных сборках произойдет ошибка ASSERT.

## <a name="ccomcritseclockunlock"></a><a name="unlock"></a>Ккомкритсеклокк:: Unlock

Вызовите этот метод, чтобы разблокировать объект критической секции.

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>Примечания

Если объект уже разблокирован, в отладочных сборках произойдет ошибка ASSERT.

## <a name="see-also"></a>См. также статью

[Класс Ккомкритикалсектион](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Класс Ккомаутокритикалсектион](../../atl/reference/ccomautocriticalsection-class.md)
