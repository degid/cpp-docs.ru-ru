---
title: pragma (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pragma
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
ms.openlocfilehash: e5683a6f52eccf9eae7c29010849a148e506b286
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836173"
---
# <a name="pragma"></a>pragma

Выдает указанную строку в созданный IDL-файл без использования кавычек.

## <a name="syntax"></a>Синтаксис

```cpp
[ pragma(pragma_statement) ];
```

### <a name="parameters"></a>Параметры

*pragma_statement*<br/>
Директива pragma, которую необходимо поместить в созданный IDL-файл.

## <a name="remarks"></a>Примечания

Атрибут **pragma** C++ имеет те же функциональные возможности, что и атрибут [pragma](/windows/win32/Midl/pragma) MIDL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_pragma.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[pragma(pack(4))];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A
{
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|В любом месте|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[pack](../../preprocessor/pack.md)
