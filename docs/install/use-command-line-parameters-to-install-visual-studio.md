---
title: 使用命令行参数安装 Visual Studio
description: 了解如何使用命令行参数来控制或自定义 Visual Studio 安装。
ms.custom: ''
ms.date: 11/14/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- command-line parameters
- switches
- command prompt
ms.assetid: 480f3cb4-d873-434e-a8bf-82cff7401cf2
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e52d61c1226e131c9d989a70f7c8e6432d8f3733
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51768517"
---
# <a name="use-command-line-parameters-to-install-visual-studio-2017"></a>使用命令行参数安装 Visual Studio 2017

通过命令提示符安装 Visual Studio 2017 时，可以使用各种命令行参数来控制或自定义安装。 通过命令行，可以执行下列操作：

- 启动预先选定了特定选项的安装。
- 自动执行安装过程。
- 创建安装文件的缓存（布局）以备日后使用。

将命令行选项与安装引导程序结合使用。安装引导程序是启动下载过程的小型（约 1MB）文件。 安装引导程序是你从 Visual Studio 网站下载时启动的第一个可执行文件。 单击下面的链接，直接链接到要安装的产品版本所对应的最新版安装引导程序：

- [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=15?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2017)
- [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=15?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2017)
- [Visual Studio 2017 Community](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=15?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=link+cta&utm_content=download+commandline+parameters+vs2017)

## <a name="list-of-command-line-parameters"></a>命令行参数列表

 Visual Studio 命令行参数不区分大小写。

> 语法：`vs_enterprise.exe [command] <options>...`

（将 `vs_enterprise.exe` 替换为要安装的相应产品版本。）

>[!TIP]
> 有关如何使用命令行安装 Visual Studio 2017 的更多示例，请参阅[命令行参数示例](command-line-parameter-examples.md)页。

| **命令** | **说明** |
| ----------------------- | --------------- |
| (空白) | 安装产品。 |
| `modify` | 修改已安装的产品。 |
| `update` | 更新已安装的产品。 |
| `repair` | 修复已安装的产品。 |
| `uninstall` | 卸载已安装的产品。 |
| `export` | **15.9 版中的新增功能**：将安装所选内容导出到安装配置文件。 |

