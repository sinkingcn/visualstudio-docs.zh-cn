---
title: IDebugProgramEngines2 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgramEngines2
helpviewer_keywords:
- IDebugProgramEngines2 interface
ms.assetid: 53d648f0-6c11-4337-badd-c43f3872b62c
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 90bcc838c230d317ed2261161c488be18a462bc0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51765995"
---
# <a name="idebugprogramengines2"></a>IDebugProgramEngines2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此接口由程序节点用于指定所有可能的调试引擎 (DE)，可以调试该程序。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProgramEngines2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 DE 或自定义端口提供程序实现此接口上实现的相同对象[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)以支持建立特定部署要用于特定的程序。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)上`IDebugProgramNode2`接口，以获得此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugProgramEngines2`。  
  
|方法|描述|  
|------------|-----------------|  
|[EnumPossibleEngines](../../../extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines.md)|指示可以调试该程序的所有可能的 DEs。|  
|[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)|选择要用于调试此程序 DE。|  
  
## <a name="remarks"></a>备注  
 一旦用户选择部署后，选择是否已注册程序节点通过调用[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)。 所选的引擎将成为由返回的引擎[GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)

