---
title: /Gy (включение компоновки на уровне функций)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 8724ae4d018948c0f6aa9456f229db96878d7bf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328281"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (включение компоновки на уровне функций)

Компилятор может упаковывать отдельные функции в форме упакованных функций (COMDAT).

## <a name="syntax"></a>Синтаксис

```
/Gy[-]
```

## <a name="remarks"></a>Примечания

Связующее лицо требует, чтобы функции были упакованы отдельно как COMDATs, чтобы исключить или заказать отдельные функции в файле DLL или .exe.

Вы можете использовать опцию linker [/OPT (Оптимизация),](opt-optimizations.md) чтобы исключить нессылкупакетные упакованные функции из файла .exe.

Вы можете использовать опцию linker [/ORDER (Put Functions in Order),](order-put-functions-in-order.md) чтобы включить упакованные функции в заданном порядке в файл .exe.

Функции inline всегда упаковываются, если они мгновенно используются в виде вызовов (что происходит, например, если выравнивание выключено или вы берете адрес функции). Кроме того, функции члена СЗ, определенные в декларации класса, автоматически упаковываются; другие функции не являются, и выбор этого параметра требуется для компиляции их в виде упакованных функций.

> [!NOTE]
> Опция [/ЗИ,](z7-zi-zi-debug-information-format.md) используемая для edit and Continue, автоматически устанавливает опцию **/Gy.**

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите на страницу свойства **генерации кода.**

1. Измените свойство **ссылок уровня функции.**

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)
