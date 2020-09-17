---
title: ArgTraitsHelper - структура
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
ms.openlocfilehash: 4acbd9fa660f29bbaf209282ff0e90f43621574d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360769"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>Параметры

*TDelegateИнтерфейс*<br/>
Интерфейс делегата.

## <a name="remarks"></a>Примечания

Помогает определить общие характеристики аргументов делегатов.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

Имя         | Описание
------------ | ------------------------------------------------------
`methodType` | Синоним для `decltype(&TDelegateInterface::Invoke)`.
`Traits`     | Синоним для `ArgTraits<methodType>`.

### <a name="public-constants"></a>Открытые константы

Имя                           | Описание
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[ArgTraitsHelper::args](#args) | Помогает [ArgTraits::args](#args) держать подсчет количества параметров `Invoke` на метод еликделегата интерфейса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ArgTraitsHelper`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="argtraitshelperargs"></a><a name="args"></a>ArgTraitsHelper::args

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>Примечания

Помогает `ArgTraitsHelper::args` вести подсчет количества параметров `Invoke` на методе интерфейса делегата.
