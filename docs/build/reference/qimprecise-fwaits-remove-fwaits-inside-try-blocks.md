---
title: /Qimprecise_fwaits (Удалить ожидания в блоке try)
ms.date: 11/04/2016
f1_keywords:
- /Qimprecise_fwaits
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
ms.openlocfilehash: 424feda66f6925cb305256249101ea4013e3090f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232681"
---
# <a name="qimprecise_fwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (Удалить ожидания в блоке try)

Удаляет `fwait` команды, внутренние для **`try`** блоков, при использовании параметра компилятора [/FP: except](fp-specify-floating-point-behavior.md) .

## <a name="syntax"></a>Синтаксис

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>Примечания

Этот параметр не действует, если **/FP: except** также не задан. Если указать параметр **/FP: except** , компилятор вставит `fwait` в блоке команды вокруг каждой строки кода **`try`** . Таким образом, компилятор может опознать конкретную строку кода, которая создает исключение. **/Qimprecise_fwaits** удаляют внутренние `fwait` инструкции, в результате чего выполняется только ожидание **`try`** блока. Это повышает производительность, но компилятор может только сказать, какой **`try`** блок вызывает исключение, а не какую строку.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также статью

[Параметры/q (низкоуровневые операции)](q-options-low-level-operations.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
