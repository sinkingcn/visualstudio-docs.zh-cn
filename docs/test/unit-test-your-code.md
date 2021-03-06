---
title: Visual Studio 中的单元测试
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, unit tests
- unit tests, verifying code with
- testing code, automated tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: e9bb75c6d7265ca66ccc0922e2d26deaa4d7857a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49874834"
---
# <a name="unit-test-your-code"></a>对代码进行单元测试

通过单元测试，开发人员和测试人员可以快速查找 C#、Visual Basic 和 C++ 项目中各个类的方法中的逻辑错误。

单元测试工具包括：

* **测试资源管理器** &mdash; 可在测试资源管理器中运行单元测试并查看结果。 可以使用任何单元测试框架，包括具有资源管理器的适配器的第三方框架。

* **托管代码的 Microsoft 单元测试框架** &mdash; 托管代码的 Microsoft 单元测试框架随 Visual Studio 安装，并提供测试 .NET 代码的框架。

* **适用于 C++ 的 Microsoft 单元测试框架** &mdash; 适用于 C++ 的 Microsoft 单元测试框架作为“使用 C++ 的桌面开发”工作负载的一部分安装。 它提供一个框架，用于测试本机代码。 还随附有 Google Test、Boost.Test 和 CTest 框架，并且提供了第三方适配器用于其他测试框架。 有关详细信息，请参阅[编写适用于 C/C++ 的单元测试](../test/writing-unit-tests-for-c-cpp.md)。

* **代码覆盖工具** &mdash; 可以确定单元测试从“测试资源管理器”中的一个命令执行的产品代码数量。

* **Microsoft Fakes 隔离框架** &mdash; Microsoft Fakes 隔离框架可以为创建所测试代码中的依赖关系的产品和系统代码创建替代类和方法。 通过实施函数的假委托，可以控制依赖对象的行为和输出。

还可以使用 [IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md) 浏览 .NET 代码，以生成测试数据和单元测试套件。 对于代码中的每个语句，将生成执行该语句的测试输入。 为代码中的每个条件分支执行案例分析。

## <a name="key-tasks"></a>关键任务

下面的主题可帮助你了解和创建单元测试：

|任务|相关主题|
|-|-----------------------|
|**快速入门和演练：** 借助以下主题从代码示例中学习 Visual Studio 中的单元测试。|-   [演练：创建并运行托管代码的单元测试](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)<br />-   [快速入门：通过测试资源管理器进行测试驱动开发](../test/quick-start-test-driven-development-with-test-explorer.md)<br />-   [将单元测试添加到现有 C++ 应用程序](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)|
|**使用“测试资源管理器”进行单元测试：** 了解“测试资源管理器”如何帮助创建成效和效率更高的单元测试。|-   [单元测试基本信息](../test/unit-test-basics.md)<br />-   [创建单元测试项目](../test/create-a-unit-test-project.md)<br />-   [使用测试资源管理器运行单元测试](../test/run-unit-tests-with-test-explorer.md)<br />-   [安装第三方单元测试框架](../test/install-third-party-unit-test-frameworks.md)|
|**对 C++ 代码进行单元测试**|-   [通过适用于 C++ 的 Microsoft 单元测试框架编写适用于 C/C++ 的单元测试](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)|
|**隔离单元测试**|-   [使用 Microsoft Fakes 隔离受测代码](../test/isolating-code-under-test-with-microsoft-fakes.md)|
|**使用代码覆盖率确定测试的项目代码的比例：** 了解 Visual Studio 测试工具的代码覆盖率功能。|-   [使用代码覆盖率确定正在测试的代码量](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)|
|**通过使用负载测试来执行压力和性能分析：** 可以创建负载测试并向其添加单元测试，以帮助隔离应用程序中的性能和压力问题。|-   [负载测试（Azure Test Plans 和 TFS）](/azure/devops/test/load-test/index?view=vsts)|
|**设置质量要求：** 可以创建质量要求以在签入或合并代码之前强制运行测试，从而帮助确保代码质量。|-   [签入策略 (Azure Repos TFVC)](/azure/devops/repos/tfvc/add-check-policies?view=vsts)|
|**设置测试选项：** 例如，可以指定测试结果的存储位置。|[使用 .runsettings 文件配置单元测试](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)|

## <a name="api-reference-documentation"></a>API 参考文档

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting> 介绍 UnitTesting 命名空间，该命名空间提供支持单元测试的属性、异常、断言和其他类。
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Web> 介绍 UnitTesting.Web 命名空间，该命名空间通过提供对 ASP.NET 和 Web 服务单元测试的支持扩展了 UnitTesting 命名空间。

## <a name="see-also"></a>请参阅

- [提高代码质量](../test/improve-code-quality.md)
