---
title: Erase 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: cab3da4465b4671d203036c2d9bcd40662dc234a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522435"
---
# <a name="erase-statement-visual-basic"></a>Erase 语句 (Visual Basic)
用于释放数组变量并解除分配用于其元素的内存。  
  
## <a name="syntax"></a>语法  
  
```  
Erase arraylist  
```  
  
## <a name="parts"></a>部件  
 `arraylist`  
 必需。 要清除的数组变量的列表。 以逗号分隔多个变量。  
  
## <a name="remarks"></a>备注  
 `Erase`语句只能出现在过程级别。 这意味着，你可以释放过程内，但不能在类或模块级别的数组。  
  
 `Erase`语句是等效于分配`Nothing`到每个数组变量。  
  
## <a name="example"></a>示例  
 下面的示例使用`Erase`语句清除两个数组并释放其内存 (1000年和 100 个存储元素分别)。 `ReDim`然后语句将新的数组实例分配给三维数组。  
  
 [!code-vb[VbVbalrStatements#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/erase-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅
- [Nothing](../../../visual-basic/language-reference/nothing.md)
- [ReDim 语句](../../../visual-basic/language-reference/statements/redim-statement.md)
