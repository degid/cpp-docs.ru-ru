---
title: Функция GetModuleBase
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: 0d130fffa9fad9ae327d03eaa01d84742094cc67
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213971"
---
# <a name="getmodulebase-function"></a>Функция GetModuleBase

Извлекает указатель [ModuleBase](modulebase-class.md) , позволяющий увеличивать и уменьшать число ссылок объекта [RuntimeClass](runtimeclass-class.md) .

## <a name="syntax"></a>Синтаксис

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на объект `ModuleBase`.

## <a name="remarks"></a>Примечания

Эта внутренняя функция используется для увеличения и уменьшения числа ссылок объекта.

Эту функцию можно использовать для управления счетчиком ссылок путем вызова [ModuleBase:: IncrementObjectCount](modulebase-class.md#incrementobjectcount) и [ModuleBase::D екрементобжекткаунт](modulebase-class.md#decrementobjectcount).

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
