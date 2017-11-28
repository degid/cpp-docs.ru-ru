---
title: "Бинарные операторы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6a76b9505d11f17848232c69650c8e523bad91c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="binary-operators"></a>Бинарные операторы
В следующей таблице приведен список операторов, которые можно перегрузить.  
  
### <a name="redefinable-binary-operators"></a>Переопределяемые бинарные операторы  
  
|Оператор|Имя|  
|--------------|----------|  
|**,**|Comma|  
|`!=`|Неравенство|  
|`%`|Модуль|  
|`%=`|Модуль/назначение|  
|**&**|Побитовое И|  
|**&&**|Логическое И|  
|**&=**|Побитовое И/назначение|  
|**\***|Умножение|  
|**\*=**|Умножение/назначение|  
|**+**|Сложение|  
|`+=`|Сложение/назначение|  
|**-**|Вычитание|  
|**-=**|Вычитание/назначение|  
|**->**|Выбор члена|  
|**->\***|Выбор указателя на член|  
|**/**|Деление|  
|`/=`|Деление/назначение|  
|**<**|Меньше|  
|**<<**|Сдвиг влево|  
|**<<=**|Сдвиг влево/назначение|  
|**<=**|Меньше или равно|  
|**=**|Назначение|  
|`==`|Равенство|  
|**>**|Больше|  
|**>=**|Больше или равно|  
|**>>**|Сдвиг вправо|  
|**>>=**|Сдвиг вправо/назначение|  
|**^**|Исключающее ИЛИ|  
|`^=`|Исключающее ИЛИ/назначение|  
|**&#124;**|Побитовое включающее ИЛИ|  
|`&#124;=`|Побитовое включающее ИЛИ/назначение|  
|`&#124;&#124;`|Логическое ИЛИ|  
  
 Чтобы объявить функцию бинарного оператора как нестатический член, необходимо объявить ее в виде  
  
 *RET-type* **оператор**`op`**(** `arg` **)**  
  
 где *ret-type* является тип возвращаемого `op` — один из операторов, перечисленных в предыдущей таблице, и `arg` — аргумент любого типа.  
  
 Чтобы объявить функцию бинарного оператора как глобальную функцию, необходимо объявить ее в виде  
  
 *RET-type* **оператор**`op`**(** `arg1` **,** `arg2` **)**  
  
 где *ret-type* и `op` соответствуют описанию для функций-членов операторов и `arg1` и `arg2` являются аргументами. Хотя бы один из аргументов должен принадлежать типу класса.  
  
> [!NOTE]
>  Ограничений на типы возвращаемого значения бинарных операторов нет, однако большинство пользовательских бинарных операторов возвращает тип класса или ссылку на тип класса.  
  
## <a name="see-also"></a>См. также  
 [Перегрузка операторов](../cpp/operator-overloading.md)