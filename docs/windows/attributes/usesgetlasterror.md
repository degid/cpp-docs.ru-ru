---
title: усесжетластеррор (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: e3d3c292554350d85296971a9bd3620909ef47c7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831636"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Сообщает вызывающему, что при возникновении ошибки при вызове этой функции вызывающий объект может вызвать метод, `GetLastError` чтобы получить код ошибки.

## <a name="syntax"></a>Синтаксис

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Примечания

Атрибут **усесжетластеррор** C++ имеет те же функциональные возможности, что и атрибут [усесжетластеррор](/windows/win32/Midl/usesgetlasterror) MIDL.

## <a name="example"></a>Пример

Пример использования **усесжетластеррор**см. в примере [idl_module](idl-module.md) .

## <a name="requirements"></a>Требования

| Контекст атрибута | Значение |
|-|-|
|**Относится к**|атрибут **module**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)
