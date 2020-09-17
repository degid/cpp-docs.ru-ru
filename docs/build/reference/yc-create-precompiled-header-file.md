---
title: /Yc (создать предварительно скомпилированный заголовочный файл)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
ms.openlocfilehash: 71a05df3adc74edfd814bb6dc15121e4a343dc4d
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825760"
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (создать предварительно скомпилированный заголовочный файл)

Указывает компилятору создать предварительно скомпилированный файл заголовка (PCH), представляющий состояние компиляции в определенной точке.

## <a name="syntax"></a>Синтаксис

> __/Yc__\
> __/Yc__*Имя файла* /Yc

## <a name="arguments"></a>Аргументы

*файлов*<br/>
Указывает файл заголовка (h). При использовании этого аргумента компилятор компилирует весь код и включает h-файл.

## <a name="remarks"></a>Примечания

Если параметр **/Yc** указан без аргумента, компилятор компилирует весь код до конца базового исходного файла или до точки в базовом файле, где происходит директива [hdrstop](../../preprocessor/hdrstop.md) . Полученный PCH-файл имеет то же базовое имя, что и базовый исходный файл, если не указано другое имя файла с помощью директивы pragma **hdrstop** или параметра **/FP** .

Предварительно скомпилированный код сохраняется в файле с именем, созданным на основе базового имени файла, указанного с помощью параметра **/Yc** , и расширения PCH. Можно также использовать [/FP (Name. PCH-файл)](fp-name-dot-pch-file.md) , чтобы указать имя файла предкомпилированного заголовка.

При использовании __/Yc__*filename*компилятор компилирует весь код вплоть до указанного файла и включает его для последующего использования с параметром [/Yu (использовать предкомпилированный заголовочный файл)](yu-use-precompiled-header-file.md) .

Если параметры __/Yc__*filename* и __/Yu__*filename* выполняются в одной командной строке, и обе ссылки или подразумевают одно и то же имя файла, приоритет имеет значение __/Yc__*filename* . Эта функция упрощает написание файлов Makefile.

Дополнительные сведения о предкомпилированных заголовках см. в следующих статьях:

- [/Y (Предкомпилированные заголовки)](y-precompiled-headers.md)

- [Файлы предварительно скомпилированных заголовков](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Выберите CPP-файл. CPP файл должен #include h файл, содержащий сведения о предкомпилированном заголовке. Параметр **/Yc** проекта можно переопределить на уровне файла.

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте страницу свойств **Свойства конфигурации**, **C/C++**, **предварительно скомпилированные заголовки** .

1. Измените свойство **предкомпилированного заголовка** .

1. Чтобы задать имя файла, измените свойство **файла предкомпилированного заголовка** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- Ознакомьтесь с разделами <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.

## <a name="example"></a>Пример

Рассмотрим следующий код.

```cpp
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
// ...
```

При компиляции этого кода с помощью команды `CL /YcMYAPP.H PROG.CPP`компилятор сохраняет всю предварительную обработку для AFXWIN.h, Resource.h и MyApp.h в файле предкомпилированного заголовка с именем MyApp. pch.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)<br/>
[Файлы предварительно скомпилированных заголовков](../creating-precompiled-header-files.md)
