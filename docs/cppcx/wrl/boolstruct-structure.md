---
title: BoolStruct - структура
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::BoolStruct
- internal/Microsoft::WRL::Details::BoolStruct::Member
helpviewer_keywords:
- Microsoft::WRL::Details::BoolStruct structure
- Microsoft::WRL::Details::BoolStruct::Member data member
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
ms.openlocfilehash: 4f2a5acf6edb824cff2121c1b6444181b5cfcf98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371855"
---
# <a name="boolstruct-structure"></a>BoolStruct - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
struct BoolStruct;
```

## <a name="remarks"></a>Примечания

Структура `BoolStruct` определяет, `ComPtr` управляет ли a течением срока службы объекта интерфейса. `BoolStruct`используется внутренне оператором [BoolType()](comptr-class.md#operator-microsoft-wrl-details-booltype)

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

Имя                          | Описание
----------------------------- | ------------------------------------------------------------------------------------------------------------------
[BoolStruct::Член](#member) | Упомянет, что [ComPtr](comptr-class.md) управляет или не управляет сроком службы объекта интерфейса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BoolStruct`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="boolstructmember"></a><a name="member"></a>BoolStruct::Член

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
int Member;
```

### <a name="remarks"></a>Примечания

Упомянет, что [ComPtr](comptr-class.md) управляет или не управляет сроком службы объекта интерфейса.
