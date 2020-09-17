---
title: Предупреждение компилятора (уровень 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: 20d6010cb83107946c00f2f7b00cda771b2e70b9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199021"
---
# <a name="compiler-warning-level-3-c4159"></a>Предупреждение компилятора (уровень 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>pragma pragma (POP,...): извлеченный ранее идентификатор "*идентификатор*"

## <a name="remarks"></a>Примечания

Исходный код содержит инструкцию **Push** с идентификатором для директивы pragma, за которой следует инструкция **POP** без идентификатора. В результате извлекается *идентификатор* , и последующие применения *идентификатора* могут привести к непредвиденному поведению.

## <a name="example"></a>Пример

Чтобы избежать этого предупреждения, предоставьте идентификатор в инструкции **POP** . Пример:

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```
