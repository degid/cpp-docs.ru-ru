---
title: Пространство имен Microsoft::WRL::Wrappers::HandleTraits
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: b19cc426fc7c1b4fc6ec0638730d59998f8c108a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213737"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Пространство имен Microsoft::WRL::Wrappers::HandleTraits

Описывает характеристики общих типов ресурсов на основе маркеров.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>Члены

### <a name="structures"></a>Структуры

|Имя|Описание|
|----------|-----------------|
|[Структура CriticalSectionTraits](criticalsectiontraits-structure.md)|Специализирует объект `CriticalSection` для поддержки недопустимого критического раздела или функции для освобождения критического раздела.|
|[Структура EventTraits](eventtraits-structure.md)|Определяет характеристики `Event`ного обработчика класса.|
|[Структура FileHandleTraits](filehandletraits-structure.md)|Определяет характеристики маркера файла.|
|[Структура HANDLENullTraits](handlenulltraits-structure.md)|Определяет общие характеристики неинициализированного маркера.|
|[Структура HANDLETraits](handletraits-structure.md)|Определяет общие характеристики дескриптора.|
|[Структура MutexTraits](mutextraits-structure.md)|Определяет общие характеристики класса [мьютекса](mutex-class.md) .|
|[Структура SemaphoreTraits](semaphoretraits-structure.md)|Определяет общие характеристики объекта семафора.|
|[Структура SRWLockExclusiveTraits](srwlockexclusivetraits-structure.md)|Описывает общие характеристики класса `SRWLock` в режиме монопольной блокировки.|
|[Структура SRWLockSharedTraits](srwlocksharedtraits-structure.md)|Описывает общие характеристики класса `SRWLock` в режиме общей блокировки.|

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Программы Microsoft:: WRL:: оболочки

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL::Wrappers](microsoft-wrl-wrappers-namespace.md)
