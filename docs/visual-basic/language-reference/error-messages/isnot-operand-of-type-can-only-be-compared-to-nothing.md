---
title: '&#39;IsNot&#39;类型的操作数&#39;typename&#39;仅可与比较&#39;Nothing&#39;，因为&#39;typename&#39;为 null 的类型'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 65b04c85bccd169bbb2eea847d7b8af96c1a292f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505713"
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39;IsNot&#39;类型的操作数&#39;typename&#39;仅可与比较&#39;Nothing&#39;，因为&#39;typename&#39;为 null 的类型
声明为可以为 null 的变量进行了比较表达式以外`Nothing`使用`IsNot`运算符。  
  
 **错误 ID:** BC32128  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  要将可以为 null 的类型和表达式进行比较（而不是使用 `Nothing` 运算符比较 `IsNot` ），请调用可以为 null 的类型中的 `GetType` 方法并将结果与表达式进行比较，如下面的示例所示。  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>请参阅
- [可以为 null 的值类型](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [IsNot 运算符](../../../visual-basic/language-reference/operators/isnot-operator.md)
