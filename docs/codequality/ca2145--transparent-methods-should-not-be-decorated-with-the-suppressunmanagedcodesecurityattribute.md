---
title: "CA2145: Transparent methods should not be decorated with the SuppressUnmanagedCodeSecurityAttribute"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CA2145"
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
caps.latest.revision: 11
ms.author: "douge"
manager: "douge"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# CA2145: Transparent methods should not be decorated with the SuppressUnmanagedCodeSecurityAttribute
|||  
|-|-|  
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|  
|CheckId|CA2145|  
|Category|Microsoft.Security|  
|Breaking Change|Breaking|  
  
## Cause  
 A transparent method, a method that is marked with the \<xref:System.Security.SecuritySafeCriticalAttribute> method, or a type that contains a method is marked with the \<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.  
  
## Rule Description  
 Methods decorated with the \<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute have an implicit LinkDemand placed upon any method that calls it. This LinkDemand requires that the calling code be security critical. Marking the method that uses SuppressUnmanagedCodeSecurity with the \<xref:System.Security.SecurityCriticalAttribute> attribute makes this requirement more obvious for callers of the method.  
  
## How to Fix Violations  
 To fix a violation of this rule, mark the method or type with the \<xref:System.Security.SecurityCriticalAttribute> attribute.  
  
## When to Suppress Warnings  
 Do not suppress a warning from this rule.  
  
### Code  
 [!code[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../codequality/codesnippet/CSharp/ca2145--transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute_1.cs)]  
  
### Comments