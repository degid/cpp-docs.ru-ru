---
title: support_error_info (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.support_error_info
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
ms.openlocfilehash: cf02af793b97c55de4c52280ad2795a460a98d9f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832182"
---
# <a name="support_error_info"></a>support_error_info

Реализует поддержку для возвращения подробных сведений об ошибках.

## <a name="syntax"></a>Синтаксис

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>Параметры

*error_interface*<br/>
Идентификатор интерфейса, реализующего интерфейс `IErrorInfo` .

## <a name="remarks"></a>Примечания

Атрибут **support_error_info** языка C++ реализует поддержку для возвращения на клиент подробных контекстных ошибок, обнаруженных для целевого объекта. Чтобы объект поддерживал ошибки, методы `IErrorInfo` интерфейса должны быть реализованы объектом. Дополнительные сведения см. в разделе [Supporting IDispatch and IErrorInfo](../../atl/supporting-idispatch-and-ierrorinfo.md)(Поддержка IDispatch и IErrorInfo).

Этот атрибут добавляет [ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md) в качестве базового класса для целевого объекта. Это приводит к реализации по умолчанию `ISupportErrorInfo` и может использоваться, когда один интерфейс создает ошибки для объекта.

## <a name="example"></a>Пример

Следующий код добавляет в объект поддержку по умолчанию для `ISupportErrorInfo` интерфейса `CMyClass` .

```cpp
// cpp_attr_ref_support_error_info.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="mymod")];
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]
__interface IMyErrors
{
};

[ coclass, support_error_info("IMyErrors"),
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]
class CMyClass
{
};
```

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`class`**|
|**REPEATABLE**|Да|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)
