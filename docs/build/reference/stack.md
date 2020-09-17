---
title: /STACK
ms.date: 11/04/2016
f1_keywords:
- /stack_editbin
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
ms.openlocfilehash: 63fcddec8ff8afd81084bb5a2786f394db594b07
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438882"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Примечания

Этот параметр задает размер стека в байтах и принимает аргументы в десятичной или C-языковой нотации. Параметр/STACK применяется только к исполняемому файлу.

Аргумент *Reserve* задает общее выделение стека в виртуальной памяти. Программа EDITBIN Округляет указанное значение до ближайших 4 байт.

Необязательный аргумент `commit` подлежит интерпретации операционной системы. В Windows NT, Windows 95 и Windows 98 `commit` указывает объем физической памяти, выделяемой за раз. Выделенная виртуальная память приводит к тому, что пространство резервируется в файле подкачки. Более высокое значение `commit` экономит время, когда приложению требуется больше пространства стека, но увеличивает требования к памяти и, возможно, время запуска.

## <a name="see-also"></a>См. также раздел

[Параметры EDITBIN](editbin-options.md)
