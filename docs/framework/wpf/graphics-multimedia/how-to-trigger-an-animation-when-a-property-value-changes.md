---
title: 如何：在属性值更改时触发动画
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: 2be85a9ae93d504d98930468ad2e257385e835f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705292"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a>如何：在属性值更改时触发动画
此示例演示如何使用<xref:System.Windows.Trigger>以启动<xref:System.Windows.Media.Animation.Storyboard>属性值更改时。 可以使用<xref:System.Windows.Trigger>内<xref:System.Windows.Style>， <xref:System.Windows.Controls.ControlTemplate>，或<xref:System.Windows.DataTemplate>。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Trigger>进行动画处理<xref:System.Windows.UIElement.Opacity%2A>的<xref:System.Windows.Controls.Button>时其<xref:System.Windows.UIElement.IsMouseOver%2A>属性将成为`true`。  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 应用属性的动画<xref:System.Windows.Trigger>对象的行为以更复杂的方式比<xref:System.Windows.EventTrigger>动画开始使用<xref:System.Windows.Media.Animation.Storyboard>方法。  在"切换"时使用动画定义由其他<xref:System.Windows.Trigger>对象，但是在编写使用<xref:System.Windows.EventTrigger>和方法触发的动画。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Trigger>
- [属性动画技术概述](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
- [演示图板概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
