---
title: IDebugDocumentProvider 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentProvider interface
ms.assetid: 36510acf-1ef9-479c-a430-d3f09502f82c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d775deb153205d0e9a452775272285c67e74a210
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49949859"
---
# <a name="idebugdocumentprovider-interface"></a>IDebugDocumentProvider 接口
提供按需实例化文档的方法。  
  
## <a name="remarks"></a>备注  
 这间接实例化文档意味着：  
  
- 允许要在需要时加载的文档。  
  
- 允许要包含在调试器 IDE 的文档对象。  
  
- 允许通过多种方式来访问相同的文档对象。  
  
  这有效地将文档从其提供程序分隔开来，并允许提供程序来执行其他运行时上下文信息。  
  
  除了继承的方法之外`IDebugDocumentInfo`，则`IDebugDocumentProvider`接口公开以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugDocumentProvider::GetDocument](../../winscript/reference/idebugdocumentprovider-getdocument.md)|导致要进行实例化，如果尚不存在的文档。|