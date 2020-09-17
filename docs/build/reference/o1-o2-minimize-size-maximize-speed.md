---
title: /O1, /O2 (минимизировать размер, максимизировать скорость)
description: Параметры компилятора КОМПИЛЯТОРОМ MSVC/O1 и/O2 указывают все оптимизации для минимального размера или максимальной скорости.
ms.date: 07/08/2020
f1_keywords:
- /O2
- /O1
helpviewer_keywords:
- maximize speed compiler option [C++]
- minimize size compiler option [C++]
- -O2 compiler option [C++]
- fast code
- small code
- O2 compiler option [C++]
- /O2 compiler option [C++]
- -O1 compiler option [C++]
- O1 compiler option [C++]
- /O1 compiler option [C++]
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
ms.openlocfilehash: c1eda8395e604468cbb23572ec930d6171984fe4
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180907"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>`/O1`, `/O2` (Минимальный размер, максимальная скорость)

Выбирает предопределенный набор параметров, которые влияют на размер и скорость созданного кода.

## <a name="syntax"></a>Синтаксис

> **`/O1`**\
> **`/O2`**

## <a name="remarks"></a>Примечания

**`/O1`** **`/O2`** Параметры компилятора и позволяют быстро задать несколько отдельных параметров оптимизации. **`/O1`** Параметр задает отдельные параметры оптимизации, которые создают наименьший код в большинстве случаев. **`/O2`** Параметр задает параметры, создающие самый быстрый код в большинстве случаев. **`/O2`** Параметр используется по умолчанию для сборок выпуска. В этой таблице показаны конкретные параметры, заданные в **`/O1`** и **`/O2`** :

| Параметр | Эквивалент |
|--|--|
| **`/O1`**(Минимальный размер) | [`/Og`](og-global-optimizations.md) [`/Os`](os-ot-favor-small-code-favor-fast-code.md) [`/Oy`](oy-frame-pointer-omission.md) [`/Ob2`](ob-inline-function-expansion.md) [`/GF`](gf-eliminate-duplicate-strings.md) [`/Gy`](gy-enable-function-level-linking.md) |
| **`/O2`**(Максимизировать скорость) | [`/Og`](og-global-optimizations.md) [`/Oi`](oi-generate-intrinsic-functions.md) [`/Ot`](os-ot-favor-small-code-favor-fast-code.md) [`/Oy`](oy-frame-pointer-omission.md) [`/Ob2`](ob-inline-function-expansion.md) [`/GF`](gf-eliminate-duplicate-strings.md) [`/Gy`](gy-enable-function-level-linking.md) |

**`/O1`** и **`/O2`** являются взаимоисключающими.

> [!NOTE]
> **только для x86**\
> Эти параметры подразумевают использование параметра «подавление указателя фрейма» ( [`/Oy`](oy-frame-pointer-omission.md) ).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **Configuration Properties**  >  страницу свойств «Оптимизация**C/C++**» свойств конфигурации  >  **Optimization** .

1. Измените свойство **Оптимизация** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.

## <a name="see-also"></a>См. также раздел

[`/O`Параметры (оптимизация кода)](o-options-optimize-code.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[`/EH`(Модель обработки исключений)](eh-exception-handling-model.md)
