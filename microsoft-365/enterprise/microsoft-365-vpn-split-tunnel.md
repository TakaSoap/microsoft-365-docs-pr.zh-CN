---
title: 概述：用于服务器的 VPN 拆分Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
- m365initiative-coredeploy
f1.keywords:
- NOCSH
description: VPN 拆分隧道概述，Microsoft 365为远程用户优化连接。
ms.openlocfilehash: 67ce8a38b536dab12af679ba860aac6d974db60e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329067"
---
# <a name="overview-vpn-split-tunneling-for-microsoft-365"></a>概述：用于服务器的 VPN 拆分Microsoft 365

>[!NOTE]
>本文是一组文章的一部分，这些文章Microsoft 365远程用户的优化。

>- 有关实现 VPN 拆分隧道的详细指南，请参阅[实现 VPN 拆分隧道Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)。
>- 有关 VPN 拆分隧道方案的详细列表，请参阅公用 VPN 拆分隧道[方案Microsoft 365](microsoft-365-vpn-common-scenarios.md)。
>- 有关在 VPN 拆分隧道Teams保护媒体流量的指南，请参阅 [Securing Teams media traffic for VPN split tunneling](microsoft-365-vpn-securing-teams.md)。
>- 若要了解如何在 VPN 环境中配置 Stream 和实时事件，请参阅 VPN 环境中 Stream 和 [实时事件的特殊注意事项](microsoft-365-vpn-stream-and-live-events.md)。
>- 有关为中国用户Microsoft 365全球租户性能的信息，请参阅Microsoft 365[中国用户的性能优化](microsoft-365-networking-china.md)。

企业通常使用 VPN 来支持其用户的安全远程体验。 尽管核心工作负载仍位于本地，但通过企业网络上的数据中心路由的远程客户端中的 VPN 是远程用户访问公司资源的主要方法。 为保证这些连接的安全性，企业将沿 VPN 路径构建网络安全解决方案层。 构建此安全是为了保护内部基础结构，并通过将流量重新路由到 VPN 然后通过本地 Internet 外围来保护外部网站的移动浏览。 VPN、网络外围和相关安全基础结构通常是针对定义的流量进行特意构建和扩展的，通常大多数连接都是从企业网络内部启动的，并且大部分连接都位于内部网络边界内。

在相当长的一段时间内，只要远程用户的并发规模适中且遍历 VPN 的流量较低，那么所有来自远程用户设备的连接都被路由回本地网络的 VPN 模型（这称为 _强制隧道_）基本上是可持续的。  一些客户继续使用 VPN 强制隧道作为状态仲裁，即使他们的应用程序从企业外围内部移动到公共 SaaS 云也是如此。

使用强制隧道 VPN 连接到分布式和性能敏感的云应用程序是非优化的，但为了维持安全状态仲裁，一些企业已接受负面影响。 下面是此场景的一个示例图：

![强制Tunnel VPN 配置。](../media/vpn-split-tunneling/enterprise-network-traditional.png)

_图 1：传统的强制Tunnel VPN 解决方案。_

此问题多年来一直在增长，许多客户报告网络流量模式发生显著变化。 过去位于本地的流量现在连接到外部云终结点。 许多 Microsoft 客户报告，以前大约 80% 的网络流量是发往某些内部源 (由上图中的虚线表示) 。 2020 年，随着主要工作负载转移到云，这一数字降低了约 20% 或更低。 这些趋势在其他企业中并不常见。 随着时间的推移，随着云之旅的发展，上述模型变得越来越麻烦和麻烦，从而阻止组织在进入云第一世界时变得敏捷。

全球 COVID-19 危机升级了此问题，需要立即修正。 确保员工安全的需要对企业 IT 部门提出了前所未有的要求，要求他们支持大规模在家办公的工作效率。 Microsoft 365有助于客户满足此需求，但在家办公的用户的高并发性会产生大量 Microsoft 365 流量，如果通过强制隧道 VPN 和本地网络外围进行路由，则会导致快速饱和并运行容量不足的 VPN 基础结构。 在此新现实中，使用 VPN 访问 Microsoft 365 不再是性能障碍，而是一个不仅影响 Microsoft 365 而且仍必须依赖 VPN 才能运行的关键业务运营的硬墙。

