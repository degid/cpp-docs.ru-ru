---
title: /HIGHENTROPYVA
ms.date: 06/12/2018
f1_keywords:
- /HIGHENTROPYVA
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
ms.openlocfilehash: 80e34a3f57974e1af6afb65196697cce9aa344b1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835003"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Указывает, поддерживает ли исполняемый образ 64-разрядную технологию ASLR с высокой энтропией.

## <a name="syntax"></a>Синтаксис

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>Примечания

Этот параметр изменяет заголовок файла *исполняемого образа* (например, *`.dll`* *`.exe`* файла или), чтобы указать поддержку ASLR с 64-битным адресом. Чтобы получить результат, задайте параметр как для исполняемого файла, так и для всех модулей, от которых он зависит. Затем операционные системы, поддерживающие 64-разрядный ASLR, могут перераспределять сегменты исполняемого образа во время загрузки, используя случайные 64-битные виртуальные адреса. Благодаря обширному адресному пространству злоумышленнику будет труднее догадаться о расположении определенной области в памяти.

По умолчанию компоновщик поддерживает **`/HIGHENTROPYVA`** 64-разрядные исполняемые образы. Этот параметр требует [`/DYNAMICBASE`](dynamicbase.md) и [`/LARGEADDRESSAWARE`](largeaddressaware.md) , и, которые также включены по умолчанию для 64-разрядных изображений. **`/HIGHENTROPYVA`** не применяется к 32-разрядным исполняемым образам, в которых параметр игнорируется. Чтобы явно отключить этот параметр, используйте **`/HIGHENTROPYVA:NO`** .

## <a name="see-also"></a>См. также

[Параметры EDITBIN](editbin-options.md)\
[`/DYNAMICBASE`](dynamicbase.md)\
[`/LARGEADDRESSAWARE`](largeaddressaware.md)\
[Средства защиты программного обеспечения Windows ISV](/previous-versions/bb430720(v=msdn.10))
