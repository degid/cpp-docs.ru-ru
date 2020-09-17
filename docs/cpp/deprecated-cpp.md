---
title: deprecated (C++)
ms.date: 03/28/2017
f1_keywords:
- deprecated_cpp
helpviewer_keywords:
- __declspec keyword [C++], deprecated
- deprecated __declspec keyword
ms.assetid: beef1129-9434-4cb3-8392-f1eb29e04805
ms.openlocfilehash: 44cb33bae43b32b12dda95423aec5484f61aa596
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90683420"
---
# <a name="deprecated-c"></a>deprecated (C++)

В этом разделе рассматриваются устаревшие объявления declspec, относящиеся к Microsoft. Сведения об атрибуте C++ 14 `[[deprecated]]` и рекомендации по использованию этого атрибута и declspec или директивы pragma Майкрософт см. в разделе [стандартные атрибуты c++](attributes.md).

В приведенных ниже исключениях **`deprecated`** объявление предоставляет те же функциональные возможности, что и [нерекомендуемая](../preprocessor/deprecated-c-cpp.md) директива pragma:

- **`deprecated`** Объявление позволяет указать определенные формы перегрузок функций как устаревшие, в то время как форма pragma применяется ко всем перегруженным формам имени функции.

- **`deprecated`** Объявление позволяет указать сообщение, которое будет отображаться во время компиляции. Текст сообщения может быть взят из макроса.

- Макросы могут быть помечены как нерекомендуемые с помощью **`deprecated`** директивы pragma.

Если компилятор обнаруживает использование устаревшего идентификатора или стандартного [`[[deprecated]]`](attributes.md) атрибута, выдается предупреждение [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) .

## <a name="examples"></a>Примеры

В следующем примере показано, как отметить функции как нерекомендуемые и как указать сообщение, которое будет отображаться во время компиляции, если будет использоваться нерекомендуемая функция.

```cpp
// deprecated.cpp
// compile with: /W3
#define MY_TEXT "function is deprecated"
void func1(void) {}
__declspec(deprecated) void func1(int) {}
__declspec(deprecated("** this is a deprecated function **")) void func2(int) {}
__declspec(deprecated(MY_TEXT)) void func3(int) {}

int main() {
   func1();
   func1(1);   // C4996
   func2(1);   // C4996
   func3(1);   // C4996
}
```

В следующем примере показано, как отметить классы как нерекомендуемые и как указать сообщение, которое будет отображаться во время компиляции, если будет использоваться нерекомендуемый класс.

```cpp
// deprecate_class.cpp
// compile with: /W3
struct __declspec(deprecated) X {
   void f(){}
};

struct __declspec(deprecated("** X2 is deprecated **")) X2 {
   void f(){}
};

int main() {
   X x;   // C4996
   X2 x2;   // C4996
}
```

## <a name="see-also"></a>См. также

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
