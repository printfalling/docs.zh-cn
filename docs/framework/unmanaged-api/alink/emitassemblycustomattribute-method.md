---
title: EmitAssemblyCustomAttribute 方法
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b4909ae23d077ee079e062d0252dbf1ee11663c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538825"
---
# <a name="emitassemblycustomattribute-method"></a>EmitAssemblyCustomAttribute 方法
调用以设置程序集级别自定义属性。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
#### <a name="parameters"></a>参数  
 `AssemblyID`  
 程序集的 ID。  
  
 `FileToken`  
 定义该属性的文件。 可以为 NULL，如果`AssemblyID`并不表示未绑定的 netmodule。  
  
 `tkType`  
 自定义特性的类型。  
  
 `pCustomValue`  
 自定义值的数据。  
  
 `cbCustomValue`  
 自定义值数据的长度。  
  
 `bSecurity`  
 如果自定义特性与程序集签名，则为 TRUE。  
  
 `bAllowMulti`  
 如果要在发出多个属性，则为 TRUE。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h  
  
## <a name="see-also"></a>请参阅
- [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