Microsoft 一直与客户和更广泛的行业密切合作，从我们自身服务中为这些问题提供有效的现代解决方案，并与行业最佳做法保持一致。 [Microsoft 365](./microsoft-365-network-connectivity-principles.md) 服务的连接原则旨在有效为远程用户工作，同时仍允许组织维护安全性和控制其连接。 这些解决方案也可在有限的工作下快速实施，但是对上述问题产生显著正面影响。

对于通过 VPN 将其远程工作者设备连接到企业网络或云基础结构的客户，Microsoft 建议通过 _VPN_ 拆分隧道配置路由关键 Microsoft 365 方案 **Microsoft Teams**、**SharePoint Online** 和 **Exchange Online**。 作为在 COVID-19 危机等大规模在家工作活动中促进员工持续提高工作效率的第一线策略，这一点尤其重要。

![拆分Tunnel VPN 配置。](../media/vpn-split-tunneling/vpn-model-2.png)

_图 2：VPN 拆分隧道解决方案，Microsoft 365直接发送到服务的定义异常。所有其他流量都将遍历 VPN 隧道，而不考虑目标。_

此方法的本质是，为企业提供一种简单方法来降低 VPN 基础结构饱和的风险，并尽可能在尽可能短的Microsoft 365显著提高系统性能。 将 VPN 客户端配置为允许最关键、Microsoft 365流量绕过 VPN 隧道可以实现以下好处：

