---
title: Перечисления &lt;codecvt&gt;
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
ms.openlocfilehash: e67290d8de0b8251191c4a93b66b7e19a293ed61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371945"
---
# <a name="ltcodecvtgt-enums"></a>Перечисления &lt;codecvt&gt;

## <a name="codecvt_mode-enumeration"></a><a name="codecvt_mode"></a>codecvt_mode Инумерация

Определяет информацию о конфигурации для аспектов [локализации.](../standard-library/locale-class.md)

```cpp
enum codecvt_mode {
    consume_header = 4,
    generate_header = 2,
    little_endian = 1
};
```

### <a name="remarks"></a>Примечания

Перечисление определяет три константы, которые поставляют информацию о конфигурации в грани локализации, заявленные в [ \<codecvt>. ](../standard-library/codecvt.md) Это могут быть следующие значения:

- `consume_header`, чтобы использовать начальную последовательность заголовка при чтении многобайтовой последовательности и определении порядка байтов следующей многобайтовой последовательности для чтения;

- `generate_header`, чтобы создавать начальную последовательность заголовка при записи многобайтовой последовательности для объявления порядка байтов следующей многобайтовой последовательности для записи;

- `little_endian`, чтобы создавать многобайтовую последовательность в прямом порядке байтов, в отличие от порядка "сначала старший байт" по умолчанию.

Эти константы можно связывать логическим оператором OR в произвольные сочетания.

## <a name="see-also"></a>См. также раздел

[\<codecvt>](../standard-library/codecvt.md)
