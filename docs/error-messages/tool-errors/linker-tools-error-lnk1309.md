---
title: Ошибка средств компоновщика LNK1309
ms.date: 11/04/2016
f1_keywords:
- LNK1309
helpviewer_keywords:
- LNK1309
ms.assetid: 10146071-883f-4849-97d1-c7468f90efbb
ms.openlocfilehash: 88b05512fd45adb6dc96a6c130ceccb74f3ab14e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194906"
---
# <a name="linker-tools-error-lnk1309"></a>Ошибка средств компоновщика LNK1309

> обнаружен модуль *Type1* ; Недопустимый с параметром/CLRIMAGETYPE:*тип2*

## <a name="remarks"></a>Примечания

Тип образа CLR был запрошен с помощью **/CLRIMAGETYPE** , но компоновщику не удалось создать изображение этого типа, так как один или несколько модулей несовместимы с этим типом.

Например, вы увидите LNK1309, если указать **/CLRIMAGETYPE: Сейф** и передать модуль, созданный с помощью **/clr: pure**.

Параметры компилятора **/clr: pure** и **/clr: Сейф** и библиотеки поддержки являются устаревшими в Visual Studio 2015 и не поддерживаются в Visual Studio 2017.

Если вы попытаетесь создать частично доверенное чистое приложение CLR с помощью птрусту [d]. lib, вы также увидите LNK1309. Сведения о создании приложения с частичным доверием см. в разделе [как создать частично доверенное приложение путем удаления зависимости от библиотеки DLL библиотеки CRT](../../dotnet/create-a-partially-trusted-application.md).

Дополнительные сведения см. в разделе [/CLR (компиляция среды CLR)](../../build/reference/clr-common-language-runtime-compilation.md) и [/CLRIMAGETYPE (укажите тип образа CLR)](../../build/reference/clrimagetype-specify-type-of-clr-image.md).
