---
title: /Zp (Выравнивание члена структуры)
ms.date: 04/04/2019
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
ms.openlocfilehash: c78e670303bde68299725e18c6f588f5e410a971
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234306"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Выравнивание члена структуры)

Управляет упаковкой элементов структуры в память и задает одну и ту же упаковку для всех структур в модуле.

## <a name="syntax"></a>Синтаксис

> **`/Zp`**[**`1`**|**`2`**|**`4`**|**`8`**|**`16`**]

## <a name="remarks"></a>Примечания

**`/ZpN`** Параметр указывает компилятору, где следует хранить каждый член структуры. Компилятор сохраняет элементы после первого элемента на границе, которая меньше либо размера типа элемента, либо *N*-байтовой границы.

Доступные значения упаковки описаны в следующей таблице.

|/ZP, аргумент|Действие|
|-|-|
|1|Упаковывает структуры по 1-байтным границам. То же, что и **`/Zp`** .|
|2|Упаковывает структуры на 2-байтовые границы.|
|4|Упаковывает структуры на 4-байтные границы.|
|8|Упаковывает структуры по 8-байтным границам (по умолчанию для x86, ARM и ARM64).|
|16| Упаковывает структуры по 16-байтным границам (по умолчанию для x64).|

Не используйте этот параметр, если не заданы конкретные требования к выравниванию.

> [!WARNING]
> Заголовки C++ в наборе Windows SDK и предполагают **`/Zp8`** внутреннюю упаковку. Повреждение памяти может возникать, если **`/Zp`** параметр изменяется в заголовке Windows SDK. На заголовки не влияют никакие **`/Zp`** Параметры, заданные в командной строке.

Также можно использовать [`pack`](../../preprocessor/pack.md) для управления упаковкой структуры. Дополнительные сведения о выравнивании см. в разделах:

- [`align`](../../cpp/align-cpp.md)

- [`alignof`Станции](../../cpp/alignof-operator.md)

- [`__unaligned`](../../cpp/unaligned.md)

- [`/ALIGN`(Выравнивание разделов)](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите страницу свойств **Свойства "**  >  Создание кода**C/C++**"  >  **Code Generation** .

1. Измените свойство **Выравнивание члена структуры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>См. также статью

[Параметры компилятора КОМПИЛЯТОРОМ MSVC](compiler-options.md) \
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
