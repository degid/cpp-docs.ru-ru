---
title: /LINENUMBERS
ms.date: 11/04/2016
f1_keywords:
- /linenumbers
helpviewer_keywords:
- LINENUMBERS dumpbin option
- line numbers
- -LINENUMBERS dumpbin option
- /LINENUMBERS dumpbin option
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
ms.openlocfilehash: ea4c3ac2ad582e0fe364f2da26511a66e9dc376c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269245"
---
# <a name="linenumbers"></a>/LINENUMBERS

```
/LINENUMBERS
```

## <a name="remarks"></a>Примечания

Этот параметр отображает номера строк COFF. Номера строк существует в объектный файл, если он был скомпилирован с помощью базы данных программы (/Zi), совместимость C7 (/ Z7), или только нумерация строк (/ Zd). Исполняемый файл или библиотека DLL содержит COFF номера строк, если он был связан с создать отладочную информацию (/ DEBUG).

Только [/Headers](headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](dumpbin-options.md)
