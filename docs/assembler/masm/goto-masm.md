---
title: GOTO (MASM)
ms.date: 12/16/2019
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: 18f286d8634202b57dea788aa6984755a5afb197
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440795"
---
# <a name="goto"></a>GOTO

Передает сборку в строку, помеченную **:** _макролабел_.

## <a name="syntax"></a>Синтаксис

> **Goto** *макролабел*

## <a name="remarks"></a>Примечания

**Оператор goto** разрешен только внутри [макросов](macro.md), [для](for-masm.md), [Форк](forc.md), [Repeat](repeat.md)и [while](while-masm.md) . Целевой объект *макролабел* должен быть единственной директивой в строке и должен предшествовать начальному двоеточию.

## <a name="see-also"></a>См. также раздел

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
