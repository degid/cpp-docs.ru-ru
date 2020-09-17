---
title: Функция TerminateMap
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
ms.openlocfilehash: 2aa4d6733d2a4e458ff8abff192778d52a4522b2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233500"
---
# <a name="terminatemap-function"></a>Функция TerminateMap

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.

## <a name="syntax"></a>Синтаксис

```cpp
inline bool TerminateMap(
   _In_ ModuleBase *module,
   _In_opt_z_ const wchar_t *serverName,
    bool forceTerminate) throw()
```

### <a name="parameters"></a>Параметры

*модуль*<br/>
[Модуль](module-class.md).

*Имя*<br/>
Имя подмножества фабрик класса в модуле, заданном *модулем*параметров.

*форцетерминате*<br/>
**`true`** для завершения фабрик классов, независимо от того, активны они, **`false`** значение, чтобы не завершать фабрики класса, если активна какая-либо фабрика.

## <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если все фабрики класса были завершены; в противном случае — **`false`** .

## <a name="remarks"></a>Примечания

Завершает работу фабрик классов в указанном модуле.

## <a name="requirements"></a>Требования

**Заголовок:** Module.h

**Пространство имен:** Microsoft:: WRL::D состояния

## <a name="see-also"></a>См. также статью

[Пространство имен Microsoft:: WRL::D состояния](microsoft-wrl-details-namespace.md)
