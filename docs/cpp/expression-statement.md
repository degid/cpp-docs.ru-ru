---
title: Оператор выражений
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
ms.openlocfilehash: 2f12bbbafd9be50f851e36f472098431f9ac0d5d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189004"
---
# <a name="expression-statement"></a>Оператор выражений

Операторы выражений обеспечивают вычисление выражений. В результате выполнения оператора выражения ни передачи управления, ни итерации не происходит.

Синтаксис оператора выражения простой:

## <a name="syntax"></a>Синтаксис

```
[expression ] ;
```

## <a name="remarks"></a>Примечания

Вычисление всех выражений в операторе выражения и учет всех побочных эффектов осуществляются до выполнения следующего оператора. Самые распространенные операторы выражений — присваивания и вызовы функций.  Поскольку выражение является необязательным, только точка с запятой считается пустым оператором выражения, называемой оператором [null](../cpp/null-statement.md) .

## <a name="see-also"></a>См. также раздел

[Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)
