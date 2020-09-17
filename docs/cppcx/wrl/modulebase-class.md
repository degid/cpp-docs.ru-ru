---
title: Класс ModuleBase
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::~ModuleBase
helpviewer_keywords:
- ModuleBase class
- Microsoft::WRL::Details::ModuleBase::DecrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::IncrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::ModuleBase, constructor
- Microsoft::WRL::Details::ModuleBase::~ModuleBase, destructor
ms.assetid: edce7591-6893-46f7-94a7-382827775548
ms.openlocfilehash: 13a8ceef3133e9946524e1fcd02e96535eccd7fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371260"
---
# <a name="modulebase-class"></a>Класс ModuleBase

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Примечания

Представляет базовый класс классов [модуля.](module-class.md)

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                         | Описание
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase::ModuleBase](#modulebase)        | Инициализирует экземпляр класса `Module`.
[ModuleBase:::»ModuleBase](#tilde-modulebase) | Деприиратизирует текущий `Module` экземпляр класса.

### <a name="public-methods"></a>Открытые методы

Имя                                                      | Описание
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase::DecrementObjectCount](#decrementobjectcount) | При реализации уменьшает число объектов, отслеживаемых модулем.
[ModuleBase::IncrementObjectCount](#incrementobjectcount) | При реализации увеличивает число объектов, отслеживаемых модулем.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ModuleBase`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="modulebasemodulebase"></a><a name="tilde-modulebase"></a>ModuleBase:::»ModuleBase

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>Примечания

Деприиратизирует текущий `ModuleBase` экземпляр класса.

## <a name="modulebasedecrementobjectcount"></a><a name="decrementobjectcount"></a>ModuleBase::DecrementObjectCount

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Подсчет перед операцией по декретуму.

### <a name="remarks"></a>Примечания

При реализации уменьшает число объектов, отслеживаемых модулем.

## <a name="modulebaseincrementobjectcount"></a><a name="incrementobjectcount"></a>ModuleBase::IncrementObjectCount

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Подсчет перед операцией приращения.

### <a name="remarks"></a>Примечания

При реализации увеличивает число объектов, отслеживаемых модулем.

## <a name="modulebasemodulebase"></a><a name="modulebase"></a>ModuleBase::ModuleBase

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
ModuleBase();
```

### <a name="remarks"></a>Примечания

Инициализирует экземпляр класса `Module`.
