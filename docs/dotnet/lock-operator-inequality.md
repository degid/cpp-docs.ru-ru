---
title: "Lock::operator! = | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- lock.operator!=
- msclr.lock.operator!=
- msclr::lock::operator!=
- lock::operator!=
dev_langs: C++
helpviewer_keywords: lock::operator!=
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 090d461a8f11d47d25119f5949f9f570093244fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="lockoperator"></a>lock::operator!=
Оператор неравенства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class T> bool operator!=(  
   T t  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `t`  
 Объект для сравнения на неравенство.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает `true` Если `t` , отличается от объекта блокировки `false` в противном случае.  
  
## <a name="example"></a>Пример  
  
```  
// msl_lock_op_ineq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   Object^ o2 = gcnew Object;  
   lock l1(o1);  
   if (l1 != o2) {  
      Console::WriteLine("Inequal!");  
   }  
}  
```  
  
```Output  
Inequal!  
```  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\lock.h >  
  
 **Пространство имен** msclr  
  
## <a name="see-also"></a>См. также  
 [Блокировка членов](../dotnet/lock-members.md)   
 [lock::operator==](../dotnet/lock-operator-equality.md)