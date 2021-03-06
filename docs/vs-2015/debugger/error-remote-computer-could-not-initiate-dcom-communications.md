---
title: 错误： 远程计算机无法启动 DCOM 通信 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.unmarshal_callback_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: bbba0766-2502-4ef1-a75d-bf1f0db39e37
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c86e5a193348a8f90e4888e0df3472d102beb08
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51800869"
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>错误：远程计算机未能启动 DCOM 通信
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

当远程计算机尝试与本地计算机通信时，发生 DCOM 错误。 本地计算机是  
  
 运行 Visual Studio 的计算机。 出现此错误的原因可能有多种：  
  
-   本地计算机启用了防火墙。  
  
-   从远程计算机到本地计算机的 Windows 身份验证不起作用。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  如果在本地计算机已启用 Windows 防火墙，请参阅[设置 Up the Remote Tools 在设备上](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)有关如何配置防火墙以便进行本地调试的说明。  
  
2.  通过尝试从远程服务器打开本地计算机上的文件共享来测试 Windows 身份验证。  
  
3.  若要还原 Windows 身份验证，请尝试重新启动本地计算机和远程计算机。 检查本地和远程计算机上的事件日志以找出 Kerberos 错误，并与域管理员联系以了解已知问题。  
  
## <a name="see-also"></a>请参阅  
 [在设备上安装远程工具](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)



