---
title: "Как: использование регулярных выражений для изменения порядка данных (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- regular expressions [C++], rearranging data
- data [C++], rearranging
ms.assetid: 5f91e777-9471-424e-ba75-dca3d1b49e42
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 62154cf33ba3705c89a5ad5a520b678e3f516498
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-regular-expressions-to-rearrange-data-ccli"></a>Практическое руководство. Использование регулярных выражений для изменения порядка данных (C++/CLI)
В следующем примере кода показано, как поддержка регулярных выражений .NET Framework можно использовать для изменения порядка или формата данных. Следующий пример кода использует <xref:System.Text.RegularExpressions.Regex> и <xref:System.Text.RegularExpressions.Match> классы для извлечения имени и фамилии из строки и отображения этих имен элементов в обратном порядке.  
  
 <xref:System.Text.RegularExpressions.Regex> Класс используется для создания регулярного выражения, описывающий текущий формат данных. Два имени считаются разделяемых запятыми и можно использовать любое количество пробелов вокруг запятой. <xref:System.Text.RegularExpressions.Match> Метод используется для анализа каждой строки. В случае успешного выполнения, имена и фамилии извлекаются из <xref:System.Text.RegularExpressions.Match> объекта и отображается.  
  
## <a name="example"></a>Пример  
  
```  
// regex_reorder.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ name =   
   {  
      "Abolrous, Sam",   
      "Berg,Matt",   
      "Berry , Jo",  
      "www.contoso.com"  
   };  
  
   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");  
  
   for ( int i=0; i < name->Length; i++ )  
   {  
      Console::Write( "{0,-20}", name[i] );  
      Match^ m = reg->Match( name[i] );  
      if ( m->Success )  
      {  
         String^ first = m->Groups["first"]->Value;  
         String^ last = m->Groups["last"]->Value;  
         Console::WriteLine("{0} {1}", first, last);  
      }  
      else  
         Console::WriteLine("(invalid)");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения в .NET Framework](/dotnet/standard/base-types/regular-expressions)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)