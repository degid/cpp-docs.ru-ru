---
title: PTR (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ptr
helpviewer_keywords:
- ptr attribute
ms.assetid: 95eaea57-a5be-45f6-a612-ba2c9bc4645a
ms.openlocfilehash: c01fe93d8c4092b3a4754b0c70ff161d66dfe49f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839872"
---
# <a name="ptr"></a>ptr

Назначает указатель в качестве полного указателя.

## <a name="syntax"></a>Синтаксис

```cpp
[ptr]
```

## <a name="remarks"></a>Примечания

Атрибут **ptr** C++ имеет те же функциональные возможности, что и атрибут [ptr](/windows/win32/Midl/ptr) MIDL.

## <a name="example"></a>Пример

См. пример для [DefaultValue](defaultvalue.md) для примера использования **ptr**.

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|Параметр интерфейса, метод интерфейса, **`typedef`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)
