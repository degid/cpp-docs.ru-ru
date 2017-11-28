---
title: "Вычитание (-) | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d07f6bf2c5d48b3149eb43448e217d1a66b92c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="subtraction--"></a>Вычитание (-)
Оператор вычитания (**-**) вычитает второй операнд из первого. Оба операнда могут быть целочисленными типами или типами с плавающей запятой либо один операнд может быть указателем, а второй — целым числом.  
  
 При вычитании двух указателей разница преобразуется в целочисленное значение со знаком путем деления разницы на размер значения типа, к которому обращаются указатели. Размер целочисленного значения определяется типом **ptrdiff_t** в стандартном включаемом файле STDDEF.H. Результат представляет собой число позиций памяти данного типа, расположенных между двумя адресами. Результат гарантировано имеет значение только для двух элементов одного массива, как описано в разделе [Арифметические операции с указателями](../c-language/pointer-arithmetic.md).  
  
 Если целочисленное значение вычитается из значения указателя, оператор вычитания преобразует целочисленное значение (*i*) путем его умножения на размер значения, к которому обращается указатель. После преобразования значение целого числа представляет позиции памяти *i*, где каждая позиция имеет длину, заданную типом указателя. Если преобразованное целочисленное значение вычесть из значения указателя, будут получены позиции *i* адреса памяти, расположенные до исходного адреса. Новый указатель указывает на значение типа, к которому обращается исходное значение указателя.  
  
## <a name="see-also"></a>См. также  
 [Аддитивные операторы в C](../c-language/c-additive-operators.md)