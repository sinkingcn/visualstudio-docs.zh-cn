---
title: 如何：从 XML 架构资源管理器向工作区添加节点
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 3b5a5749-9693-4b29-b0c2-8e07e0e55514
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e1f5821d3a4207d89eb62b9344cff967c73b536
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752048"
---
# <a name="how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer"></a>如何： 从 XML 架构资源管理器将节点添加到工作区

本主题说明如何将节点添加到[XML 架构设计器工作区](../xml-tools/xml-schema-designer-workspace.md)从**XML 架构资源管理器**。 这可以通过拖放的节点来实现**XML 架构资源管理器**放到 XSD 设计器视图，或通过使用**XML 架构资源管理器的**上下文菜单。 你还可以添加作为执行的搜索结果突出显示的节点**XML 架构资源管理器**。 有关详细信息，请参阅[如何： 向工作区中添加架构集搜索结果节点](../xml-tools/how-to-add-schema-set-search-result-nodes-to-the-workspace.md)。

> [!NOTE]
> 只能将全局节点可以添加到[XML 架构设计器工作区](../xml-tools/xml-schema-designer-workspace.md)。

## <a name="to-add-nodes-through-the-xml-explorer-context-menu"></a>若要添加节点通过 XML 资源管理器上下文菜单

1.  按照中的步骤[如何： 创建和编辑 XSD 架构文件](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)。

2.  右键单击`PurchaseOrderType`在 XSD 资源管理器中的节点。 选择**在关系图视图中显示**。

     `purchaseOrderType` 节点出现在图形视图的设计图面上。

## <a name="to-drag-and-drop-a-node-on-to-a-view"></a>将节点拖放到视图

1.  右键单击`PurchaseOrderType`关系图视图中的节点。 选择**在 XML 架构资源管理器中显示**。

     节点中会突出显示**XML 架构资源管理器**。

2.  右键单击`PurchaseOrderType`中的节点**XML 架构资源管理器**和选择**显示所有引用**。

     `purchaseOrder` 节点将突出显示。

3.  将 `purchaseOrder` 节点拖到图形视图上。

     `purchaseOrder` 节点和 `PurchaseOrderType` 节点在图形视图的设计图面上紧挨着出现。 因为这两个节点相关（`purchaseOrder` 元素属于 `PurchaseOrderType` 类型），因此会在这两个节点之间绘制一个箭头。

## <a name="to-add-nodes-using-the-schema-explorer-search-capability"></a>使用架构资源管理器的搜索功能添加节点

1.  中的搜索文本框中键入"purchaseOrder" [XML 资源管理器](../xml-tools/xml-schema-explorer.md)工具栏，然后单击搜索按钮。

     ![XML 架构资源管理器关键字搜索](../xml-tools/media/schemaexplorersearch.gif)

     搜索结果将以突出显示**XML 架构资源管理器**和由垂直滚动条上的刻度标记。

2.  向工作区添加搜索结果，通过单击**将突出显示的节点添加到工作区**摘要结果窗格上的按钮。

     ![XML 架构资源管理器搜索结果](../xml-tools/media/schemaexplorersearchresult.gif)

     `purchaseOrder`节点和`PurchaseOrderType`节点显示彼此相邻的设计图面上[图形视图](../xml-tools/graph-view.md)。 因为这两个节点相关（`purchaseOrder` 元素属于 `PurchaseOrderType` 类型），因此会在这两个节点之间绘制一个箭头。

## <a name="see-also"></a>请参阅

- [XML 架构资源管理器](../xml-tools/xml-schema-explorer.md)