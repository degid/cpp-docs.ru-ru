---
title: IsBaseOfStrict - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
ms.openlocfilehash: 11acb4c7162a17ff763a574c27c186061ae476a7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211532"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict - структура

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Параметры

*Из*<br/>
Базовый тип.

*Производный*<br/>
Производный тип.

## <a name="remarks"></a>Примечания

Проверяет, является ли один тип базовым для другого.

Первый шаблон проверяет, является ли тип производным от базового типа, который может возвращать **`true`** или **`false`** . Второй шаблон проверяет, является ли тип производным от самого себя, который всегда возвращает **`false`** .

## <a name="members"></a>Элементы

### <a name="public-constants"></a>Открытые константы

Имя                            | Описание
------------------------------- | --------------------------------------------------
[IsBaseOfStrict:: value](#value) | Указывает, является ли один тип базовым для другого.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IsBaseOfStrict`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="isbaseofstrictvalue"></a><a name="value"></a>IsBaseOfStrict:: value

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Примечания

Указывает, является ли один тип базовым для другого.

`value`имеет значение **`true`** , если тип `Base` является базовым классом типа `Derived` , в противном случае — значение **`false`** .
