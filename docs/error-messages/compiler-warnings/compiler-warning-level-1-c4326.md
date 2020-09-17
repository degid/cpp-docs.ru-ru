---
title: Предупреждение компилятора (уровень 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: 41d8b271660ce0b6840e701ddac0f0538b265968
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87196556"
---
# <a name="compiler-warning-level-1-c4326"></a>Предупреждение компилятора (уровень 1) C4326

> возвращаемый тип "*функция*" должен быть "*тип1*", а не "*тип2*"

## <a name="remarks"></a>Примечания

Функция вернула тип, отличный от *Type1*. Например, при использовании [/Za](../../build/reference/za-ze-disable-language-extensions.md) **Main** не возвращает **`int`** .

## <a name="example"></a>Пример

В следующем примере создается C4326 и демонстрируется его устранение.

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```
