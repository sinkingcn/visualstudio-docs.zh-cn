---
title: 扩展状态栏 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- status bars, about status bars
- status bars, overview
ms.assetid: f955115c-4c5f-45ec-b41b-365868c5ec0c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0e072814120f18c7cc1ea09bf0829266958691ba
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497909"
---
# <a name="extend-the-status-bar"></a>扩展状态栏
可用于 Visual Studio 状态栏在 IDE 底部显示的信息。  
  
 扩展状态栏时，您可以在四个区域中显示信息和用户界面： 反馈区域、 进度栏、 动画区域和设计器区域。 反馈区域可以显示文本并突出显示所显示的文本。 进度栏显示短时间运行操作，如保存文件的进度。 动画区域显示为长时间运行的操作或操作不确定的长度，如生成多个项目在解决方案中的一个连续循环的动画。 和设计器区域显示的光标所在的位置的行和列号。  
  
 可以通过获取状态栏<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>接口 (从<xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar>服务)。 此外，在窗口框架上放置任何对象可以通过注册为状态栏客户端对象实现<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>接口。 Visual Studio 窗口已激活，只要查询放置在该窗口上的对象`IVsStatusbarUser`接口。 如果找到，则会调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>上返回的接口和对象的方法可以更新状态栏从该方法中的。 文档窗口，例如，可以使用<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>方法来更新设计器区域中的信息，当它们变为活动状态。  
  
 下面的过程假定您了解如何创建 VSIX 项目并添加自定义菜单命令。 有关信息，请参阅[与菜单命令创建扩展](../extensibility/creating-an-extension-with-a-menu-command.md)。  
  
## <a name="modify-the-status-bar"></a>修改状态栏  
 此过程演示如何设置和获取文本、 显示静态文本，并突出显示状态栏的反馈区域中显示的文本。  
  
### <a name="read-and-write-to-the-status-bar"></a>读取和写入到状态栏  
  
1.  创建一个名为的 VSIX 项目**TestStatusBarExtension**并添加名为的菜单命令**TestStatusBarCommand**。  
  
2.  在中*TestStatusBarCommand.cs*，将为命令处理程序方法代码 (`MenuItemCallback`) 以下：  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar = (IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
  
        // Make sure the status bar is not frozen  
        int frozen;  
  
        statusBar.IsFrozen(out frozen);  
  
        if (frozen != 0)   
        {  
            statusBar.FreezeOutput(0);  
        }  
  
        // Set the status bar text and make its display static.  
        statusBar.SetText("We just wrote to the status bar.");  
  
        // Freeze the status bar.  
        statusBar.FreezeOutput(1);  
  
        // Get the status bar text.   
        string text;  
        statusBar.GetText(out text);  
        System.Windows.Forms.MessageBox.Show(text);  
  
        // Clear the status bar text.  
        statusBar.FreezeOutput(0);  
        statusBar.Clear();  
    }  
    ```  
  
3.  编译代码并开始调试。  
  
4.  打开**工具**Visual Studio 的实验实例中的菜单。 单击**调用 TestStatusBarCommand**按钮。  
  
     您应该会看到现在读取状态栏中的文本**我们刚刚写入状态栏。** 并将显示该消息框具有相同的文本。  
  
### <a name="update-the-progress-bar"></a>更新进度条  
  
1.  在此过程中，我们将演示如何初始化和更新进度条。  
  
2.  打开*TestStatusBarCommand.cs*文件，然后替换`MenuItemCallback`方法使用以下代码：  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar = (IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
        uint cookie = 0;  
        string label = "Writing to the progress bar";  
  
        // Initialize the progress bar.  
        statusBar.Progress(ref cookie, 1, "", 0, 0);  
  
        for (uint i = 0, total = 20; i <= total; i++)  
        {  
            // Display progress every second.  
            statusBar.Progress(ref cookie, 1, label, i, total);  
            System.Threading.Thread.Sleep(1000);  
        }  
  
        // Clear the progress bar.  
        statusBar.Progress(ref cookie, 0, "", 0, 0);  
    }  
    ```  
  
3.  编译代码并开始调试。  
  
4.  打开**工具**Visual Studio 的实验实例中的菜单。 单击**调用 TestStatusBarCommand**按钮。  
  
     您应该会看到现在读取状态栏中的文本**写入进度栏。** 您还会看到进度栏会更新每秒 20 秒的时间。 在此之后清除状态栏，进度栏。  
  
### <a name="display-an-animation"></a>显示动画  
  
1.  状态栏会显示循环的动画指示一个长时间运行的操作 （例如，生成解决方案中的多个项目）。 如果看不到此动画，请确保您具有正确**工具** > **选项**设置：  
  
     转到**工具** > **选项** > **常规**选项卡上，取消选中**自动调整视觉体验基于客户端性能**。 然后检查子选项**启用丰富客户端视觉体验**。 现在应能够生成你的 Visual Studio 的实验实例中的项目时看到动画。  
  
     在此过程中，我们显示标准的 Visual Studio 动画表示生成项目或解决方案。  
  
2.  打开*TestStatusBarCommand.cs*文件，然后替换`MenuItemCallback`方法使用以下代码：  
  
    ```csharp  
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        IVsStatusbar statusBar =(IVsStatusbar)ServiceProvider.GetService(typeof(SVsStatusbar));  
  
        // Use the standard Visual Studio icon for building.  
        object icon = (short)Microsoft.VisualStudio.Shell.Interop.Constants.SBAI_Build;  
  
        // Display the icon in the Animation region.  
        statusBar.Animation(1, ref icon);  
  
        // The message box pauses execution for you to look at the animation.  
        System.Windows.Forms.MessageBox.Show("showing?");  
  
        // Stop the animation.   
        statusBar.Animation(0, ref icon);  
    }  
    ```  
  
3.  编译代码并开始调试。  
  
4.  打开**工具**在实验实例中的 Visual Studio，然后单击菜单**调用 TestStatusBarCommand**。  
  
     当您看到的消息框时，还将看到在状态栏中的动画最右侧。 当您关闭消息框时，动画将消失。