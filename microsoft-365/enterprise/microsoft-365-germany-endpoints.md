---
title: 适用于德国的 Office 365 终结点
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: 本文将介绍在德国使用 Office 365 的客户能够访问的终结点。
hideEdit: true
ms.openlocfilehash: 767c7dd570ac03ae1ceb784b4917ee816837530a
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751623"
---
# <a name="office-365-germany-endpoints"></a>Office 365 Germany 终结点

 *适用于：Office 365 管理员*

Office 365 需要连接到 Internet。 以下终结点应仅适用于使用 **Office 365 Germany** 计划的客户。
  
 **Office 365 终结点：**[全球（包括 GCC）](urls-and-ip-address-ranges.md)  | [由世纪互联运营的 Office 365](urls-and-ip-address-ranges-21vianet.md)  | *Office 365 Germany* | [Office 365 美国政府版 DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 美国政府版 GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
|||
|:-----|:-----|
|**上次更新时间** ：01/04/2021 - ![ RSS ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [更改日志订阅](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) |**下载：** 一个 [JSON 格式](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)列表中的所有必需和可选目标。  <br/> |

从 [管理 Office 365](managing-office-365-endpoints.md) 终结点开始，了解我们关于使用此数据管理网络连接的建议。 终结点数据在每月开始时更新，在处于活动状态前 30 天发布新的 IP 地址和 URL。 这使尚未自动更新的客户可以在需要新连接之前完成其流程。 如果需要解决支持升级、安全事件或其他即时操作要求，也可在一个月内更新终结点。 你始终可以参考 [更改日志订阅](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)。

以下页面上显示的数据都是从基于 REST 的 Web 服务生成的。 如果使用脚本或网络设备访问此数据，应直接转到 [Web](microsoft-365-ip-web-service.md) 服务。

以下终结点数据列出了从用户计算机到 Office 365 的连接要求。 它不包括从 Microsoft 到客户网络的网络连接，有时称为混合或入站网络连接。

终结点分为四个服务区域。可以独立选择前三个服务区域进行连接。第四个服务区域是一个常见的依赖项（称为 Microsoft 365 Common 和 Office），并且必须始终具有网络连接。

显示的数据列是：

- **ID**：行的 ID 号，也称为终结点集。此 ID 与终结点集的 Web 服务返回的 ID 相同。

- **类别**：显示终结点集是分类为“优化”、“允许”还是“默认”。可以在 [https://aka.ms/pnc](https://aka.ms/pnc) 上了解管理它们的这些类别和指南。此列还列出了哪些终结点集需要具有网络连接。对于不需要具有网络连接的终结点集，我们在此字段中提供备注，以指示在终结点集被阻止时将丢失哪些功能。如果要排除整个服务区域，则根据需要列出的终结点集不需要连接。

- **ER**：如果使用带有 Office 365 路由前缀的 Azure ExpressRoute 支持终结点集，则为 **是**。包含所显示的路由前缀的 BGP 社区与列出的服务区域一致。当 ER 为 **否** 时，这意味着此终结点集不支持 ExpressRoute。但是，不应假设没有为 ER 为 **否** 的终结点集播发路由。

- **地址**：列出终结点集的 FQDN 或通配符域名以及 IP 地址范围。请注意，IP 地址范围采用 CIDR 格式，并且可能包含指定网络中的许多单独 IP 地址。
 
- **端口**：列出与地址合并以形成网络终结点的 TCP 或 UDP 端口。你会注意到 IP 地址范围中存在一些重复，其中列出了不同的端口。

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

 

