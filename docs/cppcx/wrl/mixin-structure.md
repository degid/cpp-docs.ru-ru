---
title: MixIn - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
ms.openlocfilehash: cfa03706bc6030b337009f7228466a26e242aa6b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221540"
---
# <a name="mixin-structure"></a>MixIn - структура

Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.

## <a name="syntax"></a>Синтаксис

```cpp
template<
    typename Derived,
    typename MixInType,
    bool hasImplements = __is_base_of(Details::ImplementsBase, MixInType)
>
struct MixIn;
```

### <a name="parameters"></a>Параметры

*Производный*<br/>
Тип, производный от структуры [Implements](implements-structure.md) .

*миксинтипе*<br/>
Базовый тип.

*хасимплементс*<br/>
**`true`** Если *миксинтипе* является производным от текущей реализации базового типа; **`false`** в противном случае — значение.

## <a name="remarks"></a>Примечания

Если класс является производным от среда выполнения Windows и COM-интерфейсов класса, список объявлений класса должен сначала отобразить все интерфейсы среда выполнения Windows, а затем — любые классические COM-интерфейсы. **Примеси** гарантирует, что интерфейсы указываются в правильном порядке.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`MixIn`

## <a name="requirements"></a>Требования

**Заголовок:** Implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft:: WRL](microsoft-wrl-namespace.md)
