---
title: /Zc:alignedNew (выделение С++17 с избыточным выравниванием)
ms.date: 05/18/2019
f1_keywords:
- /Zc:alignedNew
helpviewer_keywords:
- /Zc:alignedNew
- Zc:alignedNew
- -Zc:alignedNew
ms.openlocfilehash: f036c2d7bc4619685d2763702f447476e8e1a1e4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217198"
---
# <a name="zcalignednew-c17-over-aligned-allocation"></a>/Zc:alignedNew (выделение С++17 с избыточным выравниванием)

Включить поддержку для C++ 17 с выведением по рассогласованию **`new`** , динамическое выделение памяти по границам больше, чем по умолчанию для стандартного выходящего по размеру типа, **Max \_ aligned \_ t**.

## <a name="syntax"></a>Синтаксис

> **/Zc: alignedNew** \[ -]

## <a name="remarks"></a>Примечания

Поддержка компилятором и библиотекой MSVC стандартного выделения памяти с избыточным выравниванием C++17. Если указан параметр **/Zc: alignedNew** , динамическое выделение, например, `new Example;` учитывает выравнивание *примера* , даже если оно больше `max_align_t` , чем максимальное выравнивание, необходимое для любого фундаментального типа. Если Выравнивание выделенного типа не превышает выравнивание, которое гарантируется исходным оператором **`new`** , доступно как значение предопределенного макроса, ** \_ \_ стдкпп \_ по умолчанию \_ новое \_ Выравнивание \_ \_ **, инструкция `new Example;` приводит к вызову `::operator new(size_t)` как в c++ 14. Если выравнивание превышает ** \_ \_ стдкпп \_ по умолчанию \_ новое \_ Выравнивание \_ \_ **, то реализация вместо этого получает память с помощью `::operator new(size_t, align_val_t)` . Аналогичным образом удаление типов с избыточным выравниванием вызывает `::operator delete(void*, align_val_t)` или сигнатуру удаления `::operator delete(void*, size_t, align_val_t)` с определенным размером.

Параметр **/Zc:alignedNew** доступен, только если включены [/std:c++17](std-specify-language-standard-version.md) или [/std:c++latest](std-specify-language-standard-version.md). В **/std:c++17** или **/std:c++latest****/Zc:alignedNew** включен по умолчанию для соответствия стандарту ISO C++17. Если единственной причиной реализации оператора **`new`** **`delete`** является поддержка перераспределенных выделений, этот код больше не потребуется в режиме c++ 17. Чтобы отключить этот параметр и вернуться к поведению C++ 14 в **`new`** и **`delete`** при использовании **/std:: c++ 17** или **/std: C + + Latest**, укажите **/Zc: alignedNew-**. Если вы реализуете оператор, **`new`** **`delete`** но не готовы реализовать оператор с чрезмерным выведением **`new`** и **`delete`** перегрузкой с `align_val_t` параметром, используйте параметр **/Zc: AlignedNew-** , чтобы компилятор и стандартная библиотека не создавали вызовы к перегрузкам с чрезмерным согласованием. Оператор [/permissive-](permissive-standards-conformance.md) не изменяет настройку **/Zc:alignedNew** по умолчанию.

Поддержка **/Zc:alignedNew** доступна начиная с Visual Studio 2017 версии 15.5.

## <a name="example"></a>Пример

В этом примере показано **`new`** поведение оператора и оператора **`delete`** при установке параметра **/Zc: alignedNew** .

```cpp
// alignedNew.cpp
// Compile by using: cl /EHsc /std:c++17 /W4 alignedNew.cpp
#include <iostream>
#include <malloc.h>
#include <new>

// "old" unaligned overloads
void* operator new(std::size_t size) {
    auto ptr = malloc(size);
    std::cout << "unaligned new(" << size << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size) {
    std::cout << "unaligned sized delete(" << ptr << ", " << size << ")\n";
    free(ptr);
}

void operator delete(void* ptr) {
    std::cout << "unaligned unsized delete(" << ptr << ")\n";
    free(ptr);
}

// "new" over-aligned overloads
void* operator new(std::size_t size, std::align_val_t align) {
    auto ptr = _aligned_malloc(size, static_cast<std::size_t>(align));
    std::cout << "aligned new(" << size << ", " <<
        static_cast<std::size_t>(align) << ") = " << ptr << '\n';
    return ptr ? ptr : throw std::bad_alloc{};
}

void operator delete(void* ptr, std::size_t size, std::align_val_t align) {
    std::cout << "aligned sized delete(" << ptr << ", " << size <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

void operator delete(void* ptr, std::align_val_t align) {
    std::cout << "aligned unsized delete(" << ptr <<
        ", " << static_cast<std::size_t>(align) << ")\n";
    _aligned_free(ptr);
}

struct alignas(256) OverAligned {}; // warning C4324, structure is padded

int main() {
    delete new int;
    delete new OverAligned;
}
```

Такой результат является типичным для 32-разрядных сборок. Значения указателя могут варьироваться в зависимости от того, где приложение выполняется в памяти.

```Output
unaligned new(4) = 009FD0D0
unaligned sized delete(009FD0D0, 4)
aligned new(256, 256) = 009FE800
aligned sized delete(009FE800, 256, 256)
```

Сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры**, включив параметр **/Zc:alignedNew** или **/Zc:alignedNew-**, а затем нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также раздел

[/Zc (соответствие)](zc-conformance.md)
