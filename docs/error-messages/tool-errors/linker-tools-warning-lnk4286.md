---
title: Предупреждение средств компоновщика LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: d0205ba065f6e410383c38a0f1c2eaa0da55fe93
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173872"
---
# <a name="linker-tools-warning-lnk4286"></a>Предупреждение средств компоновщика LNK4286

> символ "*symbol*", определенный в "*filename_1. obj*", импортируется "*filename_2. obj*"

для *symbol* был указан [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) , хотя символ определен в объектном файле *filename_1. obj* в том же образе. Удалите модификатор `__declspec(dllimport)`, чтобы устранить это предупреждение.

## <a name="remarks"></a>Примечания

Предупреждение LNK4286 — это более общая версия [средств компоновщика LNK4217 Warning](linker-tools-warning-lnk4217.md). Компоновщик создает предупреждение LNK4286, когда он может определить, какой объектный файл ссылается на символ, но не какая функция.

Чтобы разрешить LNK4286, удалите модификатор объявления `__declspec(dllimport)` из прямого объявления *символа* , указанного в *filename_2. obj*.

Хотя окончательный созданный код работает правильно, код, созданный для вызова импортированной функции, менее эффективен, чем вызов функции напрямую. Это предупреждение не появляется при компиляции с параметром [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) .

Дополнительные сведения об объявлениях импорта и экспорта данных см. в разделе [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

## <a name="see-also"></a>См. также раздел

[Предупреждение средств компоновщика LNK4049](linker-tools-warning-lnk4049.md) \
[Предупреждение средств компоновщика LNK4217](linker-tools-warning-lnk4217.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
