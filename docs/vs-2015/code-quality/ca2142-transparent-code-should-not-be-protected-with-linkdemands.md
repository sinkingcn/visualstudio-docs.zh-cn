---
title: CA2142： 透明代码应不使用 Linkdemand 保护 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 744ca0b6b988591b646c66d349cc39649d323116
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587487"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142：不应使用 LinkDemand 保护透明代码
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA2142： 不应使用 Linkdemand 保护透明代码](https://docs.microsoft.com/visualstudio/code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands)。

|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 透明方法需要<xref:System.Security.Permissions.SecurityAction>或其他安全要求。

## <a name="rule-description"></a>规则说明
 对于需要 LinkDemand 来访问它们的透明方法，将会引发此规则。 安全透明代码不应负责验证某个操作的安全，因此不应要求权限。 透明方法不会为非特定的安全，因为它们不应作出任何安全决策。 此外，安全关键代码，这会使安全决策，不应依赖透明代码以之前进行此类决定。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请删除透明方法链接要求或此方法标记<xref:System.Security.SecuritySafeCriticalAttribute>属性，如果它正在执行安全检查，如安全要求。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 在以下示例中，将引发规则方法因为该方法是透明的并标有 LinkDemand <xref:System.Security.PermissionSet> ，其中包含<xref:System.Security.Permissions.SecurityAction>。

 [!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2142.transparentmethodsshouldnotbeprotectedwithlinkdemands/cs/ca2142 -transparentmethodsshouldnotbeprotectedwithlinkdemands.cs#1)]

 不禁止显示此规则发出的警告。


