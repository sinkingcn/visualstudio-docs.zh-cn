---
title: 如何：将 XML 架构设计器用于 XML 文本
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d11803e7-f81a-41a2-a145-ba494a45cc93
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 9858768da0096c98ffb3014f0a52936adbf39019
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49931111"
---
# <a name="how-to-use-the-xml-schema-designer-with-xml-literals"></a>如何： 使用 XML 文本中使用 XML 架构设计器

本主题描述如何查看与 Visual Basic 项目中的 XML 文本关联的架构。

## <a name="to-create-a-new-visual-basic-console-application-project"></a>创建新的 Visual Basic 控制台应用程序项目

1.  启动 Visual Studio。

2.  从**文件**菜单中，选择**新建**，然后选择**项目**。 此时将出现 “新建项目” 对话框。 有关**项目类型**，选择**其他语言**，然后选择**Visual Basic**。 有关**模板**，选择控制台应用程序。 然后键入`XMLLiterals`中**名称**字段和中的项目位置**位置**字段。 单击 **“确定”**。

     新项目创建完成。 XMLLiterals 项目包含一个 Visual Basic 源文件*Module1.vb*。

## <a name="to-add-an-existing-xsd-file-to-the-project"></a>向项目中添加现有的 XSD 文件

1.  在记事本中打开新的文本文件。 中的 XML 架构示例代码复制[采购订单架构](../xml-tools/sample-xsd-file-simple-schema.md)并将其粘贴到该文件。

2.  将文件保存在某个位置具有名称*PurchaseOrderSchema.xsd*。

3.  在中**解决方案资源管理器**，右键单击项目的名称，选择**添加**，然后选择**现有项**。 **添加现有项**对话框随即出现。 浏览到*PurchaseOrderSchema.xsd*文件中，选择它，，然后单击**添加**。

     XMLLiterals 项目现在包含两个文件： *Module1.vb*并*PurchaseOrderSchema.xsd*。

## <a name="to-add-visual-basic-code-with-an-xml-literal-based-on-the-xsd-file-included-in-the-project"></a>基于项目中包含的 XSD 文件添加带 XML 文本的 Visual Basic 代码

1. 中的代码替换*Module1.vb*文件使用以下代码：

   ```vb
   Imports <xmlns:ns="http://tempuri.org/PurchaseOrderSchema.xsd">

   Module Module1
      Sub Main()

          Dim XMLLiteral = <ns:PurchaseOrder OrderDate="1900-01-01">
                               <ns:ShipTo country="US">
                                   <ns:name>name1</ns:name>
                                   <ns:street>street1</ns:street>
                                   <ns:city>city1</ns:city>
                                   <ns:state>state1</ns:state>
                                   <ns:zip>1</ns:zip>
                               </ns:ShipTo>
                               <ns:BillTo country="US">
                                   <ns:name>name1</ns:name>
                                   <ns:street>street1</ns:street>
                                   <ns:city>city1</ns:city>
                                   <ns:state>state1</ns:state>
                                   <ns:zip>1</ns:zip>
                               </ns:BillTo>
                           </ns:PurchaseOrder>

      End Sub
   End Module
   ```

2. 右键单击 XML 文本或导入的 XML 命名空间中的任何 XML 节点并选择**在架构资源管理器中显示**。

    **XML 架构资源管理器**具有 XML 文本与 XML 架构集相关联的 Visual Basic 文件将并排显示。