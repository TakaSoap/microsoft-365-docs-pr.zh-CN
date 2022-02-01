---
title: 由世纪互联运营的 Office 365 的 URL 和 IP 地址范围
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 01/31/2022
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: 本文列出了由中国的世纪互联运营的 Office 365 的 Url 和 IP 地址范围。
hideEdit: true
ms.openlocfilehash: 8250fcddbc9b23317a0a3760b59c5f7776b98378
ms.sourcegitcommit: 7fd1bcbd8246501029837e3ea92adea64c3406e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2022
ms.locfileid: "62294806"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>由世纪互联运营的 Office 365 的 URL 和 IP 地址范围

 *适用于：由世纪互联运营的 Office 365 - 小型企业管理员、由世纪互联运营的 Office 365 - 管理员*

**摘要**：以下终结点（FQDN、端口、URL、IPv4 和 IPv6 前缀）适用于由世纪互联运营的 Office 365，旨在为仅使用这些计划的组织提供生产力服务。
  
 **Office 365终结点**：全球 ([GCC)](urls-and-ip-address-ranges.md)  |  Office 365 由 *21 Vianet* |  [Office 365 美国政府 DoD](microsoft-365-u-s-government-dod-endpoints.md) |  Office 365 美国政府高级GCC [运营](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
**上次更新时间：** 2021 年 9 月 28 日 -![ RSS。](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [更改日志订阅](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

**下载：** 一个 [JSON 格式](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)列表中的所有必需和可选目标。

从[管理 Office 365 终结点](managing-office-365-endpoints.md)开始了解我们使用此数据管理网络连接的建议。终结点数据视需要在每月月初更新，并在生效前 30 天发布新的 IP 地址和 URL。这允许尚未进行自动更新的客户在需要新连接之前完成其过程。如果需要解决支持提升、安全事件或其他即时操作要求，终结点也可以在月内更新。以下页面上显示的数据全部由基于 REST 的 Web 服务生成。如果使用脚本或网络设备访问此数据，应直接转到 [Web 服务](microsoft-365-ip-web-service.md)。

下面的终结点数据列出了从用户计算机到 Office 365 的连接要求。它不包括从 Microsoft 到客户网络的网络连接（有时称为混合或入站网络连接）。

终结点分为四个服务区域。可以独立选择前三个服务区域进行连接。第四个服务区域是一个常见的依赖项（称为 Microsoft 365 Common 和 Office），并且必须始终具有网络连接。

显示的数据列是：

- **ID**：行的 ID 号，也称为终结点集。此 ID 与终结点集的 Web 服务返回的 ID 相同。

- **类别**：显示终结点集是分类为“优化”、“允许”还是“默认”。可以在 [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md) 上了解管理它们的这些类别和指南。此列还列出了哪些终结点集需要具有网络连接。对于不需要具有网络连接的终结点集，我们在此字段中提供备注，以指示在终结点集被阻止时将丢失哪些功能。如果要排除整个服务区域，则根据需要列出的终结点集不需要连接。

- **ER**：如果使用带有 Office 365 路由前缀的 Azure ExpressRoute 支持终结点集，则为 **是**。包含所显示的路由前缀的 BGP 社区与列出的服务区域一致。当 ER 为 **否** 时，这意味着此终结点集不支持 ExpressRoute。但是，不应假设没有为 ER 为 **否** 的终结点集播发路由。

- **地址**：列出终结点集的 FQDN 或通配符域名以及 IP 地址范围。请注意，IP 地址范围采用 CIDR 格式，并且可能包含指定网络中的许多单独 IP 地址。
 
- **端口**：列出与地址合并以形成网络终结点的 TCP 或 UDP 端口。你会注意到 IP 地址范围中存在一些重复，其中列出了不同的端口。

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]