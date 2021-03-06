---
title: 如何：将列添加到 Windows 窗体 ListView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: eed032ec0bacd50666c30979b33362dabf00d565
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700190"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a>如何：将列添加到 Windows 窗体 ListView 控件
在详细信息视图中，<xref:System.Windows.Forms.ListView>控件可以显示每个列表项的多个列。 列可用于向用户显示多种类型的每个列表项的相关信息。 例如，文件的列表可以显示文件名、 文件类型、 大小和文件的上次修改的日期。 有关在创建后填充列的信息，请参阅[如何：在具有 Windows 的列中显示子项窗体 ListView 控件](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)。  
  
### <a name="to-add-columns-programmatically"></a>若要以编程方式添加列  
  
1.  设置控件的<xref:System.Windows.Forms.ListView.View%2A>属性设置为<xref:System.Windows.Forms.View.Details>。  
  
2.  使用<xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A>方法的列表视图<xref:System.Windows.Forms.ListView.Columns%2A>属性。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.ListView>
- [ListView 控件](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [ListView 控件概述](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
