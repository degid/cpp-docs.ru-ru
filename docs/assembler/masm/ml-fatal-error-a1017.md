---
title: Неустранимая ошибка ML A1017
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: 523fed26afae5a88c5f154283487d3453a2e48c7
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318063"
---
# <a name="ml-fatal-error-a1017"></a>Неустранимая ошибка ML A1017

**отсутствует имя исходного файла**

МАШИНному обучению не удалось найти файл для сборки или передачи в компоновщик.

Эта ошибка возникает при предоставлении параметров командной строки ML без указания имени файла для действия. Чтобы собрать файлы, не имеющие расширения ASM, используйте параметр командной строки **/та** .

Эту ошибку также можно создать, вызвав ML без параметров, если переменная среды машинного обучения содержит параметры командной строки.

## <a name="see-also"></a>См. также:

[Сообщения об ошибках ML](ml-error-messages.md)