| **安装选项** | **说明** |
| ----------------------- | --------------- |
| `--installPath <dir>` | 要对其执行操作的实例的安装目录。 对于安装命令，这是**可选**选项，表示实例的安装位置。 对于其他命令，此为必需选项，表示以前安装的实例的安装位置。 |
| `--addProductLang <language-locale>` | **可选**：在安装或修改操作期间，这可确定要在产品中安装的 UI 语言包。 可以在命令行处多次使用此选项，从而添加多个语言包。 如果缺少此选项，将使用计算机区域设置进行安装。 有关详细信息，请参阅本页的[语言区域设置列表](#list-of-language-locales)部分。|
| `--removeProductLang <language-locale>` | **可选**：在安装或修改操作期间，这可确定要从产品中删除的 UI 语言包。 可以在命令行处多次使用此选项，从而添加多个语言包。 有关详细信息，请参阅本页的[语言区域设置列表](#list-of-language-locales)部分。|
| `--add <one or more workload or component IDs>` | **可选**：要添加的一个或多个工作负荷或组件 ID。 将安装项目的所需组件，而不是建议组件或可选组件。 可以使用 `--includeRecommended` 和/或 `--includeOptional` 全局控制其他组件。 若要包括多个工作负荷或组件，请重复 `--add` 命令（例如，`--add Workload1 --add Workload2`）。 若要更精确地进行控制，可以将 `;includeRecommended` 或 `;includeOptional` 追加到 ID 中（例如，`--add Workload1;includeRecommended` 或 `--add Workload2;includeRecommended;includeOptional`）。 有关详细信息，请参阅[工作负载和组件 ID](workload-and-component-ids.md) 页。 可以根据需要重复此选项。|
| `--remove <one or more workload or component IDs>` | **可选**：要删除的一个或多个工作负荷或组件 ID。 有关详细信息，请参阅[工作负载和组件 ID](workload-and-component-ids.md) 页。 可以根据需要重复此选项。|
| `--in <path>` | **可选**：响应文件的 URI 或路径。  |
| `--all` | **可选**：是否安装产品的所有工作负荷和组件。 |
| `--allWorkloads` | **可选**：安装所有工作负载和组件，不安装建议组件或可选组件。 |
| `--includeRecommended` | **可选**：包含所有已安装工作负载的推荐组件，但不包含可选组件。 可使用 `--allWorkloads` 或 `--add` 指定工作负载。 |
| `--includeOptional` | **可选**：包含所有已安装工作负荷的可选组件，但不包含建议组件。 可使用 `--allWorkloads` 或 `--add` 指定工作负载。  |
| `--quiet, -q` | **可选**：执行安装时不显示任何用户界面。 |
| `--passive, -p` | **可选**：显示用户界面，但不请求用户进行任何交互。 |
| `--norestart` | **可选**：如果指定，包含 `--passive` 或 `--quiet` 的命令不会自动重启计算机（如有必要）。  如果 `--passive` 和 `--quiet` 均未指定，则忽略此选项。  |
| `--nickname <name>` | **可选**：此参数定义分配给已安装产品的别名。 别名长度不能超过 10 个字符。  |
| `--productKey` | **可选**：这定义要用于已安装产品的产品密钥。 由 25 个字母数字字符组成，格式为 `xxxxx-xxxxx-xxxxx-xxxxx-xxxxx` 或 `xxxxxxxxxxxxxxxxxxxxxxxxx`。 |
| `--help, --?, -h, -?` | 显示此页的脱机版本。 |
| `--config <path>` | **15.9 版中的可选**和**新增功能**：在安装或修改操作期间，这将根据以前保存的安装配置文件确定要添加的工作负载和组件。 此操作是附加的，如果文件中不存在任何工作负载或组件，也不会删除任何工作负载或组件。 此外，不会添加不适用于该产品的项目。 在导出操作期间，这将确定保存安装配置文件的位置。 |

> 注意：指定多个工作负载和组件时，必须对每项重复运行 `--add` 或 `--remove` 命令行开关。

| **布局选项** | **说明** |
| ----------------------- | --------------- |
| `--layout <dir>` | 指定用于创建脱机安装缓存的目录。 有关详细信息，请参阅[创建 Visual Studio 的网络安装](create-a-network-installation-of-visual-studio.md)。|
| `--lang <one or more language-locales>` | **可选**：与 `--layout` 结合使用，以准备脱机安装缓存，以便使用包含指定语言的资源包。 有关详细信息，请参阅本页的[语言区域设置列表](#list-of-language-locales)部分。|
| `--add <one or more workload or component IDs>` | **可选**：要添加的一个或多个工作负荷或组件 ID。 将安装项目的所需组件，而不是建议组件或可选组件。 可以使用 `--includeRecommended` 和/或 `--includeOptional` 全局控制其他组件。 若要更精确地进行控制，可以将 `;includeRecommended` 或 `;includeOptional` 追加到 ID 中（例如，`--add Workload1;includeRecommended` 或 `--add Workload2;includeOptional`）。 有关详细信息，请参阅[工作负载和组件 ID](workload-and-component-ids.md) 页。 <br/>**注意**：如果使用了 `--add`，只会下载指定的工作负载和组件及其依赖项。 如果未指定 `--add`，所有工作负载和组件都会下载到布局中。|
| `--includeRecommended` | **可选**：包含所有已安装工作负载的推荐组件，但不包含可选组件。 可使用 `--allWorkloads` 或 `--add` 指定工作负载。 |
| `--includeOptional` | **可选**：添加布局中包含的任何工作负载的推荐*和*可选组件。 可使用 `--add` 指定工作负载。  |
| `--keepLayoutVersion` | **15.3 中新增的可选选项**：无需更新布局版本，即可将更改应用到布局中。 |
| `--verify` | **15.3 中新增的可选选项**：验证布局内容。 将列出所有损坏或缺失的文件。 |
| `--fix` | **15.3 中新增的可选选项**：验证布局内容。  如果发现任何文件损坏或缺失，将重新进行下载。 必须连接 Internet，才能修复布局。 |
| `--clean <one or more paths to catalogs>` | **15.3 中新增的可选选项**：从已更新到新版本的布局中删除旧版组件。 |

| **高级安装选项** | **说明** |
| ----------------------- | --------------- |
| `--channelId <id>` | **可选**：要安装的实例的通道 ID。 如果指定了 `--installPath`，对于安装命令，此为是必需选项，对于其他命令，此选项可忽略。 |
| `--channelUri <uri>` | **可选**：通道清单的 URI。 如果不需要更新，`--channelUri` 可以指向不存在的文件。 （例如，--channelUri C:\doesntExist.chman）此参数可用于 install 命令；其他命令则可忽略。 |
| `--installChannelUri <uri>` | **可选**：要用于安装的通道清单的 URI。 `--channelUri` 指定的 URI（指定 `--installChannelUri` 时必须指定）用于检测更新。 此参数可用于 install 命令；其他命令则可忽略。 |
| `--installCatalogUri <uri>` | **可选**：要用于安装的目录清单的 URI。 如果指定此选项，通道管理器会先尝试通过此 URI 下载目录清单，然后再在安装通道清单中使用 URI。 此参数用于支持脱机安装，安装期间会使用已下载的产品目录创建布局缓存。 此参数可用于 install 命令；其他命令则可忽略。 |
| `--productId <id>` | **可选**：将要安装的实例的产品 ID。 在正常安装条件下，这是预填充的。 |
| `--wait` | **可选**：进程会先等待安装完成，然后再返回退出代码。 在需要等待安装完成以处理来自该安装的返回代码的自动安装中，这非常有用。 |
| `--locale <language-locale>` | **可选**：更改安装程序本身的用户界面的显示语言。 将保留设置。 有关详细信息，请参阅本页的[语言区域设置列表](#list-of-language-locales)部分。|
| `--cache` | **15.2 中的新增选项，可选**：如果指定，将在安装后保存包，以便后续修复时使用。 这会替代用于后续安装、修复或修改的全局策略设置。 默认策略是缓存包。 对于卸载命令，忽略此选项。 有关详细信息，请了解如何[禁用或移动包缓存](disable-or-move-the-package-cache.md)。 |
| `--nocache` | **15.2 中新增的可选选项**：如果指定，将在安装或修复完成后删除包。 只有在需要时才会重新下载，并且会在使用后再次删除。 这会替代用于后续安装、修复或修改的全局策略设置。 默认策略是缓存包。 对于卸载命令，忽略此选项。 有关详细信息，请了解如何[禁用或移动包缓存](disable-or-move-the-package-cache.md)。 |
| `--noUpdateInstaller` | **15.2 中的新增功能（可选）**：如果存在，指定无提示安装时阻止安装程序进行自我更新。 如果在需要更新安装程序时通过无提示安装指定 noUpdateInstaller，则安装程序将忽略该命令并返回非零退出代码。 |
| `--noWeb` | **15.3 中新增的可选选项**：安装程序现在从 Internet 下载要安装的所有内容。  离线布局中必须有要安装的所有内容。  如果布局中缺少内容，安装将失败。  有关详细信息，请参阅[从网络安装点进行部署](create-a-network-installation-of-visual-studio.md)。 |
| `--path <name>=<path>` | **15.7 版中新增的可选选项**：用于指定安装的自定义安装路径。 支持的路径名称有 shared、cache 和 install。 |
| `--path cache=<path>` | **15.7 版中新增的可选选项**：使用指定的位置下载安装文件。 只可以在首次安装 Visual Studio 时设置此位置。 示例：`--path cache="C:\VS\cache"` |
| `--path shared=<path>` | **15.7 版中新增的可选选项**：包含用于并行 Visual Studio 安装的共享文件。 某些工具和 SDK 会安装到此驱动器上的某个位置，而其他一些工具可能会替代此设置并安装到另一个驱动器。 示例：`--path shared="C:\VS\shared"` <br><br>重要说明：只能在首次安装 Visual Studio 时对此设置一次。 |
| `--path install=<path>` | **15.7 版中新增的可选选项**：等效于 `–-installPath`。 具体而言，`--installPath "C:\VS"` 与 `--path install="C:\VS"` 等效。 一次只能使用其中一个。 |

## <a name="list-of-workload-ids-and-component-ids"></a>工作负荷 ID 和组件 ID 列表

有关按 Visual Studio 产品排序的工作负载和组件 ID 的列表，请参阅 [Visual Studio 2017 工作负载和组件 ID](workload-and-component-ids.md) 页面。

## <a name="list-of-language-locales"></a>语言区域设置列表

| **语言-区域设置** | **语言** |
| ----------------------- | --------------- |
| Cs-cz | 捷克语 |
| De-de | 德语 |
| En-us | 英语 |
| Es-es | 西班牙语 |
| Fr-fr | 法语 |
| It-it | 意大利语 |
| Ja-jp | 日语 |
| Ko-kr | 朝鲜语 |
| Pl-pl | 波兰语 |
| Pt-br | 葡萄牙语 - 巴西 |
| Ru-ru | 俄语 |
| Tr-tr | 土耳其语 |
| Zh-cn | 中文 - 简体 |
| Zh-tw | 中文 - 繁体 |

## <a name="error-codes"></a>错误代码

`%ERRORLEVEL%` 环境变量设为下列值之一，具体视操作结果而定：

| **值** | **结果** |
| --------- | ---------- |
| 0 | 操作成功完成 |
| 1602 | 操作已取消 |
| 3010 | 操作成功完成，但安装需要重启才能使用 |
| 5004 | 操作已取消 |
| 5007 | 操作被屏蔽 - 计算机不符合要求 |
| 其他 | 发生了故障，请查看日志，了解详细信息 |

每个操作都会在指明安装进度的 `%TEMP%` 目录中生成多个日志文件。 按日期对文件夹进行排序，再查找以“`dd_bootstrapper`”、“`dd_client`”和“`dd_setup`”开头的文件，分别查找安装引导程序、安装程序应用和安装程序引擎。

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>请参阅

- [Visual Studio 2017 安装的命令行参数示例](command-line-parameter-examples.md)
- [创建 Visual Studio 2017 的脱机安装](create-an-offline-installation-of-visual-studio.md)
- [通过响应文件自动执行 Visual Studio 安装](automated-installation-with-response-file.md)
- [Visual Studio 2017 工作负载和组件 ID](workload-and-component-ids.md)