---
title: 'Idiasession:: Findlines |Microsoft Docs'
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
- IDiaSession::findLines method
ms.assetid: d6e84916-fd55-457e-b057-57f97b51fe73
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6f80912e66a7a4d355eefeb545aa40192ae7cc6
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51793134"
---
# <a name="idiasessionfindlines"></a>IDiaSession::findLines
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索指定的编译单位和源文件标识符中的行号。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT findLines (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `compiland`  
 [in][IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)对象，表示将编译单位。 使用此接口作为要在其中搜索的行号的上下文。  
  
 `file`  
 [in][IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)对象，表示要在其中搜索的行号的源文件。  
  
 `ppResult`  
 [out]返回[IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)检索包含的行号列表的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



