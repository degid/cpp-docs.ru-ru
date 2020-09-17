---
title: инклуделиб (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 30e84a6c82ec25e07ca0eb08f64c7aa5b560e9e7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830700"
---
# <a name="includelib-c"></a>includelib (C++)

Вызывает включение IDL-или h-файла в созданный IDL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>Параметры

*Name. idl*<br/>
Имя IDL-файла, который должен быть включен в состав созданного idl-файла.

## <a name="remarks"></a>Примечания

Атрибут **инклуделиб** C++ вызывает включение IDL-или h-файла в созданный IDL-файл после `importlib` инструкции.

## <a name="example"></a>Пример

В cpp-файле показан следующий код:

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|В любом месте|
|**REPEATABLE**|Да|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[относится](include-cpp.md)<br/>
[importlib](importlib.md)
