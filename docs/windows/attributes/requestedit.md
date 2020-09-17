---
title: рекуестедит (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requestedit
helpviewer_keywords:
- requestedit attribute
ms.assetid: b3c24790-3c4a-4646-8722-03d7b51172ee
ms.openlocfilehash: d5cf2bb8fab75c64d74a2f28964b3019200dad51
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846021"
---
# <a name="requestedit"></a>requestedit

Указывает, что свойство поддерживает уведомление `OnRequestEdit`.

## <a name="syntax"></a>Синтаксис

```cpp
[requestedit]
```

## <a name="remarks"></a>Примечания

Атрибут **рекуестедит** C++ имеет те же функциональные возможности, что и атрибут [рекуестедит](/windows/win32/Midl/requestedit) MIDL.

## <a name="example"></a>Пример

Пример использования **рекуестедит**см. в примере для [привязки](bindable.md) .

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|Метод интерфейса|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)
