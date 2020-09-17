---
title: Пределы поля "Путь"
ms.date: 11/04/2016
f1_keywords:
- _MAX_EXT
- _MAX_DIR
- _MAX_PATH
- _MAX_FNAME
- _MAX_DRIVE
helpviewer_keywords:
- path field constants
- MAX_FNAME constant
- _MAX_DIR constant
- _MAX_DRIVE constant
- paths, maximum limit
- _MAX_PATH constant
- MAX_DRIVE constant
- _MAX_FNAME constant
- _MAX_EXT constant
- MAX_DIR constant
- MAX_EXT constant
ms.assetid: 2b5d0e43-1347-45b4-8397-24a8a45c444e
ms.openlocfilehash: 8db9961bd2d5b5b3ea9d3addad3c26737b4f5199
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171402"
---
# <a name="path-field-limits"></a>Пределы поля "Путь"

## <a name="syntax"></a>Синтаксис

```cpp
#include <stdlib.h>
```

## <a name="remarks"></a>Примечания

Эти константы определяют максимальную длину пути и отдельных полей в пути.

|Постоянно|Значение|
|--------------|-------------|
|`_MAX_DIR`|Максимальная длина компонента каталога|
|`_MAX_DRIVE`|Максимальная длина компонента диска|
|`_MAX_EXT`|Максимальная длина компонента расширения|
|`_MAX_FNAME`|Максимальная длина компонента имени файла|
|`_MAX_PATH`|Максимальная длина полного пути|

> [!NOTE]
> Среда выполнения языка C поддерживает длину пути до 32768 символов, но поддержка таких длинных путей зависит от операционной системы, а именно, от файловой системы. Для полной обратной совместимости с файловыми системами FAT32 общая длина полей не должна превышать `_MAX_PATH`. Файловая система Windows NTFS поддерживает пути длиной до 32 768 символов, но только при использовании API Юникода. Если вы используете длинные пути, указывайте в начале пути символы \\\\?\ и используйте версии для Юникода функций среды выполнения языка С.

## <a name="see-also"></a>См. также раздел

[Глобальные константы](../c-runtime-library/global-constants.md)
