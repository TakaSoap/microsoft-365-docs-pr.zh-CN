---
title: Office 365美国政府 DOD 终结点
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 02/28/2022
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: 5d7dce60-4892-4b58-b45e-ee42fe8a907f
f1.keywords:
- NOCSH
description: Office 365 要求连接到 Internet。 以下终结点应仅适用于使用美国政府 doD Office 365客户。
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 000ae3590b0c99b59f557e6b70deaa60649054a6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325625"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365美国政府 DoD 终结点

*适用于：Office 365 Admin*

Office 365 要求连接到 Internet。 以下终结点应仅适用于使用美国政府 doD Office 365客户。
  
**Office 365终结点**：全球 ([GCC)](urls-and-ip-address-ranges.md) \| Office 365 由 [21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| *Office 365 美国政府 doD Office 365 美国政府 doD* \| GCC [运营](microsoft-365-u-s-government-gcc-high-endpoints.md)

<br>

****

|备注|下载|
|---|---|
|**Last updated：** 02/28/2022 - ![RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [更改日志订阅](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**下载：**[JSON 格式的完整列表](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|
|

通过 [管理 Office 365 终结点](managing-office-365-endpoints.md) 开始，以了解我们针对使用此数据管理网络连接性的建议。 在每月开始时，以活动前 30 天发布的新 IP 地址和 URL 按需更新终结点数据。 这使尚未自动更新的客户可以在需要新连接前完成其流程。 如果需要解决支持升级、安全事故或其他紧急操作需求，也可在当月更新终结点。 此页下方显示的数据全部基于 REST 的 web 服务生成。 如果正在使用脚本或网络设备访问此数据，应直接转到 [Web 服务](microsoft-365-ip-web-service.md)。

下面的终结点数据列出了从用户计算机到 Office 365 的连接要求。 它不包括从 Microsoft 到客户网络的网络连接，有时称为混合或入站网络连接。 有关详细信息，请参阅 [Web 服务中未包含的其他终结点](additional-office365-ip-addresses-and-urls.md)。

终结点分为四个服务区域。可以独立选择前三个服务区域进行连接。第四个服务区域是一个常见的依赖项（称为 Microsoft 365 Common 和 Office），并且必须始终具有网络连接。

显示的数据列是：

- **ID**：行的 ID 号，也称为终结点集。此 ID 与终结点集的 Web 服务返回的 ID 相同。

- **类别**：显示终结点集是分类为“优化”、“允许”还是“默认”。可以在 [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md) 上了解管理它们的这些类别和指南。此列还列出了哪些终结点集需要具有网络连接。对于不需要具有网络连接的终结点集，我们在此字段中提供备注，以指示在终结点集被阻止时将丢失哪些功能。如果要排除整个服务区域，则根据需要列出的终结点集不需要连接。

- **ER**：如果 **终结点集通过** 具有路由前缀的 Azure ExpressRoute Office 365是。 包含显示的路由前缀的 BGP 社区与列出的服务区域一致。 当 ER 为 **"否**"时，这意味着此终结点集不支持 ExpressRoute。 但是，不应假定没有为 ER 为 No 的终结点集播发 **路由**。 如果您计划使用Azure AD 连接，请阅读特殊的[注意事项部分](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government)，以确保您具有适当的Azure AD 连接配置。

- **地址**：列出终结点集的 FQDN 或通配符域名以及 IP 地址范围。请注意，IP 地址范围采用 CIDR 格式，并且可能包含指定网络中的许多单独 IP 地址。

- **端口**：列出与地址合并以形成网络终结点的 TCP 或 UDP 端口。你会注意到 IP 地址范围中存在一些重复，其中列出了不同的端口。

[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
关于此表的注释：

- SCC 安全与 (中心) Azure ExpressRoute for Office 365。 这同样适用于通过 SCC 公开的许多功能，如报告、审核、Advanced eDiscovery、统一 DLP 和数据管理。 PST 导入和电子数据展示导出这两个特定功能当前不支持仅具有 Office 365 路由筛选器的 Azure ExpressRoute，因为它们依赖于 Azure Blob 存储。 若要使用这些功能，你需要使用任何支持的 Azure 连接选项（包括 Internet 连接或 Azure ExpressRoute 和 Azure 公共路由筛选器存储 Azure Blob 连接选项）进行单独的连接。 您必须评估为这两个功能建立此类连接。 Office 365信息保护团队已注意到此限制，并积极致力于支持 Azure ExpressRoute for Office 365，但仅限于这两Office 365功能的 Office 365 路由筛选器。

- 对于未列出的Microsoft 365 企业应用版用户来说，还有一些可选的终结点，用户不需要Microsoft 365 企业应用版应用程序和编辑文档。 可选终结点托管在 Microsoft 数据中心中，不处理、传输或存储客户数据。 建议将用户与这些终结点的连接定向到默认 Internet 出口外围。
