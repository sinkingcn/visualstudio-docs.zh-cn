---
title: 内存选项卡上，进程属性对话框 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: a70785f2-5997-40ec-a90f-80a52449768b
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 92718a20f5deb19890a58d68af85e7f897f2440a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51785139"
---
# <a name="memory-tab-process-properties-dialog-box"></a>“进程属性”对话框 ->“内存”选项卡
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用**内存**选项卡以显示进程使用内存的方式。 若要显示[进程属性对话框](../debugger/process-properties-dialog-box.md)，将焦点移至[进程视图](../debugger/processes-view.md)窗口。 在树中，选择任何进程节点，然后选择**属性**从**视图**菜单。  
  
 以下设置位于**内存**选项卡：  
  
|条目|描述|  
|-----------|-----------------|  
|**虚拟字节数**|进程正在使用的虚拟地址空间的当前大小 （以字节为单位）。 使用虚拟地址空间不一定意味着使用相应的磁盘或主内存页。 但是，虚拟空间是有限的并且使用过多可能会限制进程加载库的能力。|  
|**峰值虚拟字节数**|在任何一个时间使用的最大虚拟地址空间在过程的字节数。|  
|**工作集**|最近使用过的进程中线程的内存页的集合。 如果计算机中的可用内存高于阈值，页会保留在进程的工作集中，即使它们不是在使用中。 如果可用内存降到阈值以下，将从工作集中削减页。 如果需要它们将软恢复到工作集中在离开主内存之前。|  
|**峰值工作集**|在任何时间点此进程的工作集最大页数。|  
|**分页的池字节数**|当前页面缓冲池进程已分配的量。 分页的池是一个操作系统组件以它们完成指定的任务中，获取空间的系统内存区域。 页面缓冲的池页可以换出到分页文件时不访问持续时间内的系统。|  
|**非分页的池字节数**|当前在非分页池的进程分配的字节数。 非分页的池是其中空间是由操作系统组件在完成获取指定的任务的系统内存区域。 非分页缓冲的池页不能将调出到分页文件中;它们保留在主内存中，只要它们分配。|  
|**专用字节数**|当前此进程已分配的字节数不能与其他进程共享。|  
|**可用字节**|此进程的总未使用的虚拟地址空间。|  
|**保留的字节**|此过程保留供将来使用的虚拟内存的总量。|  
|**可用图像字节**|未使用或保留的进程中的图像的虚拟地址空间量。|  
|**保留的图像字节**|保留通过此进程中运行的映像的所有虚拟内存的总和。|



