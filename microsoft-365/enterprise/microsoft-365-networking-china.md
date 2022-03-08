---
title: Microsoft 365中国用户实现全局租户性能优化
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
search.appverid: MET150
f1.keywords:
- NOCSH
description: 本文提供了针对全球用户和租户中国用户Microsoft 365性能的指导。
ms.openlocfilehash: 6c99245d523048d30124fc8f8b0c01d7c2004327
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326925"
---
# <a name="microsoft-365-global-tenant-performance-optimization-for-china-users"></a>Microsoft 365中国用户实现全局租户性能优化

> [!IMPORTANT]
> 本指南特定于使用方案，在此方案中，Microsoft 365中国的企业用户连接到全球企业Microsoft 365 **租户**。 本指南不适用于 **由** 世纪Office 365中的租户。

>[!NOTE]
>本文是一组文章的一部分，这些文章Microsoft 365远程用户的优化。

>- 有关使用 VPN 拆分隧道优化远程Microsoft 365连接的概述，请参阅[概述：适用于远程用户的 VPN 拆分Microsoft 365](microsoft-365-vpn-split-tunnel.md)。
>- 有关实现 VPN 拆分隧道的详细指南，请参阅[实现 VPN 拆分隧道Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)。
>- 有关 VPN 拆分隧道方案的详细列表，请参阅公用 VPN 拆分隧道[方案Microsoft 365](microsoft-365-vpn-common-scenarios.md)。
>- 有关在 VPN 拆分隧道Teams保护媒体流量的指南，请参阅 [Securing Teams media traffic for VPN split tunneling](microsoft-365-vpn-securing-teams.md)。
>- 若要了解如何在 VPN 环境中配置 Stream 和实时事件，请参阅 VPN 环境中 Stream 和 [实时事件的特殊注意事项](microsoft-365-vpn-stream-and-live-events.md)。

对于具有全球 Microsoft 365 租户的企业以及中国的公司业务，Microsoft 365中国用户的客户端性能可能会因中国 Telco 的 Internet 体系结构的独特因素而变得复杂。

中国 ISP 已监管全球公共 Internet 的接口连接，这些连接经过容易出现高级跨界网络拥塞的外围设备。 此拥塞会为进入和离开中国的所有 Internet 流量造成数据包丢失和延迟。

![Microsoft 365流量 - 未优化。](../media/O365-networking/China-O365-unoptimized.png)

数据包丢失和延迟会对网络服务的性能产生不利影响，尤其是需要大型数据交换 (（如大型文件传输) 或需要近实时性能 (音频和视频应用程序) ）的服务。

本主题旨在提供最佳实践，缓解中国跨边界网络拥塞对服务Microsoft 365的影响。 本主题不讨论其他常见的最后一英里性能问题，例如由于中国运营商内部路由复杂而导致数据包延迟高的问题。

## <a name="corporate-network-best-practices"></a>企业网络最佳实践

许多具有全球Microsoft 365租户和用户的企业都实施了专用网络，这些专用网络承载了中国办事处地点和世界各地的办公楼地点之间的公司网络流量。 这些企业可以利用此网络基础结构避免跨边界网络拥塞，并优化其Microsoft 365服务性能。

> [!IMPORTANT]
> 与所有专用 WAN 实施一样，您应始终咨询您国家/地区及/或地区的法规要求，以确保网络配置合规。

作为第一步，遵循 Network [planning and performance tuning for Microsoft 365（](./network-planning-and-performance.md)网络规划和性能优化）的基准网络指南Microsoft 365。 主要目标应该是避免在可能的情况下Microsoft 365 Internet 访问全球服务。

