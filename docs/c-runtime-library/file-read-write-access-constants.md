---
title: Константы доступа на чтение и запись файлов
ms.date: 11/04/2016
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
ms.openlocfilehash: 96d146b2e2f0ed82cbdc52b11d92c049da50e2cb
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438393"
---
# <a name="file-readwrite-access-constants"></a>Константы доступа чтения и записи файлов

## <a name="syntax"></a>Синтаксис

```
#include <stdio.h>
```

## <a name="remarks"></a>Примечания

Эти константы определяют запрашиваемый для файла тип доступа ("a", "r" или "w"). В типе доступа можно указать как [режим преобразования](../c-runtime-library/file-translation-constants.md) ("b" или "t"), так и [режим фиксации на диск](../c-runtime-library/commit-to-disk-constants.md) ("c" или "n").

Типы доступа описаны в следующей таблице.

|Тип доступа|Description|
|----------|----------------|
|**"r"**|Открывает для чтения. Если файл не существует или его невозможно найти, открытие файла завершается ошибкой.|
|**"w"**|Открывает пустой файл для записи. Если указанный файл существует, его содержимое удаляется.|
|**"a"**|Открывает для записи в конец файла (добавление); сначала создает файл, если он не существует. Все операции записи выполняются в конце файла. Положение указателя файла можно изменить с помощью функции `fseek` или `rewind`, но он всегда возвращается в конец файла перед выполнением любой операции записи. |
|**"r+"**|Открывает для чтения и записи. Если файл не существует или его невозможно найти, открытие файла завершается ошибкой.|
|**"w+"**|Открывает пустой файл для чтения и записи. Если указанный файл существует, его содержимое удаляется.|
|**"a+"**|То же, что и **"a"** , но допускает чтение.|

Если задан тип доступа "r+", "w+" или "a+", разрешены чтение и запись (считается, что файл открыт "для обновления"). Однако при переключении между чтением и записью должны быть промежуточные операции `fflush`, `fsetpos`, `fseek` или `rewind`. Для операции `fsetpos` или `fseek` можно задать текущее положение.

## <a name="see-also"></a>См. также раздел

[_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)<br/>
[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)<br/>
[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)<br/>
[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)<br/>
[_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
