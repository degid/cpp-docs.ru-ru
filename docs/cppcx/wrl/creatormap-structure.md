---
title: CreatorMap - структура
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
ms.openlocfilehash: 1527f81694d1d809d585f3f6504c0e6433a2c26b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372598"
---
# <a name="creatormap-structure"></a>CreatorMap - структура

Поддерживает инфраструктуру библиотеки шаблонов Windows Runtime C'и не предназначен айме к использованию непосредственно из кода.

## <a name="syntax"></a>Синтаксис

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>Примечания

Содержит информацию о том, как инициализировать, зарегистрировать и не регистрировать объекты.

`CreatorMap` содержит следующие сведения:

- Как инициализировать, зарегистрировать и отменить объекты.

- Как сравнить данные активации в зависимости от классической фабрики COM или Windows Runtime.

- Информация о заводском кэше и названии сервера для интерфейса.

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

Имя                                          | Описание
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[CreatorMap::activationId](#activationid)     | Представляет идентификатор объекта, идентифицированный либо классическим идентификатором класса COM, либо именем Windows Runtime.
[CreatorMap::factoryCache](#factorycache)     | Хранит указатель на заводской кэш для `CreatorMap`.
[CreatorMap::factoryCreator](#factorycreator) | Создает фабрику для `CreatorMap`указанного.
[CreatorMap::serverName](#servername)         | Хранит имя сервера `CreatorMap`для .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`CreatorMap`

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft:WRL::Details

## <a name="creatormapactivationid"></a><a name="activationid"></a>CreatorMap::activationId

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>Параметры

*clsid*<br/>
Идентификатор интерфейса.

*getRuntimeName*<br/>
Функция, которая извлекает имя объекта в среде выполнения Windows.

### <a name="remarks"></a>Примечания

Представляет идентификатор объекта, который определен идентификатором класса классической модели COM или именем в среде выполнения Windows.

## <a name="creatormapfactorycache"></a><a name="factorycache"></a>CreatorMap::factoryCache

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>Примечания

Хранит указатель на заводской кэш для `CreatorMap`.

## <a name="creatormapfactorycreator"></a><a name="factorycreator"></a>CreatorMap::factoryCreator

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>Параметры

*текущие флаги*<br/>
Один из числят [runtimeClassType.](runtimeclasstype-enumeration.md)

*Запись*<br/>
A CreatorMap.

*iidClassFactory*<br/>
Идентификатор интерфейса фабрики класса.

*фабрика*<br/>
Когда операция завершается, адрес фабрики класса.

### <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

### <a name="remarks"></a>Примечания

Создает фабрику для указанного CreatorMap.

## <a name="creatormapservername"></a><a name="servername"></a>CreatorMap::serverName

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из кода.

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>Примечания

Хранит имя сервера для объекта CreatorMap.
