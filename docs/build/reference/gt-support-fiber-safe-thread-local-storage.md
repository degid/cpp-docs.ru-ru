---
title: /GT (поддержка локальной памяти потока, безопасной относительно волокон)
description: Параметр компилятора КОМПИЛЯТОРОМ MSVC/GT позволяет выполнять оптимизацию для данных локального хранилища потока.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
ms.openlocfilehash: 1b1d9f6514cec8c3d247f86be063f2ac3e0dfe72
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180816"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>`/GT`(Поддерживает локальное оптоволоконное хранилище потока)

Поддерживает безопасность волокон для данных, выделенных с помощью статического локального хранилища потока, то есть данных, которые выделены с помощью `__declspec(thread)` .

## <a name="syntax"></a>Синтаксис

> **`/GT`**

## <a name="remarks"></a>Примечания

Данные, объявленные с `__declspec(thread)` , указываются через массив локального хранилища потока (TLS). Массив TLS — это массив адресов, поддерживаемых системой для каждого потока. Каждый адрес в этом массиве предоставляет расположение данных локального хранилища потока.

Волокно — это упрощенный объект, состоящий из стека и контекста регистра, который может быть запланирован в различных потоках. Волокно может выполняться в любом потоке. Так как волокно может быть перезагружено и перезапущено позже в другом потоке, компилятор не должны кэширует адрес массива TLS или оптимизирует его как общую часть выражения в вызове функции. **`/GT`** предотвращает такие оптимизации.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **Configuration Properties**  >  страницу свойств «Оптимизация**C/C++**» свойств конфигурации  >  **Optimization** .

1. Измените свойство **включить многослойную оптимизацию** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
