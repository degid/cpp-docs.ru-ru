---
title: VerifyInheritanceHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper
- implements/Microsoft::WRL::Details::VerifyInheritanceHelper::Verify
helpviewer_keywords:
- Microsoft::WRL::Details::VerifyInheritanceHelper structure
- Microsoft::WRL::Details::VerifyInheritanceHelper::Verify method
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
ms.openlocfilehash: 3650cfb70ffc12572b3965534eff4e1f2ecb2cf5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374233"
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename I, typename Base>
struct VerifyInheritanceHelper;

template <typename I>
struct VerifyInheritanceHelper<I, Nil>;
```

### <a name="parameters"></a>Параметры

*Я*<br/>
Тип.

*Базы*<br/>
Другой тип.

## <a name="remarks"></a>Примечания

Тестирует, является ли один интерфейс производным от другого интерфейса.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

Имя                                       | Описание
------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------
[VerifyInheritanceHelper::Verify](#verify) | Тестирует два интерфейса, указанные текущими параметрами шаблона, и определяет, является ли один интерфейс производным от другого.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`VerifyInheritanceHelper`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="verifyinheritancehelperverify"></a><a name="verify"></a>VerifyInheritanceHelper::Verify

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
static void Verify();
```

### <a name="remarks"></a>Примечания

Тестирует два интерфейса, указанные текущими параметрами шаблона, и определяет, является ли один интерфейс производным от другого.

Если это условие не выполняется, выдается ошибка.
