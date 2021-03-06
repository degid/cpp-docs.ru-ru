---
title: Приведение целочисленных значений к значениям с плавающей запятой
ms.date: 11/04/2016
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
ms.openlocfilehash: b3c65beee0cef4eb74d1bad3c03e5a9c11efae27
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227924"
---
# <a name="casting-integers-to-floating-point-values"></a>Приведение целочисленных значений к значениям с плавающей запятой

**ANSI 3.2.1.3** Направление усечения при преобразовании целого числа в число с плавающей запятой, которое не может точно представить исходное значение

Если целое число приводится к значению с плавающей запятой, которое точно не может представить это значение, это значение округляется (в большую или меньшую сторону) до ближайшего подходящего значения.

Например, приведение числа типа **`unsigned long`** (точность — 32 бита) к типу **`float`** (мантисса которого имеет точность 23 бита) приводит к округлению числа до ближайшего кратного 256. Значения **`long`** в диапазоне от 4 294 966 913 до 4 294 967 167 округляются до значения 4 294 967 040 с типом **`float`** .

## <a name="see-also"></a>См. также

[Вычисления с плавающей запятой](../c-language/floating-point-math.md)
