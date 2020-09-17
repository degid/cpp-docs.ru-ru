---
title: CancelTransitionPolicy - перечисление
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
ms.openlocfilehash: e820b3fffb4a00e95a1210a5c0beb3229c6d1657
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214127"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy - перечисление

Показывает, как попытка перехода асинхронной операции к окончательному состоянию завершения или ошибки должна происходить с учетом запрошенного клиентом состояния отмены.

## <a name="syntax"></a>Синтаксис

```cpp
enum CancelTransitionPolicy;
```

## <a name="members"></a>Члены

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`RemainCanceled`|Если асинхронная операция в данный момент находится в запрошенном клиентом состоянии отмены, это означает, что данный элемент остается в отмененном состоянии, в отличие от перехода к окончательному состоянию завершения или ошибки.|
|`TransitionFromCanceled`|Если асинхронная операция в данный момент находится в запрошенном клиентом состоянии отмены, это означает, что состояние должно перейти из данного состояния отмены в окончательное состояние завершения или ошибки, как определено вызовом, который использует этот флажок.|

## <a name="requirements"></a>Требования

**Заголовок:** Async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
