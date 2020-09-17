---
title: EXTERN (MASM)
ms.date: 12/06/2019
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 2674f358fe22f74c5272d90a0d8cbff234ddcd11
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440882"
---
# <a name="extern"></a>EXTERN

Определяет одну или несколько внешних переменных, меток или символов *с именем, типом которых* является *Type*.

## <a name="syntax"></a>Синтаксис

> **Extern** ⟦*Language — Type*⟧ *Name* ⟦ __(__ *АЛТИД* __)__ ⟧ __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* ⟦ __(__ *АЛТИД* __)__ ⟧ __:__ *Type* ... ⟧

## <a name="remarks"></a>Примечания

Аргумент *Language-Type* допустим только в 32-разрядном MASM.

*Тип* может быть [ABS](operator-abs.md), который импортирует *имя* как константу. То же, что и [екстрн](extrn.md).

## <a name="see-also"></a>См. также раздел

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
