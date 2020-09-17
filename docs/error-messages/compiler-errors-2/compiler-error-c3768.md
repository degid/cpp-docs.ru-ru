---
title: Ошибка компилятора C3768
ms.date: 11/04/2016
f1_keywords:
- C3768
helpviewer_keywords:
- C3768
ms.assetid: 091f0d53-1dff-43fd-813d-5c43c85b6ab0
ms.openlocfilehash: 534be9e3873276313335ca921264be92c9259b93
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165747"
---
# <a name="compiler-error-c3768"></a>Ошибка компилятора C3768

> невозможно получить адрес виртуальной функции vararg в чистом управляемом коде

## <a name="remarks"></a>Примечания

Параметр компилятора **/clr: pure** является устаревшим в visual Studio 2015 и не поддерживается в visual Studio 2017.

При компиляции с **параметром/clr: pure**нельзя получить адрес виртуальной функции `vararg`.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3768:

```cpp
// C3768.cpp
// compile with: /clr:pure
struct A
{
   virtual void f(...);
};

int main()
{
   &(A::f);   // C3768
}
```
