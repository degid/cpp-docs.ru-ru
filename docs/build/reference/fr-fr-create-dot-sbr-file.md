---
title: /FR, /Fr (создать SBR-файл)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BrowseInformation
- VC.Project.VCCLCompilerTool.BrowseInformation
- /fr
- VC.Project.VCCLCompilerTool.BrowseInformationFile
- VC.Project.VCCLWCECompilerTool.BrowseInformationFile
helpviewer_keywords:
- /FR compiler option [C++]
- -FR compiler option [C++]
- FR compiler option [C++]
- symbolic browser information
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
ms.openlocfilehash: 58f55811f5d2bb81bc77da38a87c35bae91ce6cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320523"
---
# <a name="fr-fr-create-sbr-file"></a>/FR, /Fr (создать SBR-файл)

Создает SBR-файлы.

## <a name="syntax"></a>Синтаксис

```
/FR[pathname[\filename]]
/Fr[pathname[\filename]]
```

## <a name="remarks"></a>Примечания

> [!WARNING]
> Хотя средство BSCMAKE по-прежнему устанавливается вместе с Visual Studio, оно больше не используется в интегрированной среде разработки. Начиная с Visual Studio 2008 информация об исходном коде и символах автоматически сохраняется в SDF-файле SQL Server в папке решения.

В процессе сборки программа обслуживания файлов информации об исходном коде Майкрософт (BSCMAKE) использует эти файлы для создания BSC-файла, с помощью которого отображается информация об исходном коде.

**/FR** создает SBR-файл с полными символьными данными.

**/Fr** создает SBR-файл без сведений о локальных переменных.

Если не указать `filename`, SBR-файл получает такое же базовое имя, как у исходного файла.

Использовать параметр **/Fr** не рекомендуется; используйте вместо него **/FR** . Дополнительные сведения см. в разделе "Нерекомендуемые и удаленные параметры компилятора" статьи [Compiler Options Listed by Category](compiler-options-listed-by-category.md).

> [!NOTE]
> Не изменяйте расширение SBR. Программе BSCMAKE требуются промежуточные файлы с этим расширением.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. В области навигации выберите страницу свойств **C/C++**, **Информация об исходном коде** .

1. Измените свойство **Файл информации об исходном коде** или **Включить информацию об исходном коде** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- Ознакомьтесь с разделами <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)<br/>
[Указание имени Пути](specifying-the-pathname.md)
