---
title: Класс conditional
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: 03ec6248ba3361622ad061ac3854a60995148f4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228379"
---
# <a name="conditional-class"></a>Класс conditional

Выделяет один из 2 типов в зависимости от указанного условия.

## <a name="syntax"></a>Синтаксис

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>Параметры

*&*\
Значение, определяющее выбранный тип.

*T1*\
Результат типа, если B — true.

*T2*\
Результат типа, если B — false.

## <a name="remarks"></a>Примечания

Typedef элемента шаблона `conditional<B, T1, T2>::type` принимает значение *T1* , если *b* принимает значение **`true`** , и при вычислении *b* принимает значение *T2* **`false`** .

## <a name="requirements"></a>Требования

**Заголовок:**\<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также статью

[<type_traits>](../standard-library/type-traits.md)
