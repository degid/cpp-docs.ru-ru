---
title: "Оператор static_cast | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: static_cast_cpp
dev_langs: C++
helpviewer_keywords: static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d04c49076f5189e913c8755a5bce4d7e5c7daf11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="staticcast-operator"></a>Оператор static_cast
Преобразует *выражение* типу *идентификатор типа* на основе только типы, которые присутствуют в выражении.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static_cast <type-id> ( expression )   
```  
  
## <a name="remarks"></a>Примечания  
 В стандартном языке C++, проверка типа во время выполнения не выполняется, что обеспечивает безопасность преобразования. В C ++/CX выполняются проверки во время компиляции и во время выполнения. Дополнительные сведения см. в разделе [приведение](casting.md).  
  
 Оператор `static_cast` можно использовать для таких операций, как преобразование указателя на базовый класс в указатель на производный класс. Такие преобразования не всегда являются безопасными.  
  
 Обычно `static_cast` используется, когда требуется преобразовать числовые типы данных, например перечисления в целые числа или целые числа в числа с плавающей запятой, и при полной уверенности в том, какие типы данных используются в преобразовании. Преобразования `static_cast` не так безопасны, как преобразования `dynamic_cast`, поскольку `static_cast` не выполняет проверку типа во время выполнения, а `dynamic_cast` выполняет. Применение `dynamic_cast` к неоднозначному указателю завершится ошибкой, тогда как `static_cast` возвращает результат, как будто бы все в порядке; это может быть опасно. Хотя преобразования `dynamic_cast` более безопасны, `dynamic_cast` работает только с указателями или ссылками, а проверка типа во время выполнения является дополнительной нагрузкой. Дополнительные сведения см. в разделе [оператор dynamic_cast](../cpp/dynamic-cast-operator.md).  
  
 В следующем примере строка `D* pd2 = static_cast<D*>(pb);` небезопасна, поскольку `D` может иметь поля и методы, не входящие в `B`. Однако строка `B* pb2 = static_cast<B*>(pd);` является безопасным преобразованием, поскольку `D` всегда содержит все `B`.  
  
```  
// static_cast_Operator.cpp  
// compile with: /LD  
class B {};  
  
class D : public B {};  
  
void f(B* pb, D* pd) {  
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields  
                                   // and methods that are not in B.  
  
   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always  
                                   // contains all of B.  
}  
```  
  
 В отличие от к [dynamic_cast](../cpp/dynamic-cast-operator.md), проверка во время выполнения не проводится на `static_cast` преобразование `pb`. Объект, на который указывает `pb`, может не быть объектом типа `D`, и в этом случае использование `*pd2` может привести ужасным последствиям. Например, вызов функции, являющейся членом класса `D`, но не класса `B`, может привести к нарушению прав доступа.  
  
 Операторы `dynamic_cast` и `static_cast` перемещают указатель по всей иерархии классов. Однако `static_cast` основывается только на сведениях, предоставленных в операторе приведения и поэтому может быть небезопасно. Например:  
  
```  
// static_cast_Operator_2.cpp  
// compile with: /LD /GR  
class B {  
public:  
   virtual void Test(){}  
};  
class D : public B {};  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  
   D* pd2 = static_cast<D*>(pb);  
}  
```  
  
 Если `pb` действительно указывает на объект типа `D`, `pd1` и `pd2` получат одно и то же значение. Также они получат одно и то же значение, если `pb == 0`.  
  
 Если `pb` указывает на объект типа `B`, а не на полный класс `D`, у `dynamic_cast` будет достаточно информации, чтобы вернуть ноль. Однако `static_cast` основывается на утверждении программиста, что `pb` указывает на объект типа `D` и просто возвращает указатель на этот предполагаемый объект `D`.  
  
 Соответственно, `static_cast` может выполнить операции, обратные неявным преобразованиям, и в таком случае результаты не будут определены. Необходимость убедиться в том, что результаты преобразования `static_cast` безопасны, возлагается на программиста.  
  
 Это поведение также применяется к типам, отличным от типов класса. Например, `static_cast` можно использовать для преобразования из int в `char`. Однако полученный `char` может иметь недостаточно бит для хранения всего значения `int`. Еще раз, он остается программисту, чтобы убедиться, что результаты `static_cast` преобразования являются безопасными.  
  
 Оператор `static_cast` также можно использовать для выполнения любого неявного преобразования, включая стандартные преобразования и определенные пользователем преобразования. Например:  
  
```  
// static_cast_Operator_3.cpp  
// compile with: /LD /GR  
typedef unsigned char BYTE;  
  
void f() {  
   char ch;  
   int i = 65;  
   float f = 2.5;  
   double dbl;  
  
   ch = static_cast<char>(i);   // int to char  
   dbl = static_cast<double>(f);   // float to double  
   i = static_cast<BYTE>(ch);  
}  
```  
  
 Оператор `static_cast` может явным образом преобразовывать целое значение в тип перечисления. Если значение типа целого не оказывается в диапазоне значений перечисления, получаемое значение перечисления не определено.  
  
 Оператор `static_cast` преобразует значение пустого указателя в значение пустого указателя конечного типа.  
  
 Любое выражение можно явно преобразовать или в тип void с помощью оператора `static_cast`. Тип назначения void может дополнительно включать в себя атрибут `const`, `volatile` или `__unaligned`.  
  
 Оператор `static_cast` не может удалять атрибуты `const`, `volatile` и `__unaligned`. В разделе [оператор const_cast](../cpp/const-cast-operator.md) сведения об удалении этих атрибутов.  
  
 Из-за опасности выполнения непроверенных приведений в дополнение к перемещению сборщика мусора использовать `static_cast` необходимо только в критическом для производительности коде при наличии уверенности, что его работа будет верной. Если необходимо использовать `static_cast` в режиме выпуска, заменить его с [safe_cast](../windows/safe-cast-cpp-component-extensions.md) в отладочных построениях обеспечить успешный.  
  
## <a name="see-also"></a>См. также  
 [Операторы приведения](../cpp/casting-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)