---
title: /GF (Исключение повторяющихся строк)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
ms.openlocfilehash: e0d23004c7b710f51065db52410fbb15b7cca040
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320494"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Исключение повторяющихся строк)

Позволяет компилятору создать единую копию одинаковых строк в изображении программы и в памяти во время выполнения. Это оптимизация называется *строка объединения,* которые могут создавать меньшие программы.

## <a name="syntax"></a>Синтаксис

```
/GF
```

## <a name="remarks"></a>Примечания

Если вы используете **/GF,** операционная система не меняет строку часть памяти и может читать строки обратно из файла изображения.

**/GF** пули строки, как только читать. При попытке изменить строки под **/GF**возникает ошибка приложения.

Объединение строк позволяет, как это было задумано как несколько указателей, к нескольким буферам быть несколькими указателями на один буфер. В следующем коде, `s` и `t` инициализированы с той же строки. Объединение строк заставляет их указывать на ту же память:

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
> Опция [/ЗИ,](z7-zi-zi-debug-information-format.md) используемая для edit and Continue, автоматически устанавливает опцию **/GF.**

> [!NOTE]
> Опция компилятора **/GF** создает адресный раздел для каждой уникальной строки. По умолчанию файл объекта может содержать до 65 536 адресных разделов. Если программа содержит более 65 536 строк, используйте опцию компилятора [/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md) для создания большего количества разделов.

**/GF** действует при [использовании /O1](o1-o2-minimize-size-maximize-speed.md) или [/O2.](o1-o2-minimize-size-maximize-speed.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите на страницу свойства **генерации кода.**

1. Измените свойство **пульания строки.**

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)
