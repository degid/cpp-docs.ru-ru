---
title: Класс Mutex
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Mutex class
- Microsoft::WRL::Wrappers::Mutex::Lock method
- Microsoft::WRL::Wrappers::Mutex::Mutex, constructor
- Microsoft::WRL::Wrappers::Mutex::operator= operator
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
ms.openlocfilehash: 36466bd00c5b100f20ee87173e68fdef4131ec23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371236"
---
# <a name="mutex-class"></a>Класс Mutex

Представляет объект синхронизации, который исключительно управляет общим ресурсом.

## <a name="syntax"></a>Синтаксис

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя       | Описание
---------- | ------------------------------------------------------
`SyncLock` | Синоним для класса, поддерживающего синхронные блокировки.

### <a name="public-constructor"></a>Общественный конструктор

Имя                   | Описание
---------------------- | ------------------------------------------------
[Mutex::Mutex](#mutex) | Инициализирует новый экземпляр класса `Mutex`.

### <a name="public-members"></a>Общественные члены

Имя                 | Описание
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[Mutex::Lock](#lock) | Ожидание, пока текущий `Mutex` объект или объект, связанный с указанной ручкой, не выпустит mutex или указанный интервал тайм-аута.

### <a name="public-operator"></a>Оператор

Имя                                 | Описание
------------------------------------ | ---------------------------------------------------------------------------
[Mutex::оператор](#operator-assign) | Присваивает (перемещает) указанный `Mutex` объект текущему `Mutex` объекту.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Mutex`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Wrappers

## <a name="mutexlock"></a><a name="lock"></a>Mutex::Lock

Ожидание, пока текущий `Mutex` объект или объект, связанный с указанной ручкой, не выпустит mutex или указанный интервал тайм-аута.

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>Параметры

*Миллисекунд*<br/>
Интервал времени ожидания в миллисекундах. Значение по умолчанию равно INFINITE, что означает неограниченное время ожидания.

*H*<br/>
Ручка `Mutex` объекта.

### <a name="return-value"></a>Возвращаемое значение

## <a name="mutexmutex"></a><a name="mutex"></a>Mutex::Mutex

Инициализирует новый экземпляр класса `Mutex`.

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Ручка, или rvalue-ссылка на ручку, к объекту. `Mutex`

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует `Mutex` объект из указанной ручки. Второй конструктор инициализирует `Mutex` объект из указанной ручки, а затем `Mutex` перемещает право собственности на mutex к текущему объекту.

## <a name="mutexoperator"></a><a name="operator-assign"></a>Mutex::оператор

Присваивает (перемещает) указанный `Mutex` объект текущему `Mutex` объекту.

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Rvalue-ссылка на `Mutex` объект.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `Mutex` текущий объект.

### <a name="remarks"></a>Примечания

Для получения дополнительной информации, **см. Переместить Семантика** раздел [Rvalue Справочник Декларатор:  &&](../../cpp/rvalue-reference-declarator-amp-amp.md).
