---
title: Метод CompareStringOrdinal
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: 1291084395b02602b7a3de9013df6720d2e237fc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214101"
---
# <a name="comparestringordinal-method"></a>Метод CompareStringOrdinal

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
inline INT32 CompareStringOrdinal(
   HSTRING lhs,
   HSTRING rhs)
```

### <a name="parameters"></a>Параметры

*LHS*<br/>
Первый HSTRING для сравнения.

*rhs*<br/>
Второй HSTRING для сравнения.

## <a name="return-value"></a>Возвращаемое значение

|Значение|Условие|
|-----------|---------------|
|-1|*LHS* меньше, чем *RHS*.|
|0|*LHS* равняется *RHS*.|
|1|*LHS* больше, чем *RHS*.|

## <a name="remarks"></a>Примечания

Сравнивает два указанных объекта HSTRING и возвращает целое число, которое указывает их относительное расположение в порядке сортировки.

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Microsoft:: WRL:: оболочки::D состояния

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Wrappers::Details](microsoft-wrl-wrappers-details-namespace.md)
