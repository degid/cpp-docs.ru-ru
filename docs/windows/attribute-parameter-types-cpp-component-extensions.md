---
title: "Типы параметров атрибутов (расширения компонентов C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "настраиваемые атрибуты, типы параметров"
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Типы параметров атрибутов (расширения компонентов C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Значения, передаваемые в атрибуты, должны быть известны компилятору во время компиляции.  Параметры атрибута могут быть следующих типов:  
  
-   `bool`  
  
-   `char`, `unsigned char`  
  
-   `short`, `unsigned short`  
  
-   `int`, `unsigned int`  
  
-   `long`, `unsigned long`  
  
-   `__int64`, `unsigned __int64`  
  
-   `float`, `double`  
  
-   `wchar_t`  
  
-   `char*` или `wchar_t*` или `System::String*`  
  
-   `System::Type ^`  
  
-   `System::Object ^`  
  
-   `enum`  
  
## Пример  
  
### Код  
  
```  
// attribute_parameter_types.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct AStruct {};  
  
[AttributeUsage(AttributeTargets::ReturnValue)]  
ref struct Attr : public Attribute {  
   Attr(AStruct ^ i){}  
   Attr(bool i){}  
   Attr(){}  
};  
  
ref struct MyStruct {  
   static AStruct ^ x = gcnew AStruct;  
   [returnvalue:Attr(x)] int Test() { return 0; }   // C3104  
   [returnvalue:Attr] int Test2() { return 0; }   // OK  
   [returnvalue:Attr(true)] int Test3() { return 0; }   // OK  
};  
```  
  
## Пример  
  
### Описание  
 При определении атрибутов все неименованные \(позиционные\) аргументы должны предшествовать всем именованным аргументам.  
  
### Код  
  
```  
// extending_metadata_c.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class)]  
ref class MyAttr : public Attribute {  
public:  
   MyAttr() {}  
   MyAttr(int i) {}  
   property int Priority;  
   property int Version;  
};  
  
[MyAttr]   
ref class ClassA {};   // No arguments  
  
[MyAttr(Priority = 1)]   
ref class ClassB {};   // Named argument  
  
[MyAttr(123)]   
ref class ClassC {};   // Positional argument  
  
[MyAttr(123, Version = 1)]   
ref class ClassD {};   // Positional and named  
```  
  
## Пример  
  
### Описание  
 Параметры атрибутов могут быть одномерными массивами предыдущих типов.  
  
### Код  
  
```  
// extending_metadata_d.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## См. также  
 [Пользовательские атрибуты](../windows/user-defined-attributes-cpp-component-extensions.md)