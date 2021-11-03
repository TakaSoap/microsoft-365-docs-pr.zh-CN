---
title: Office 365 URL 和 IP 地址范围
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/29/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 摘要：Office 365 需要连接到 Internet。对于使用 Office 365 计划（包括政府社区云 (GCC)）的客户，应该可以访问以下终结点。
hideEdit: true
ms.openlocfilehash: d223ec20be108cdcfa53a2357e95cccdf6474e69
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60700874"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL 和 IP 地址范围

Office 365 需要连接到 Internet。对于使用 Office 365 计划（包括政府社区云 (GCC)）的客户，应该可以访问以下终结点。
  
*Office 365 全球 （+GCC）* \| [由 21 Vianet 运营的 Office 365](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 Germany](microsoft-365-germany-endpoints.md) \| [Office 365 美国政府版 DoD](microsoft-365-u-s-government-dod-endpoints.md) \| [Office 365 美国政府版GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) \|

|备注|下载|用途|
|---|---|---|
|**上次更新时间：** 2021 年 10 月 29 日–![RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [更改日志订阅](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**下载：** 一个 [JSON 格式](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)列表中的所有必需和可选目标。|**使用：** 代理 [PAC 文件](managing-office-365-endpoints.md#pacfiles)|
|

从[管理 Office 365 终结点](managing-office-365-endpoints.md)开始了解我们使用此数据管理网络连接的建议。终结点数据视需要在每月月初更新，并在生效前 30 天发布新的 IP 地址和 URL。这允许尚未进行自动更新的客户在需要新连接之前完成其过程。如果需要解决支持提升、安全事件或其他即时操作要求，终结点也可以在月内更新。以下页面上显示的数据全部由基于 REST 的 Web 服务生成。如果使用脚本或网络设备访问此数据，应直接转到 [Web 服务](microsoft-365-ip-web-service.md)。

下面的终结点数据列出了从用户计算机到 Office 365 的连接要求。 有关用于从 Microsoft 到客户网络的网络连接（有时称为混合或入站网络连接）的 IP 地址的详细信息，请参阅[其他终结点](additional-office365-ip-addresses-and-urls.md)了解详细信息。

终结点分为四个服务区域，表示三个主要工作负荷和一组常用资源。 这些组可用于将流量流与特定应用程序相关联，但是，鉴于功能通常在多个工作负荷中使用终结点，这些组无法有效地用于限制访问。

显示的数据列是：

- **ID**：行的 ID 号，也称为终结点集。此 ID 与终结点集的 Web 服务返回的 ID 相同。

- **类别**：显示端点集是分类为“优化”、“允许”还是“默认”。若要了解这些类别及其管理指南，可以访问 [新 Office 365 端点类别](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)。此列还列出了哪些端点集必须有网络连接。对于不需要有网络连接的端点集，我们在此字段中提供了备注，以指明在端点集被阻止时会缺少什么功能。若要排除整个服务区域，则列出的必须有网络连接的端点集不需要连接。

- **ER**：如果使用带有 Office 365 路由前缀的 Azure ExpressRoute 支持终结点集，则为 **是**。包含所显示的路由前缀的 BGP 社区与列出的服务区域一致。当 ER 为 **否** 时，这意味着此终结点集不支持 ExpressRoute。但是，不应假设没有为 ER 为 **否** 的终结点集播发路由。

- **地址**：列出终结点集的 FQDN 或通配符域名以及 IP 地址范围。请注意，IP 地址范围采用 CIDR 格式，并且可能包含指定网络中的许多单独 IP 地址。

- **端口**：列出与地址合并以形成网络终结点的 TCP 或 UDP 端口。你会注意到 IP 地址范围中存在一些重复，其中列出了不同的端口。

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

> [!NOTE]
> 有关 Yammer IP 地址和 UR L的建议，请参阅 Yammer 博客上的[不建议为 Yammer 使用硬编码 IP 地址](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592)。

## <a name="related-topics"></a>相关主题

[Office 365 IP 地址和 URL Web 服务中未包含的其他终结点](additional-office365-ip-addresses-and-urls.md)

[管理 Office 365 终结点](managing-office-365-endpoints.md)

[通用 Microsoft Stream 终结点](/stream/network-overview#general-microsoft-stream-endpoints)
  
[监视 Microsoft 365 连接性](./monitor-connectivity.md)

[第三方应用程序系统中的根 CA 和中级 CA 捆绑](../compliance/encryption-office-365-certificate-chains.md)
  
[客户端连接](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[内容分发网络](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Microsoft Azure IP 范围和服务标签 – 公共云](https://www.microsoft.com/download/details.aspx?id=56519)

[Microsoft Azure IP 范围和服务标签 - 美国政府云](https://www.microsoft.com/download/details.aspx?id=57063)

[Microsoft Azure IP 范围和服务标签 – 德国云](https://www.microsoft.com/download/details.aspx?id=57064)

[Microsoft Azure IP 范围和服务标签 – 中国云](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft 公共 IP 空间](https://www.microsoft.com/download/details.aspx?id=53602)

[服务名称和传输协议端口号注册表](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
