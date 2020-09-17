---
title: уникальный (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.unique
helpviewer_keywords:
- unique attribute
ms.assetid: abd7ed14-5ae7-44a8-8333-0058e9c92b2f
ms.openlocfilehash: 8b0bd5be19baddaed367bb619135be5cea8e7677
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836160"
---
# <a name="unique-c"></a>unique (C++)

Задает уникальный указатель.

## <a name="syntax"></a>Синтаксис

```cpp
[unique]
```

## <a name="remarks"></a>Примечания

**Уникальный** атрибут C++ имеет те же функциональные возможности, что и [уникальный](/windows/win32/Midl/unique) атрибут MIDL.

## <a name="example"></a>Пример

Пример использования **UNIQUE**см. в примере [ref](ref-cpp.md) .

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`typedef`**, **`struct`** , **`union`** , параметр интерфейса, метод интерфейса|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)
