---
title: "Триграфы | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ??) trigraph
- ??- trigraph
- question mark, in trigraphs
- ??= trigraph
- ?? trigraph
- ??< trigraph
- ??/ trigraph
- trigraphs
- '? symbol, trigraph'
- ??> trigraph
- ??! trigraph
- ??' trigraph
ms.assetid: 617f76ec-b8e8-4cfe-916c-4bc32cbd9aeb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a480a38411536266c8cd4c23f8b29190550d3444
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="trigraphs"></a>Триграфы
Кодировка исходного кода исходных программ на языке C содержится в 7-разрядной кодировке ASCII, но в то же время является надмножеством инвариантной кодировки ISO 646-1983. Последовательности триграфа позволяют писать программы на языке C с использованием только инвариантной кодировки, соответствующей стандартам ISO. Триграфы — это последовательности из трех символов (которым предшествует два вопросительных знака), которые компилятор заменяет соответствующими знаками пунктуации. Триграфы можно использовать в файлах исходного кода на языке C с набором символов, который не содержит удобных графических представлений некоторых знаков пунктуации.  
  
 C++17 удаляет триграфы из языка. Поддержка триграфов может сохраняться при определяемом реализацией сопоставлении физического исходного файла с *основной кодировкой исходного кода*, хотя обычно это не рекомендуется. C++14 обеспечивает такую же поддержку триграфов как в языке C.  
  
 Visual C++ по-прежнему поддерживает подстановку триграфов, но по умолчанию она отключена. Сведения о том, как включить подстановку триграфов, см. в разделе [/Zc: trigraphs (подстановка триграфов)](../build/reference/zc-trigraphs-trigraphs-substitution.md).  
  
 В следующей таблице показаны девять последовательностей триграфов. Все вхождения знаков препинания в первом столбце файла исходного кода заменяются соответствующим символом во втором столбце.  
  
### <a name="trigraph-sequences"></a>Последовательности триграфов  
  
|Триграф|Знак препинания|  
|--------------|---------------------------|  
|??=|#|  
|??(|[|  
|??/|\|  
|??)|]|  
|??'|^|  
|??\<|{|  
|??!|&#124;|  
|??>|}|  
|??-|~|  
  
 Триграф всегда отображается как один символ исходного кода. Преобразование триграфов происходит на первом [этапе перевода](../preprocessor/phases-of-translation.md) перед распознаванием escape-символов в строковых литералах и символьных константах. Распознаются только девять триграфов, отображаемых в таблице выше. Все другие последовательности символов остаются непреобразованными.  
  
 Последовательность escape-символов, **\\\?**, не позволяет неверно интерпретировать символьные последовательности, напоминающие триграфы. (Сведения об escape-последовательностях см. в разделе [Escape-последовательности](../c-language/escape-sequences.md).) Например, при попытке напечатать строку `What??!` с данной инструкцией `printf`  
  
```  
printf( "What??!\n" );  
```  
  
 напечатанная строка имеет вид `What|`, так как `??!` — это триграфическая последовательность, которая заменяется символом `|`. Напишите инструкцию следующим образом, чтобы правильно напечатать строку:  
  
```  
printf( "What?\?!\n" );  
```  
  
 В этой инструкции `printf` escape-символ обратной косой черты перед вторым вопросительным знаком не позволяет неверно интерпретировать `??!` как триграф.  
  
## <a name="see-also"></a>См. также  
 [/Zc:trigraphs (подстановка триграфов)](../build/reference/zc-trigraphs-trigraphs-substitution.md)   
 [Идентификаторы C](../c-language/c-identifiers.md)