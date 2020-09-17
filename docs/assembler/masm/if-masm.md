---
title: IF (MASM)
ms.date: 12/17/2019
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 6e63f5c8075b3c94370ad8863d224c097cf0ecdf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440747"
---
# <a name="if"></a>IF

Предоставляет сборку *ифстатементс* , если *expression1* имеет значение true (отличное от нуля) или *елсеифстатементс* , если *expression1* имеет значение false (0), а *Expression2* имеет значение true.

## <a name="syntax"></a>Синтаксис

> **Если** *expression1*\
> *If-операторы*\
> ⟦**ELSEIF**\ *выражение2*
> *ElseIf-операторы*⟧ \
> ⟦**ELSE**\
> *else-Операторы*⟧ \
> **ENDIF**

## <a name="remarks"></a>Примечания

Следующие директивы могут быть заменены на [ElseIf](elseif-masm.md): **елсеифб**, **елсеифдеф**, **елсеифдиф**, **елсеифдифи**, **ELSEIF**, **елсеифидн**, **елсеифидни**, **елсеифнб**и **елсеифндеф**. При необходимости собирает *else-Операторы* , если предыдущее выражение имеет значение false. Обратите внимание, что выражения оцениваются во время сборки.

## <a name="see-also"></a>См. также раздел

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
