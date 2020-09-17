---
title: InterfaceList - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
ms.openlocfilehash: 7fd06f71bc4d8097366dc0e87d7ff92c5a12a790
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213867"
---
# <a name="interfacelist-structure"></a>InterfaceList - структура

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T, typename U>
struct InterfaceList;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Имя интерфейса; Первый интерфейс в рекурсивном списке.

*U*<br/>
Имя интерфейса; остальные интерфейсы в рекурсивном списке.

## <a name="remarks"></a>Примечания

Используется для создания рекурсивного списка интерфейсов.

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Открытые определения типов

|Имя|Описание|
|----------|-----------------|
|`FirstT`|Синоним для параметра шаблона *T*.|
|`RestT`|Синоним для параметра шаблона *U*.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`InterfaceList`

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)
