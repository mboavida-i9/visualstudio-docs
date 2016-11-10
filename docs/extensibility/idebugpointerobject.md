---
title: "IDebugPointerObject"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "IDebugPointerObject"
helpviewer_keywords: 
  - "IDebugPointerObject interface"
ms.assetid: 257fa167-b46e-4ffb-9a12-272efbf26702
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
translation.priority.mt: 
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
# IDebugPointerObject
> [!IMPORTANT]
>  In Visual Studio 2015, this way of implementing expression evaluators is deprecated. For information about implementing CLR expression evaluators, please see [CLR Expression Evaluators](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) and [Managed Expression Evaluator Sample](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 This interface represents a pointer object.  
  
## Syntax  
  
```  
IDebugPointerObject : IDebugObject  
```  
  
## Notes for Implementers  
 The expression evaluator implements this interface to represent a pointer object.  
  
## Notes for Callers  
 The [IDebugObject](../extensibility/idebugobject.md) interface can obtain this interface by using [QueryInterface](../Topic/QueryInterface.md) if the `IDebugObject` represents a pointer.  
  
## Methods in Vtable Order  
 In addition to the methods inherited from [IDebugObject](../extensibility/idebugobject.md), the `IDebugPointerObject` interface exposes the following methods.  
  
|Method|Description|  
|------------|-----------------|  
|[Dereference](../extensibility/idebugpointerobject--dereference.md)|Gets the object to which the interface points.|  
|[GetBytes](../extensibility/idebugpointerobject--getbytes.md)|Gets the value to which the interface points as a series of consecutive bytes.|  
|[SetBytes](../extensibility/idebugpointerobject--setbytes.md)|Sets the value to which the interface points from a series of consecutive bytes.|  
  
## Remarks  
 An expression evaluator uses this interface to represent a pointer in a parse tree.  
  
## Requirements  
 Header: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## See Also  
 [Expression Evaluation Interfaces](../extensibility/expression-evaluation-interfaces.md)   
 [IDebugObject](../extensibility/idebugobject.md)