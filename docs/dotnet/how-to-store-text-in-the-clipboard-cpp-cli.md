---
title: "Как: хранение текста в буфер обмена (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- text, storing in Clipboard
- Clipboard, storing text
ms.assetid: 9996023f-b700-47ad-8ad9-1ba201eaa5a6
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 971d87da7045e079e62d2ab3274ddc35ddbffaea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-store-text-in-the-clipboard-ccli"></a>Практическое руководство. Хранение текста в буфере обмена (C++/CLI)
Следующий пример кода использует <xref:System.Windows.Forms.Clipboard> объект, определенный в <xref:System.Windows.Forms> пространство имен для хранения строки. Этот объект предоставляет две функции-члена: <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> и <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>. Данные хранятся в буфере обмена посредством отправки любого объекта, производного от <xref:System.Object> для <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>.  
  
## <a name="example"></a>Пример  
  
```  
// store_clipboard.cpp  
// compile with: /clr  
#using <System.dll>  
#using <System.Drawing.dll>  
#using <System.Windows.Forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main()  
{  
   String^ str = "This text is copied into the Clipboard.";  
  
   // Use 'true' as the second argument if  
   // the data is to remain in the clipboard  
   // after the program terminates.  
   Clipboard::SetDataObject(str, true);  
  
   Console::WriteLine("Added text to the Clipboard.");  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Как: извлечение текста из буфера обмена (C + +/ CLI)](../dotnet/how-to-retrieve-text-from-the-clipboard-cpp-cli.md)   
 [Операции Windows (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)