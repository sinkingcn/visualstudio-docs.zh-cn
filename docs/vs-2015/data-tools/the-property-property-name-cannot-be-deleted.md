---
title: 该属性&lt;属性名称&gt;不能删除 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 98b065500c9c881a7190b59c4d70a0433eb8864c
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49186519"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted"></a>该属性&lt;属性名称&gt;无法删除
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
该属性\<属性名称 > 不能删除，因为它被设置为之间的继承鉴别器属性\<类名称 > 和\<类名称 >  
  
 所选的属性设置为**鉴别器属性**类之间的继承所指示的错误消息中。 如果属性参与数据类之间的继承配置，则无法删除这些属性。  
  
 设置**鉴别器属性**到不同的数据类可以成功删除删除所需的属性的属性。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  在 O/R 设计器中选择连接错误消息中指示的数据类的继承连线。  
  
2.  设置**鉴别器**为另一个属性的属性。  
  
3.  再次尝试删除该属性。  
  
## <a name="see-also"></a>请参阅  
 [如何： 通过使用 O/R 设计器配置继承](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)   
 [数据类继承 （O/R 设计器）](../data-tools/data-class-inheritance-o-r-designer.md)   
 [演练：通过使用单表继承创建 LINQ to SQL 类（O/R 设计器）](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)

