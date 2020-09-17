---
title: /await (включение поддержки соподпрограмм)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: 526216ba2ae259b53bcf77691ebd09a6152b83f0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223932"
---
# <a name="await-enable-coroutine-support"></a>/await (включение поддержки соподпрограмм)

Используйте параметр компилятора **/await** , чтобы включить поддержку компилятора для соподпрограмм.

## <a name="syntax"></a>Синтаксис

> /await

## <a name="remarks"></a>Примечания

Параметр компилятора **/await** включает поддержку компилятора для соподпрограмм C++ и ключевых слов **`co_await`** , **`co_yield`** и **`co_return`** . По умолчанию она отключена. Сведения о поддержке соподпрограмм в Visual Studio см. в [блоге группы разработчиков Visual Studio](https://devblogs.microsoft.com/cppblog/category/coroutine/). Дополнительные сведения о стандартном предложении "коподпрограмми" см. в разделе [N4628 Working, техническая спецификация расширений C++ для соподпрограмм](https://wg21.link/n4628).

Параметр **/await** доступен начиная с Visual Studio 2015.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **страницы свойств** проекта.

1. В разделе **Свойства конфигурации**разверните папку **C/C++** и выберите страницу свойств **Командная строка** .

1. В поле **Дополнительные параметры** введите параметр компилятора **/await** . Нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также статью

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)
