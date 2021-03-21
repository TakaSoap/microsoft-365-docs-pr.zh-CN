---
title: Office 365 视频网络常见问题
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: 查找有关带宽规划、加密以及服务如何利用内容交付网络& CDN 等最常见的 (问题的答案) 。
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921566"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Office 365 视频网络常见问题

Office 365 视频存储库和流式处理服务使在组织中存储和流式传输视频变得简单。 关于[Office 365 视频有很多很好的信息](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50);此网络常见问题解答旨在回答有关带宽规划、加密以及服务如何利用内容交付网络和 CDN (最常见的) 。 [](content-delivery-networks.md)
  
如果还没有完全了解上传或播放视频时会发生什么情况，请观看我们放在一起的视频，上传到 [Office 365](https://www.youtube.com/watch?v=HXSZ0jYBKlM)视频时视频文件会发生什么情况。
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Office 365 视频带宽要求是什么？

有许多受支持的 [视频格式](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) 可以上载到 Office 365。 然后，将每个视频文件编码为具有多个不同视频质量的标准格式进行播放。 Office 365 视频使用自适应比特率流，根据可用网络带宽和视频播放器的大小选择最佳的视频播放质量。 为此，播放器最初请求最低播放质量。 然后，该服务开始向视频播放器发送 2 秒的视频段。 然后，玩家可以基于每个段的传送速度请求较高或更低的播放质量。
  
自适应比特率流在后台执行所有这些操作，同时视频播放中断或缓冲最少。 在视频播放期间，视频播放器允许查看器手动覆盖自动播放质量，以选择特定的视频播放质量。
  
下面是一个快速表，其中概述了每个视频播放质量的网络要求。 每个人播放视频所需的最小带宽为 802Kbps。
  
| 播放质量 | 网络速度 |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1.2 Mbps  <br/> |
|576p  <br/> |2.5 Mbps  <br/> |
|720p  <br/> |3.8 Mbps  <br/> |

 ([返回顶部) ](office-365-video-networking-faq.md)
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>内容交付网络 (CDN 如何) 视频播放？

如果同一地理位置内同一组织的多个人员正在流式传输 (视频) ，CDN 将在离该地理区域更近的位置存储这些视频的副本。 存储视频或将视频缓存在最靠近的位置后，每个人都会从离他们最近的位置流式传输视频，而不是从远离的位置流式传输视频。 Office 365 视频使用 Azure 媒体服务管理 Azure CDN 中缓存的内容以及缓存时间。 Azure 媒体服务可以使用任何 [Azure CDN](/azure/cdn/cdn-pop-locations) 位置在几天内缓存视频片段和清单。 如果组织成员继续观看缓存的视频，他们将留在缓存中。 如果在几天内没有人访问视频，视频最终会从缓存中删除。 下次有人尝试观看视频时，它将再次缓存在最近的 CDN 位置。
  
当内容缓存在附近的 CDN 上时尝试观看视频的每个人都受益于距离视频更近，并且在大多数情况下，跃点数较少。 这将提高视频播放速度;但是，它不会更改播放视频的网络要求。
  
> [!NOTE]
> 在某些情况下，例如达到容量限制，在达到三天之前可能会删除视频。
  
 ([返回顶部) ](office-365-video-networking-faq.md)
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>能否在本地缓存视频以加快播放速度？

是。 Office 365 不会阻止你使用本地 CDN 或缓存代理将视频或其他 Office 365 内容引入本地网络，以加快访问速度。 有几种方法可以网络上实现本地缓存解决方案，最常见的方法是使用在本地缓存内容的代理解决方案。 代理或专用 CDN 缓存视频片段和清单后，通过代理或专用 CDN 路由的文件的未来请求会从本地缓存提取，而不是从 Internet 位置提取。 在规划类似这样的解决方案时，请考虑网络带宽、容量和视频播放并发。
  
 ([返回顶部) ](office-365-video-networking-faq.md)
  
## <a name="how-videos-are-encrypted-and-secured"></a>视频是如何加密和安全的？

Office 365 视频了解保护数据安全和隐私非常重要。 [Microsoft 信任](https://products.office.com/business/office-365-trust-center-welcome) 中心介绍了我们对内容的隐私和安全性的承诺。 通过视频播放，速度对于获得良好的体验非常重要;但是，我们不会为了速度而损害你的安全或隐私。 下面我们是如何适应速度、安全性和隐私的。
  
当你或你组织中的某人上载新视频时，该视频会转码、使用 AES-128 加密进行加密并存储在 Azure 媒体服务中。 这意味着视频在传输过程中和处于其余时间都进行加密。
  
当贵组织中有人尝试观看新视频时，他们会按照以下步骤操作：
  
1. 询问 SharePoint Online 他们是否有权观看视频。

2. SharePoint Online 使用文件权限来确定用户能否观看视频。

3. 如果允许，SharePoint Online 会从 Azure 检索令牌，以向视频播放器提供令牌。

4. 然后，视频播放器使用该令牌从 Azure 请求解密密钥。

5. 有了解密密钥，视频播放器可以流式传输视频。

![O365 视频播放](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
 ([返回顶部) ](office-365-video-networking-faq.md)
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>播放 Office 365 视频有什么要求？

Office 365 视频支持的操作系统和 Web 浏览器与 [Office 365](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45)系统要求中的 SharePoint Online 要求相同。 根据你拥有的操作系统和 Web 浏览器配置，将确定视频播放器的特定需求。 以下是有关视频播放 [要求的信息](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)。
  
 ([返回顶部) ](office-365-video-networking-faq.md)
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>无法让 Office 365 视频正常工作，应从何处开始？

Office 365 视频连接疑难解答涉及网络疑难解答、ISP () 和 Office 365 配置。 首先需要服务运行状况仪表板。 这会告诉您 Office 365 视频是否出现问题。 如果一切看起来都不错，下面提供了一些其他资源来帮助你。
  
- 确保你可以连接到 [Office 365 视频所需的网络终结点](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)。

- 使用 Office [365](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)网络疑难解答指南 检查网络连接。

- 请参阅 [我们在慢速网络上使用 Office 365 的最佳实践](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)。

- [查找有关 Office 365 视频配置的帮助](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)。

 ([返回顶部) ](office-365-video-networking-faq.md)
  
## <a name="office-365-video-resources"></a>Office 365 视频资源

下面是帮助您成功部署和使用 Office 365 视频的一些其他资源：
  
[查找有关 Office 365 视频配置的帮助](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[“了解 Office 365”视频](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[在 Office 365 视频中创建和管理频道](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[管理 Office 365 视频门户](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[在 Office 365 视频中工作的视频格式](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
 ([返回顶部) ](office-365-video-networking-faq.md)
  
以下是可以用于返回的简短链接：[https://aka.ms/video365networkfaq]()