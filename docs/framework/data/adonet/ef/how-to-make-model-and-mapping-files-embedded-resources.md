---
title: 如何：创建模型及映射文件嵌入资源
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: 0fd7e4fe751fd05a8b48f3dee79d374f669917fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660341"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>如何：创建模型及映射文件嵌入资源
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ，你可以为应用程序的嵌入资源部署模型和映射文件。 包含嵌入模型和映射文件的程序集必须加载到实体连接所在的应用程序域中。 有关详细信息，请参阅[连接字符串](../../../../../docs/framework/data/adonet/ef/connection-strings.md)。 默认情况下，[!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]工具嵌入模型和映射文件。 手动定义模型和映射文件时，请使用下面的过程以确保文件作为嵌入资源与[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]应用程序一起部署。  
  
> [!NOTE]
>  若要维护嵌入资源，每次修改模型和映射文件时都必须重复此过程。  
  
### <a name="to-embed-model-and-mapping-files"></a>嵌入模型和映射文件  
  
1.  在中**解决方案资源管理器**，选择的概念 (.csdl) 文件。  
  
2.  在中**属性**窗格中，设置**生成操作**到**嵌入的资源**。  
  
3.  对存储文件 (.ssdl) 和映射文件 (.msl) 重复步骤 1 和步骤 2。  
  
4.  在中**解决方案资源管理器**，双击 App.config 文件，然后修改`Metadata`中的参数`connectionString`属性基于以下格式之一：  
  
    -   `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    -   `Metadata=` `res://*/<resourceName>;`  
  
    -   `Metadata=res://*;`  
  
     有关详细信息，请参阅[连接字符串](../../../../../docs/framework/data/adonet/ef/connection-strings.md)。  
  
## <a name="example"></a>示例  
 下面的连接字符串引用嵌入的模型和映射文件[AdventureWorks 销售模型](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)。 该连接字符串存储在项目的 App.config 文件中。  
  
  
  
## <a name="see-also"></a>请参阅
- [建模和映射](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [如何：定义连接字符串](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [如何：生成 EntityConnection 连接字符串](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- [ADO.NET 实体数据模型工具](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
