---
title: Класс RoInitializeWrapper
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::HRESULT
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
helpviewer_keywords:
- Microsoft::WRL::Wrappers::RoInitializeWrapper class
- Microsoft::WRL::Wrappers::RoInitializeWrapper::operator HRESULT operator
- Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper, constructor
- Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper, destructor
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
ms.openlocfilehash: eba9162f17b98d13a9caf956b4f110b89dd81c37
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371224"
---
# <a name="roinitializewrapper-class"></a>Класс RoInitializeWrapper

Инициализирует время выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class RoInitializeWrapper;
```

## <a name="remarks"></a>Примечания

`RoInitializeWrapper`это удобство, которое инициализирует Время выполнения Windows и возвращает HRESULT, который указывает, была ли операция успешной. Поскольку вызовы `::Windows::Foundation::Uninitialize`деструктора класса `RoInitializeWrapper` должны быть объявлены в глобальном или верхнем уровне.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                    | Описание
----------------------------------------------------------------------- | -----------------------------------------------------------------
[RoInitializeWrapper::RoInitializeWrapper](#roinitializewrapper)        | Инициализирует новый экземпляр класса `RoInitializeWrapper`.
[RoInitializeWrapper:: »RoInitializeWrapper](#tilde-roinitializewrapper) | Уничтожает текущий `RoInitializeWrapper` экземпляр класса.

### <a name="public-operators"></a>Открытые операторы

Имя                                       | Описание
------------------------------------------ | ------------------------------------------------------------------------
[RoInitializeWrapper::HRESULT()](#hresult) | Извлекает HRESULT производства `RoInitializeWrapper` конструктора.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RoInitializeWrapper`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Wrappers

## <a name="roinitializewrapperhresult"></a><a name="hresult"></a>RoInitializeWrapper::HRESULT()

Извлекает значение HRESULT, произведенное последним `RoInitializeWrapper` конструктором.

```cpp
operator HRESULT()
```

## <a name="roinitializewrapperroinitializewrapper"></a><a name="roinitializewrapper"></a>RoInitializeWrapper::RoInitializeWrapper

Инициализирует новый экземпляр класса `RoInitializeWrapper`.

```cpp
RoInitializeWrapper(RO_INIT_TYPE flags)
```

### <a name="parameters"></a>Параметры

*Флаги*<br/>
Один из RO_INIT_TYPE перечисления, который определяет поддержку, предоставляемую Windows Runtime.

### <a name="remarks"></a>Примечания

Класс `RoInitializeWrapper` вызывает `Windows::Foundation::Initialize(flags)`.

## <a name="roinitializewrapperroinitializewrapper"></a><a name="tilde-roinitializewrapper"></a>RoInitializeWrapper:: »RoInitializeWrapper

Не инициирует время выполнения Windows.

```cpp
~RoInitializeWrapper()
```

### <a name="remarks"></a>Примечания

Класс `RoInitializeWrapper` вызывает `Windows::Foundation::Uninitialize()`.
