---
title: 'Idiasourcefile:: Get_checksum |Microsoft Docs'
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
- IDiaSourceFile::get_checksum method
ms.assetid: aad63a7e-4e22-44e4-8a5b-81b5174ced1e
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: efbbd3b7e77de6d1124e04132dbf55dbfffa8871
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51783228"
---
# <a name="idiasourcefilegetchecksum"></a>IDiaSourceFile::get_checksum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索的校验和字节数。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_checksum (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cbData`  
 [in]数据缓冲区，以字节为单位的大小。  
  
 `pcbData`  
 [out]返回校验和字节数。 此参数不能为`NULL`。  
  
 `data`  
 [in、 out]使用校验和字节填充缓冲区。 如果此参数为`NULL`，然后`pcbData`返回所需的字节数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 若要确定用于生成校验和字节的校验和算法的类型，请调用[idiasourcefile:: Get_checksumtype](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)方法。  
  
 从源代码文件的映像通常生成校验和，因此源文件中的更改会反映在校验和字节中的更改。 如果不匹配的校验和字节生成从加载的图像的文件，则应被视为该文件的校验和损坏或被篡改。  
  
 典型的校验和不会超过 32 个字节的大小，但不要认为这是最大大小的校验和。 设置`data`参数`NULL`获取检索校验和所需的字节数。 然后分配适当大小的缓冲区并调用此方法一次使用新的缓冲区。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)



