---
title: 如何：向绘图应用 GuidelineSet
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 4bd2ee349f2c1855a9af6b4c00f2630cd50a9108
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493373"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>如何：向绘图应用 GuidelineSet
此示例演示如何将应用<xref:System.Windows.Media.GuidelineSet>到<xref:System.Windows.Media.DrawingGroup>。  
  
 <xref:System.Windows.Media.DrawingGroup>类是唯一的类型<xref:System.Windows.Media.Drawing>具有<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>属性。 若要将应用<xref:System.Windows.Media.GuidelineSet>为另一种<xref:System.Windows.Media.Drawing>，将其添加到<xref:System.Windows.Media.DrawingGroup>，然后应用<xref:System.Windows.Media.GuidelineSet>到你<xref:System.Windows.Media.DrawingGroup>。  
  
## <a name="example"></a>示例  
 下面的示例创建两个<xref:System.Windows.Media.DrawingGroup>对象的几乎完全相同; 唯一的区别是： 第二个<xref:System.Windows.Media.DrawingGroup>具有<xref:System.Windows.Media.GuidelineSet>和第一个却没有。  
  
 下图显示该示例的输出。 因为之间的两个的呈现差别<xref:System.Windows.Media.DrawingGroup>对象很小，因此放大绘图的各个部分。  
  
 ![具有和没有 GuidelineSet 的 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
