---
title: IDiaStackWalkHelper::searchForReturnAddress |Microsoft Docs
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
- IDiaStackWalkHelper2::searchForReturnAddress method
ms.assetid: 904223b1-6e26-4980-b310-d0b222cdbbbd
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4198202de5f66cc483c03738cfb9a56b2b8d98d9
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51780056"
---
# <a name="idiastackwalkhelpersearchforreturnaddress"></a>IDiaStackWalkHelper::searchForReturnAddress
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

搜索指定的堆栈帧的最接近的函数返回地址。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT searchForReturnAddress(   
   IDiaFrameData*  frame,  
   ULONGLONG*      returnAddress  
);  
```  
  
#### <a name="parameters"></a>参数  
 `frame`  
 [in][IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)对象，表示当前堆栈帧。  
  
 `returnAddress`  
 [out]返回最接近的函数返回地址。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)



