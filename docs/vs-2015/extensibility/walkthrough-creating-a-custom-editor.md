---
title: 演练： 创建自定义编辑器 |Microsoft Docs
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
- editors [Visual Studio SDK], custom - create
ms.assetid: d090abb6-d99f-4083-a3db-cd16bf81ce7d
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0b7c8bd8643b6c670e614f4745650f42ccca35f5
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51809735"
---
# <a name="walkthrough-creating-a-custom-editor"></a>演练：创建自定义编辑器
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPackage 项目模板可以在 c + + 中创建一个简单的自定义编辑器。  VSPackage 项目模板不再支持 C# 或 Visual Basic 项目。 有关详细信息，请参阅[Visual Studio SDK](../extensibility/visual-studio-sdk.md)。  
  
## <a name="prerequisites"></a>系统必备  
 要按照本演练的步骤操作，必须安装 Visual Studio SDK。 有关详细信息，请参阅[安装 Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md)。  
  
## <a name="the-visual-studio-package-project-template"></a>Visual Studio 包项目模板  
 Visual Studio 包项目模板可在**新的项目**c + + 扩展性文件夹中的对话框  
  
### <a name="to-create-a-vspackage-using-the-visual-studio-package-template"></a>若要创建使用 Visual Studio 包模板的 VSPackage  
  
1.  使用 Visual Studio 包模板创建项目。  
  
2.  选择**自定义编辑器**选项，然后单击**下一步**。 **编辑器选项**显示页。  
  
3.  键入您的编辑器中的名称**编辑器名称**框。 键入你想要与编辑器中关联的文件扩展名**文件扩展名**框。 你的编辑器是可供具有此扩展名的文件。 文件扩展名为注册 Visual Studio 仅，不适用于 Windows。 键入与您的编辑器中创建的新文档的默认文件名**默认文件名**框。  
  
4.  单击“完成”  以在指定的文件夹中创建 VSPackage。  
  
### <a name="to-test-your-custom-editor"></a>若要测试自定义编辑器  
  
1.  上**文件**菜单，依次指向**新建**，然后单击**文件**。  
  
2.  在中**已安装的模板**窗格**新文件**对话框中，选择文件模板，则该文件键入您刚刚注册。  
  
3.  单击**打开**查看和编辑文档。  
  
     该编辑器支持剪切和粘贴、 查找和替换和打开并加载操作。  
  
## <a name="see-also"></a>请参阅  
 [VSPackage](../extensibility/internals/vspackages.md)

