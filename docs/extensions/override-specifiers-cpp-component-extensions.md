---
title: Описатели переопределения (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- override specifiers, C++
- override specifiers
ms.assetid: 155bbf6f-4722-4654-afb1-9cb52af799fb
ms.openlocfilehash: 410fe9ecc48b92c68132f7b1b8057c2549c8afcf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181906"
---
# <a name="override-specifiers--ccli-and-ccx"></a>Описатели переопределения (C++/CLI и C++/CX)

*Описатели переопределения* изменяют поведение унаследованных типов и членов унаследованных типов в производных типах.

## <a name="all-runtimes"></a>Все среды выполнения

### <a name="remarks"></a>Примечания

Дополнительные сведения о спецификаторах переопределения см. в разделах:

- [abstract](abstract-cpp-component-extensions.md)

- [new (новая ячейка в таблице vtable)](new-new-slot-in-vtable-cpp-component-extensions.md)

- [override](override-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- [Описатели переопределения и компиляции в машинный код](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)

Также при объявлении типа можно использовать **abstract** и **sealed** в качестве описателей переопределения.

Дополнительные сведения о функциях явного переопределения базового класса см. в статье [Явное переопределение](explicit-overrides-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Среда выполнения Windows

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде выполнения Windows).

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

(Отсутствуют комментарии для этой возможности языка, которая применяется только в среде CLR).

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

## <a name="see-also"></a>См. также раздел

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)
