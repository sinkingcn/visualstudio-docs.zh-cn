---
title: GetTaskSchedulersForDebugger 方法 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f748eae50ab810477cb625eac4373903236fec82
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51749608"
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger 方法
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索的所有数组<xref:System.Threading.Tasks.TaskScheduler>当前处于活动状态的对象。  
  
 **Namespace**：<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （在 mscorlib.dll 中)  
  
 无法从.NET Framework 来访问此内部成员，因为以下语法提供通用中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## <a name="return-value"></a>返回值  
 所有的数组<xref:System.Threading.Tasks.TaskScheduler>在此当前处于活动状态的对象<xref:System.AppDomain>。  
  
## <a name="remarks"></a>备注  
 此方法不是线程安全，因此不应与其他实例同时<xref:System.Threading.Tasks.TaskScheduler>。 它时，应调用从调试器仅在调试器已挂起的所有其他线程。  
  
## <a name="see-also"></a>请参阅  
 [TaskScheduler 类](../../extensibility/debugger/taskscheduler-class-internal-members.md)

