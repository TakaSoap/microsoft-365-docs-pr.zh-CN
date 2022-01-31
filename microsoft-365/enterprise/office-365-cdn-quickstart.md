---
title: Office 365 内容分发网络 (CDN) 快速入门
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 01/13/2022
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 内容分发网络 (CDN) 快速入门
ms.openlocfilehash: b0684fdfd8583ae6780cb23d47dc697582ae133b
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281431"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 内容分发网络 (CDN) 快速入门

可以使用内置 Office 365 内容分发网络 (CDN) 来托管静态资产 (图像、JavaScript、样式表、WOFF) ，为 SharePoint Online 页面提供更好的性能。 Office 365 CDN 将静态资产缓存到距离请求这些资产的浏览器更近的位置，这样可以加快下载速度并减少延迟，进而提高性能。 此外，Office 365 CDN使用 HTTP/2 协议改进压缩和 HTTP 管道传输。 Office 365 CDN 服务被归入 SharePoint Online 订阅。

有关更详细的信息指南，请参阅[将 Office 365 内容分发网络 (CDN) 与 SharePoint Online 一起使用](use-microsoft-365-cdn-with-spo.md)。

>[!NOTE]
>此Office 365 CDN仅适用于全球云中生产 (租户) 租户。 美国政府、中国德国云中的租户当前不支持Office 365 CDN。

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>使用页面诊断 for SharePoint 工具识别不在页面CDN

您可以使用 SharePoint 工具浏览器扩展的页面诊断轻松列出 SharePoint Online 页面中可添加到 CDN 资源。

**SharePoint** 页面诊断工具是新的 Microsoft Edge (<https://www.microsoft.com/edge>) 和 Chrome 浏览器的浏览器扩展，可分析 SharePoint Online 新式门户和经典发布网站页面。 该工具对已分配的每个页面提供一个报告，其中显示根据一组定义的性能条件得出的页面性能情况。 要安装和了解适用于 SharePoint 的页面诊断工具，请参阅[使用适用于 SharePoint Online 的页面诊断工具](./page-diagnostics-for-spo.md)。

当您在 SharePoint Online 页面上运行 SharePoint 页面诊断工具时，可单击"诊断测试"选项卡以查看未由 CDN 托管的资产列表。 这些资产将列在标题"内容分发网络 (CDN) **检查"** 下，如下面的屏幕截图所示。

![页面诊断。](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>页面诊断工具仅适用于 SharePoint Online，无法用于 SharePoint 系统页面。

## <a name="cdn-overview"></a>CDN概述

此 Office 365 CDN 旨在通过在高速全局网络中分发经常访问的对象（如图像和 javascript 文件）来优化用户性能，从而减少页面加载时间，并尽可能为用户提供对托管对象的访问。 the CDN fetches your assets from a location called an _origin_. 源可以是 URL SharePoint访问的文档网站、文档库或文件夹。

该Office 365 CDN分为两种基本类型：

- **公共 CDN** 旨在用于 JS (JavaScript) 、CSS (StyleSheets) 、Web 字体文件 (WOFF、WOFF2) 以及公司徽标等非专有图像。
- **专用CDN** 用于 PNG (JPG、JPEG 等图像) 。

你可以选择同时为组织提供公共源或专用源。 大多数组织都将选择实施这两者的组合。 公共和专用选项都提供相似的性能提升，但每个选项都有独特的属性和优点。 有关公用源和专用源CDN，请参阅选择每个源[是公共源还是私有源](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>如何使用默认配置CDN公用和专用服务器
在更改租户策略设置CDN，应验证它是否符合组织的合规性、安全性和隐私策略。

有关更详细的配置设置，或者如果你已启用 CDN 并且想要添加其他位置 (源) ，请参阅使用 [SharePoint Online](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) 命令行管理程序设置和配置 Office 365 CDN 部分

连接命令行管理程序SharePoint租户：

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

若要使组织能够将公用源和专用源与默认配置一同使用，请键入以下命令：

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

这些 cmdlet 的输出应如下所示：

![Set-SPOTenantCdnEnabled 的输出。](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>另请参阅

[使用适用于 SharePoint Online 的页面诊断工具](./page-diagnostics-for-spo.md)

[结合使用 Office 365 内容分发网络和 SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[内容分发网络](./content-delivery-networks.md)

[Office 365 网络计划和性能优化](./network-planning-and-performance.md)

[SharePoint性能系列 - Office 365 CDN视频系列](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
