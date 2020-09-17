---
title: Оператор __uuidof
ms.date: 10/10/2018
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
- __uuidof
- _uuidof
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
ms.openlocfilehash: f7564270408d14f58d1528c1f41c0afd2dbe219c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226975"
---
# <a name="__uuidof-operator"></a>Оператор `__uuidof`

**Блок, относящийся только к системам Microsoft**

Извлекает идентификатор GUID, присоединенный к выражению.

## <a name="syntax"></a>Синтаксис

> **`__uuidof (`***выражение***`)`**

## <a name="remarks"></a>Примечания

*Выражение* может быть именем типа, указателем, ссылкой или массивом этого типа, шаблоном, специализированным для этих типов, или переменной этих типов. Этот аргумент является допустимым, если компилятор может использовать его для поиска прикрепленного GUID.

Особым случаем этого встроенного параметра является то, что в качестве аргумента указывается значение **0** или null. В этом случае вернет **`__uuidof`** идентификатор GUID, состоящие из нулей.

Это ключевое слово позволяет извлечь GUID, прикрепленный к следующим объектам:

- Объект по [`uuid`](../cpp/uuid-cpp.md) расширенному атрибуту.

- Блок библиотеки, созданный с помощью [`module`](../windows/attributes/module-cpp.md) атрибута.

> [!NOTE]
> В отладочной сборке **`__uuidof`** всегда инициализирует объект динамически (во время выполнения). В сборке выпуска **`__uuidof`** можно статически (во время компиляции) инициализировать объект.

Для совместимости с предыдущими версиями аргумент **`_uuidof`** является синонимом, **`__uuidof`** если только параметр компилятора не [ `/Za` \( отключает расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

## <a name="example"></a>Пример

Следующий код (скомпилированный с библиотекой ole32.lib) будет выводить идентификатор uuid для блока библиотеки, созданного с атрибутом module.

```cpp
// expre_uuidof.cpp
// compile with: ole32.lib
#include "stdio.h"
#include "windows.h"

[emitidl];
[module(name="MyLib")];
[export]
struct stuff {
   int i;
};

int main() {
   LPOLESTR lpolestr;
   StringFromCLSID(__uuidof(MyLib), &lpolestr);
   wprintf_s(L"%s", lpolestr);
   CoTaskMemFree(lpolestr);
}
```

## <a name="comments"></a>Комментарии

В случаях, когда имя библиотеки больше не находится в области, можно использовать `__LIBID_` вместо **`__uuidof`** . Пример:

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
