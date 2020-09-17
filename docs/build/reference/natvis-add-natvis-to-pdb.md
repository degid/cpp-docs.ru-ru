---
title: /NATVIS (добавление файла NATVIS в файл PDB)
ms.date: 08/10/2017
f1_keywords:
- /natvis
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
ms.openlocfilehash: a16e320a2f8f946912fef6a354f27f6514a67e29
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439274"
---
# <a name="natvis-add-natvis-to-pdb"></a>/NATVIS (добавление файла NATVIS в файл PDB)

> /НАТВИС:*имя файла*

## <a name="parameters"></a>Параметры

*filename*<br/>
Natvis-файл для добавления в PDB-файл. Он внедряет визуализацию отладчика в файл Natvis в PDB.

## <a name="remarks"></a>Примечания

Параметр/НАТВИС внедряет визуализации отладчика, определенные в файле Natvis-файла, в PDB *-файл,* созданный LINK. Это позволяет отладчику отображать визуализации независимо от natvis – файла. Можно использовать несколько параметров/НАТВИС для внедрения нескольких Natvis-файлов в созданный PDB-файл.

LINK игнорирует/НАТВИС, если PDB-файл не создается с помощью параметра [/Debug](debug-generate-debug-info.md) . Сведения о создании и использовании natvis файлов см. [в разделе Создание пользовательских представлений собственных объектов в отладчике Visual Studio](/visualstudio/debugger/create-custom-views-of-native-objects).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Командная строка** в папке **Компоновщик** .

1. Добавьте параметр/НАТВИС в текстовое поле **Дополнительные параметры** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- Этот параметр не имеет программного эквивалента.

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
