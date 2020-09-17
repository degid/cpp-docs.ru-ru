---
title: include (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: 6b75df74ee69ee4f89eb7bf18fb6bcd77d8a6284
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842199"
---
# <a name="include-c"></a>include (C++)

Указывает один или несколько файлов заголовков для включения в созданный IDL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>Параметры

*header_file*<br/>
Имя файла, который необходимо добавить в созданный IDL-файл.

## <a name="remarks"></a>Примечания

Атрибут **include** C++ приводит к тому, что `#include` инструкция будет помещена под `import "docobj.idl"` инструкцией в созданном IDL-файле.

Атрибут **include** C++ имеет те же функциональные возможности, что и атрибут [include](/windows/win32/Midl/include) языка MIDL.

## <a name="example"></a>Пример

В следующем коде показан пример использования **include**. В этом примере файл include.h содержит только `#include` инструкцию.

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
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

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[инклуделиб](includelib-cpp.md)<br/>
[importlib](importlib.md)
