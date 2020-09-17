---
title: FactoryCache - структура
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
ms.openlocfilehash: 507d35179b9fa86399e56b18171800f41eaf1f10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371488"
---
# <a name="factorycache-structure"></a>FactoryCache - структура

Поддерживает инфраструктуру библиотеки шаблонов Windows Runtime C'и не предназначен айме к использованию непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>Примечания

Содержит местоположение фабрики класса и значение, которое идентифицирует зарегистрированный объект класса Среды выполнения Windows или модели COM.

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

Имя                              | Описание
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[ФабрикаCache::cookie](#cookie)   | Содержит значение, которое идентифицирует зарегистрированный объект класса Windows Runtime или COM, а затем используется для отстранителя объекта.
[ЗаводCache::фабрика](#factory) | Указывает на фабрику Windows Runtime или COM класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`FactoryCache`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="factorycachecookie"></a><a name="cookie"></a>ФабрикаCache::cookie

Поддерживает инфраструктуру библиотеки шаблонов Windows Runtime C'и не предназначен айме к использованию непосредственно из кода.

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>Примечания

Содержит значение, которое идентифицирует зарегистрированный объект класса Windows Runtime или COM, а затем используется для отстранителя объекта.

## <a name="factorycachefactory"></a><a name="factory"></a>ЗаводCache::фабрика

Поддерживает инфраструктуру библиотеки шаблонов Windows Runtime C'и не предназначен айме к использованию непосредственно из кода.

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>Примечания

Указывает на фабрику Windows Runtime или COM класса.
