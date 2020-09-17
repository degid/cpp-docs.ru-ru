---
title: Структура CloakedIid
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 1cc9e79384bbf4aae44199c2f35331e3afd8fd8f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214114"
---
# <a name="cloakediid-structure"></a>Структура CloakedIid

Указывает на шаблоны `RuntimeClass`, `Implements` и `ChainInterfaces`, которые указанный интерфейс недоступен в списке IID.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Скрытый (замаскированный) интерфейс.

## <a name="remarks"></a>Примечания

Ниже приведен пример использования **клоакедиид** : `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`T`

`CloakedIid`

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
