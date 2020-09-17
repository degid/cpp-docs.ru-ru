---
title: /Zc:forScope (принудительное обеспечение соответствия в области видимости оператора for)
ms.date: 03/06/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope
- VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope
- /zc:forScope
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
ms.openlocfilehash: b1173ad609a1b2c95d6cf118f4e2d5defeec5b9c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234345"
---
# <a name="zcforscope-force-conformance-in-for-loop-scope"></a>/Zc:forScope (принудительное обеспечение соответствия в области видимости оператора for)

Использовался для реализации стандартного поведения C++ для циклов [for](../../cpp/for-statement-cpp.md) с расширениями Майкрософт ([/Ze](za-ze-disable-language-extensions.md)).

## <a name="syntax"></a>Синтаксис

> **/Zc: forScope**[ **-** ]

## <a name="remarks"></a>Примечания

Стандартное поведение заключается в том, чтобы **`for`** инициализатор цикла выйдет за пределы области действия после **`for`** цикла. В разделе **/Zc: forScope-** and [/Ze](za-ze-disable-language-extensions.md) **`for`** инициализатор цикла остается в области видимости, пока не завершится локальная область.

Параметр **/Zc: forScope** включен по умолчанию. **/Zc: forScope** не затрагивается, если указан параметр [/permissive-](permissive-standards-conformance.md) .

Параметр **/Zc:forScope-** не рекомендуется к использованию и будет удален в одном из следующих выпусков. Использование **/Zc:forScope-** приводит к созданию предупреждения D9035 о нерекомендуемом элементе.

Приведенный ниже код компилируется при использовании параметра **/Ze** , но не при использовании **/Za**.

```cpp
// zc_forScope.cpp
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp
// C2065, D9035 expected
int main() {
    // Compile by using cl /Zc:forScope- zc_forScope.cpp
    // to compile this non-standard code as-is.
    // Uncomment the following line to resolve C2065 for /Za.
    // int i;
    for (int i = 0; i < 1; i++)
        ;
    i = 20;   // i has already gone out of scope under /Za
}
```

Если используется параметр **/Zc:forScope-**, то каждый раз, когда переменная будет попадать в область из-за ее объявления в предыдущей области, будет выдаваться предупреждение C4288 (оно отключено по умолчанию). Для иллюстрации этого поведения в примере кода необходимо убрать символы `//` для объявления `int i`.

Поведение параметра **/Zc:forScope** во время выполнения можно изменить с помощью директивы pragma [conform](../../preprocessor/conform.md) .

При использовании параметра **/Zc:forScope-** в проекте с существующим файлом PCH выдается предупреждение, параметр **/Zc:forScope-** пропускается, а компиляция продолжается c использованием существующих файлов PCH. Если необходимо создать новый PCH-файл, используйте параметр [/Yc (создать предварительно скомпилированный заголовочный файл)](yc-create-precompiled-header-file.md).

Дополнительные сведения о вопросах соответствия в Visual C++ см. в статье [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на **Configuration Properties**  >  страницу свойств языка**C/C++**  >  **Language** .

1. Измените свойство **Обеспечение согласования видимости переменных, объявленных в заголовке оператора for** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>.

## <a name="see-also"></a>См. также статью

[/Zc (соответствие)](zc-conformance.md)<br/>
[/ZA,/Ze (Отключение расширений языка)](za-ze-disable-language-extensions.md)<br/>
