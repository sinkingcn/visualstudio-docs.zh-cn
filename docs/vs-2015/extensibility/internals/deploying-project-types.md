---
title: 部署项目类型 |Microsoft Docs
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
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0a1da27c22f2675042ecd03ffe092c209eaa1bbc
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51729748"
---
# <a name="deploying-project-types"></a>部署项目类型
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] 安装新的项目类型聚合器 (ProjectAggregator2.dll) 以及重新分发 (ProjectAggregator2.msi) 是 Windows 安装程序包。 托管代码项目类型必须使用新的聚合器。 ProjectAggregator2 办法限制适用于[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]项目导致无法正常工作的托管代码项目类型的聚合器。 以下步骤介绍如何更改你的 VSPackage 使用新的聚合器。  
  
1.  从解决方案中删除 NativeHierarchyWrapper 项目。  
  
2.  从您的安装程序中删除任何 NativeHierarchyWrapper 二进制文件。  
  
3.  将 ProjectAggregator2.msi 添加到你的设置。

