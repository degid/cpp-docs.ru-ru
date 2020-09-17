---
title: nullptr
ms.date: 07/22/2020
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 801ae927d6c9fb70c3187d10269e87097a879bfc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223633"
---
# <a name="nullptr"></a>nullptr

**`nullptr`** Ключевое слово указывает константу указателя NULL типа `std::nullptr_t` , которая преобразуется в любой Необработанный тип указателя.  Хотя можно использовать ключевое слово **`nullptr`** без включения заголовков, если код использует тип `std::nullptr_t` , его необходимо определить, включив заголовок `<cstddef>` .

> [!NOTE]
> **`nullptr`** Ключевое слово также определено в C++/CLI для приложений управляемого кода и не является взаимозаменяемым с ключевым словом C++ Standard в стандарте ISO. Если код может быть скомпилирован с помощью [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) параметра компилятора, который предназначен для управляемого кода, используйте `__nullptr` в любой строке кода, где необходимо гарантировать, что компилятор использует собственную интерпретацию C++. Дополнительные сведения см. в разделе [ `nullptr` (c++/CLI и c++/CX)](../extensions/nullptr-cpp-component-extensions.md).

## <a name="remarks"></a>Примечания

Избегайте использования `NULL` или нулевого значения ( `0` ) в качестве константы указателя NULL; **`nullptr`** менее уязвимо к неправильному использованию и лучше всего работает в большинстве случаев.  Например, если для функции `func(std::pair<const char *, double>)` произвести вызов `func(std::make_pair(NULL, 3.14))`, возникнет ошибка компилятора.  Макрос `NULL` разворачивается в `0` , поэтому вызов `std::make_pair(0, 3.14)` возвращает `std::pair<int, double>` , который не может быть преобразован в `std::pair<const char *, double>` тип параметра в `func` .  Вызов `func(std::make_pair(nullptr, 3.14))` успешно компилируется, поскольку `std::make_pair(nullptr, 3.14)` возвращает значение `std::pair<std::nullptr_t, double>`, которое допускает преобразование в тип `std::pair<const char *, double>`.

## <a name="see-also"></a>См. также статью

[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[`nullptr`(C++/CLI и C++/CX)](../extensions/nullptr-cpp-component-extensions.md)
