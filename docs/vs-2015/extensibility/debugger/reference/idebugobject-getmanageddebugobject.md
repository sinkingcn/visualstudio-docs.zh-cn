---
title: IDebugObject::GetManagedDebugObject |Microsoft Docs
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
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5530865b9d6c7cfb74c91f00b6a65e41702135cb
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807265"
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

调试引擎的地址空间中创建托管对象的副本。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetManagedDebugObject(   
   IDebugManagedObject** ppObject  
);  
```  
  
```csharp  
int GetManagedDebugObject(  
   out IDebugManagedObject ppObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppObject`  
 [out]返回[IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)对象，表示新创建的托管的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。 如果此返回 E_FAIL [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)不表示托管的值类实例。  
  
## <a name="remarks"></a>备注  
 这[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象必须代表托管的值类实例，如`System.Decimal`实例。 通过让本地副本，而调用的开销[Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)被消除。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)

