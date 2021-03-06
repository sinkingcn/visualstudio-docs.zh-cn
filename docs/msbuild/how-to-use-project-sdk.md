---
title: 如何：引用 MSBuild 项目 SDK | Microsoft 文档
ms.custom: ''
ms.date: 01/25/2018
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, SDKs, SDK
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: abc61f0e07ed1e22d0ec3b2c8fb15d66c9eea3cd
ms.sourcegitcommit: d462dd10746624ad139f1db04edd501e7737d51e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "50220438"
---
# <a name="how-to-use-msbuild-project-sdks"></a>如何：使用 MSBuild 项目 SDK

[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 15.0 引入了“项目 SDK”概念，此概念简化了需要导入属性和目标才能使用的软件开发工具包的用法。

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>
</Project>
```

在项目评估期间，[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 在项目的顶部和底部添加了隐式导入：

```xml
<Project>
    <!-- Implicit top import -->
    <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />

    <PropertyGroup>
        <TargetFramework>net46</TargetFramework>
    </PropertyGroup>

    <!-- Implicit bottom import -->
    <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

## <a name="reference-a-project-sdk"></a>引用项目 SDK

 可通过三种方法引用项目 SDK：

1. 使用 `<Project/>` 元素的 `Sdk` 属性：

    ```xml
    <Project Sdk="My.Custom.Sdk">
        ...
    </Project>
    ```

    将隐式导入添加到项目的顶部和底部，如上文所述。  `Sdk` 属性的格式为 `Name[/Version]`，其中版本可选。  例如，你可以指定 `My.Custom.Sdk/1.2.3`。

    > [!NOTE]
    > 这是目前在 Visual Studio for Mac 中引用项目 SDK 的唯一受支持的方式。

2. 使用顶级 `<Sdk/>` 元素：

    ```xml
    <Project>
        <Sdk Name="My.Custom.Sdk" Version="1.2.3" />
        ...
    </Project>
   ```

   将隐式导入添加到项目的顶部和底部，如上文所述。  不需要 `Version` 属性。

3. 在项目任意位置使用 `<Import/>` 元素：

    ```xml
    <Project>
        <PropertyGroup>
            <MyProperty>Value</MyProperty>
        </PropertyGroup>
        <Import Project="Sdk.props" Sdk="My.Custom.Sdk" />
        ...
        <Import Project="Sdk.targets" Sdk="My.Custom.Sdk" />
    </Project>
   ```

   通过在项目中显式包含导入，可使你完全控制顺序。

   使用 `<Import/>` 元素时，你还可以指定一个可选的 `Version` 属性。  例如，你可以指定 `<Import Project="Sdk.props" Sdk="My.Custom.Sdk" Version="1.2.3" />`。

## <a name="how-project-sdks-are-resolved"></a>如何解析项目 SDK

导入评估时，[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 将基于名称和你指定的版本动态解析到项目 SDK 的路径。  此外，[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 还具有已注册的 SDK 解析程序，它是在计算机上查找项目 SDK 的插件。  这些插件包括：

1. 基于 NuGet 的解析程序，用于查询为 NuGet 包配置的包源是否匹配所指定 SDK 的 ID 和版本。<br/>
   如果你指定的是可选版本，并且它可以用于任何自定义项目 SDK，该解析程序才有效。  
2. .NET CLI 解析程序，用于解析随 .NET CLI 一起安装的 SDK。<br/>
   此解析程序查找项目 SDK，如 `Microsoft.NET.Sdk` 和 `Microsoft.NET.Sdk.Web`，这些项目是该产品的一部分。
3. 默认解析程序，用于解析随 MSBuild 一起安装的 SDK。

基于 NuGet 的 SDK 解析程序支持在 [global.json](https://docs.microsoft.com/dotnet/core/tools/global-json) 中指定版本，可使你在一个位置而不是在每个项目中控制项目 SDK 版本：

```json
{
    "msbuild-sdks": {
        "My.Custom.Sdk": "5.0.0",
        "My.Other.Sdk": "1.0.0-beta"
    }
}
```

在生成期间，只能使用每个项目 SDK 的一个版本。  如果你正在引用同一项目 SDK 的两个不同版本，MSBuild 将发出警告。  如果在 global.json 中指定了版本，则不建议在项目中指定版本。  

## <a name="see-also"></a>请参阅

 [MSBuild 概念](../msbuild/msbuild-concepts.md)   
 [自定义生成](../msbuild/customize-your-build.md)   
 [包、元数据和框架](/dotnet/core/packages)   
 [.NET Core 的 csproj 格式的新增内容](/dotnet/core/tools/csproj)
