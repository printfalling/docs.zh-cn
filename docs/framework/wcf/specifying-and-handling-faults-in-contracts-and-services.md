---
title: 在协定和服务中指定和处理错误
ms.date: 03/30/2017
helpviewer_keywords:
- handling faults [WCF]
ms.assetid: a9696563-d404-4905-942d-1e0834c26dea
ms.openlocfilehash: e0a81915d35bc382cb4f51ec6d26a429c8a759c1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594923"
---
# <a name="specifying-and-handling-faults-in-contracts-and-services"></a>在协定和服务中指定和处理错误
Windows Communication Foundation (WCF) 应用程序处理错误情况下，通过将托管的异常对象映射到 SOAP 错误对象，并对托管的异常对象的 SOAP 错误对象。 本节中的主题讨论如何设计协定以将错误条件作为自定义 SOAP 错误公开、如何作为服务实现的一部分返回这些错误，以及客户端如何捕捉这些错误。  
  
## <a name="error-handling-overview"></a>错误处理概述  
 在所有托管应用程序中，处理错误由 <xref:System.Exception> 对象表示。 在基于 SOAP 的应用程序如 WCF 应用程序，服务方法进行通信使用 SOAP 错误消息的处理错误信息。 SOAP 错误是包括在服务操作元数据中的消息类型，因此会创建一个错误协定，客户端可使用该协定来使操作更加可靠或更具交互性。 此外，由于 SOAP 错误在客户端以 XML 格式表示，它是一个高度可互操作类型系统，可以使用任何 SOAP 平台上的客户端，增加的 WCF 应用程序。  
  
 因为在这两种错误系统下运行 WCF 应用程序，任何托管的异常信息都发送到客户端必须从在服务上的 SOAP 错误异常转换为，发送，而从 SOAP 错误转换为 WCF 客户端中的错误异常。 对于双工客户端，客户端协定还可以将 SOAP 错误发送回服务。 在任一种情况下，您都可以使用默认的服务异常行为，或者可以显式控制是否（以及如何）将异常映射到错误消息。  
  
 可以发送两种类型的 SOAP 错误：*声明*并*未声明*。 已声明的 SOAP 错误是指其中的某个操作具有 <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> 属性（用于指定自定义 SOAP 错误类型）的错误。 *未声明*操作的协定中未指定 SOAP 错误。  
  
 强烈建议服务操作使用 <xref:System.ServiceModel.FaultContractAttribute> 属性来声明其错误，以正式指定在正常操作过程中客户端应该可以接收的所有 SOAP 错误。 此外，还建议在 SOAP 错误中仅返回客户端必须了解的信息，以将信息泄露的风险降至最低。  
  
 通常，服务（以及双工客户端）使用下列步骤将错误处理成功地集成到其应用程序中：  
  
-   将异常条件映射到自定义 SOAP 错误。  
  
-   客户端和服务将 SOAP 错误作为异常进行发送和接收。  
  
 此外，WCF 客户端和服务可以出于调试目的使用未声明的 soap 错误，并可以扩展默认的错误行为。 下面的部分讨论这些任务和概念。  
  
## <a name="map-exceptions-to-soap-faults"></a>将异常映射到 SOAP 错误  
 创建用于处理错误条件的操作的第一步是：决定在什么条件下应向客户端应用程序通知有关错误的信息。 某些操作具有特定于其功能的错误条件。 例如，`PurchaseOrder` 操作可能会向不再允许其发起采购订单的用户返回特定信息。 在其他情况下（如 `Calculator` 服务），一个更宽泛的 `MathFault` SOAP 错误也许可以描述整个服务内的所有错误条件。 在标识服务客户端的错误条件之后，可以构造一个自定义 SOAP 错误，并可以将操作标记为在出现相应的 SOAP 错误条件时返回该 SOAP 错误。  
  
 开发您的服务或客户端的此步骤的详细信息，请参阅[定义和指定错误](../../../docs/framework/wcf/defining-and-specifying-faults.md)。  
  
