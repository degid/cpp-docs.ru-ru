---
title: In (атрибут C++ COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: 2838a00ffe365f42fb7778b654306eb0c73b5996
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842238"
---
# <a name="in-c"></a>in (C++)

Указывает, что параметр передается из вызывающей процедуры в вызываемую процедуру.

## <a name="syntax"></a>Синтаксис

```cpp
[in]
```

## <a name="remarks"></a>Примечания

Атрибут **в** C++ имеет те же функциональные возможности, что и [в](/windows/win32/Midl/in) атрибуте MIDL.

## <a name="example"></a>Пример

Пример использования в см. **в**разделе о возможности [привязки](bindable.md) .

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|Параметр интерфейса, метод интерфейса|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|**retval**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[максимально](defaultvalue.md)<br/>
[идентификатор](id.md)<br/>
[out](out-cpp.md)
