---
title: /C (сохранять комментарии во время предварительной обработки)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- VC.Project.VCCLWCECompilerTool.KeepComments
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
ms.openlocfilehash: f80ebf45dd396a3f92d9b755c56522d4731bb2d0
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440274"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (сохранять комментарии во время предварительной обработки)

Сохраняет комментарии на этапе предварительной обработки.

## <a name="syntax"></a>Синтаксис

```
/C
```

## <a name="remarks"></a>Примечания

Для этого параметра компилятора требуется параметр **/e**, **/p**или **/EP** .

В следующем образце кода отображается комментарий к исходному коду.

```cpp
// C_compiler_option.cpp
// compile with: /E /C /c
int i;   // a variable
```

В этом примере будут получены следующие выходные данные.

```
#line 1 "C_compiler_option.cpp"
int i;   // a variable
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Щелкните страницу свойств **препроцессора** .

1. Измените свойство " **оставить комментарии** ".

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[/E (предварительная обработка в stdout)](e-preprocess-to-stdout.md)<br/>
[/P (вывод результатов предварительной обработки в файл)](p-preprocess-to-a-file.md)<br/>
[/EP (предварительная обработка в stdout без директив #line)](ep-preprocess-to-stdout-without-hash-line-directives.md)
