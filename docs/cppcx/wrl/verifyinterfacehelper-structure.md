---
title: VerifyInterfaceHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper
- implements/Microsoft::WRL::Details::VerifyInterfaceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInterfaceHelper structure
- Microsoft::WRL::Details::VerifyInterfaceHelper::Verify method
ms.assetid: ea95b641-199a-4fdf-964b-186b40cb3ba7
ms.openlocfilehash: 09c2cc7e08e2dc0e8df42c64d285c37627c5925a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374237"
---
# <a name="verifyinterfacehelper-structure"></a>VerifyInterfaceHelper - структура

Поддерживает инфраструктуру библиотеки шаблонов Windows Runtime C'и не предназначен айме к использованию непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <bool isWinRTInterface, typename I>
struct VerifyInterfaceHelper;

template <typename I>
struct VerifyInterfaceHelper<false, I>;
```

### <a name="parameters"></a>Параметры

*Я*<br/>
Интерфейс для проверки.

*isWinRTИнтерфейс*

## <a name="remarks"></a>Примечания

Проверяет, что интерфейс, указанный параметром шаблона, соответствует определенным требованиям.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

Имя                                            | Описание
----------------------------------------------- | ---------------------------------------------------------------------------------------------------
[Метод VerifyInterfaceHelper::Verify](#verify) | Проверяет, отвечает ли определенным требованиям интерфейс, заданный текущим параметром шаблона.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VerifyInterfaceHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="verifyinterfacehelperverify"></a><a name="verify"></a>VerifyInterfaceHelper::Verify

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
static void Verify();
```

### <a name="remarks"></a>Примечания

Проверяет, отвечает ли определенным требованиям интерфейс, заданный текущим параметром шаблона.
