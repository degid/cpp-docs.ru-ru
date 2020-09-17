---
title: /Ox (включение большинства быстрых оптимизаций)
description: Параметр КОМПИЛЯТОРОМ MSVC/Ox объединяет некоторые параметры оптимизации компилятора для ускорения одного параметра.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /Ox
- /Oxs
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
ms.openlocfilehash: 10893fe1cf032f2ab56f27aa4af95b050c2ec37e
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180842"
---
# <a name="ox-enable-most-speed-optimizations"></a>`/Ox`(Включить Большинство оптимизаций скорости)

**`/Ox`** Параметр компилятора позволяет сочетать оптимизацию, которая имеет приоритет. В некоторых версиях интегрированной среды разработки Visual Studio и сообщениях справки компилятора это называется *полной оптимизацией*, но **`/Ox`** параметр компилятора включает только подмножество параметров оптимизации скорости, включенных **`/O2`** .

## <a name="syntax"></a>Синтаксис

> **`/Ox`**

## <a name="remarks"></a>Примечания

**`/Ox`** Параметр компилятора включает **`/O`** параметры компилятора, которые имеют приоритет над скоростью. **`/Ox`** Параметр компилятора не включает дополнительные параметры [ `/GF` (исключения повторяющихся строк)](gf-eliminate-duplicate-strings.md) и [ `/Gy` (включить компоновку на уровне функций)](gy-enable-function-level-linking.md) , включенные [ `/O1` или `/O2` (минимальный размер, максимальная скорость)](o1-o2-minimize-size-maximize-speed.md). Дополнительные параметры, применяемые **`/O1`** и, **`/O2`** могут вызывать указатели на строки или функции для совместного использования целевого адреса, что может повлиять на отладку и соответствие определенному языку. **`/Ox`** Параметр является простым способом включения большинства оптимизаций без включения **`/GF`** и **`/Gy`** . Дополнительные сведения см. в описании [`/GF`](gf-eliminate-duplicate-strings.md) [`/Gy`](gy-enable-function-level-linking.md) параметров и.

**`/Ox`** Параметр компилятора аналогичен использованию следующих параметров в сочетании.

- [ `/Ob` (Расширение встроенных функций)](ob-inline-function-expansion.md), где параметр Option имеет значение 2 ( **`/Ob2`** )

- [`/Oi`(Создание встроенных функций)](oi-generate-intrinsic-functions.md)

- [`/Ot`(Предпочитать быстрый код)](os-ot-favor-small-code-favor-fast-code.md)

- [`/Oy`(Подавление указателя фрейма)](oy-frame-pointer-omission.md)

**`/Ox`** является взаимоисключающим из:

- [`/O1`(Минимальный размер)](o1-o2-minimize-size-maximize-speed.md)

- [`/O2`(Максимизировать скорость)](o1-o2-minimize-size-maximize-speed.md)

- [`/Od`(Отключить (отладку))](od-disable-debug.md)

Можно отменить смещение до скорости **`/Ox`** параметра компилятора, если указать **`/Oxs`** , который сочетает **`/Ox`** параметр компилятора с [ `/Os` (подходит для малого кода)](os-ot-favor-small-code-favor-fast-code.md). Объединенные параметры имеют меньший размер кода.  **`/Oxs`** Параметр точно такой же, как и при указании **`/Ox`** **`/Os`** параметров в указанном порядке.

Чтобы применить все доступные оптимизации на уровне файлов для сборок выпуска, рекомендуется указать [ `/O2` (максимизировать скорость)](o1-o2-minimize-size-maximize-speed.md) вместо **`/Ox`** и [ `/O1` (уменьшить размер)](o1-o2-minimize-size-maximize-speed.md) вместо **`/Oxs`** . Для еще большей оптимизации в сборках выпуска также следует использовать параметр компилятора [ `/GL` (оптимизация всей программы)](gl-whole-program-optimization.md) и параметр компоновщика [ `/LTCG` (создание кода во время компоновки)](ltcg-link-time-code-generation.md) .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **Configuration Properties**  >  страницу свойств «Оптимизация**C/C++**» свойств конфигурации  >  **Optimization** .

1. Измените свойство **Оптимизация** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>См. также раздел

[`/O`Параметры (оптимизация кода)](o-options-optimize-code.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