- 立即缓解企业 VPN 体系结构中大多数客户报告的性能和网络容量问题的根本原因，这些问题Microsoft 365用户体验
  
  建议的解决方案专门面向Microsoft 365 URL 和 IP 地址范围主题Microsoft 365"优化"[的服务终结点](./urls-and-ip-address-ranges.md)。 这些终结点的流量对延迟和带宽限制非常敏感，如果允许流量绕过 VPN 隧道，可以显著改善最终用户体验，并降低企业网络负载。 Microsoft 365大部分带宽或用户体验占用空间的连接可以继续通过 VPN 隧道进行路由，并路由其余 Internet 绑定流量。 有关详细信息，请参阅 [VPN 拆分隧道策略](#the-vpn-split-tunnel-strategy)。

- 客户无需其他基础结构或应用程序要求，就可以快速配置、测试和实现

  根据 VPN 平台和网络体系结构，实现可能只需几个小时。 有关详细信息，请参阅[实现 VPN 拆分隧道](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)。

- 通过不更改其他连接的路由方式（包括到 Internet 的流量）来保留客户 VPN 实现的安全状况

  建议的配置遵循 VPN 流量异常的 **最低特权** 原则，并允许客户实现拆分隧道 VPN，而不会将用户或基础结构暴露于额外的安全风险中。 直接路由到 Microsoft 365 终结点的网络流量通过 Office 客户端应用程序堆栈进行加密和完整性验证，并且范围为专用于 Microsoft 365 服务的 IP 地址，这些服务在应用程序和网络级别进行了强化。 有关详细信息，请参阅[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法（Microsoft 安全团队博客）](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)。

- 由大多数企业 VPN 平台在本地提供支持

  Microsoft 与制作商业版 VPN 解决方案的行业合作伙伴持续协作，帮助合作伙伴开发与以上建议一致的解决方案的目标指南和配置模板。 有关详细信息，请参阅[适用于常见 VPN 平台的操作指南](microsoft-365-vpn-implement-split-tunnel.md#howto-guides-for-common-vpn-platforms)。

>[!TIP]
>Microsoft 建议将拆分隧道 VPN 配置集中在记录的服务专用 IP Microsoft 365范围。 基于 FQDN 或基于 AppID 的拆分隧道配置（在某些 VPN 客户端平台上可能实现）可能不能完全涵盖关键 Microsoft 365 方案，并且可能会与基于 IP 的 VPN 路由规则冲突。 因此，Microsoft 不建议使用 FQDN Microsoft 365拆分隧道 VPN。 使用 FQDN 配置在其他相关方案中可能非常有用，例如 .pac 文件自定义或实现代理绕过。

有关完整实现指南，请参阅为用户实现 [VPN 拆分Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)。

有关为远程工作者配置 Microsoft 365的分步过程，请参阅[设置远程工作的基础结构](..\solutions\empower-people-to-work-remotely.md)

## <a name="the-vpn-split-tunnel-strategy"></a>VPN 拆分隧道策略

传统的公司网络通常旨在在预云环境中安全工作，其中最重要的数据、服务和应用程序在本地托管，并且与大多数用户一样直接连接到内部公司网络。 因此，网络基础结构是围绕这些元素构建的，分支机构通过 _多协议标签切换 (MPLS)_ 网络连接到总部，而远程用户必须通过 VPN 连接到公司网络才能访问本地终结点和 Internet。 在此模型中，来自远程用户的所有流量都将遍历公司网络，并通过公共出口点路由到云服务。

![强制 VPN 配置。](../media/vpn-split-tunneling/vpn-model-1.png)

_图 2：适用于远程用户的公共 VPN 解决方案，其中所有流量都会被强制流回公司网络，而无需考虑目标_

随着组织将数据和应用程序移动到云中，此模型的效率开始降低，因为它很快就会变得麻烦、昂贵且不可缩放，从而显著影响用户的网络性能和效率，并限制组织适应不断变化的需求的能力。 许多 Microsoft 客户都报告，在几年之前，80% 的网络流量是到内部目标，但在 2020 年，80% 以上的流量会连接到基于云的外部资源。

COVID-19 危机加剧了此问题，需要立即为绝大多数组织提供解决方案。 许多客户发现强制 VPN 模型的缩放性或性能不足以实现 100% 的远程工作场景，例如这次危机所需的远程工作场景。 若要使这些组织继续高效运行，需要快速的解决方案。

对于 Microsoft 365 服务，Microsoft 已针对此问题为服务设计连接要求，其中可以非常简单快速地优化一组集中的、严格控制且相对静态的服务终结点，以便为访问该服务的用户提供高性能，同时减轻 VPN 基础结构的负担，以便仍需要该服务的流量可以使用它。

Microsoft 365要求终结点分为三Microsoft 365："优化"、"**允许**"和"**默认"**。  **优化** 终结点是我们的重点，具有以下特征：

- 为 Microsoft 拥有和托管的终结点，托管在 Microsoft 基础结构上
- 专用于核心Microsoft 365工作负载，如 Exchange Online、SharePoint Online、Skype for Business Online 和 Microsoft Teams
- 提供了 IP
- 低更改率，预计仍保持较小数量（目前有 20 个 IP 子网）
- 高容量和/或延迟敏感
- 可在服务中提供所需的安全元素，而不是在网络上内联
- 大约占到服务流量的 70-80% Microsoft 365流量

这组严格作用域的终结点可以拆分出强制 VPN 隧道，然后通过用户的本地接口安全直接发送到 Microsoft 365 服务。 这称为 **拆分隧道**。

DLP、AV 保护、身份验证和访问控制等安全元素可在服务的不同层针对这些终结点更有效地交付。 由于我们还将大部分流量从 VPN 解决方案中转移，这为仍依赖于它的业务关键流量释放了 VPN 容量。 在许多情况下，它还应消除通过冗长而昂贵的升级程序来应对这种新操作方式的需要。

![拆分Tunnel VPN 配置详细信息。](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

_图 3：VPN 拆分隧道解决方案，Microsoft 365直接发送到服务的定义异常。所有其他流量将强制返回到企业网络，而不考虑目标。_

从安全角度来看，Microsoft 提供了一系列安全功能，可用于提供类似甚至增强的安全性，而不是由本地安全堆栈通过内联检查提供的安全性。 Microsoft 安全团队的博客文章[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)对可用功能进行了清晰的总结，你将在本文找到更详细的指导。 有关 Microsoft 实现 VPN 拆分隧道的信息，还可以参阅[运行 VPN：Microsoft 如何让远程工作人员互联](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)。

在许多情况下，可在几个小时内完成此实现，以便快速解决在组织迅速转变到全面远程工作时面临的最紧迫的问题之一。 有关 VPN 拆分隧道实现指南，请参阅[实现 VPN 拆分隧道Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)。

## <a name="faq"></a>常见问题

Microsoft 安全团队发布了供安全专业人员和 [IT](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) 人员在今天独特的远程工作场景中实现新式安全控制的替代方法（博客文章）概述了安全专业人员和 IT 人员在当今独特的远程工作场景中实现新式安全控制的关键方法。 此外，下面是有关此主题的一些常见客户问题和解答。

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>我如何阻止用户访问我不信任的其他租户（他们可能会泄漏数据）？

答案是[称为租户限制的功能](/azure/active-directory/manage-apps/tenant-restrictions)。 身份验证流量不高，也不对延迟特别敏感，因此可以通过 VPN 解决方案发送到应用该功能的本地代理。 此处维护受信任租户的允许列表，如果客户端尝试获取到不受信任的租户的令牌，代理将拒绝请求。 如果租户受信任，则在用户具有正确的凭据和权限的情况下，令牌可供访问。

因此，即使用户可以建立与上述"优化"标记的终结点的 TCP/UDP 连接，但没有有效的令牌来访问有关租户，他们也无法登录和访问/移动任何数据。

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>此模型是否允许访问诸如个人 OneDrive 帐户之类的使用者服务？

否，不是，Microsoft 365 终结点与使用者服务 (Onedrive.live.com 与示例) 不同，因此拆分隧道不允许用户直接访问使用者服务。 流向使用方终结点的流量将继续使用 VPN 隧道，并且现有策略将继续生效。

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>如果流量不再流经本地解决方案，我该如何应用 DLP 并保护我的敏感数据？

为了帮助防止意外泄露敏感信息，Microsoft 365 提供了一组 [丰富的内置工具](../compliance/information-protection.md)。 可使用 Teams 和 SharePoint 的内置 [DLP 功能](../compliance/dlp-learn-about-dlp.md)来检测未恰当存储或共享的敏感信息。 如果远程工作策略的一部分涉及自带设备办公 (BYOD) 策略，可以使用基于应用的条件访问来防止敏感数据下载到用户的个人设备[](/azure/active-directory/conditional-access/app-based-conditional-access)

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>如何在用户直接连接时评估和保留用户身份验证的控制权？

除了问题 1 中提到的租户限制功能之外，还可以应用[条件访问策略](/azure/active-directory/conditional-access/overview)来动态评估身份验证请求的风险并做出相应的反应。 Microsoft 建议 [随着时间的推移实现零](https://www.microsoft.com/security/zero-trust?rtc=1) 信任模型，我们可以使用 Azure AD 条件访问策略在移动和云第一世界保持控制。 可使用条件访问策略对身份验证请求是否成功作出实时决策，具体取决于以下诸多因素：

- 设备，设备是否已知/受信任/已加入域？
- IP – 身份验证请求是否来自已知公司 IP 地址？ 或者来自不信任的国家/地区？
- 应用程序 – 用户是否有权使用此应用程序？

然后，我们可以根据这些策略触发批准、触发 MFA 或阻止身份验证等策略。

### <a name="how-do-i-protect-against-viruses-and-malware"></a>如何防范病毒和恶意软件？

同样，Microsoft 365 为服务本身的各个层中标记为"优化"的终结点 [提供保护，本文档对此进行概述](/office365/Enterprise/office-365-malware-and-ransomware-protection)。 如前所述，在服务本身中提供这些安全元素比尝试在可能完全了解协议/流量的设备中这样做效率更高。 默认情况下，SharePoint Online [自动扫描文件上传中的](../security/office-365-security/virus-detection-in-spo.md) 已知恶意软件

对于上面列出的 Exchange 终结点， [Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 和 [Microsoft Defender for Microsoft 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 出色地为服务通信提供安全保护。

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>除了优化流量外，我是否可以直接发送更多流量？

应优先考虑标记为 **优化** 的终结点，因为这些终结点将为低级别的工作提供最大好处。 但是，如果需要，服务需要"允许标记的终结点"才能工作，并拥有为在必要时可以使用的终结点提供的 IP 地址。

此外，还有各种供应商提供基于云的代理/安全解决方案，称为安全 _Web_ 网关，可提供用于常规 Web 浏览的中心安全、控制和公司策略应用程序。 这些解决方案在云第一世界（如果高度可用、性能高且预配接近用户）中可以正常工作，通过允许从靠近用户的基于云的位置提供安全 Internet 访问。 这将无需通过 VPN/公司网络进行发夹，用于常规浏览流量，同时仍允许中央安全控制。

但是，即使这些解决方案已就位，Microsoft 仍强烈建议将标记为"优化"的 Microsoft 365 流量直接发送到服务。

有关允许直接访问 Azure 虚拟网络的指南，请参阅使用 [Azure VPN 网关点到站点的远程工作](/azure/vpn-gateway/work-remotely-support)。

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>为什么需要端口 80？ 流量是否明文发送？

端口 80 仅用于重定向到端口 443 会话之类的操作，不会通过端口 80 发送或访问任何客户数据。 [加密](../compliance/encryption.md)概述了 Microsoft 365 中传输和静态数据的加密，流量类型概述了如何使用 SRTP 保护 Teams 媒体流量。[](/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic)

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-microsoft-365"></a>此建议是否适用于使用 Microsoft 365 全球实例的中国用户？

**否**，不适用。 上述建议需要注意的一个注意事项是，中国用户连接到 Microsoft 365 的全球实例。 由于该区域会经常出现跨境网络拥挤现象，因此直接 Internet 出口性能可能会有变化。 该区域中的大多数客户都使用 VPN 将流量引入公司网络，并利用其经授权的 MPLS 专线或类似于通过优化路径的国家/地区之外的出口。 本文针对中国用户的 [Microsoft 365 性能优化进一步概述了这一点](microsoft-365-networking-china.md)。

### <a name="does-split-tunnel-configuration-work-for-teams-running-in-a-browser"></a>拆分隧道配置是否适用于在浏览器中运行的 Teams？

是，有注意事项。 获取 Microsoft Teams 客户端中列出的浏览器支持 [大多数 Teams 功能](/microsoftteams/get-clients#web-client)。

此外，Microsoft Edge **96** 及以上通过启用 Edge [WebRtcRespectOsRoutingTableEnabled](/deployedge/microsoft-edge-policies#webrtcrespectosroutingtableenabled) 策略支持对等流量的 VPN 拆分隧道。 目前，其他浏览器可能不支持对等流量的 VPN 拆分隧道。

## <a name="related-articles"></a>相关文章

[为 Microsoft 365 实现 VPN 拆分隧道](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365 的常见 VPN 拆分隧道方案](microsoft-365-vpn-common-scenarios.md)

[保护用于 VPN 拆分隧道的 Teams 媒体流量](microsoft-365-vpn-securing-teams.md)

[VPN 环境中 Stream 和实时事件的特殊注意事项](microsoft-365-vpn-stream-and-live-events.md)

[针对中国用户的 Microsoft 365 性能优化](microsoft-365-networking-china.md)

[Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)

[评估 Microsoft 365 网络连接](assessing-network-connectivity.md)

[Microsoft 365 网络和性能调整](network-planning-and-performance.md)

[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法（Microsoft 安全团队博客）](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[增强 Microsoft 的 VPN 性能：使用 Windows 10 VPN 配置文件以允许自动打开连接](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[运行 VPN：Microsoft 如何让远程工作人员互联](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft 全球网络](/azure/networking/microsoft-global-network)
