---
title: 有关连接到 Office 365 服务的网络设备的计划
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 073433ca-3511-4db9-b173-7a2edca57691
description: 摘要：介绍用于连接到数据库的网络容量、WAN 加速器和负载平衡Office 365。
ms.openlocfilehash: 38df9a64610c4b4d44014a142bf7d255aa0a0f46
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166774"
---
# <a name="plan-for-network-devices-that-connect-to-office-365-services"></a>有关连接到 Office 365 服务的网络设备的计划

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 
  
某些网络硬件可能限制支持的并发会话数。 对于拥有 2，000 多个用户的组织，我们建议他们监视其网络设备，以确保他们能够处理额外的 Office 365 流量。 SNMP (简单网络管理) 可帮助您实现此目标。

本文是 Network [planning and performance tuning for Office 365 的一Office 365。](./network-planning-and-performance.md)

本地传出 Internet 代理设置还会影响与客户端Office 365服务的连接。 还必须配置网络代理设备，以允许连接 Microsoft 云服务 URL 和应用程序。 每个组织各不相同。 若要了解 Microsoft 如何管理此过程以及我们预配的带宽量， [请阅读案例研究](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)。
  
以下Skype for Business帮助文章包含有关Skype for Business设置的信息：
  
- [管理员Skype for Business联机登录错误疑难解答](/skypeforbusiness/set-up-skype-for-business-online/troubleshooting-sign-in-errors-for-admins)

- [无法连接到Skype for Business，或某些功能不起作用，因为本地防火墙会阻止连接](https://go.microsoft.com/fwlink/p/?LinkID=243625)

> [!NOTE]
> 虽然其中许多设置Skype for Business特定设置，但有关网络配置的一般指南对于所有服务Office 365有用。
  
## <a name="determining-network-capacity"></a>确定网络容量

连接上存在的每个网络设备都有其容量限制。 这些设备包括相互连接的客户端和服务器网络适配器、路由器、交换机和集线器。 足够的网络容量意味着它们都不是饱和的。 监视网络活动对于帮助确保所有网络设备的实际负载都小于其最大容量至关重要。 网络容量影响代理设备性能。
  
在大多数情况下，Internet 连接带宽会设置流量限制。 高峰流量时段性能较弱可能是由于过度使用 Internet 链接所致。 这种情况还适用于分支机构方案，其中分支机构代理服务器计算机通过慢速广域网 (WAN) 链接连接到分支机构总部的代理设备。
  
若要测试网络容量，请监视代理网络接口上的网络活动。 如果超过任何网络接口最大带宽的 75%，请考虑增加不足的网络基础结构的带宽。 或者，请考虑使用高级功能，如 HTTP 压缩。
  
## <a name="wan-accelerators"></a>WAN 加速器

如果你的组织使用广域网 (WAN) 加速代理设备，你在访问 Office 365 服务时可能会遇到问题。 你可能需要优化你的网络设备，以确保你的用户在访问网络时拥有一致的Office 365。 例如，Office 365加密某些Office 365和 TCP 标头。 你的设备可能无法处理此类流量。
  
阅读我们的支持声明，[了解将 WAN 优化控制器或流量/检查设备与 Office 365。](https://support.microsoft.com/kb/2690045)
  
## <a name="hardware-and-software-load-balancing-devices"></a>硬件和软件负载平衡设备

组织需要使用硬件负载平衡器 (HLB) 或网络负载平衡 (NLB) 解决方案将请求分发到 Active Directory 联合身份验证服务 (AD FS) 服务器和/或 Exchange 混合服务器。 负载平衡设备控制到内部部署服务器的网络流量。 这些服务器对于确保单一登录和混合部署Exchange至关重要。
  
我们提供内置于 Windows Server 的基于软件的 NLB 解决方案。 Office 365 支持此解决方案以实现负载平衡。
  
## <a name="firewalls-and-proxies"></a>防火墙和代理

有关配置防火墙和代理以连接到 Office 365 的更多详细信息，请参阅管理[Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点、评估[Office 365](assessing-network-connectivity.md)网络连接和 Office 365 终结点[常见问题](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)，了解有关设备和电路选择的详细信息。
  
## <a name="see-also"></a>另请参阅

[服务设置Office 365指南](setup-guides-for-microsoft-365.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)