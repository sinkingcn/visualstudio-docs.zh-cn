---
title: -Upgrade (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /upgrade Devenv switch
- Devenv, /upgrade switch
- upgrade Devenv switch
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ba94a599c119d537efb90b29c1c2ec0084ace447
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948330"
---
# <a name="upgrade-devenvexe"></a>/Upgrade (devenv.exe)
将解决方案文件及其所有项目文件或指定的项目文件更新为这些文件的当前 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 格式。

## <a name="syntax"></a>语法

```cmd
devenv SolutionFile | ProjectFile /upgrade
```

## <a name="arguments"></a>自变量
 `SolutionFile`

 如果要升级整个解决方案及其项目，则是必需的。 解决方案文件的路径和名称。 可以只输入解决方案文件的名称，也可以输入解决方案文件的完整路径和名称。 如果命名的文件夹或文件尚不存在，将创建该文件夹或文件。

 `ProjectFile`

 如果要升级单个项目，则是必需的。 解决方案中项目文件的路径和名称。 可以只输入项目文件的名称，也可以输入项目文件的完整路径和名称。 如果命名的文件夹或文件尚不存在，将创建该文件夹或文件。

## <a name="remarks"></a>备注
 备份文件自动创建并复制到一个名为 Backup 的目录中，该目录是在当前目录中创建的。

 要升级源代码控制的解决方案或项目，必须先将其签出。

 使用 `/upgrade` 开关不会启动 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]。 可在解决方案或项目的开发语言的“升级报告”中看到升级结果。 不会返回任何错误或使用情况信息。 有关在 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 中升级项目的详细信息，请参阅[移植、迁移和升级 Visual Studio 项目](../../porting/port-migrate-and-upgrade-visual-studio-projects.md)。

## <a name="example"></a>示例
 此示例升级 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 解决方案的默认文件夹中名为“MyProject.sln”的解决方案文件。

```cmd
devenv "MyProject.sln" /upgrade
```

## <a name="see-also"></a>请参阅

- [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)