---
title: "Ошибка компилятора C3763 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3763
dev_langs: C++
helpviewer_keywords: C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 51810524b36a714404ce45a51186bc635dacebd3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3763"></a>Ошибка компилятора C3763
«Тип»: «retval» и «out» могут использоваться только в тип данных указателя  
  
 [Out](../../windows/out-cpp.md) или [retval](../../windows/retval.md) атрибуты могут появляться только в параметрах типа указателя. Удалите атрибут или использовать параметр типа указателя.  
  
 Следующий пример приводит к возникновению ошибки C3763:  
  
```  
// C3763.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atlcom.h>  
  
[ module(name=test) ];  
  
[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IF84 : IDispatch  
{  
   [id(0x00000002)]HRESULT m2([out]unsigned char);  
};  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]  
class CF84 : public IF84  
{   // C3763  
public:  
   HRESULT __stdcall m2(unsigned char i)  
   {  
      return S_OK;  
   }  
};  
  
int main()  
{  
}  
```