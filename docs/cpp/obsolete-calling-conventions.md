---
title: Устаревшие соглашения о вызовах
ms.date: 11/04/2016
f1_keywords:
- __fortran
- __pascal
- __syscall
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
ms.openlocfilehash: 156482a395c7dfc8711e273141a09a37ea3e135d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188562"
---
# <a name="obsolete-calling-conventions"></a>Устаревшие соглашения о вызовах

**Блок, относящийся только к системам Microsoft**

Соглашения о вызовах **__pascal**, **__fortran**и **__syscall** больше не поддерживаются. Их функциональные возможности можно эмулировать с помощью одного из поддерживаемых соглашений о вызовах и соответствующих параметров компоновщика.

\<Windows.h > теперь поддерживает макрос WINAPI, который преобразуется в соответствующее соглашение о вызовах для целевого объекта. Используйте WINAPI, где ранее использовался стиль PASCAL или **__far \__pascal**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md)
