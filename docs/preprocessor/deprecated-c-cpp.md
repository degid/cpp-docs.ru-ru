---
title: нерекомендуемая прагма
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.deprecated
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 52d9deb4ad68dacc99fab9d12bc9eb21bc0d360e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231615"
---
# <a name="deprecated-pragma"></a>нерекомендуемая прагма

**`deprecated`** Директива pragma позволяет указать, что функция, тип или любой другой идентификатор может больше не поддерживаться в будущем выпуске или больше не должна использоваться.

> [!NOTE]
> Сведения об атрибуте C++ 14 `[[deprecated]]` и рекомендации по использованию этого атрибута вместо `__declspec(deprecated)` модификатора Майкрософт или **`deprecated`** директивы pragma см. в разделе [атрибуты в C++](../cpp/attributes.md).

## <a name="syntax"></a>Синтаксис

> **#pragma устарел (** *идентификатор1* [ **,** *идентификатор2* ...] **)**

## <a name="remarks"></a>Примечания

Когда компилятор встречает идентификатор, заданный **`deprecated`** директивой pragma, он выдает предупреждение компилятора [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md).

Имена макросов можно объявить нерекомендуемыми. Поместите имя макроса в кавычки; в противном случае произойдет расширение макроса.

Поскольку **`deprecated`** директива pragma работает с любыми совпадающими идентификаторами и не принимает подписи в учетную запись, это не лучший вариант для устаревших версий перегруженных функций. Все совпадающие имена функций, которые были добавлены в область действия, инициируют предупреждение.

Рекомендуется использовать атрибут C++ 14 `[[deprecated]]` , если это возможно, вместо **`deprecated`** директивы pragma. Модификатор объявления __declspec Майкрософт [(не рекомендуется)](../cpp/deprecated-cpp.md) является также лучшим выбором во многих случаях, чем **`deprecated`** директива pragma. `[[deprecated]]`Атрибут и `__declspec(deprecated)` Модификатор позволяют указать нерекомендуемое состояние для определенных форм перегруженных функций. Предупреждение диагностики отображается только в ссылках на конкретную перегруженную функцию, к которой применяется атрибут или модификатор.

## <a name="example"></a>Пример

```cpp
// pragma_directive_deprecated.cpp
// compile with: /W3
#include <stdio.h>
void func1(void) {
}

void func2(void) {
}

int main() {
   func1();
   func2();
   #pragma deprecated(func1, func2)
   func1();   // C4995
   func2();   // C4995
}
```

В следующем примере показано, как объявить класс устаревшим.

```cpp
// pragma_directive_deprecated2.cpp
// compile with: /W3
#pragma deprecated(X)
class X {  // C4995
public:
   void f(){}
};

int main() {
   X x;   // C4995
}
```

## <a name="see-also"></a>См. также раздел

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
