---
title: Параметры /O (оптимизация кода)
description: Параметры компилятора КОМПИЛЯТОРОМ MSVC/O указывают используемые оптимизации компилятора.
ms.date: 07/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
ms.openlocfilehash: 36ef582787a3ec2d7aee1e589c70b48712d9d552
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180881"
---
# <a name="o-options-optimize-code"></a>`/O`Параметры (оптимизация кода)

С помощью **`/O`** параметров можно управлять различными оптимизациями, которые помогают создавать код для максимальной скорости или минимального размера.

- [`/O1`](o1-o2-minimize-size-maximize-speed.md)задает сочетание оптимизаций, формирующих код минимального размера.

- [`/O2`](o1-o2-minimize-size-maximize-speed.md)задает сочетание оптимизаций, которое оптимизирует код для максимальной скорости.

- [`/Ob`](ob-inline-function-expansion.md)управляет расширением встроенных функций.

- [`/Od`](od-disable-debug.md)отключает оптимизацию, ускоряет компиляцию и упрощает отладку.

- [`/Og`](og-global-optimizations.md)(не рекомендуется) включает глобальные оптимизации.

- [`/Oi`](oi-generate-intrinsic-functions.md)создает встроенные функции для соответствующих вызовов функций.

- [`/Os`](os-ot-favor-small-code-favor-fast-code.md)Указывает компилятору предпочтение оптимизации для увеличения размера с оптимизацией для ускорения.

- [`/Ot`](os-ot-favor-small-code-favor-fast-code.md)(значение по умолчанию) указывает компилятору предпочтение оптимизации для ускорения оптимизации для размера.

- [`/Ox`](ox-full-optimization.md)— это комбинированный вариант, выбирающий несколько оптимизаций с акцентом на скорость. **`/Ox`**— Это ограниченное подмножество **`/O2`** операций оптимизации.

- [`/Oy`](oy-frame-pointer-omission.md)подавляет создание указателей на фреймы в стеке вызовов для ускорения вызовов функций.

## <a name="remarks"></a>Примечания

Несколько параметров можно объединить **`/O`** в один оператор Option. Например, **`/Odi`** имеет то же значение, что и **`/Od /Oi`** . Некоторые параметры являются взаимоисключающими и вызывают ошибку компилятора, если они используются вместе. Дополнительные сведения см. в разделе индивидуальные **`/O`** Параметры.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
