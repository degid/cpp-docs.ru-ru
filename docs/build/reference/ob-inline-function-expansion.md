---
title: Параметр /Ob (расширение встраиваемых функций)
ms.date: 08/08/2019
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
helpviewer_keywords:
- inline functions, function expansion compiler option [C++]
- -Ob1 compiler option [C++]
- -Ob0 compiler option [C++]
- /Ob0 compiler option [C++]
- /Ob1 compiler option [C++]
- any suitable compiler option [C++]
- Ob2 compiler option [C++]
- Ob1 compiler option [C++]
- /Ob2 compiler option [C++]
- Ob compiler option [C++]
- -Ob2 compiler option [C++]
- disable compiler option [C++]
- -Ob compiler option [C++]
- /Ob compiler option [C++]
- only __inline compiler option [C++]
- Ob0 compiler option [C++]
- inline expansion, compiler option
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
ms.openlocfilehash: 238e5533c062678c59b61ebeba71eee3231fb5fb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215222"
---
# <a name="ob-inline-function-expansion"></a>Параметр /Ob (расширение встраиваемых функций)

Управляет подстановкой функций. По умолчанию при оптимизации расширение происходит по усмотрению компилятора на все функции, часто называемое *автовстраиванием*.

## <a name="syntax"></a>Синтаксис

::: moniker range=">=vs-2019"

> **/Ob**{**0** | **1** | **2** | **3**}

::: moniker-end

::: moniker range="<=vs-2017"

> **/Ob**{**0** | **1** | **2**}

::: moniker-end

## <a name="arguments"></a>Аргументы

**0,0**\
Значение по умолчанию в параметре [/OD](od-disable-debug.md). Отключает подставляемые функции.

**1**\
Разрешает расширение только функций, помеченных как [inline](../../cpp/inline-functions-cpp.md), [__inline](../../cpp/inline-functions-cpp.md)или [__forceinline](../../cpp/inline-functions-cpp.md), или в функции-члене C++, определенной в объявлении класса.

**2**\
Значение по умолчанию в разделе [/O1](o1-o2-minimize-size-maximize-speed.md) и [/O2](o1-o2-minimize-size-maximize-speed.md). Позволяет компилятору развернуть любую функцию, не помеченную явно для отсутствия встраивания.

::: moniker range=">=vs-2019"

**3-5**\
Этот параметр указывает более агрессивное встраивание, чем **/Ob2**, но имеет те же ограничения. Параметр **/Ob3** доступен начиная с Visual Studio 2019.

::: moniker-end

## <a name="remarks"></a>Примечания

Параметры и ключевые слова подстановки компилятор обрабатывает как рекомендации. Нет никакой гарантии, что встроенная функция будет расширена. Встроенные расширения можно отключить, но нельзя заставить компилятор подставляемь определенную функцию даже при использовании **`__forceinline`** ключевого слова.

Чтобы исключить из рассмотрения функции в качестве кандидатов для встроенного расширения, можно использовать [__declspec (noinline)](../../cpp/noinline.md)или регион, помеченный [#pragma auto_inline (off)](../../preprocessor/auto-inline.md) и [#pragma auto_inline (on)](../../preprocessor/auto-inline.md) . Сведения о других способах предоставления подсказок для встраивания в компилятор см. в разделе [Встроенная](../../preprocessor/intrinsic.md) директива #pragma.

> [!NOTE]
> Сведения, собираемые из тестовых запусков профилирования, переопределяют оптимизации, которые в противном случае были бы в силе, так как вы указали **/Ob**, **/OS**или **/OT**. Дополнительные сведения см. в статье [Профильные оптимизации](../profile-guided-optimizations.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **Configuration Properties**  >  страницу свойств «Оптимизация**C/C++**» свойств конфигурации  >  **Optimization** .

1. Измените свойство **расширения встроенной функции** .

::: moniker range=">=vs-2019"

Параметр **/Ob3** недоступен во **встроенном свойстве расширения функции** . Чтобы задать **/Ob3**, сделайте следующее:

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойств **Свойства конфигурации** > **C/C++** > **Командная строка**.

1. Введите **/Ob3** в **дополнительных параметрах**.

::: moniker-end

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры/o (оптимизация кода)](o-options-optimize-code.md)\
[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md)\
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
