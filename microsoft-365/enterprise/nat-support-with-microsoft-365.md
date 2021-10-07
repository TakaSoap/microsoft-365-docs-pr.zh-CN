---
title: Office 365 中的 NAT 支持
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: 本文详细介绍了如何使用 NAT 在组织中按 IP 地址使用客户端的数量。
ms.openlocfilehash: 5335ac87bb579b6cb00e1387da97dd5a1d4f6c7f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177107"
---
# <a name="nat-support-with-office-365"></a>Office 365 中的 NAT 支持

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

以前，指南建议每个 IP 地址Exchange连接到 Office 365 的最大客户端数是每个网络端口 2，000 个客户端。
  
## <a name="why-use-nat"></a>为什么使用 NAT？

通过使用 NAT，企业网络上的成千上万人可以"共享"一些可公开路由的 IP 地址。
  
大多数公司网络都使用专用 (RFC1918) IP 地址空间。 专用地址空间由 Internet 号码分配机构 (IANA) 分配，仅用于不直接路由到全局 Internet 和从全局 Internet 路由的网络。
  
为了提供对专用 IP 地址空间上的设备的 Internet 访问，组织使用防火墙和代理等网关技术，这些技术提供网络地址转换 (NAT) 或端口地址转换 (PAT) 服务。 这些网关使流量从内部设备到 Internet (包括Office 365) 似乎来自一个或多个可公开路由的 IP 地址。 内部设备的每个出站连接都转换为公共 IP 地址上的不同源 TCP 端口。 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>为什么需要同时为多个用户打开Office 365连接？

Outlook加载项、共享日历、邮箱等 (，用户可能会打开八个或多个连接) 。 由于基于 Windows 的 NAT 设备上最多有 64，000 个端口可用，因此在端口用尽之前，IP 地址后面最多可有 8，000 个用户。 请注意，如果客户为 NAT Windows基于操作系统的设备，则可用端口总数取决于所使用的 NAT 设备或软件。 在此方案中，最大端口数可能小于 64，000。 端口的可用性还受其他因素影响，如 Windows 限制 4，000 个端口供自己使用，这将可用端口总数减少至 60，000。 可能有其他应用程序（如 Internet Explorer）可能同时连接，需要额外的端口。
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>计算单个公用 IP 地址后面支持的最大设备数（Office 365

若要确定单个公用 IP 地址后面的设备的最大数量，应监视网络流量以确定每个客户端的端口使用峰值。 此外，应该将峰值因素用于端口使用率 (4) 。 
  
 **使用以下公式可计算每个 IP 地址支持的设备数：**
  
单个公用 IP 地址后面支持的最大设备数 = (64，000 - 受限端口) / (峰值端口消耗 + 峰值) 
  
 **例如，如果以下情况为 true：**
  
- **受限端口** ：4，000 用于操作系统

- **端口使用峰值：** 每个设备 6 个

- **峰值因素：4**

然后，单个公用 IP 地址后面支持的最大设备数 = (64，000 - 4，000) / (6 + 4) = 6，000
  
随着 Office 365 托管包的发布（包括 2011 年 9 月发布的 Microsoft Office Outlook 2007 更新或 2011 年 11 月针对 Microsoft Outlook 2010 的更新）或更高版本的更新，从 Outlook (Office Outlook 2007 Service Pack 2 和 Outlook 2010) 到 Exchange 的连接数量可以只有 2 个。 你需要考虑不同的操作系统、用户行为等，以确定网络在峰值时需要的最小和最大端口数。
  
如果你想要支持单个公用 IP 地址后面的更多设备，请按照概述的步骤评估可支持的最大设备数：
  
监视网络流量以确定每个客户端的端口使用峰值。 您应收集此数据：
  
- 从多个位置
    
- 从多个设备
    
- 多次
    
使用前面的公式可计算环境中可支持每个 IP 地址的最大用户数。
  
有各种方法可以跨其他公用 IP 地址分布客户端负载。 可用的策略取决于企业网关解决方案的功能。 最简单的解决方案是划分用户地址空间，并静态地"分配"每个网关的一些 IP 地址。 许多网关设备提供的另一种替代方法是能够使用 IP 地址池。 地址池的好处是，它更动态，且不太可能随着用户群的增大而需要调整。
  
## <a name="see-also"></a>另请参阅

[管理 Office 365 终结点](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Office 365 终结点 FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
