---
title: Ошибка компилятора ресурсов RC2148
ms.date: 11/04/2016
f1_keywords:
- RC2148
helpviewer_keywords:
- RC2148
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
ms.openlocfilehash: e2394dbb93dd2d203d65760d805e09f60a692ba4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191331"
---
# <a name="resource-compiler-error-rc2148"></a>Ошибка компилятора ресурсов RC2148

Идентификатор языка слишком велик

Значение идентификатора языка выходит за пределы допустимого диапазона.

Оператор **LANGUAGE** должен использовать следующий синтаксис:

**LANGUAGE** *Primary_language_ID*языка,*secondary_language_ID*

Допустимые идентификаторы языков определяются как **SUBLANG_** константы в файле WINNT.h.
