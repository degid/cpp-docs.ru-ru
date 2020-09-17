---
title: /Zc:noexceptTypes (правила noexcept C++17)
ms.date: 06/04/2020
f1_keywords:
- /Zc:noexceptTypes
helpviewer_keywords:
- /Zc:noexceptTypes
- Zc:noexceptTypes
- -Zc:noexceptTypes
ms.assetid: 1cbf7e3c-0f82-4f91-84dd-612bcf26d2c6
ms.openlocfilehash: 09817372e818a05c389a083aac5f04e03b1ab0e1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218953"
---
# <a name="zcnoexcepttypes-c17-noexcept-rules"></a>/Zc:noexceptTypes (правила noexcept C++17)

Стандарт c++ 17 создает `throw()` псевдоним для **`noexcept`** , удаляет `throw(` *`type-list`* `)` и `throw(...)` , а также позволяет включать определенные типы **`noexcept`** . Это изменение может вызвать ряд проблем совместимости с исходным кодом в коде, который соответствует C++ 14 или более ранней версии. **`/Zc:noexceptTypes`** Параметр указывает на соответствие стандарту c++ 17. **`/Zc:noexceptTypes-`** разрешает поведение C++ 14 и более ранних версий при компиляции кода в режиме C++ 17.

## <a name="syntax"></a>Синтаксис

> **`/Zc:noexceptTypes`**\[**`-`**]

## <a name="remarks"></a>Примечания

Если **`/Zc:noexceptTypes`** указан параметр, компилятор соответствует стандарту c++ 17 и обрабатывает его [**`throw()`**](../../cpp/exception-specifications-throw-cpp.md) как псевдоним для [**`noexcept`**](../../cpp/noexcept-cpp.md) , удаляет `throw(` *`type-list`* `)` и `throw(...)` , а также позволяет включать определенные типы **`noexcept`** . **`/Zc:noexceptTypes`** Параметр доступен, только если [**`/std:c++17`**](std-specify-language-standard-version.md) включен или [**`/std:c++latest`**](std-specify-language-standard-version.md) . **`/Zc:noexceptTypes`** по умолчанию включено в соответствие стандарту ISO C++ 17. [**`/permissive-`**](permissive-standards-conformance.md)Параметр не влияет на **`/Zc:noexceptTypes`** . Отключите этот параметр, указав **`/Zc:noexceptTypes-`** для возврата к поведению c++ 14 **`noexcept`** при **`/std:c++17`** указании аргумента или **`/std:c++latest`** .

Начиная с Visual Studio 2017 версии 15,5 компилятор C++ выполняет диагностику более несоответствий спецификаций исключений в объявлениях в режиме C++ 17 или при указании [**`/permissive-`**](permissive-standards-conformance.md) параметра.

В этом примере показано поведение объявлений с описателем исключения при **`/Zc:noexceptTypes`** установке или отключении параметра. Чтобы отобразить поведение при установке, Скомпилируйте с помощью `cl /EHsc /W4 noexceptTypes.cpp` . Чтобы отобразить поведение при отключении, Скомпилируйте с помощью `cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp` .

```cpp
// noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 noexceptTypes.cpp
// Compile by using: cl /EHsc /W4 /Zc:noexceptTypes- noexceptTypes.cpp

void f() throw();    // equivalent to void f() noexcept;
void f() { }         // warning C5043
void g() throw(...); // warning C5040

struct A
{
    virtual void f() throw();
};

struct B : A
{
    virtual void f() { } // error C2694
};
```

При компиляции с параметром по умолчанию в **`/Zc:noexceptTypes`** примере создаются указанные предупреждения. Чтобы обновить код, используйте следующую команду:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A
{
    virtual void f() noexcept;
};

struct B : A
{
    virtual void f() noexcept { }
};
```

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства конфигурации**  >  **C/C++**  >  **Командная строка** .

1. Измените свойство **Дополнительные параметры** на включить *`/Zc:noexceptTypes`* или *`/Zc:noexceptTypes-`* и нажмите кнопку **ОК**.

## <a name="see-also"></a>См. также раздел

[**`/Zc`** Соответствия](zc-conformance.md)\
[noexcept](../../cpp/noexcept-cpp.md)\
[Спецификации исключений (throw)](../../cpp/exception-specifications-throw-cpp.md)
