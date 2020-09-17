---
title: /HEAP (Установка размера кучи)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- VC.Project.VCLinkerTool.HeapReserveSize
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
ms.openlocfilehash: f155ad56ec1a90479b402e38e7ec7f3e3d80e470
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439523"
---
# <a name="heap-set-heap-size"></a>/HEAP (Установка размера кучи)

```
/HEAP:reserve[,commit]
```

## <a name="remarks"></a>Примечания

Параметр/HEAP задает размер кучи в байтах. Этот параметр используется только при сборке EXE-файла.

Аргумент *Reserve* задает общее выделение кучи в виртуальной памяти. Размер кучи по умолчанию — 1 МБ. Компоновщик Округляет указанное значение до ближайших 4 байт.

Необязательный аргумент `commit` указывает объем физической памяти, выделяемой за раз. Выделенная виртуальная память приводит к тому, что пространство резервируется в файле подкачки. Более высокое значение `commit` экономит время, когда приложению требуется больше пространства в куче, но увеличивает требования к памяти и, возможно, время запуска.

Укажите значения *Reserve* и `commit` в формате десятичной или C-языковой нотации.

Эта функция также доступна через файл определения модуля с [хеапсизе](heapsize.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите папку **компоновщика**.

1. Перейдите на страницу свойств **системы** .

1. Измените свойство " **Размер фиксации кучи** ".

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- Ознакомьтесь с разделами <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
