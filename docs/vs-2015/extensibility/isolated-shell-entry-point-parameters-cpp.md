---
title: 独立 Shell 入口点参数 （c + +） |Microsoft Docs
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
- Shell [Visual Studio], isolated mode%2C Start entry point
- Visual Studio shell, isolated mode%2C Start entry point
ms.assetid: 18f4b18b-2173-4afa-ba0a-42fe33e61118
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 270a5c932429a518447d0029b05d3c9522db7387
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51749179"
---
# <a name="isolated-shell-entry-point-parameters-c"></a>独立的 Shell 入口点参数 （c + +）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 基于 shell 的应用程序启动时，它调用的 Visual Studio shell 的启动入口点。 可以在外壳程序的启动入口点的调用中重写以下设置。 每个设置的说明，请参阅[。Pkgdef 文件](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)。  
  
- AddinsAllowed  
  
- AllowsDroppedFilesOnMainWindow  
  
- 应用程序名  
  
- CommandLineLogo  
  
- DefaultHomePage  
  
- DefaultProjectsLocation  
  
- DefaultSearchPage  
  
- DefaultUserFilesFolderRoot  
  
- DisableOutputWindow  
  
- HideMiscellaneousFilesByDefault  
  
- HideSolutionConcept  
  
- NewProjDlgInstalledTemplatesHdr  
  
- NewProjDlgSlnTreeNodeTitle  
  
- SolutionFileCreatorIdentifier  
  
- SolutionFileExt  
  
- UserFilesSubFolderName  
  
- UserOptsFileExt  
  
  Visual Studio Shell 独立模板创建一个源文件， *solutionName*.cpp，其中*solutionName*是应用程序的解决方案名称。 此文件定义应用程序，_tWinMain 函数的主入口点。 此函数调用的命令行程序的启动入口点。  
  
  可以通过应用程序启动时更改这些设置来更改应用程序的行为。  
  
## <a name="parameters"></a>参数  
 在 Visual Studio shell 的启动入口点定义五个参数。 不要更改前四个参数。 第五个参数将设置重写列表。 从应用程序的主入口点调用 shell 的启动入口点。  
  
 在 shell 的启动入口点具有以下签名。  
  
```  
typedef int (__cdecl *STARTFCN)(LPSTR, LPWSTR, int, GUID *, WCHAR *pszSettings);  
```  
  
 如果您不想要重写任何应用程序设置中，保留的设置的值覆盖参数为 null 指针。  
  
 若要覆盖一个或多个设置，请将传递一个 Unicode 字符串，包含要重写的设置。 字符串是以分号分隔名称 / 值对的列表。 每个对包含要重写，请设置的名称跟有等号 （=） 后, 跟要应用于该设置的值。  
  
> [!NOTE]
>  Unicode 字符串中不包含空格。  
  
 对于布尔设置，以下字符串表示值 true;所有其他字符串表示值 false。 这些字符串不区分大小写。  
  
-   \+  
  
-   1  
  
-   -1  
  
-   on  
  
-   true  
  
-   是  
  
## <a name="example"></a>示例  
 若要禁用加载项和更改你的应用程序的默认项目位置，可以设置为"AddinsAllowed=false;DefaultProjectsLocation=%USERPROFILE%\temp"的最后一个参数。  
  
## <a name="see-also"></a>请参阅  
 [自定义独立的 Shell](../extensibility/customizing-the-isolated-shell.md)   
 [.Pkgdef 文件](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)

