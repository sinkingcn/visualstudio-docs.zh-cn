---
title: DiaAddressMapEntry |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa2824b7fbd10e7628e5c6b0a016615620933df9
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51756240"
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

描述在映射的地址中的项。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
struct DiaAddressMapEntry {   
   DWORD rva,  
   DWORD rvaTo  
};  
```  
  
## <a name="elements"></a>元素  
 `rva`  
 A.映像中的相对虚拟地址 (RVA)  
  
 `rvaTo`  
 相对虚拟地址`rva`映像 B.中映射到  
  
## <a name="remarks"></a>备注  
 映射的地址提供了从一个图像布局 （A） 到另一个 （B） 的转换。 一个数组`DiaAddressMapEntry`结构按`rva`定义映射的地址。  
  
 地址转换`addrA`，在图 A 中为地址， `addrB`，在图 B 中，执行以下步骤：  
  
1. 搜索的项映射`e`，，最大`rva`小于或等于`addrA`。  
  
2. 设置`delta = addrA – e.rva`。  
  
3. 设置`addrB = e.rvaTo + delta`。  
  
   一个数组`DiaAddressMapEntry`结构传递给[idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： dia2.h  
  
## <a name="see-also"></a>请参阅  
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)



