---
title: Класс Module::MethodReleaseNotifier
ms.date: 09/17/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::Invoke
- module/Microsoft::WRL::Module::MethodReleaseNotifier::method_
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
- module/Microsoft::WRL::Module::MethodReleaseNotifier::object_
helpviewer_keywords:
- Microsoft::WRL::Module::MethodReleaseNotifier class
- Microsoft::WRL::Module::MethodReleaseNotifier::Invoke method
- Microsoft::WRL::Module::MethodReleaseNotifier::method_ data member
- Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier, constructor
- Microsoft::WRL::Module::MethodReleaseNotifier::object_ data member
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
ms.openlocfilehash: 5b0e5766fda878acb1fdc54a79ce162444eb06de
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225726"
---
# <a name="modulemethodreleasenotifier-class"></a>Класс Module::MethodReleaseNotifier

Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается объектом и его указателем на член метода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
class MethodReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Тип объекта, функция-член которой является обработчиком событий.

## <a name="members"></a>Элементы

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                                                                                 | Описание:
---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------
[Модуль:: MethodReleaseNotifier:: MethodReleaseNotifier](#methodreleasenotifier-methodreleasenotifier) | Инициализирует новый экземпляр класса `Module::MethodReleaseNotifier`.

### <a name="public-methods"></a>Открытые методы

name                                                                   | Описание:
---------------------------------------------------------------------- | -------------------------------------------------------------------------------------------
[Модуль:: MethodReleaseNotifier:: Invoke](#methodreleasenotifier-invoke) | Вызывает обработчик событий, связанный с текущим `Module::MethodReleaseNotifier` объектом.

### <a name="protected-data-members"></a>Защищенные члены данных

Имя                                                                    | Описание:
----------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[Модуль:: MethodReleaseNotifier:: method_](#methodreleasenotifier-method) | Содержит указатель на обработчик событий для текущего `Module::MethodReleaseNotifier` объекта.
[Модуль:: MethodReleaseNotifier:: object_](#methodreleasenotifier-object) | Содержит указатель на объект, функция-член которой является обработчиком событий для текущего `Module::MethodReleaseNotifier` объекта.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ReleaseNotifier`

`MethodReleaseNotifier`

## <a name="requirements"></a>Требования

**Заголовок:** Module.h

**Пространство имен:** Microsoft::WRL

## <a name="modulemethodreleasenotifierinvoke"></a><a name="methodreleasenotifier-invoke"></a>Модуль:: MethodReleaseNotifier:: Invoke

Вызывает обработчик событий, связанный с текущим `Module::MethodReleaseNotifier` объектом.

```cpp
void Invoke();
```

## <a name="modulemethodreleasenotifiermethod_"></a><a name="methodreleasenotifier-method"></a>Модуль:: MethodReleaseNotifier:: method_

Содержит указатель на обработчик событий для текущего `Module::MethodReleaseNotifier` объекта.

```cpp
void (T::* method_)();
```

## <a name="modulemethodreleasenotifiermethodreleasenotifier"></a><a name="methodreleasenotifier-methodreleasenotifier"></a>Модуль:: MethodReleaseNotifier:: MethodReleaseNotifier

Инициализирует новый экземпляр класса `Module::MethodReleaseNotifier`.

```cpp
MethodReleaseNotifier(
   _In_ T* object,
   _In_ void (T::* method)(),
   bool release) throw() :
            ReleaseNotifier(release), object_(object),
            method_(method);
```

### <a name="parameters"></a>Параметры

*object*<br/>
Объект, функция-член которого является обработчиком событий.

*Method*<br/>
Функция-член *объекта* Parameter, который является обработчиком событий.

*отпускании*<br/>
Укажите, **`true`** чтобы разрешить вызов базового метода [модуля:: ReleaseNotifier:: Release ()](module-releasenotifier-class.md#releasenotifier-release) ; в противном случае укажите **`false`** .

## <a name="modulemethodreleasenotifierobject_"></a><a name="methodreleasenotifier-object"></a>Модуль:: MethodReleaseNotifier:: object_

Содержит указатель на объект, функция-член которой является обработчиком событий для текущего `Module::MethodReleaseNotifier` объекта.

```cpp
T* object_;
```
