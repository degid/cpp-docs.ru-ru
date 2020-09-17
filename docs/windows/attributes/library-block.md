---
title: library_block (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 13988abc12eb0b136dfc8d2c0d597005b56f0526
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834120"
---
# <a name="library_block"></a>library_block

Размещает конструкцию внутри блока библиотеки IDL.

## <a name="syntax"></a>Синтаксис

```cpp
[library_block]
```

## <a name="remarks"></a>Примечания

При помещении конструкции в блок библиотеки вы гарантируете, что она будет передаваться в библиотеку типов, независимо от того, есть ли на нее ссылка. По умолчанию в блок библиотеки помещаются только конструкции, измененные атрибутами [coclass](coclass.md), [DISP](dispinterface.md)и [idl_module](idl-module.md) .

## <a name="example"></a>Пример

В следующем коде пользовательский интерфейс помещается внутрь блока Library.

```cpp
// cpp_attr_ref_library_block.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib")];
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface IMyInterface {
   HRESULT f1();
};
```

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|В любом месте|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)
