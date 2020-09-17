---
title: DerefHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 43453d3162de697fa1cfcf0581953c91bbe3934f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214049"
---
# <a name="derefhelper-structure"></a>DerefHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
struct DerefHelper;

template <typename T>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Параметр шаблона.

## <a name="remarks"></a>Примечания

Представляет разыменованный указатель на параметр шаблона `T*`.

**Дерефхелпер** используется в выражении, например: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Открытые определения типов

|Имя|Описание|
|----------|-----------------|
|`DerefType`|Идентификатор для разыменованного параметра шаблона `T*`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`DerefHelper`

## <a name="requirements"></a>Требования

**Заголовок:** Async.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)
