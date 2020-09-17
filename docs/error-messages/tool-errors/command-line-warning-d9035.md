---
title: Предупреждение командной строки D9035
ms.date: 12/10/2018
f1_keywords:
- D9035
helpviewer_keywords:
- D9035
ms.assetid: 6254f933-e37a-45ba-b860-1a870d1bc8e8
ms.openlocfilehash: 778830892bca1cbf3520599eb6e918e56bdf17ea
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196642"
---
# <a name="command-line-warning-d9035"></a>Предупреждение командной строки D9035

> параметр "*параметр*" является устаревшим и будет удален в следующем выпуске

## <a name="remarks"></a>Примечания

Вы указали параметр компилятора, который будет удален в следующем выпуске компилятора. Если предложено заменить *параметр*, это предупреждение должно следовать за предупреждением [D9036](../../error-messages/tool-errors/command-line-warning-d9036.md).

Указанный параметр все еще работает, но вы должны обновить конфигурацию сборки прямо сейчас. В результате проект, скорее всего, будет продолжать создаваться при обновлении компилятора.

## <a name="see-also"></a>См. также раздел

[Нерекомендуемые и удаленные параметры компилятора](../../build/reference/compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options)<br/>
[Предупреждение командной строки D9036](command-line-warning-d9036.md)
