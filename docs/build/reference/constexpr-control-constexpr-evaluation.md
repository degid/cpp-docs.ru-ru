---
title: /constexpr (управление вычислениями constexpr)
ms.date: 08/15/2017
f1_keywords:
- /constexpr
- -constexpr
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
ms.openlocfilehash: 7b3ae1cd732fe1ec234e2734ea4c6fa86db9d5af
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223867"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (управление вычислениями constexpr)

Используйте параметры компилятора **/constexpr** для управления параметрами **`constexpr`** вычисления во время компиляции.

## <a name="syntax"></a>Синтаксис

> **/constexpr: глубина**<em>N</em>\
> **/constexpr: отследить**<em>N</em>\
> **/constexpr: шаги**<em>N</em>

## <a name="arguments"></a>Аргументы

**глубина**<em>n</em> . Ограничьте глубину вызова рекурсивной **`constexpr`** функции до *N* уровней. Значение по умолчанию — 512.

в **трассировке**невыполненной обработки<em>n</em> отображаются до *n* **`constexpr`** оценок в диагностике. Значение по умолчанию равно 10.

**шаги**<em>n</em> завершают **`constexpr`** оценку после *n* шагов. Значение по умолчанию — 100 000.

## <a name="remarks"></a>Примечания

Параметры компилятора **/constexpr** управляют вычислением выражений во время компиляции **`constexpr`** . Этапы оценки, уровни рекурсии и глубина обратной трассировки управляются так, чтобы компилятор не тратил слишком много времени на **`constexpr`** оценку. Дополнительные сведения об **`constexpr`** элементе Language см. в разделе [constexpr (C++)](../../cpp/constexpr-cpp.md).

Параметры **/constexpr** доступны начиная с Visual Studio 2015.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **страницы свойств** проекта.

2. В разделе **Свойства конфигурации**разверните папку **C/C++** и выберите страницу свойств **Командная строка** .

3. Введите любые параметры компилятора **/constexpr** в поле **Дополнительные параметры** . Нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также статью

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
