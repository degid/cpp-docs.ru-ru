---
title: /DYNAMICBASE
ms.date: 06/12/2018
f1_keywords:
- /dynamicbase
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
ms.openlocfilehash: 5451e3d16883eef225aebc3c420e6c0700947ad6
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842589"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

Указывает, создавать ли исполняемый образ, который может быть случайным образом изменен во время загрузки, с помощью функции имитации макета адресного пространства (ASLR) Windows, которая была впервые доступна в Windows Vista.

## <a name="syntax"></a>Синтаксис

> **/DynamicBase**[**: нет**]

## <a name="remarks"></a>Примечания

Параметр **/DynamicBase** изменяет заголовок *исполняемого образа*, DLL или EXE-файла, чтобы указать, должно ли приложение случайным образом перераспределяться во время загрузки, и разрешает случайное выделение виртуальных адресов, что влияет на расположение кучи, стеки и другие выделения операционных систем. Параметр **/DynamicBase** применяется как для 32-разрядных, так и для 64-разрядных изображений. ASLR поддерживается в операционных системах Windows Vista и более поздних версий. Этот параметр не учитывается в более ранних операционных системах.

По умолчанию **/DynamicBase** включен. Чтобы отключить этот параметр, используйте **/DynamicBase: No**. Параметр **/DynamicBase** требуется для того, чтобы параметр [/highentropyva](highentropyva-support-64-bit-aslr.md) действовал.

## <a name="see-also"></a>См. также раздел

- [Параметры EDITBIN](editbin-options.md)
- [Средства защиты программного обеспечения Windows ISV](/previous-versions/bb430720(v=msdn.10))
