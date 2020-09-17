---
title: импортидл (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 8f3c2c5c67ac216d096d1082814c561698f3f732
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842251"
---
# <a name="importidl"></a>importidl

Вставляет указанный IDL-файл в созданный IDL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>Параметры

*idl_file*<br/>
Определяет имя IDL-файла, который необходимо объединить с IDL-файлом, который будет создан для приложения.

## <a name="remarks"></a>Примечания

Атрибут **импортидл** C++ помещает раздел за пределами блока библиотеки (в *idl_file*) в созданный IDL-файл программы и раздел Library (в *idl_file*) в раздел Library созданного idl-файла программы.

Можно использовать **импортидл**, например, если вы хотите использовать idl-файл с собственной кодировкой с созданным файлом IDL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
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
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importlib](importlib.md)<br/>
[относится](include-cpp.md)<br/>
[инклуделиб](includelib-cpp.md)
