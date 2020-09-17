---
title: /Zc:strictStrings (отключение преобразования типов строковых литералов)
ms.date: 03/06/2018
f1_keywords:
- /Zc:strictStrings
- strictStrings
helpviewer_keywords:
- /Zc:strictStrings
- -Zc compiler options (C++)
- strictStrings
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: b7eb3f3b-82c1-48a2-8e63-66bad7397b46
ms.openlocfilehash: df880ed64fa472ff55eb5ee0d17caacf56228ab6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211896"
---
# <a name="zcstrictstrings-disable-string-literal-type-conversion"></a>`/Zc:strictStrings`(Отключить преобразование типов строковых литералов)

Если этот параметр указан, **`const`** для указателей, инициализированных с помощью строковых литералов, компилятору требуется обеспечить соответствие требованиям.

## <a name="syntax"></a>Синтаксис

> **`/Zc:strictStrings`**[**`-`**]

## <a name="remarks"></a>Примечания

Если **`/Zc:strictStrings`** задано значение, компилятор применяет стандартную **`const`** квалификацию C++ для строковых литералов в качестве типа "массив" `const char` или "массив" в `const wchar_t` зависимости от объявления. Строковые литералы являются неизменяемыми, и при попытке изменения содержимого одного из них возникает ошибка нарушения доступа во время выполнения. Необходимо объявить указатель строки как **`const`** для его инициализации с помощью строкового литерала или явно использовать **`const_cast`** для инициализации без **`const`** указателя. По умолчанию или если **`/Zc:strictStrings-`** указан параметр, компилятор не применяет стандартные стандарты C++ **`const`** для указателей на строки, инициализированных с помощью строковых литералов.

По **`/Zc:strictStrings`** умолчанию параметр отключен. [`/permissive-`](permissive-standards-conformance.md)Параметр компилятора неявно задает этот параметр, но его можно переопределить с помощью **`/Zc:strictStrings-`** .

Используйте **`/Zc:strictStrings`** параметр, чтобы предотвратить компиляцию неверного кода. В этом примере демонстрируется, как простая ошибка объявления приводит к сбою во время выполнения.

```cpp
// strictStrings_off.cpp
// compile by using: cl /W4 strictStrings_off.cpp
int main() {
   wchar_t* str = L"hello";
   str[2] = L'a'; // run-time error: access violation
}
```

Если **`/Zc:strictStrings`** включен, то тот же код сообщает об ошибке в объявлении `str` .

```cpp
// strictStrings_on.cpp
// compile by using: cl /Zc:strictStrings /W4 strictStrings_on.cpp
int main() {
   wchar_t* str = L"hello"; // error: Conversion from string literal
   // loses const qualifier
   str[2] = L'a';
}
```

Если используется **`auto`** для объявления указателя строки, компилятор создает правильное **`const`** объявление типа указателя. При попытке изменить содержимое **`const`** указателя компилятором сообщается об ошибке.

> [!NOTE]
> Стандартная библиотека C++ в Visual Studio 2013 не поддерживает **`/Zc:strictStrings`** параметр компилятора в отладочных сборках. Если в выходных данных сборки отображается несколько ошибок [C2665](../../error-messages/compiler-errors-2/compiler-error-c2665.md) , это может быть причиной.

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** , чтобы включить его **`/Zc:strictStrings`** , а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также раздел

[`/Zc`Соответствия](zc-conformance.md)<br/>
