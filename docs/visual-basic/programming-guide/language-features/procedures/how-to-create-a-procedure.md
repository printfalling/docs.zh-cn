---
title: 如何：创建过程 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 06fed04a0ebe7a0b3111a94308d15d01bcf47c1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636529"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>如何：创建过程 (Visual Basic)
将起始的声明语句之间的过程 (`Sub`或`Function`) 和结束的声明语句 (`End Sub`或`End Function`)。 该过程的所有代码均位于这些语句之间。  
  
 过程不能包含另一个过程，使其开始和结束语句必须位于任何其他过程之外。  
  
 如果你有在不同的位置执行相同的任务的代码，您可以编写一次在过程中的任务，然后调用它从不同的位置在代码中。  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>若要创建一个过程，不会返回一个值  
  
1.  任何其他过程之外，使用`Sub`语句后, 跟`End Sub`语句。  
  
2.  在中`Sub`语句，请按照`Sub`关键字的过程，然后在括号中的参数列表的名称。  
  
3.  将过程的代码语句之间`Sub`和`End Sub`语句。  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>若要创建的过程将返回一个值  
  
1.  任何其他过程之外，使用`Function`语句后, 跟`End Function`语句。  
  
2.  在中`Function`语句，请按照`Function`关键字的过程，然后在括号中的参数列表的名称，然后`As`子句，用于指定返回值的数据类型。  
  
3.  将过程的代码语句之间`Function`和`End Function`语句。  
  
4.  使用`Return`语句以返回到调用代码的值。  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>若要连接用旧的重复的块的代码的新过程  
  
1.  请确保你在旧代码有权访问其中的位置来定义新过程。  
  
2.  在旧的重复代码块中，将为执行重复任务使用的单个语句的调用的语句`Sub`或`Function`过程。  
  
3.  如果您的过程是`Function`返回一个值，请确保调用语句中执行的操作的返回值，例如将其存储在变量中，否则将丢失的值。  
  
## <a name="example"></a>示例  
 以下`Function`过程计算的最长边或斜边的直角三角形而言，其他两个方面为给定的值。  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a>请参阅

- [过程](./index.md)
- [Sub 过程](./sub-procedures.md)
- [Function 过程](./function-procedures.md)
- [属性过程](./property-procedures.md)
- [运算符过程](./operator-procedures.md)
- [过程参数和自变量](./procedure-parameters-and-arguments.md)
- [递归过程](./recursive-procedures.md)
- [过程重载](./procedure-overloading.md)
- [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [面向对象的编程 (Visual Basic)](../../concepts/object-oriented-programming.md)
