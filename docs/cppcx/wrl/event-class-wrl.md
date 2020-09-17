---
title: Класс событий (WRL)
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
ms.openlocfilehash: 27a90bb801d1b6869b2391227464bb215dd42538
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220487"
---
# <a name="event-class-wrl"></a>Класс событий (WRL)

Представляет событие.

## <a name="syntax"></a>Синтаксис

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

name                   | Описание
---------------------- | ------------------------------------------------
[Событие:: событие](#event) | Инициализирует новый экземпляр класса `Event`.

### <a name="public-operators"></a>Открытые операторы

Имя                                 | Описание
------------------------------------ | ------------------------------------------------------------------------
[Событие::operator=](#operator-assign) | Присваивает указанную `Event` ссылку текущему `Event` экземпляру.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HandleT`

`Event`

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Программы Microsoft:: WRL:: оболочки

## <a name="eventevent"></a><a name="event"></a>Событие:: событие

Инициализирует новый экземпляр класса `Event`.

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Дескриптор события. По умолчанию *h* инициализируется значением **`nullptr`** .

## <a name="eventoperator"></a><a name="operator-assign"></a>Событие::operator=

Присваивает указанную `Event` ссылку текущему `Event` экземпляру.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на `Event` экземпляр.

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий `Event` экземпляр.
