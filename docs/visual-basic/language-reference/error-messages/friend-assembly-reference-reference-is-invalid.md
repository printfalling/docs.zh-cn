---
title: 友元程序集引用&lt;引用&gt;无效
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: cdedcc18aa82f6efd8c52cdca5d915d7d78e269f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611925"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a>友元程序集引用&lt;引用&gt;无效
友元程序集引用\<引用 > 无效。 用强名称签名的程序集必须在他们的 InternalsVisibleTo 声明中指定一个公钥。  
  
 程序集名称传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>属性构造函数将识别的强名称的程序集，但它不包括`PublicKey`属性。  
  
 **错误 ID:** BC31535  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  确定强名称的友元程序集的公钥。 将公钥包含为程序集名称的一部分传递给<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>特性构造函数通过使用`PublicKey`属性。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Reflection.AssemblyName>
- [友元程序集](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


