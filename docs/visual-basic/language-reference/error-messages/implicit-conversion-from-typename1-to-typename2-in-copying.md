---
title: 从隐式转换&#39; &lt;typename1&gt; &#39;到&#39; &lt;typename2&gt; &#39;的值复制&#39;ByRef&#39;参数&#39; &lt;parametername&gt; &#39;返回到匹配的参数。
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 9f05a5fbcbef828b4ffa920d8cade475cedb64d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537227"
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>从隐式转换&#39; &lt;typename1&gt; &#39;到&#39; &lt;typename2&gt; &#39;的值复制&#39;ByRef&#39;参数&#39; &lt;parametername&gt; &#39;返回到匹配的参数。
与调用了过程[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)比其对应的参数的不同类型的参数。  
  
 如果传递参数`ByRef`，Visual Basic 有时会将参数值复制到本地变量中而不是传递一个引用，该过程。 在这种情况下，当过程返回时，Visual Basic 必须然后将本地变量值复制回调用代码中的参数。  
  
 如果将 `ByRef` 实参值复制到过程中，并且实参与形参为同一类型，则不必进行转换。 但如果类型不同，必须将 Visual Basic 转换两个方向。 因为不能使用`CType`或任何其他转换关键字上过程自变量或参数，此类转换始终是隐式。  
  
 默认情况下，此消息是一个警告。 有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。  
  
 **错误 ID:** BC41999  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果可能，请与过程参数，使用相同类型的调用参数，因此 Visual Basic 不需要执行任何转换。  
  
-   如果需要调用实参类型与形参类型不同的过程，但不需要将值返回到调用实参中，请将形参定义为 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 而不是 `ByRef`。  
  
## <a name="see-also"></a>请参阅
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [过程参数和自变量](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [按值和按引用传递自变量](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [隐式转换和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
