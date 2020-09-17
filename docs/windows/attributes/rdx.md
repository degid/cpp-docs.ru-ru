---
title: RDX (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.rdx
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
ms.openlocfilehash: f61eaf535102c8885e828176434acf221dfe2457
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836885"
---
# <a name="rdx"></a>rdx

Создает раздел реестра или изменяет существующий раздел реестра.

## <a name="syntax"></a>Синтаксис

```cpp
[ rdx(key, valuename=NULL, regtype) ]
```

### <a name="parameters"></a>Параметры

*key*<br/>
Имя создаваемого или открываемого ключа.

*valueName*<br/>
Используемых Указывает поле значения, которое должно быть задано. Если поле значения с таким именем еще не существует в ключе, оно добавляется.

*регтипе*<br/>
Тип добавляемого раздела реестра. Может быть одним из следующих: `text` , `dword` , `binary` или `CString` .

## <a name="remarks"></a>Примечания

Атрибут **RDX** C++ создает или изменяет существующий раздел реестра для COM-компонента. Атрибут добавляет BEGIN_RDX_MAPный макрос к объекту, реализующему целевой элемент. `RegistryDataExchange`, функция, вставленная в результате макроса BEGIN_RDX_MAP, может использоваться для перемещения данных между реестром и элементами данных.

Этот атрибут можно использовать совместно с атрибутами [coclass](coclass.md), [ProgID](progid.md)или [vi_progid](vi-progid.md) или другими атрибутами, которые подразумевают один из этих атрибутов.

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`class`** или **`struct`** элемент|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Пример

Следующий код добавляет раздел реестра с именем значения MyValue в систему, описывающую COM-компонент Кмикласс.

```cpp
// cpp_attr_ref_rdx.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include "atlbase.h"

[module (name="MyLib")];

class CMyClass {
public:
   CMyClass() {
      strcpy_s(m_sz, "SomeValue");
   }

   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]
   char m_sz[256];
};
```

## <a name="see-also"></a>См. также раздел

[Атрибуты COM](com-attributes.md)<br/>
[registration_script](registration-script.md)