## <a name="clients-and-services-handle-soap-faults-as-exceptions"></a>客户端和服务将 SOAP 错误作为异常进行处理  
 标识操作错误条件，定义自定义 SOAP 错误，并将这些操作为返回这些错误标记是成功进行错误处理 WCF 应用程序中的第一个步骤。 下一步是正确实现这些错误的发送和接收。 通常，服务会发送错误以通知客户端应用程序有关错误条件的情况，但是双工客户端也可以向服务发送 SOAP 错误。  
  
 有关详细信息，请参阅[Sending and Receiving Faults](../../../docs/framework/wcf/sending-and-receiving-faults.md)。  
  
## <a name="undeclared-soap-faults-and-debugging"></a>未声明的 SOAP 错误和调试  
 已声明的 SOAP 错误对于生成可靠的并可互操作的分布式应用程序非常有用。 但在某些情况下，服务（或双工客户端）发送未声明的 SOAP 错误（即在相应操作的 Web 服务描述语言 (WSDL) 中未提及的错误）也很有用。 例如，在开发服务时可能会出现意外情况，此时就可以将相关信息发送回客户端以方便调试。 此外，可以设置<xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>属性或<xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>属性设置为`true`允许 WCF 客户端以获取有关内部服务操作异常的信息。 中所述发送各个错误和设置调试行为属性都[Sending and Receiving Faults](../../../docs/framework/wcf/sending-and-receiving-faults.md)。  
  
> [!IMPORTANT]
>  因为托管的异常可以公开内部应用程序的信息，设置<xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>或<xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>到`true`可以允许 WCF 客户端获取有关内部服务操作异常，包括个人信息标识或其他敏感信息。  
>   
>  因此，建议将 <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> 或 <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> 设置为 `true` 仅用作一种临时调试应用程序的方法。 此外，以这种方式返回未处理的托管异常的方法的 WSDL 并不包含类型为 <xref:System.ServiceModel.FaultException%601> 的 <xref:System.ServiceModel.ExceptionDetail> 的协定。 客户端必须预见未知 SOAP 错误的可能性 (返回给 WCF 客户端作为<xref:System.ServiceModel.FaultException?displayProperty=nameWithType>对象) 以便正确获取调试信息。  
  
## <a name="customizing-error-handling-with-ierrorhandler"></a>使用 IErrorHandler 自定义错误处理  
 如果对于自定义在发生应用程序级别的异常时发送给客户端的响应消息有特殊需求，或者对于在返回响应消息之后执行某些自定义处理有特殊的要求，请实现 <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType> 接口。  
  
## <a name="fault-serialization-issues"></a>错误的序列化问题  
 在反序列化错误协定时，WCF 首先尝试将 SOAP 消息中的错误协定名称与错误协定类型相匹配。 如果找不到精确匹配项，它将按字母顺序在可用错误协定列表中搜索兼容类型。 如果两个错误协定是兼容类型（例如，一个是另一个的子类），则可能会使用错误类型对错误进行反序列化。 仅当错误协定未指定名称、命名空间和操作时，才会发生此状况。 若要防止此问题发生，则通过指定名称、命名空间和操作特性来始终完全限定错误协定。 此外，如果您定义了许多派生自共享基类的相关错误协定，请确保使用 `[DataMember(IsRequired=true)]` 标记所有新成员。 有关此 `IsRequired` 特性的更多信息，请参见 <xref:System.Runtime.Serialization.DataMemberAttribute>。 这将防止基类成为兼容类型，并强制将错误反序列化为正确的派生类型。  
  
## <a name="see-also"></a>请参阅
- <xref:System.ServiceModel.FaultException>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.FaultException>
- <xref:System.Xml.Serialization.XmlSerializer>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.CommunicationException>
- <xref:System.ServiceModel.FaultContractAttribute.Action%2A>
- <xref:System.ServiceModel.FaultException.Code%2A>
- <xref:System.ServiceModel.FaultException.Reason%2A>
- <xref:System.ServiceModel.FaultCode.SubCode%2A>
- <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>
- [定义和指定错误](../../../docs/framework/wcf/defining-and-specifying-faults.md)
