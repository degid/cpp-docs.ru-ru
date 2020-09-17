---
title: Класс Module::ReleaseNotifier
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier
- module/Microsoft::WRL::Module::ReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::ReleaseNotifier::Release
- module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
helpviewer_keywords:
- Microsoft::WRL::Module::ReleaseNotifier class
- Microsoft::WRL::Module::ReleaseNotifier::~ReleaseNotifier, destructor
- Microsoft::WRL::Module::ReleaseNotifier::Invoke method
- Microsoft::WRL::Module::ReleaseNotifier::Release method
- Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier, constructor
ms.assetid: 17249cd1-4d88-42e3-8146-da9e942d12bd
ms.openlocfilehash: 25fbb23ee7ecb7e55377aed74effe8bfa43a1597
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218368"
---
# <a name="modulereleasenotifier-class"></a>Класс Module::ReleaseNotifier

Вызывает обработчик событий при освобождении последнего объекта в модуле.

## <a name="syntax"></a>Синтаксис

```cpp
class ReleaseNotifier;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                                | Описание
----------------------------------------------------------------------------------- | --------------------------------------------------------------------------
[Модуль:: ReleaseNotifier:: ~ ReleaseNotifier](#releasenotifier-tilde-releasenotifier) | Выполняет деинициализацию текущего экземпляра `Module::ReleaseNotifier` класса.
[Модуль:: ReleaseNotifier:: ReleaseNotifier](#releasenotifier-releasenotifier)        | Инициализирует новый экземпляр класса `Module::ReleaseNotifier`.

### <a name="public-methods"></a>Открытые методы

name                                                         | Описание
------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------
[Модуль:: ReleaseNotifier:: Invoke](#releasenotifier-invoke)   | При реализации вызывает обработчик событий при освобождении последнего объекта в модуле.
[Module::ReleaseNotifier::Release](#releasenotifier-release) | Удаляет текущий `Module::ReleaseNotifier` объект, если объект был создан с помощью параметра **`true`** .

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** Module.h

**Пространство имен:** Microsoft::WRL

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-tilde-releasenotifier"></a>Модуль:: ReleaseNotifier:: ~ ReleaseNotifier

Выполняет деинициализацию текущего экземпляра `Module::ReleaseNotifier` класса.

```cpp
WRL_NOTHROW virtual ~ReleaseNotifier();
```

## <a name="modulereleasenotifierinvoke"></a><a name="releasenotifier-invoke"></a>Модуль:: ReleaseNotifier:: Invoke

При реализации вызывает обработчик событий при освобождении последнего объекта в модуле.

```cpp
virtual void Invoke() = 0;
```

## <a name="modulereleasenotifierrelease"></a><a name="releasenotifier-release"></a>Модуль:: ReleaseNotifier:: Release

Удаляет текущий `Module::ReleaseNotifier` объект, если объект был создан с помощью параметра **`true`** .

```cpp
void Release() throw();
```

## <a name="modulereleasenotifierreleasenotifier"></a><a name="releasenotifier-releasenotifier"></a>Модуль:: ReleaseNotifier:: ReleaseNotifier

Инициализирует новый экземпляр класса `Module::ReleaseNotifier`.

```cpp
ReleaseNotifier(bool release) throw();
```

### <a name="parameters"></a>Параметры

*отпускании*<br/>
**`true`** значение, чтобы удалить этот экземпляр при `Release` вызове метода; **`false`** значение, чтобы не удалять этот экземпляр.
