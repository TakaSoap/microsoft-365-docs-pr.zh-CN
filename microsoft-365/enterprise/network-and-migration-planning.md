---
title: Office 365 的网络和迁移规划
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: 本文包含指向有关网络规划、测试和迁移到 Office 365 的信息的链接。
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923584"
---
# <a name="network-and-migration-planning-for-office-365"></a>Office 365 的网络和迁移规划

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

本文包含指向有关网络规划和测试以及迁移到 Office 365 的信息的链接。
  
首次部署或迁移到 Office 365 之前，可以使用这些主题中的信息估计所需的带宽，然后测试和验证是否有足够的带宽来部署或迁移到 Office 365。

本文是 Office [365 的网络规划和性能调整的一部分](./network-planning-and-performance.md)。

有关针对 Microsoft 365 和其他 Microsoft 云平台和服务优化网络的步骤，请参阅适用于企业架构师的 [Microsoft 云网络](../solutions/cloud-architecture-models.md) 海报。
   
## <a name="estimate-network-bandwidth-requirements"></a>估计网络带宽要求
<a name="EstimateBandwidthRequirements"> </a>

使用 Office 365 可能会增加组织的 Internet 线路的利用率。 一旦完全部署 Office 365，同时至少保留 20% 的容量来处理最忙碌的天数，则确定当前可用的带宽量是否足以处理估计的增加量，这一点很重要。
  
若要估计带宽，请使用以下步骤：
  
1. 评估将使用每个 Internet 出口的客户端数量。 让我们的多 TB 网络处理尽可能多的连接。 
    
2. 确定可供客户端使用的 Office 365 服务和功能。 您可能拥有一组具有不同的服务或使用率配置文件的用户组。
    
3. 测量客户端试点组的网络使用。 确保试点客户端代表组织中不同人员以及不同地理位置的不同配置文件。 你可以针对 Exchange 和[Microsoft Teams](/microsoftteams/prepare-network)的旧计算器[](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744)交叉检查结果，也可以交叉[](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)检查我们在自己的网络上执行的案例研究。 
    
4. 使用试点组的测量推断整个组织的需求，然后重新测试以验证估计值，然后再对网络进行更改。
    
## <a name="test-your-existing-network"></a>测试现有网络
<a name="calculators"> </a>

 **网络工具。** 测试和验证 Internet 带宽以确定下载、上载和延迟限制。 这些工具将帮助您确定网络的迁移功能，以及完全部署后的功能。 
    
- [Microsoft Remote Connectivity Analyzer：](https://go.microsoft.com/fwlink/p/?LinkId=517243)测试 Exchange Online 环境中的连接性。
    
- 使用 [适用于 Office 365](https://diagnostics.office.com/#/Download?env=SOC) 的 Microsoft 支持和恢复助手修复 Outlook 和 Office 365 问题。 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Office 365 的网络规划和提高迁移性能的最佳实践
<a name="BestPractices"> </a>

深入了解这些最佳实践，详细了解如何改善 Office 365 体验。
  
1. 想要开始帮助你的用户吗？ 请参阅在慢速网络上使用 [Office 365](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) 的最佳实践，了解在网络未运行时使用 Office 365（包括 SharePoint Online、Exchange Online 和 Lync Online）的提示。 本文链接到 TechNet 和 Support.office.com 上用于优化 Office 365 体验的内容加载，并包括有关自定义网页的简便方法以及如何设置 Internet Explorer 设置以获得最佳 Office 365 体验的信息。 
    
2. 阅读 [Office 365](./microsoft-365-network-connectivity-principles.md) 网络连接原则，了解安全管理 Office 365 流量和获得最佳性能的连接原则。 本文将帮助你了解有关安全优化 Office 365 网络连接的最新指南。 
    
3. 通过仔细管理 Windows 更新的计划来提高邮件迁移性能。 可以分批更新客户端计算机，并确保在迁移到 Office 365 之前更新所有客户端计算机，以控制网络带宽的使用。 有关详细信息，请参阅 [Manually update and configure desktops for Office 365获取最新更新](https://support.microsoft.com/gp/office-2013-365-update)。
    
4. 当 Office 365 网络流量被视为受信任的 Internet 服务并允许绕过大部分传统筛选和扫描（某些组织将网络流量放在不受信任的 Internet 服务上）时，其性能最佳。 这通常包括删除代理用户身份验证和数据包检查等出站处理，以及确保具有正确的网络地址转换 (NAT) 和足够的带宽容量来处理增加的网络请求的本地 Internet 出口。 有关配置网络以将 Office 365 作为网络上受信任的 Internet 服务处理的其他指南，请参阅管理 [Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点。
    
1. 确保 [管理 Office 365 终结点](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)。 进入 Office 365 的额外流量导致出站代理连接增加，通过 TLS/SSL 的安全流量增加。
    
2. 如果您的出站代理需要用户身份验证，则可能会遇到连接缓慢或功能丢失的问题。 绕过 Office 365 域的身份验证要求可降低此开销。
    
3. 如果您具有大量共享日历和邮箱，您可能会看到从 Outlook 到 Exchange 的连接数增加。 例如，Outlook 客户端可能会为使用的每个共享日历打开最多两个附加连接。 在这种情况下，请确保出口代理可以处理连接，或绕过代理连接到 Office 365 for Outlook。
    
4. 确定公用 IP 地址支持的最大设备数以及如何在多个 IP 地址之间实现负载平衡。 有关详细信息，请参阅[与 Office 365 的 NAT 支持](nat-support-with-microsoft-365.md)。
    
5. 如果要检查来自网络上的计算机的出站连接，则绕过此筛选到 Office 365 域将提高连接性和性能。 此外，绕过出站检查通常无需单个 Internet 出口，并启用发往 Office 365 的网络请求的本地 Internet 出口。
    
6. 一些客户发现内部网络设置可能会影响性能。 诸如最大传输单元 (MTU) 大小、网络自动协商或自动检测以及到 Internet 的次最佳路由等设置是常见的查找位置。
    
## <a name="network-planning-reference-for-office-365"></a>Office 365 的网络规划参考
<a name="NetReference"> </a>

这些主题包含详细的 Office 365 网络参考信息。
  
- [管理 Office 365 终结点](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [内容分发网络](content-delivery-networks.md)
    
- [Office 365 的外部域名系统记录](external-domain-name-system-records.md)
    
- [Office 365 服务中的 IPv6 支持](ipv6-support.md)
    
- [Office 365 网络连接原则](./microsoft-365-network-connectivity-principles.md)
    
- [Office 365 视频网络常见问题解答 (常见问题) ](office-365-video-networking-faq.md)
    
- [有关连接到 Office 365 服务的网络设备的计划](plan-for-network-devices.md)
    
- [Office 365 服务的设置指南](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版概述](microsoft-365-overview.md)