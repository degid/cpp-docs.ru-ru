---
title: Предупреждение компилятора (уровень 3) C4686
description: Предупреждение компилятора Microsoft C++ C4686.
ms.date: 08/29/2020
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: 6886ae7f413de630457b53e85b5cd75c4542ee19
ms.sourcegitcommit: 3628707bc17c99aac7aac27eb126cc2eaa4d07b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2020
ms.locfileid: "89194501"
---
# <a name="compiler-warning-level-3-c4686"></a>Предупреждение компилятора (уровень 3) C4686

> "*определяемый пользователем тип*": возможное изменение в поведении, изменение соглашения о вызовах для возврата определяемого пользователем типа

## <a name="remarks"></a>Примечания

Специализация шаблона класса не определена до ее использования в возвращаемом типе. Все, что создает экземпляр класса, разрешает C4686; объявление экземпляра или доступ к элементу (например, `C<int>::some_member` ) также являются параметрами.

Это предупреждение отключено по умолчанию. Дополнительные сведения см. [в разделе предупреждения компилятора, которые по умолчанию отключены](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Пример

Вместо этого попробуйте выполнить следующие действия:

```cpp
// C4686.cpp
// compile with: /W3
#pragma warning (default : 4686)
template <class T>
class C;

template <class T>
C<T> f(T);

template <class T>
class C {};

int main() {
   f(1);   // C4686
}

template <class T>
C<T> f(T) {
   return C<int>();
}
```
