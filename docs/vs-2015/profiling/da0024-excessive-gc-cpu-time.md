---
title: DA0024：GC 占用的 CPU 时间过多 | Microsoft Docs
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
- vs.performance.DA0024
- vs.performance.24
- vs.performance.rules.DA0024
ms.assetid: 228872da-77d0-4da5-b455-ac57fb1867c9
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 910f66a31f959fe15cc7165eda4e531e7965e670
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51754262"
---
# <a name="da0024-excessive-gc-cpu-time"></a>DA0024：垃圾回收占用的 CPU 时间过多
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

规则 Id |DA0024 |  
|类别 |。NET Framework 使用情况 |  
|分析方法 |所有 |  
|消息 | %Time in GC 是非常高。 没有过多的垃圾回收的系统开销。 |  
|规则类型 |警告 |  
  
 使用采样法、.NET 内存或资源争用方法进行分析时，必须收集至少 10 个样本才能触发此规则。  
  
## <a name="cause"></a>原因  
 分析期间收集的系统性能数据表明垃圾回收所用的时间明显超过总的应用程序处理时间。  
  
## <a name="rule-description"></a>规则说明  
 Microsoft .NET 公共语言运行时 (CLR) 提供自动内存管理机制，该机制使用垃圾回收器从应用程序不再使用的对象回收内存。 垃圾回收器是面向生成的，基于大量分配为短期分配的假设。 例如，局部变量应是短期的。 新创建的对象在 0 代中启动，如果在垃圾回收后它们仍然存在，则将提升到 1 代，如果应用程序仍使用它们，则最后将过渡到 2 代。  
  
 收集 0 代中的对象时，通常频率和效率都较高。 收集 1 代中的对象时，通常频率和效率都较低。 最后，应以更低的频率收集 2 代中生存期较长的对象。 2 代回收是完整的垃圾回收运行，也是成本最高的操作。  
  
 如果垃圾回收所用的时间明显超过应用程序处理总时间，则将触发此规则。  
  
> [!NOTE]
>  垃圾回收所用时间的比例较高但未超过应用程序处理总时间时，不会触发此规则，而会触发 [DA0023：垃圾回收占用的 CPU 时间很多](../profiling/da0023-high-gc-cpu-time.md)警告。  
  
## <a name="how-to-investigate-a-warning"></a>如何调查警告  
 双击“错误列表”窗口中的消息，导航到分析数据的[标记视图](../profiling/marks-view.md)。 查找 **.NET CLR Memory\\% Time in GC** 列。 确定程序执行中是否存在托管内存垃圾回收的开销高于其他阶段的某个阶段。 将 %Time in GC 的值与**第 0 代回收 #****第 1 代回收 #**、 **第 2 代回收 #** 值中报告的垃圾回收速率进行比较。  
  
 %Time in GC 值尝试报告应用程序执行垃圾回收处理所用的时间总量（与处理总量成正比）。 请注意，有时 % Time in GC 值可能报告非常高的值，但这不是由垃圾回收过多引起的。 有关计算 % Time in GC 值的方法的详细信息，请参阅 MSDN 上 **Maoni 博客**的 [Difference Between Perf Data Reported by Different Tools – 4](http://go.microsoft.com/fwlink/?LinkId=177863)（不同工具所报告的性能数据间的差异 – 4）。 如果垃圾回收期间发生页面故障或计算机上其他操作的优先级高于此应用程序，则 %Time in GC 计数器将反映这些额外的延迟。



