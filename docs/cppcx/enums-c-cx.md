---
title: Перечисления (C++/CX)
ms.date: 12/30/2016
ms.assetid: 99fbbe28-c1cd-43af-9ead-60f90eba6e68
ms.openlocfilehash: 54e413e65b3130b9b83e6d1ed56b5ee87b84e0a3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225765"
---
# <a name="enums-ccx"></a>Перечисления (C++/CX)

C++/CX поддерживает `public enum class` ключевое слово, аналогичное стандартному C++ `scoped  enum` . При использовании перечислителя, объявленного с помощью ключевого слова `public enum class` , необходимо использовать идентификатор перечисления, чтобы определить область каждого значения перечислителя.

### <a name="remarks"></a>Примечания

Объект `public enum class` , который не имеет спецификатора доступа, например **`public`** , обрабатывается как стандартное [перечисление с областью действия](../cpp/enumerations-cpp.md)C++.

`public enum class`Объявление или `public enum struct` может иметь базовый тип любого целочисленного типа, хотя сам среда выполнения Windows требует, чтобы тип был Int32, или UInt32 для перечисления flags. Следующий синтаксис описывает части объявления `public enum class` или `public enum struct`.

В этом примере показано, как определить открытый класс перечисления:

[!code-cpp[cx_enums#01](../cppcx/codesnippet/CPP/cpp/class1.h#01)]

В следующем примере показано, как использовать его:

[!code-cpp[cx_enums#02](../cppcx/codesnippet/CPP/cpp/class1.h#02)]

### <a name="examples"></a>Примеры

В следующих примерах показано, как объявить перечисление.

[!code-cpp[cx_enums#03](../cppcx/codesnippet/CPP/cpp/class1.h#03)]

В следующем примере показано, как выполнять приведение к числовым эквивалентами и выполнять сравнения. Обратите внимание, что область использования перечислителя `One` определяется идентификатором перечисления `Enum1` , а область использования перечислителя `First` — идентификатором `Enum2`.

[!code-cpp[cx_enums#04](../cppcx/codesnippet/CPP/cpp/class1.h#04)]

## <a name="see-also"></a>См. также статью

[Система типов](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку C++/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
