---
title: '&lt;更新&gt;元素 （Visual Studio 中的 Office 开发）'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- update element
- <update> element
- application manifests [Office development in Visual Studio], <update> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ac15ee59299653c71c2d1036e8318a0fee2b693c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49927562"
---
# <a name="ltupdategt-element-office-development-in-visual-studio"></a>&lt;更新&gt;元素 （Visual Studio 中的 Office 开发）
  `update`元素指定的更新的解决方案将检查的间隔。  
  
## <a name="syntax"></a>语法  
  
```xml  
<update  
  enabled>  
  <expiration  
    maximumAge  
    unit  
  />  
</update>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `update` 元素是必需的，它位于 `vstav3` 命名空间中。  
  
 `update` 元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必须的。 将 enabled 设置为以下值之一：<br /><br /> -   **true**检查更新。<br />-   **false**以免检查更新。|  
  
 `update` 元素具有以下子元素。  
  
### <a name="expiration"></a>过期  
 `expiration` 元素是必需的，它位于 `vstav3` 命名空间中。 此元素指定的解决方案检查更新的间隔。  
  
 `expiration` 元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`maximumAge`| 必须的。 这将设置为一个整数。|  
|`unit`|必须的。 设置`unit`为以下值之一：<br /><br /> -   **小时数**<br />-   **天**<br />-   **周**|  
  
## <a name="example-of-always-checking-for-updates"></a>始终检查更新的示例  
  
### <a name="description"></a>描述  
 下面的代码示例说明了`update`设置始终检查更新 Office 解决方案中的元素。  
  
### <a name="code"></a>代码  
  
```xml  
<vstav3:update enabled="true" />  
```  
  
## <a name="example-of-setting-a-default-update-interval"></a>设置默认的更新时间间隔的示例  
  
### <a name="description"></a>描述  
 下面的代码示例说明了`update`Office 解决方案的应用程序清单中的元素。 此代码示例摘自[Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)。  
  
### <a name="code"></a>代码  
  
```xml  
<vstav3:update enabled="true">  
    <vstav3:expiration maximumAge="7" unit="days" />  
</vstav3:update>  
```  
  
## <a name="see-also"></a>请参阅  
 [使用 ClickOnce 部署 Office 解决方案](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)   
 [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  