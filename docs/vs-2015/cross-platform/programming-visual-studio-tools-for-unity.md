---
title: Visual Studio Tools for Unity 编程 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- tgt-pltfrm-cross-plat
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5758cb0-e73b-45f5-8cae-c0eb40491026
caps.latest.revision: 5
author: conceptdev
ms.author: crdun
manager: ghogen
ms.openlocfilehash: baeb860d5d5c739f7f194b780e71bc9d3768edec
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51771719"
---
# <a name="programming-visual-studio-tools-for-unity"></a>Visual Studio Tools for Unity 编程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
本部分将介绍使用 Visual Studio Tools for Unity API 的示例。  
  
## <a name="examples"></a>示例  
 下面是一些演示 Visual Studio Tools for Unity ApI 使用方法的示例。  
  
### <a name="customize-project-files-created-by-vstu"></a>自定义 VSTU 创建的项目文件  
 Visual Studio Tools for Unity 在项目文件生成期间提供 Unity 风格的回调。 若要了解每当项目文件重新生成时如何对其进行修改，请参阅[示例：项目文件生成](../cross-platform/customize-project-files-created-by-vstu.md)。  
  
### <a name="share-the-unity-log-callback-with-vstu"></a>与 VSTU 共享 Unity 日志回调  
 Visual Studio Tools for Unity 对 Unity 注册了一个日志回调，能够将其控制台流式传输到 Visual Studio。 如果编辑器脚本也对 Unity 注册了一个日志回调，则 VSTU 回调可能会妨碍此回调。 若要了解如何与 VSTU 共享 Unity 日志回叫，请参阅[示例：日志回叫](../cross-platform/share-the-unity-log-callback-with-vstu.md)。

