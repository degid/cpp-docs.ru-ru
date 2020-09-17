---
title: Пространство имен Microsoft::WRL::Wrappers
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: ece26b3f9928d44a593de830cf8a25c57e4c2d89
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213750"
---
# <a name="microsoftwrlwrappers-namespace"></a>Пространство имен Microsoft::WRL::Wrappers

Определяет оболочки типа "Получение ресурса есть инициализация" (RAII), которые упрощают управление временем существования объектов, строк и дескрипторов.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>Члены

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>Классы

|Имя|Описание|
|----------|-----------------|
|[Класс CriticalSection](criticalsection-class.md)|Представляет объект критической секции.|
|[Класс Event (WRL)](event-class-wrl.md)|Представляет событие.|
|[Класс HandleT](handlet-class.md)|Представляет дескриптор объекта.|
|[Класс HString](hstring-class.md)|Обеспечивает поддержку манипуляций с дескрипторами HSTRING.|
|[Класс HStringReference](hstringreference-class.md)|Представляет HSTRING, созданный из существующей строки.|
|[Класс Mutex](mutex-class.md)|Представляет объект синхронизации, который исключительно управляет общим ресурсом.|
|[Класс RoInitializeWrapper](roinitializewrapper-class.md)|Инициализирует среда выполнения Windows.|
|[Класс Semaphore](semaphore-class.md)|Представляет объект синхронизации, который управляет общим ресурсом и поддерживает ограниченное число пользователей.|
|[Класс SRWLock](srwlock-class.md)|Представляет тонкую блокировку чтения и записи.|

## <a name="requirements"></a>Требования

**Заголовок:** кореврапперс.h

**Пространство имен:** Программы Microsoft:: WRL:: оболочки

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
