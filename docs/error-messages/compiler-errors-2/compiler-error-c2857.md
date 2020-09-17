---
title: Ошибка компилятора C2857
ms.date: 09/13/2018
f1_keywords:
- C2857
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
ms.openlocfilehash: 11b620f9748ac85e731d79b0652c0392375b2ea4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201855"
---
# <a name="compiler-error-c2857"></a>Ошибка компилятора C2857

> Инструкция "#include", указанная с параметром командной строки/Yc*filename* , не найдена в исходном файле

Параметр [/Yc](../../build/reference/yc-create-precompiled-header-file.md) задает имя включаемого файла, который не включается в компилируемый исходный файл.

## <a name="remarks"></a>Примечания

При использовании параметра **/Yc**<em>filename</em> в исходном файле для создания файла предкомпилированного заголовка (PCH) этот исходный файл должен содержать *файл заголовка файла* . Каждый файл, включенный в исходный файл и включающий указанное *имя файла*, включается в PCH-файл. В других исходных файлах, скомпилированных с помощью параметра **/Yu**<em>filename</em> для использования PCH-файла, *имя* файла должно содержать первую строку без комментариев в файле. Компилятор пропускает все данные в исходном файле перед включением.

Эта ошибка может быть вызвана оператором `#include "filename"` в блоке условной компиляции, который не компилируется в исходном файле PCH.

## <a name="example"></a>Пример

В типичном использовании один исходный файл в проекте назначается в качестве исходного файла PCH, а в качестве файла заголовка PCH используется один файл заголовка. Стандартный файл заголовка PCH содержит все заголовки библиотек, используемые в проекте, но не локальные заголовки, которые еще находятся в разработке. В этом примере файл заголовка PCH называется *my_pch.h*.

```cpp
// my_pch.h
#pragma once
#include <stdio.h>
```

Исходный PCH-файл компилируется с помощью параметра **/yc**<em>my_pch.h</em> . Если компилятор не нашел включения этого файла заголовка PCH, он создает C2857:

```cpp
// my_pch.cpp
// Compile by using: cl /EHsc /W4 /Yumy_pch.h /c my_pch.cpp

#if 0
#include "my_pch.h"  // C2857; remove conditional directives to fix
#endif
```

Для использования этого файла PCH исходные файлы должны быть скомпилированы с параметром **/yu**<em>my_pch.h</em> . Заголовочный файл заголовка PCH должен быть сначала добавлен в исходные файлы, использующие PCH:

```cpp
// C2857.cpp
// Compile my_pch.cpp first, then
// compile by using: cl /EHsc /W4 /Yumy_pch.h my_project.cpp my_pch.obj
// Include the pch header before any other non-comment line
#include "my_pch.h"

int main()
{
    puts("Using a precompiled header file.\n");
}
```
