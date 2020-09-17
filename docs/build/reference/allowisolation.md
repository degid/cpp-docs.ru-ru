---
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION_EDITBIN
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: 3dae8ee83e25492fab0ba2c6a55681728d5f3453
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440371"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

Задает поведение нахождения файлов манифеста.

## <a name="syntax"></a>Синтаксис

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Примечания

**/ALLOWISOLATION** заставляет операционную систему выполнять поиск и загрузку манифеста.

По умолчанию используется **/ALLOWISOLATION** .

**/ALLOWISOLATION: нет** означает, что исполняемые файлы загружаются так, как если бы манифеста не было, и заставляет [ссылку EDITBIN](editbin-reference.md) задать бит `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` в поле `DllCharacteristics` необязательного заголовка.

Если изоляция для исполняемого файла отключена, загрузчик Windows не пытается найти манифест приложения для нового процесса. Новый процесс не имеет контекста активации по умолчанию, даже если существует манифест в самом исполняемом файле или если имеется манифест с именем *Executable*. exe. manifest.

## <a name="see-also"></a>См. также раздел

[Параметры EDITBIN](editbin-options.md)<br/>
[/ALLOWISOLATION (поиск манифеста)](allowisolation-manifest-lookup.md)<br/>
[Справочник по файлам манифеста](/windows/win32/SbsCs/manifest-files-reference)
