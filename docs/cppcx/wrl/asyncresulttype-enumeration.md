---
title: Перечисление AsyncResultType
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
ms.openlocfilehash: b8a2a9ec803fba1be0012fcb58bf3b42e78f9071
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214166"
---
# <a name="asyncresulttype-enumeration"></a>Перечисление AsyncResultType

Задает тип результата, возвращаемого методом `GetResults()`.

## <a name="syntax"></a>Синтаксис

```cpp
enum AsyncResultType;
```

## <a name="members"></a>Члены

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`MultipleResults`|Набор из нескольких результатов, которые отображаются последовательно между состоянием `Start` и до вызова `Close()`.|
|`SingleResult`|Один результат, представленный после возникновения события `Complete`.|

## <a name="requirements"></a>Требования

**Заголовок:** Async.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также раздел

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)
