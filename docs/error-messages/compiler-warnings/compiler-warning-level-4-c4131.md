---
title: Предупреждение компилятора (уровень 4) C4131
ms.date: 11/04/2016
f1_keywords:
- C4131
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
ms.openlocfilehash: 995891cc3b8391e09aea21751354abb189d7c8dd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198449"
---
# <a name="compiler-warning-level-4-c4131"></a>Предупреждение компилятора (уровень 4) C4131

"функция": используется декларатор старого стиля

Указанное объявление функции имеет отличную от прототипа форму.

Использующие старый стиль объявления функций следует преобразовать в форму прототипа.

В следующем примере показан старый стиль объявления функции:

```c
// C4131.c
// compile with: /W4 /c
void addrec( name, id ) // C4131 expected
char *name;
int id;
{ }
```

В следующем примере показана форма прототипа:

```c
void addrec( char *name, int id )
{ }
```
