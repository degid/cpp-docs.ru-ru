---
title: Предупреждение компилятора (уровень 1) C4715
ms.date: 11/04/2016
f1_keywords:
- C4715
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
ms.openlocfilehash: 7dba86d591f18fd7c9c562078204916000d47384
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175328"
---
# <a name="compiler-warning-level-1-c4715"></a>Предупреждение компилятора (уровень 1) C4715

"функция": не все пути управления возвращают значение

Указанная функция потенциально может не возвращать значение.

## <a name="example"></a>Пример

```cpp
// C4715a.cpp
// compile with: /W1 /LD
int func1( int i )
{
   if( i )
   return 3;  // C4715 warning, nothing returned if i == 0
}
```

Чтобы предотвратить это предупреждение, измените код так, чтобы все пути применялись к возвращаемому значению функции:

```cpp
// C4715b.cpp
// compile with: /LD
int func1( int i )
{
   if( i ) return 3;
   else return 0;     // OK, always returns a value
}
```

Возможно, ваш код содержит вызов функции, которая никогда не возвращает значение, как показано в следующем примере:

```cpp
// C4715c.cpp
// compile with: /W1 /LD
void fatal()
{
}
int glue()
{
   if(0)
      return 1;
   else if(0)
      return 0;
   else
      fatal();   // C4715
}
```

Этот код также создает предупреждение, так как компилятор не знает, что `fatal` никогда не возвращает. Чтобы этот код не создавал сообщение об ошибке, объявите `fatal` с помощью [__declspec (noreturn)](../../cpp/noreturn.md).
