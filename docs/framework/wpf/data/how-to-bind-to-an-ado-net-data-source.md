---
title: 如何：绑定到 ADO.NET 数据源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to ADO.NET data sources
- ADO.NET data sources [WPF], binding to
- binding [WPF], to ADO.NET data sources
ms.assetid: a70c6d7b-7b38-4fdf-b655-4804db7c8315
ms.openlocfilehash: 774262b33ceda3e8881fb92bcbc70a3dd5361f39
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746643"
---
# <a name="how-to-bind-to-an-adonet-data-source"></a>如何：绑定到 ADO.NET 数据源
此示例演示如何将绑定[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<xref:System.Windows.Controls.ListBox>控制对[!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] `DataSet`。  
  
## <a name="example"></a>示例  
 在本示例中，`OleDbConnection` 对象用于连接到数据源，该数据源是在连接字符串中指定的 `Access MDB` 文件。 建立连接后，会创建一个 `OleDbDataAdpater` 对象。 `OleDbDataAdpater` 对象执行一个 select [!INCLUDE[TLA#tla_sql](../../../../includes/tlasharptla-sql-md.md)] 语句，以便从数据库中检索记录集。 通过调用 `OleDbDataAdapter` 的 `Fill` 方法，此 [!INCLUDE[TLA2#tla_sql](../../../../includes/tla2sharptla-sql-md.md)] 命令的结果存储在 `DataSet` 的 `DataTable` 中。 本示例中，`DataTable` 命名为 `BookTable`。 该示例然后设置<xref:System.Windows.FrameworkElement.DataContext%2A>的属性<xref:System.Windows.Controls.ListBox>到`DataSet`对象。  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 然后，我们可以绑定<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>的属性<xref:System.Windows.Controls.ListBox>到`BookTable`的`DataSet`:  
  
 [!code-xaml[ADODataSet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#2)]  
  
 `BookItemTemplate` 是<xref:System.Windows.DataTemplate>，它定义的数据显示方式：  
  
 [!code-xaml[ADODataSet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml#3)]  
  
 `IntColorConverter` 将 `int` 转换为颜色。 通过使用此转换器<xref:System.Windows.Controls.TextBlock.Background%2A>的第三个颜色<xref:System.Windows.Controls.TextBlock>显示为绿色如果的值`NumPages`否则是小于 350，红色。 此处未显示此转换器的实现。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Data.BindingListCollectionView>
- [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
