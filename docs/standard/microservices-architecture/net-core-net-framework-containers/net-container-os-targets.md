---
title: 使用 .NET 容器时定位的操作系统
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 使用 .NET 容器时定位的操作系统
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: f6a5cf8d5e32e527977b7c142f5686310e88a068
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147195"
---
# <a name="what-os-to-target-with-net-containers"></a>使用 .NET 容器时定位的操作系统

由于 Docker 支持多种操作系统，且鉴于 .NET Framework 和 .NET Core 之间的差异，应根据所使用的框架，面向特定操作系统和特定版本。

对于 Windows，可使用 Windows Server Core 或 Windows Nano Server。 这两种 Windows 版本分别提供 .NET Framework 和 .NET Core 各自所需的特征（Windows Server Core 中的 IIS 与 Nano Server 中自承载的 web 服务器，如 Kestrel）。

对于 Linux，正式的 .NET Docker 映像（如 Debian）中提供并支持多个发行版本。

图 3-1 显示基于所使用的 .NET framework，可使用的操作系统版本。

![部署旧的 .NET Framework 应用程序时，必须针对与旧应用程序和 IIS 兼容且具有更大映像的 Windows Server Core。 部署 .NET Core 应用程序时，可以针对已经过云优化、使用 Kestrel、更小且启动速度更快的 Windows Nano Server。 还可以面向 Linux，支持 Debian、Alpine 和其他操作系统。 也使用 Kestrel、更小且启动速度更快。](./media/image1.png)

**图 3-1。** 根据 .NET framework 确定要面向的操作系统

如果想使用不同的 Linux 发行版本或要使用 Microsoft 不支持的映像版本，还可以创建自己的 Docker 映像。 例如，可以使用 ASP.NET Core 创建一个在传统 .NET Framework 和 Windows Server Core 上运行的映像，但这不是常见的 Docker 方案。

将映像名称添加到 Dockerfile 文件后，可根据所使用的标记选择操作系统和版本，如下例所示：

<table>
<thead>
<tr class="header">
<th>图像</th>
<th>注释</th>
</tr>
</thead>
<tbody>
<tr>
<td>microsoft/dotnet:2.1-runtime</td>
<td>.NET Core 2.1 多体系结构：支持 Linux 和 Windows Nano Server，具体取决于 Docker 主机。</td>
</tr>
<tr class="odd">
<td>microsoft/dotnet:2.1-aspnetcore-runtime</td>
<td><p>ASP.NET Core 2.1 多体系结构：支持 Linux 和 Windows Nano Server，具体取决于 Docker 主机。</p>
<p>ASP.NET Core 的 aspnetcore 映像具有多个优化。</p></td>
</tr>
<tr class="even">
<td>microsoft/dotnet:2.1-aspnetcore-runtime-alpine</td>
<td>.NET Core 2.1 运行时 - 仅在 Linux Alpine 发行版上</td>
</tr>
<tr class="odd">
<td>microsoft/dotnet:2.1-aspnetcore-runtime-nanoserver-1803</td>
<td>.NET Core 2.1 运行时 - 仅在 Windows Nano Server（Windows Server 版本 1803）上</td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
>[上一页](container-framework-choice-factors.md)
>[下一页](official-net-docker-images.md)