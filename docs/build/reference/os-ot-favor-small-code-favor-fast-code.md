---
title: /Os, /Ot (приоритет размера кода или скорости кода)
description: Параметры компилятора КОМПИЛЯТОРОМ MSVC/OS и/OT указывают, следует ли предпочитать размер или скорость при оптимизации кода.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed
- /os
- VC.Project.VCCLCompilerTool.FavorSizeOrSpeed
helpviewer_keywords:
- favor fast code compiler option [C++]
- /Os compiler option [C++]
- Ot compiler option [C++]
- /Ot compiler option [C++]
- small machine code
- -Ot compiler option [C++]
- fast code
- favor small code compiler option [C++]
- Os compiler option [C++]
- -Os compiler option [C++]
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
ms.openlocfilehash: 384019ddf7b80b8dd4e00197d73d1e4ac536634c
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180829"
---
# <a name="os-ot-favor-small-code-favor-fast-code"></a>`/Os``/Ot`(Предпочитать малый код, предпочитать быстрый код)

Уменьшает или увеличивает размер исполняемых файлов и библиотек DLL.

## <a name="syntax"></a>Синтаксис

> **`/Os`**\
> **`/Ot`**

## <a name="remarks"></a>Примечания

**`/Os`**(Предпочитать небольшой код) — уменьшает размер исполняемых файлов и библиотек DLL, предписывая компилятору предпочтение размера выше скорости. Компилятор может сократить многие конструкции C и C++ для функционально схожих последовательностей машинного кода. Иногда эти различия предлагают компромиссы между размером и скоростью. **`/Os`** Параметры и **`/Ot`** позволяют указать другой вариант для одного другого.

**`/Ot`**(Предпочитать быстрый код) увеличивает скорость файлов exe и DLL, предписывая компилятору предпочтение ускорения к размеру. **`/Ot`** используется по умолчанию при включении оптимизации. Компилятор может сократить многие конструкции C и C++ для функционально схожих последовательностей машинного кода. Иногда эти различия предлагают компромиссы между размером и скоростью. **`/Ot`** Параметр подразумевается [`/O2`](o1-o2-minimize-size-maximize-speed.md) параметром (максимизировать скорость). **`/O2`** Параметр объединяет несколько параметров для ускорения кода.

> [!NOTE]
> Сведения, собранные из тестовых запусков профилирования, переопределяют любые оптимизации, которые в противном случае будут действовать, если указать **`/Ob`** , **`/Os`** или **`/Ot`** . Дополнительные сведения см. в статье [Профильные оптимизации](../profile-guided-optimizations.md).

### <a name="x86-specific-example"></a>Пример для x86

В следующем примере кода демонстрируется различие между **`/Os`** параметром (предпочитать малый код) и **`/Ot`** параметром (приоритет скорости быстрого кода).

> [!NOTE]
> В этом примере описывается ожидаемое поведение при использовании **`/Os`** или **`/Ot`** . Однако поведение компилятора в выпуске может привести к различным оптимизациям кода ниже.

```c
/* differ.c
  This program implements a multiplication operator
  Compile with /Os to implement multiply explicitly as multiply.
  Compile with /Ot to implement as a series of shift and LEA instructions.
*/
int differ(int x)
{
    return x * 71;
}
```

Как показано в фрагменте машинного кода ниже, когда *`differ.c`* компилируется для size ( **`/Os`** ), компилятор реализует выражение умножения в операторе return явным образом, чтобы получить краткую, но более медленную последовательность кода:

```asm
mov    eax, DWORD PTR _x$[ebp]
imul   eax, 71                  ; 00000047H
```

Кроме того, когда *`differ.c`* компилируется для Speed ( **`/Ot`** ), компилятор реализует выражение умножения в операторе return в виде ряда Shift и `LEA` инструкций для создания быстрой, но более длинной последовательности кода:

```asm
mov    eax, DWORD PTR _x$[ebp]
mov    ecx, eax
shl    eax, 3
lea    eax, DWORD PTR [eax+eax*8]
sub    eax, ecx
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **Configuration Properties**  >  страницу свойств «Оптимизация**C/C++**» свойств конфигурации  >  **Optimization** .

1. Измените свойство **предпочитать размер или скорость** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры /O (оптимизация кода)](o-options-optimize-code.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
