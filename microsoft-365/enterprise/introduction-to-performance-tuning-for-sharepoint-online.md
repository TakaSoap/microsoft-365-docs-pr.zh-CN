---
title: SharePoint Online 性能调整简介
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: 本文介绍了在 SharePoint Online 中设计页面时需要考虑的特定方面。
ms.openlocfilehash: deabb059e2121743b35d5519e4b8684a08dd28b4
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807232"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>SharePoint Online 性能优化简介

本文介绍了在 SharePoint Online 中设计页面时需要考虑的特定方面。
     
## <a name="sharepoint-online-metrics"></a>SharePoint Online 指标

SharePoint Online 的以下广泛指标提供有关性能的实际数据：
  
- 页面加载速度
    
- 每页需要多少个往返行程
    
- 服务问题
    
- 导致性能降低的其他情况
    
### <a name="conclusions-reached-because-of-the-data"></a>由于数据而得出结论

数据告诉我们：
  
- 大多数页面在 SharePoint Online 上运行良好。
    
- 非自定义页面加载速度很快。
    
- OneDrive for Business、工作组网站和系统页面（如_layouts等）都可以快速加载。
    
- 最慢的 1% SharePoint Online 页面的加载时间超过 5，000 毫秒。
    
可以使用的一个简单的基准测试是，通过将您自己的门户的加载时间与 OneDrive for Business 主页的加载时间进行比较来测量性能，因为它使用很少的自定义功能。 这通常是在解决网络性能问题时支持会要求你完成的第一步。
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>检查性能时使用标准用户帐户

网站集管理员、网站所有者、编辑者或参与者属于另一个安全组，具有更多权限，因此具有可SharePoint加载的额外元素。
  
这适用于本地SharePoint和 SharePoint Online，但在本地方案中，差异不会像 SharePoint Online 中一样容易注意到。
  
为了正确评估页面将如何为用户执行，您应该使用标准用户帐户以避免加载创作控件和安全组相关的额外流量。
  
## <a name="connection-categories-for-performance-tuning"></a>用于性能调整的连接类别

可以将服务器和用户之间的连接分为三个主要组件。 在设计联机页面时SharePoint这些页面，以深入了解加载时间。
  
- **服务器** Microsoft 在数据中心托管的服务器。
    
- **网络** 数据中心和用户之间的 Microsoft 网络、Internet 和本地网络。
    
- **浏览器** 页面的加载位置。
    
在这三个连接中，通常有五个原因会导致 95% 的页面变慢。 本文将讨论其中每个原因：
  
- 导航问题
    
- 内容汇总
    
- 大文件
    
- 对服务器的许多请求
    
- Web 部件处理
    
### <a name="server-connection"></a>服务器连接

影响本地部署SharePoint的很多问题也适用于 SharePoint Online。
  
正如您预期，您可以更加控制服务器使用本地部署SharePoint。 使用 SharePoint Online，内容会有所不同。 服务器执行的工作越多，呈现页面所花的时间越长。 使用SharePoint，这一方面的最大原因就是包含多个 Web 部件的复杂页面。
  
SharePoint本地服务器
  
![本地服务器的屏幕截图。](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![联机服务器的屏幕截图。](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
使用 SharePoint Online，某些页面请求可能最终调用多个服务器。 最终，您可以为单个请求在服务器之间创建一个请求矩阵。 从页面加载的角度来看，这些交互成本很高，并且会使情况变慢。
  
这些服务器到服务器交互的示例如下：
  
- Web 到 SQL 服务器
    
- Web 到应用程序服务器
    
另一个会降低服务器交互速度的方面是缓存丢失。 与本地SharePoint不同，您很有可能命中之前访问的页面的同一服务器;这使得对象缓存过时。
  
### <a name="network-connection"></a>网络连接

对于不使用 WAN SharePoint本地服务器，您可以在数据中心和最终用户之间使用高速连接。 通常，从网络角度来看，管理内容很容易。
  
对于 SharePoint Online，还有一些要考虑的因素;例如：
  
- Microsoft 网络
    
- The Internet
    
- The ISP
    
无论使用哪个SharePoint (以及) 网络，通常会导致网络繁忙的事情包括：
  
- 大型负载
    
- 许多文件
    
- 与服务器的物理距离较大
    
Microsoft SharePoint Online 中可以使用的一CDN (内容分发网络) 。 一CDN基本上是跨多个数据中心部署的服务器的分布式集合。 使用 CDN，页面上的内容可以托管在靠近客户端的服务器上，即使客户端与原始 SharePoint 服务器很远。 Microsoft 将在未来使用此功能来存储无法自定义的页面的本地实例，例如 SharePoint Online 管理员主页。 有关 CDN 详细信息，请参阅内容 [交付网络](content-delivery-networks.md)。
  
需要注意但可能无法执行很多工作的是 ISP 的连接速度。 简单的速度测试工具将告知你连接速度。
  
### <a name="browser-connection"></a>浏览器连接

从性能角度考虑 Web 浏览器有几个因素。
  
访问复杂页面会影响性能。 大多数浏览器只有一个小 (大约 90 MB) ，而平均网页通常约为 1.6 MB。 这不会花很长时间就用不上。
  
带宽也可能成为问题。 例如，如果用户在另一个会话中观看视频，这将影响你的SharePoint性能。 虽然无法阻止用户流式传输媒体，但可以控制页面加载用户的方式。
  
请查看以下文章，了解不同的 SharePoint Online 页面自定义技术和其他最佳做法，以帮助你实现最佳性能。
  
- [SharePoint Online 的导航选项](navigation-options-for-sharepoint-online.md)
    
- [使用适用于 SharePoint Online 的页面诊断工具](page-diagnostics-for-spo.md)
    
- [SharePoint Online 的图像优化](image-optimization-for-sharepoint-online.md)
    
- [在 SharePoint Online 中延迟加载图像和 JavaScript](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [SharePoint Online 中的缩小和捆绑](minification-and-bundling-in-sharepoint-online.md)
    
- [结合使用 Office 365 内容分发网络和 SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [使用内容Web 部件而不是内容Web 部件来改进 SharePoint Online 中的性能](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [容量规划和负载测试 SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [诊断 SharePoint Online 性能问题](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [在 SharePoint Online 中使用对象缓存](using-the-object-cache-with-sharepoint-online.md)
    
- [如何：避免在 SharePoint Online 中受限制或被阻止](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
