---
title: Предупреждение компилятора (уровень 4) C4710
ms.date: 11/04/2016
f1_keywords:
- C4710
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
ms.openlocfilehash: c30b98204f447f4d9d0ab8d687602a361d909363
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218069"
---
# <a name="compiler-warning-level-4-c4710"></a>Предупреждение компилятора (уровень 4) C4710

"функция": функция не встроена

Данная функция была выбрана для встроенного расширения, но компилятор не выполнил встраивание.

Встраивание выполняется по усмотрению компилятора. **`inline`** Ключевое слово, как и **`register`** ключевое слово, используется в качестве подсказки для компилятора. Компилятор использует эвристику, чтобы определить, должна ли она подставлять определенную функцию для ускорения кода при компиляции для ускорения, или если она должна подставлять определенную функцию, чтобы уменьшить размер кода при компиляции пространства. Компилятор будет подставляем только немалые функции при компиляции для пространства.

В некоторых случаях компилятор не будет встроеет определенную функцию по механическим причинам. Список причин, по которым компилятор может не подставляемь функцию, см. в разделе [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) .

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .
