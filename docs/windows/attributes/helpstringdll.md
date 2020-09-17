---
title: хелпстрингдлл (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstringdll
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
ms.openlocfilehash: 0c90a6a203189eff927819a3319fac6a8e9f6a55
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842849"
---
# <a name="helpstringdll"></a>helpstringdll

Указывает имя библиотеки DLL, используемой для поиска строки документа (локализация).

## <a name="syntax"></a>Синтаксис

```cpp
[ helpstringdll("string") ]
```

### <a name="parameters"></a>Параметры

*строка*<br/>
Библиотека DLL, используемая для поиска строки документа.

## <a name="remarks"></a>Примечания

Атрибут **хелпстрингдлл** C++ имеет те же функциональные возможности, что и атрибут [хелпстрингдлл](/windows/win32/Midl/helpstringdll) MIDL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_helpstringdll.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib", helpstringdll="xx.dll")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMyI
{
   HRESULT xxx();
};
```

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`class`**, **интерфейс**, метод интерфейса|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)
