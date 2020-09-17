---
title: /SOURCELINK (включение файла Sourcelink в PDB-файл)
description: Справочное руководство по опции linker /SOURCELINK в Microsoft C .
ms.date: 03/31/2020
f1_keywords:
- /sourcelink
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
ms.openlocfilehash: bde55c401e17f7b3c84ffcdad29dda2badcc260b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336067"
---
# <a name="sourcelink-include-source-link-file-in-pdb"></a>/ИСТОЧНИКЛИНК (Включить файл ссылки на источник в PDB)

Укажите файл конфигурации ссылки источника для включения в файл PDB, генерируемый связующим.

## <a name="syntax"></a>Синтаксис

> **`/SOURCELINK:`**_`filename`_

## <a name="arguments"></a>Аргументы

*Имени файла*<br/>
Определяет файл конфигурации jSON, содержащий простое отображение локальных путей файлов к URL-адресам для исходных файлов для отображения в отладчике. Для получения дополнительной информации о формате этого [файла, см.](https://github.com/dotnet/designs/blob/master/accepted/2020/diagnostics/source-link.md#source-link-json-schema)

## <a name="remarks"></a>Примечания

Source Link — это агностик-система управления языком и исходным управлением для обеспечения отладки исходных файлов для бинарных файлов. Source Link поддерживается для местных бинарных файлов C е, начиная с визуальной студии 2017 версии 15.8. Для обзора Ссылка на источник, [см.](https://github.com/dotnet/designs/blob/master/accepted/2020/diagnostics/source-link.md) Для получения информации о том, как использовать Ссылку Наиное в проектах, и как создать файл SourceLink в рамках проекта, [см.](https://github.com/dotnet/sourcelink#using-source-link-in-c-projects)

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>Установить опцию linker /SOURCELINK в Visual Studio

1. Откройте диалоговую коробку **страниц свойств** для проекта. Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойства **configuration Properties** > **Linker** > **Command Line.**

1. В поле **Дополнительные опции** добавьте, **`/SOURCELINK:`** _`filename`_ а затем выберите **OK** или **приметесь,** чтобы сохранить изменения.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- Этот параметр не имеет программного эквивалента.

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Варианты MSVC Linker](linker-options.md)
