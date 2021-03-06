---
title: API 参考 （Visual Studio 调试） |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], API reference
ms.assetid: e4e429da-3667-41f7-9158-a8207d13e91a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 97d5aa6fc92457557493005389d129993d38e099
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49839435"
---
# <a name="api-reference-visual-studio-debugging"></a>API 引用（Visual Studio 调试）
参考部分包含的 API，一个指南，其中显示了语法和用法的所有 API 元素，概念性概述和具有多种类型的代码示例。 按以下类别按字母顺序排列的所有引用。  
  
 下表显示了常见`HRESULT`方法返回的值。  
  
|name|描述|“值”|  
|----------|-----------------|-----------|  
|S_OK|成功。|0x00000000|  
|E_UNEXPECTED|意外的失败。|0x8000FFFF|  
|E_NOTIMPL|未实现。|0x80004001|  
|E_OUTOFMEMORY|内存不足，无法完成操作。|已用完 0x8007000E|  
|E_INVALIDARG|一个或多个参数均无效。|0x80070057|  
|E_NOINTERFACE|支持任何此类接口。|0x80004002|  
|E_POINTER|无效的指针。|0x80004003|  
|E_HANDLE|无效句柄。|0x80070006|  
|E_ABORT|操作已中止。|0x80004004|  
|E_FAIL|意外的失败。|0x80004005|  
|E_ACCESSDENIED|常规拒绝访问错误。|0x80070005|  
  
> [!NOTE]
>  当[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]调试方法返回`S_OK`，假定参数指针是否有效解决所有问题、 out 参数的指针上执行任何验证，即时`S_OK`返回。  
> 
> [!NOTE]
>  无效或`NULL`[out] 参数可能会导致 IDE 崩溃。  
  
## <a name="see-also"></a>请参阅  
 [接口](../../../extensibility/debugger/reference/interfaces-visual-studio-debugging.md)   
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [用于调试的 SDK 帮助程序](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Visual Studio 调试器可扩展性](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)