---
title: /showIncludes (список включаемых файлов)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
ms.openlocfilehash: d454054c132976a899fcc4a56a63be427e79beec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318164"
---
# <a name="showincludes-list-include-files"></a>/showIncludes (список включаемых файлов)

Компилятор выводит список включаемых файлов. Вложенные включают файлы также являются отображаемые (файлы, включенные файлы, которые включены).

## <a name="syntax"></a>Синтаксис

```
/showIncludes
```

## <a name="remarks"></a>Примечания

Если включаемый файл встречается во время компиляции, выводится сообщение, например:

```
Note: including file: d:\MyDir\include\stdio.h
```

Вложенные включают файлы обозначаются отступа, одно пространство для каждого уровня вложения, например:

```
Note: including file: d:\temp\1.h
Note: including file:  d:\temp\2.h
```

В этом случае `2.h` был включен в `1.h`, поэтому отступы.

**/Showincludes** предоставляет параметр `stderr`, а не `stdout`.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **Дополнительно** страницу свойств.

1. Изменить **Показывать включаемые файлы** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
