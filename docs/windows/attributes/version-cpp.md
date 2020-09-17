---
title: версия (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: 7d21761a556455cec27087896984bdc721841d9d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832949"
---
# <a name="version-c"></a>version (C++)

Определяет определенную версию для нескольких версий класса.

## <a name="syntax"></a>Синтаксис

```cpp
[ version("version") ]
```

### <a name="parameters"></a>Параметры

*version*<br/>
Номер версии `coclass`. Если не указано, 1,0 будет помещена в IDL-файл.

## <a name="remarks"></a>Примечания

Атрибут **Version** C++ имеет те же функциональные возможности, что и атрибут MIDL [версии](/windows/win32/Midl/version) , и передается в созданный IDL-файл.

## <a name="example"></a>Пример

Пример использования **версии**см. в примере с [возможностью привязки](bindable.md) .

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|**кокласс**|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты компилятора](compiler-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)
