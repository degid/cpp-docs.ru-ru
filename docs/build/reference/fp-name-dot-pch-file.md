---
title: /FP (имя &period;PCH-файл)
description: Используйте параметр компилятора/FP, чтобы указать имя файла предкомпилированного заголовка.
ms.date: 05/31/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
ms.openlocfilehash: d62c5bd9fc7920c0a2a5530879680fad2a01d39a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439784"
---
# <a name="fp-name-periodpch-file"></a>/FP (имя &period;PCH-файл)

Предоставляет имя пути для предкомпилированного заголовка вместо использования имени по умолчанию.

## <a name="syntax"></a>Синтаксис

> **/FP**<em>путь</em>

## <a name="remarks"></a>Примечания

Используйте параметр **/FP** вместе с [/Yc (создать предварительно скомпилированный заголовочный файл)](yc-create-precompiled-header-file.md) или [/Yu (используйте предварительно скомпилированный заголовочный файл)](yu-use-precompiled-header-file.md) , чтобы указать путь и имя файла предкомпилированного заголовка (PCH). По умолчанию параметр **/Yc** создает имя PCH-файла, используя базовое имя исходного файла и расширение *PCH* .

Если не указать расширение в качестве части *пути*, предполагается расширение *PCH* . При указании имени каталога с помощью косой черты ( **/** ) в конце *пути*имя файла по умолчанию — VC*версии*0. pch, где *Version* — основной номер версии набора инструментов Visual Studio. Этот каталог должен существовать, или создается ошибка C1083.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте окно свойств **конфигурации** > страница свойств **предварительно скомпилированных заголовков** **C/C++**  > .

1. Изменение свойства **выходного файла предкомпилированного заголовка** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="examples"></a>Примеры

Чтобы создать отдельную именованную версию файла предкомпилированного заголовка для отладочной сборки программы, можно указать такую команду:

```CMD
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

Следующая команда задает использование файла предкомпилированного заголовка с именем МИПЧ. pch. Компилятор предварительно компилирует исходный код в PROG. cpp до конца MYAPP.h и помещает предварительно скомпилированный код в МИПЧ. pch. Затем он использует содержимое МИПЧ. pch и компилирует оставшуюся часть файла PROG. cpp, чтобы создать OBJ-файл. Результатом этого примера является файл с именем PROG. exe.

```CMD
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>См. также раздел

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[Указание пути](specifying-the-pathname.md)
