---
title: switch_is (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_is
helpviewer_keywords:
- switch_is attribute
ms.assetid: f1fffe5d-12d2-4e0f-8803-ccb715177d2d
ms.openlocfilehash: b017ba6dd2bbdfab7bfb5fa2dbf19e613e14772b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840547"
---
# <a name="switch_is"></a>switch_is

Указывает выражение или идентификатор, выступающий в качестве discriminant объединения, который выбирает элемент объединения.

## <a name="syntax"></a>Синтаксис

```cpp
[switch_is]
```

## <a name="remarks"></a>Примечания

Атрибут **switch_is** C++ имеет те же функциональные возможности, что и атрибут [switch_is](/windows/win32/Midl/switch-is) MIDL.

## <a name="example"></a>Пример

Пример использования **switch_is**см. в примере [варианта](case-cpp.md) .

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`typedef`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[switch_type](switch-type.md)
