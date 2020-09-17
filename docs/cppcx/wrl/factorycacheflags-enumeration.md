---
title: Перечисление FactoryCacheFlags
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 3381b2bcfcbf298270b547199ae614291855a2f7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843278"
---
# <a name="factorycacheflags-enumeration"></a>Перечисление FactoryCacheFlags

Определяет, кэшируются ли объекты фабрики.

## <a name="syntax"></a>Синтаксис

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>Примечания

По умолчанию политика кэширования фабрики указывается как параметр шаблона [ModuleType](moduletype-enumeration.md) при создании объекта [модуля](module-class.md) . Чтобы переопределить эту политику, укажите значение **факторикачефлагс** при создании объекта фабрики.

| Политика | Описание |
|-|-|
|`FactoryCacheDefault`|Используется политика кэширования объекта `Module`.|
|`FactoryCacheEnabled`|Включает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|
|`FactoryCacheDisabled`|Выключает кэширование фабрики независимо от параметра шаблона `ModuleType`, используемого для создания объекта `Module`.|

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft:: WRL](microsoft-wrl-namespace.md)
