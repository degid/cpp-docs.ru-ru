---
title: DontUseNewUseMake - класс
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
helpviewer_keywords:
- Microsoft::WRL::Details::DontUseNewUseMake class
- Microsoft::WRL::Details::DontUseNewUseMake::operator new operator
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
ms.openlocfilehash: ae67373b4f2f2d4a199b939b06e6f526f1365446
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371553"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
class DontUseNewUseMake;
```

## <a name="remarks"></a>Примечания

Предотвращает использование `new` оператора `RuntimeClass`в . Следовательно, вместо этого необходимо использовать [функцию Make.](make-function.md)

## <a name="members"></a>Участники

### <a name="public-operators"></a>Открытые операторы

Имя                                             | Описание
------------------------------------------------ | ---------------------------------------------------------------------------
[DontUseNewUseMake::оператор новый](#operator-new) | Перегружает `new` оператора и предотвращает его `RuntimeClass`использования в.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`DontUseNewUseMake`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="dontusenewusemakeoperator-new"></a><a name="operator-new"></a>DontUseNewUseMake::оператор новый

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
void* operator new(
   size_t,
   _In_ void* placement
);
```

### <a name="parameters"></a>Параметры

*__unnamed0*<br/>
Неименованный параметр, который определяет количество байт памяти для выделения.

*Размещения*<br/>
Выделяемый тип.

### <a name="return-value"></a>Возвращаемое значение

Предоставляет способ передачи дополнительных аргументов при перегрузке оператора `new`.

### <a name="remarks"></a>Примечания

Перегружает `new` оператора и предотвращает его `RuntimeClass`использования в.
