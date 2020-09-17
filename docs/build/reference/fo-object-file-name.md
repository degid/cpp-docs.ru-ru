---
title: /Fo (имя объектного файла)
description: Справочный справочник по варианту компилятора microsoft C 'Fo (название файла объекта) в Visual Studio.
ms.date: 04/20/2020
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
ms.openlocfilehash: cd22ba745128fe1df67853d98c1495491b9ca840
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748970"
---
# <a name="fo-object-file-name"></a>/Fo (имя объектного файла)

Упогоняет*`.obj`* объект () имя файла или каталог, которые будут использоваться вместо по умолчанию.

## <a name="syntax"></a>Синтаксис

> **`/Fo`**_Путь_

## <a name="remarks"></a>Примечания

Можно использовать **`/Fo`** опцию компилятора для установки каталога вывода для всех файлов объектов, генерируемых командой компилятора CL. Или вы можете использовать его для переименования одного файла объекта.

По умолчанию файлы объекта, генерируемые компилятором, размещаются в текущем каталоге. Им дается базовое название исходного файла *`.obj`* и расширение.

Чтобы использовать **`/Fo`** опцию для переименования файла объекта, укажите имя файла вывода в качестве аргумента *имени пути.* При переименовании файла объекта можно использовать любое имя и расширение, но *`.obj`* рекомендуемая конвенция заключается в использовании. Компилятор генерирует ошибку командной строки D8036, если вы указываете имя файла, **`/Fo`** когда вы указали более одного исходного файла для компиляции.

Чтобы использовать **`/Fo`** опцию для установки каталога вывода для всех файлов объектов, созданных командой CL, укажите каталог в качестве аргумента *имени пути.* Каталог указывается задней косой чертой в аргументе *имя пути.* Указанный каталог должен существовать; он не создается автоматически.

## <a name="example"></a>Пример

Следующая командная строка создает файл объекта, названный *sample.obj* в существующем каталоге, * \\промежуточный,* на диске D.

```cmd
CL /Fo"D:\intermediate\" /EHsc /c sample.cpp
```

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Установите опцию в Visual Studio или программно

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойства **configuration Properties** > **C/C'S** > **Output Files.**

1. Измените свойство **названия «Имя файла объекта»** для настройки каталога вывода. В IDE файл объекта должен иметь *`.obj`* расширение.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)<br/>
[Указание имени Пути](specifying-the-pathname.md)