- 利用现有专用网络来传输Microsoft 365网络之间的网络通信量，以及中国以外的公共 Internet 上出口的地理位置。 中国以外的几乎任何位置都将提供明显的好处。 网络管理员可以进一步优化，方法为在具有低延迟互连的区域与 [Microsoft 全球网络相互连接](/azure/networking/microsoft-global-network)。 例如，香港特别行政区、新加坡、日本和韩国。
- 将用户设备配置为通过 VPN 连接访问企业网络，以允许Microsoft 365流量传输企业网络的私有链接。 确保 VPN 客户端未配置为使用拆分隧道，或者用户设备配置为忽略流量的Microsoft 365隧道。 有关为媒体流量和实时媒体Teams优化 VPN 连接的其他信息，请参阅[本部分](#optimizing-microsoft-teams-meetings-network-performance-for-users-in-china)。
- 将网络配置为通过专用Microsoft 365路由所有流量。 如果必须最大限度地减少专用链接上的流量，可以选择仅路由"优化"类别中的终结点，并允许对"允许"和"默认"终结点的请求传输 Internet。 这将通过将优化流量限制到对高延迟和数据包丢失最敏感的关键服务，来提高性能并最大限度地减少带宽消耗。
- 如果可能，请对实时媒体流通信使用 UDP 而不是 TCP，例如Teams。 UDP 提供比 TCP 更好的实时媒体流性能。

若要了解如何选择性地路由Microsoft 365流量，请参阅[管理Office 365终结点](managing-office-365-endpoints.md)。 有关全球所有 URL 和 IP Office 365的列表，请参阅Office 365 [URL 和 IP 地址范围](urls-and-ip-address-ranges.md)。

![Microsoft 365流量 - 优化。](../media/O365-networking/China-O365-optimized.png)

## <a name="user-best-practices"></a>用户最佳做法

中国用户在未连接到企业网络的远程位置（如家庭、咖啡店、酒店和分支机构）连接到全球 Microsoft 365 租户可能会遇到较差的网络性能，因为其设备和 Microsoft 365 之间的流量必须经过中国拥堵的跨界网络线路。

如果无法选择跨边界专用网络和/或 VPN 访问企业网络，则仍可通过培训基于中国的用户以遵循这些最佳做法来缓解每用户性能问题。

- 利用Office (缓存功能（如 Outlook、Teams、OneDrive 等 ) ）的丰富客户端，并避免使用基于 Web 的客户端。 Office客户端缓存和脱机访问功能可以大大减少网络拥塞和延迟的影响。
- 如果Microsoft 365租户已配置音频会议功能，Teams用户可以通过公用电话交换网和 PSTN (加入) 。 有关详细信息，请参阅音频[会议Office 365](/microsoftteams/audio-conferencing-in-office-365)。
- 如果用户遇到网络性能问题，他们应向 IT 部门报告疑难解答，如果怀疑遇到网络Microsoft 365问题，则上报给 Microsoft 支持部门。 并非所有问题都由跨边界网络性能导致。

## <a name="optimizing-microsoft-teams-meetings-network-performance-for-users-in-china"></a>为Microsoft Teams用户优化会议网络性能

对于具有全球 Microsoft 365 租户且在中国存在的组织，Microsoft 365中国用户的客户性能可能会因中国 Internet 体系结构的独特因素而变得复杂。 许多公司和学校通过遵循此指南报告了良好结果。 但是，范围仅限于受 IT 网络设置控制的用户网络位置，例如，具有 VPN 连接的办公室位置或家庭/移动终结点。 Microsoft Teams呼叫和会议通常用于外部位置，例如家庭办公室、移动位置、路况和咖啡店。 由于通话和会议依赖于实时媒体流量，因此这些Teams体验对网络拥塞特别敏感。

因此，Microsoft 与电信提供商合作，使用中国国内和公共 Internet 连接与 Microsoft 365 全球云中的 Teams 和 Skype 服务之间更高质量、更高质量的网络路径传输 Teams 和 Skype for Business Online 实时媒体流量。 此功能导致数据包丢失和其他关键指标的改进超过 10 倍，这些指标会影响用户体验。

>[!IMPORTANT]
>目前，这些改进无法用于参加 Microsoft Live Events 会议，例如使用 microsoft Stream 或 Microsoft Stream 的大型直播或"大会堂"Teams式会议。 若要查看实时事件会议，中国用户需要使用专用网络或 SDWAN/VPN 解决方案。 但是，网络改进将有利于演示或生成实时事件会议的用户，因为该体验充当制作者或演示者的常规 Teams会议。

### <a name="organization-network-best-practices-for-teams-meetings"></a>用于会议的组织网络Teams做法

鉴于前面的指南考虑专用网络扩展以避免跨边界网络拥塞，需要考虑如何利用这些网络改进。 组织办公室网络有两个常规选项：

1. 不执行任何新工作。 继续遵循之前有关专用网络旁路的指导，以避免出现跨边界拥塞。 Teams媒体流量将像以前一样利用此设置。
2. 实现拆分/混合模式。
   - 对标记为优化的所有流量（会议Teams通话实时媒体流量除外）使用以前的指南。
   - 通过Teams Internet 路由会议并呼叫实时媒体流量。 有关标识实时媒体网络流量的具体信息，请参阅以下信息。

通过Teams Internet 发送实时媒体音频和视频流量（使用更高质量的连接）可节省大量成本，因为通过专用网络发送流量是免费还是付费。 如果用户还使用 SDWAN 或 VPN 客户端，则可能有类似的其他好处。 一般来说，某些组织可能还希望让更多数据遍历公共 Internet 连接。

相同的选项可能适用于 SDWAN 或 VPN 配置。 例如，用户使用 SDWAN 或 VPN 将 Microsoft 365 流量路由到企业网络，然后利用该网络的专用分机以避免出现跨界拥塞。 现在，可以将用户的 SDWAN 或 VPN 配置为从 VPN 路由Teams会议流量和呼叫实时流量。 此 VPN 配置称为拆分隧道。 有关详细信息[，请参阅 VPN Office 365](/microsoft-365/enterprise/microsoft-365-vpn-implement-split-tunnel)隧道。

还可以继续将 SDWAN 或 VPN 用于所有Microsoft 365流量，包括Microsoft Teams流量。 Microsoft 没有关于使用 SDWAN 或 VPN 解决方案的建议。

### <a name="home-mobile-and-user-network-best-practices-for-teams-meetings"></a>家庭、移动和用户网络最佳实践，适用于Teams会议

中国用户只需通过有线或移动连接连接到中国的公共 Internet 服务，就可以利用这些改进。 Teams Internet 上的实时媒体音频和视频流量可直接受益于改进的连接和质量。

但是，来自其他Microsoft 365服务的数据以及其他流量Teams聊天或文件）不会直接从这些改进中获益。 组织网络外部的用户可能仍遇到此流量的较差网络性能。 如本文中讨论，您可以使用 VPN 或 SDWAN 缓解这些影响。 还可以让用户通过 Web 客户端使用丰富的桌面客户端，这些客户端支持应用内缓存以减少网络问题。

### <a name="identifying-teams-real-time-media-network-traffic"></a>标识Teams实时媒体网络流量

若要配置网络设备或 VPN/SDWAN 设置，只需排除Teams媒体音频和视频流量。 可以在 URL 和 IP 地址范围的官方列表上找到 ID 11 [Office 365流量详细信息](urls-and-ip-address-ranges.md#skype-for-business-online-and-microsoft-teams)。 所有其他网络配置应保持不变。

Microsoft 一直在致力于Microsoft 365各种网络体系结构和特征改进客户端的用户体验和性能。 访问[Office 365网络技术Community](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)开始或加入对话、查找资源和提交功能请求和建议

## <a name="related-articles"></a>相关文章

[概述：用于服务器的 VPN 拆分Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[为用户实现 VPN 拆分Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[用于服务器的常见 VPN 拆分隧道Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[保护Teams VPN 拆分隧道的媒体流量](microsoft-365-vpn-securing-teams.md)

[VPN 环境中 Stream 和实时事件的特殊注意事项](microsoft-365-vpn-stream-and-live-events.md)

[Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)

[评估 Microsoft 365 网络连接](assessing-network-connectivity.md)

[Microsoft 365 网络和性能调整](network-planning-and-performance.md)

[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法（Microsoft 安全团队博客）](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[增强 Microsoft 的 VPN 性能：使用 Windows 10 VPN 配置文件以允许自动打开连接](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[运行 VPN：Microsoft 如何让远程工作人员互联](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft 全球网络](/azure/networking/microsoft-global-network)
