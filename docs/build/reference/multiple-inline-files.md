---
title: Использование нескольких встроенных файлов
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: 71f17ff6717e717693facb21b4a4341a040b14c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320595"
---
# <a name="multiple-inline-files"></a>Использование нескольких встроенных файлов

Команду можно создать несколько встроенных файлов.

## <a name="syntax"></a>Синтаксис

```
command << <<
inlinetext
<<[KEEP | NOKEEP]
inlinetext
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Примечания

Для каждого файла укажите один или несколько строк встроенного текста, за которым следует закрывающая строка, содержащая разделитель по. Начните второй файл текст в строке после разделителя строки, для первого файла.

## <a name="see-also"></a>См. также

[Подставляемые файлы в Makefile](inline-files-in-a-makefile.md)
