---
title: 如何：使用 GridViewRowPresenter 来显示数据
ms.date: 03/30/2017
helpviewer_keywords:
- displaying data with GridViewRowPresenter [WPF]
- GridViewRowPresenter [WPF]
ms.assetid: bdb785a5-a262-44d5-a517-ea14383e5f70
ms.openlocfilehash: b60fe0e78883b166688377c42113a093c78d7751
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607954"
---
# <a name="how-to-display-data-by-using-gridviewrowpresenter"></a>如何：使用 GridViewRowPresenter 来显示数据
此示例演示如何使用<xref:System.Windows.Controls.GridViewRowPresenter>和<xref:System.Windows.Controls.GridViewHeaderRowPresenter>要在列中显示数据的对象。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定<xref:System.Windows.Controls.GridViewColumnCollection>，它显示<xref:System.DateTime.DayOfWeek%2A>并<xref:System.DateTime.Year%2A>的<xref:System.DateTime>使用的对象<xref:System.Windows.Controls.GridViewRowPresenter>和<xref:System.Windows.Controls.GridViewHeaderRowPresenter>对象。 该示例还定义了<xref:System.Windows.Style>有关<xref:System.Windows.Controls.GridViewColumn.Header%2A>的<xref:System.Windows.Controls.GridViewColumn>。  
  
 [!code-xaml[GridViewRowPresenterSample#GridViewRowPresenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewRowPresenterSample/CS/Window1.xaml#gridviewrowpresenter)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewColumnCollection>
- [GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)
