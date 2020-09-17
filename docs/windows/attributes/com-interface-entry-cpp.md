---
title: com_interface_entry (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.com_interface_entry
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
ms.openlocfilehash: 8339afb97df57f5080629dfed08823c5c091c5a3
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844123"
---
# <a name="com_interface_entry-c"></a>com_interface_entry (C++)

Добавляет запись интерфейса в карту COM целевого класса.

## <a name="syntax"></a>Синтаксис

```cpp
[ com_interface_entry(
  com_interface_entry) ]
```

### <a name="parameters"></a>Параметры

*com_interface_entry*<br/>
Строка, содержащая фактический текст записи. Список возможных значений см. в разделе [COM_INTERFACE_ENTRY Macros](../../atl/reference/com-interface-entry-macros.md).

## <a name="remarks"></a>Примечания

Атрибут **COM_INTERFACE_ENTRY** C++ вставляет содержимое унабриджед строки символов в карту COM-интерфейса целевого объекта. Если атрибут применяется к целевому объекту один раз, запись вставляется в начало существующей карты интерфейса. Если атрибут применяется к тому же целевому объекту многократно, записи вставляются в начало карты интерфейса в том порядке, в котором они были получены.

Этот атрибут требует, чтобы атрибут [coclass](coclass.md), [progid](progid.md)или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу. Если используется любой отдельный атрибут, два других применяются автоматически. Например, если `progid` применяется, то применяются `vi_progid` `coclass` также и.

Поскольку первое использование **COM_INTERFACE_ENTRY** приводит к вставке нового интерфейса в начало карты интерфейса, оно должно иметь один из следующих типов COM_INTERFACE_ENTRY:

- COM_INTERFACE_ENTRY

- COM_INTERFACE_ENTRY_IID

- COM_INTERFACE_ENTRY2

- COM_INTERFACE_ENTRY2_IID

Дополнительные случаи использования атрибута **COM_INTERFACE_ENTRY** могут использовать все поддерживаемые типы COM_INTERFACE_ENTRY.

Это ограничение необходимо, поскольку в ATL используется первая запись в карте интерфейса в качестве удостоверения `IUnknown` , поэтому запись должна быть допустимым интерфейсом. Например, следующий пример кода является недопустимым, так как первая запись в карте интерфейса не указывает фактический COM-интерфейс.

```cpp
[ coclass, com_interface_entry =
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"
]
   class CMyClass
   {
   };
```

## <a name="example"></a>Пример

Следующий код добавляет две записи в существующую карту COM-интерфейса `CMyBaseClass` . Первый является стандартным интерфейсом, а второй скрывает `IDebugTest` интерфейс.

```cpp
// cpp_attr_ref_com_interface_entry.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name ="ldld")];

[ object,
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]
__interface IDebugTest{};

[ object,
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]
__interface IMyClass{};

[ coclass,
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")
]

class CMyClass: public IMyClass, public IDebugTest
{
};
```

Результирующая схема объекта COM для `CMyBaseClass` выглядит следующим образом:

```cpp
BEGIN_COM_MAP(CMyClass)
    COM_INTERFACE_ENTRY (IMyClass)
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)
    COM_INTERFACE_ENTRY(IMyClass)
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)
    COM_INTERFACE_ENTRY(IDebugTest)
    COM_INTERFACE_ENTRY(IProvideClassInfo)
END_COM_MAP()
```

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Да|
|**Требуемые атрибуты**|Один или несколько из следующих элементов: `coclass` , `progid` или `vi_progid` .|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)
