---
title: "Compiler Error CS0075"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0075"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0075"
ms.assetid: 5084d260-705e-4ff5-8f7a-7f74052fcbbb
caps.latest.revision: 7
ms.author: "billchi"
manager: "douge"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Compiler Error CS0075
To cast a negative value, you must enclose the value in parentheses  
  
 If you are casting using a keyword that identifies a predefined type, then you do not need parentheses. Otherwise, you must put the parentheses because (x) –y will not be considered a cast expression. From the C# Specification, Section 7.6.6:  
  
 *From the disambiguation rule it follows that, if x and y are identifiers, (x)y, (x)(y), and (x)(-y) are cast-expressions, but (x)-y is not, even if x identifies a type. However, if x is a keyword that identifies a predefined type (such as int), then all four forms are cast-expressions (because such a keyword could not possibly be an expression by itself).*  
  
 The following code generates CS0075:  
  
```  
// CS0075  
namespace MyNamespace  
{  
    enum MyEnum { }  
    public class MyClass  
    {  
        public static void Main()  
        {  
            // To fix the error, place the negative  
            // values below in parentheses  
            int i = (System.Int32) - 4; //CS0075  
            MyEnum e = (MyEnum) - 1;    //CS0075  
            System.Console.WriteLine(i); //to avoid warning  
            System.Console.WriteLine(e); //to avoid warning  
        }  
    }  
}  
```  
  
## See Also  
 [Casting and Type Conversions](../Topic/Casting%20and%20Type%20Conversions%20\(C%23%20Programming%20Guide\).md)