---
title: Object (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: c0c0ff552d8a33ebe70f56b9b186e963cc8e9b3d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843109"
---
# <a name="object-c"></a>object (C++)

Определяет пользовательский интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
[object]
```

## <a name="remarks"></a>Примечания

Если перед определением интерфейса, атрибут **Object** C++ помещает интерфейс в IDL-файл как пользовательский интерфейс.

Любой интерфейс, помеченный объектом, должен наследовать от `IUnknown` . Это условие выполняется, если какой-либо из базовых интерфейсов наследует от `IUnknown` . Если базовые интерфейсы не наследуются от `IUnknown` , компилятор вызовет наследование для **object** интерфейса, помеченного объектом `IUnknown` .

## <a name="example"></a>Пример

См. Пример использования **объекта**в [неотображаемом](nonbrowsable.md) виде.

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|**interface**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[настройки](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)
