---
title: 网络 (云) — 一位架构师的见解
description: 了解如何通过避免最常见的错误来优化网络，实现云连接。
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 519f3035040f563a6f3663198be3952830cb21cb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158942"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>网络 (云) — 一位架构师的见解

本文中，Microsoft &安全与合规架构师 [Ed Fisher](https://www.linkedin.com/in/edfisher/)介绍了如何避免最常见的错误来优化网络，实现云连接。 

## <a name="about-the-author"></a>作者简介

![Ed Fisher 照片。](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

我目前是零售和消费商品团队的主要技术专家，主要负责&合规性。 过去十年中，我一直Office 365迁移到客户。 我与一些小型商店合作过，其中一些位于政府机构和企业，拥有数百万用户分布于世界各地的用户，以及许多介于两者之间的其他客户，其中大多数拥有数万个用户、位于世界各地的多个位置、需要更高程度的安全性以及大量合规性要求。 我帮助数以百万计的企业和数百万用户安全移动到云。

过去 25 年的背景包括安全、基础结构和网络工程，在加入 Microsoft 之前，我之前曾将两个雇主移动到 Office 365，因此我多次支持你，请记住这一点。 虽然没有两个客户是相同的，但大多数客户都有类似的需求，在使用标准化服务（如任何 SaaS 或 PaaS 平台）时，最佳方法往往相同。

## <a name="its-not-the-network--its-how-youre-misusing-it"></a>这不是网络，而是你在使用它时 (错误) 错误！

无论发生多少次，始终会向我说明创意安全团队和网络团队如何尝试了解他们应如何连接到 Microsoft 云服务。 他们始终有一些安全策略、合规性标准或更好的方法坚持使用，而不会愿意就他们尝试完成的任务展开对话，或者如何以更好、更简单、更经济高效和更高效的方式执行此操作。 

当此类事件升级至我时，我通常愿意接受挑战，并让他们了解其方式和原因，并让他们到达所需的位置。 但是，如果我完全直白，我有时必须分享一下，有时我想让他们执行他们将要执行哪些任务，然后返回说，我告知你，当他们最终发现它不起作用时。 我有时可能想要这样做，但 *不想这样做*。 我应尝试说明本文中将包含的所有内容。 无论你的角色如何，如果你的组织想要使用 Microsoft 云服务，那么以下内容可能有一些希望，可以帮助你实现此目标。

## <a name="guiding-principles"></a>指导原则

让我们从我们在此处所执行事情的一些基础规则开始。 我们讨论如何安全地连接到云服务，以确保最低复杂度和最佳性能，同时保证真实安全性。 以下任何内容均不与上述任何内容相反，即使你或你的客户无法将你最喜爱的代理服务器用于所有内容。

- **仅仅因为可以，并不意味着** 你应该：或者从 一个 一千多米的 一位 Ian Malcolm 电影"...是的，是的，但你的安全团队对他们是否可以停止思考是否该停止思考非常有希望。"
- **安全性并不意味着复杂性：** 你并非因为花费更多资金、通过更多设备路由或单击更多按钮而更加安全。
- **Office 365 Internet 访问** 网站：但与 Internet Office 365不同。 它是由 Microsoft 管理的 SaaS 服务，由你管理。 与在 Internet 上访问的网站不同，实际上你确实可以了解这些发现，并且可以应用符合策略和合规性标准所需的控制措施，只要了解在达到目标时，可能只需以不同方式实现它们。
- **断** 点坏，本地化后效果好：每个人始终希望将所有用户的所有 Internet 流量都返回到一个中心点，这样他们通常可以监视它并强制执行策略，但通常是因为这样做比在所有位置设置 Internet 访问要低，或者只是他们这样做。 但是，这些点正是这样...路点数。 阻止用户浏览 Instagram 或流式传输 cat 视频没有任何错误，但不要以相同方式处理任务关键型业务应用程序流量。
- 如果 **DNS** 不满意，则一定不满意：最好的设计网络可能是由较差的 DNS 所攻击，无论这是通过递归对世界上其他国家/地区的服务器的请求，还是使用 ISP 的 DNS 服务器或其他缓存 DNS 解析信息的公共 DNS 服务器。
- **正如你过去** 这样执行它一样，这并不意味着你现在应该这样做：技术会不断更改，Office 365也不例外。 应用为本地服务或控制 Web 部件而开发并部署的安全措施不会提供相同级别的安全保证，并且会对性能产生显著的负面影响。
- **Office 365构建** 为通过 Internet 访问：简而言之就是这样。 无论你的用户和边缘之间要做什么，流量在离开网络之后、进入我们的网络之前仍将通过 Internet。 即使你使用 Azure ExpressRoute 将某些延迟敏感流量直接从网络路由到我们的网络，也绝对需要 Internet 连接。 接受它。 不要过度认为它。

## <a name="where-bad-choices-are-often-made"></a>经常做出错误选择的地方

虽然有很多地方在安全名称中做出错误决策，但这些都是我经常与客户接触的地方。 许多客户对话同时涉及所有这些内容。

### <a name="insufficient-resources-at-the-edge"></a>边缘资源不足

非常少的客户正在部署绿色环境，他们拥有用户的工作和 Internet 出口等方面的经验。 无论客户是具有代理服务器，还是允许直接访问且仅允许 NAT 出站流量，他们一直在执行此操作多年，不会考虑他们在将传统内部应用程序移出云时，开始通过边缘访问的量。

带宽始终是一个问题，但 NAT 设备可能没有足够的能力来处理增加的负载，并且可能会提前关闭连接以释放资源。 大多数连接到客户端的客户端软件Office 365永久连接，并且完全利用 Office 365的用户可能拥有 32 个或多个并发连接。 如果 NAT 设备提前丢弃它们，这些应用可能在尝试使用不再存在的连接时无响应。 当他们放弃并尝试建立新连接时，他们会为网络齿轮增加更多的负载。

### <a name="localized-breakout"></a>本地化后

此列表中的其他所有内容都归为一件事，即尽快离开网络和我们的网络。 将用户的流量返回到中心出口点，尤其是在该出口点位于用户位于另一个区域时，这会造成不必要的延迟，并影响客户端体验和下载速度。 Microsoft 具有全球的接入点，用于我们的所有服务和与几乎所有主要 ISP 建立对等的前端，因此将用户的流量路由到本地可确保它以最小延迟快速进入我们的网络。

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS 解析流量应遵循 Internet 出口路径

当然，客户端需要使用 DNS 来查找任何终结点。 Microsoft 的 DNS 服务器评估 DNS 请求的来源，以确保我们返回的响应（以 Internet 术语而言）最接近请求源的响应。 请确保你的 DNS 已配置，以便名称解析请求与用户的流量进入相同的路径，以免你向它们提供本地出口，但提供到另一个地区的终结点。 这意味着允许本地 DNS 服务器"转到根"，而不是转发到远程数据中心的 DNS 服务器。 此外，请留意公用和专用 DNS 服务，这些服务可能会缓存来自世界上一部分的结果，并使用它们处理来自世界其他地方的请求。

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>要代理还是不代理，这就是问题

要考虑的第一件事是是否将用户的连接代理到Office 365。 这很简单;不代理。 Office 365通过 Internet 访问，但它不是 Internet。 它是核心服务的扩展，应作为此类服务处理。 您可能希望代理执行的任何操作（如 DLP、反恶意软件或内容检查）已在服务中可用，并且可大规模使用，而无需破解 TLS 加密的连接。 但是，如果确实要代理无法控制的流量，请留意我们的指南和 中的 [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) 流量类别 [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) 。 我们有三种类别的流量用于Office 365。 "优化"和"允许"确实应该直接进行，并绕过代理。 可以代理默认值。 详细信息请参阅这些文档...读取它们。

当客户实际查看自己正在执行哪些操作时，坚持使用代理的客户会意识到，当客户端向代理发送 HTTP CONNECT 请求时，代理现在只是一个昂贵的额外路由器。 使用的协议（如 MAPI 和 RTC）甚至不是 Web 代理理解的协议，因此即使通过 TLS 破解，你并没有真正获得任何额外的安全性。 *您* 正获得额外的延迟。 有关详细信息 [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) ，请参阅针对流量的优化、允许和Microsoft 365类别。

最后，考虑对代理的总体影响及其相应的响应来处理该影响。 随着通过代理建立的连接越来越多，它可能会降低 TCP 比例系数，这样它就不必缓冲太多流量。 我所见，他们的代理超载到他们使用的是比例系数 0 的客户。 由于比例系数是指数值，并且我们希望使用 8，因此每次降低比例系数值会对吞吐量产生巨大负面影响。

TLS 检查意味着安全！ 但其实不是！ 许多具有代理的客户希望使用它们检查所有流量，这意味着 TLS"中断并检查"。 为通过 HTTPS 访问的网站执行 (隐私问题) 您的代理可能需要为 10 甚至 20 个并发流执行这些操作，数百毫秒。 如果下载量很大或视频可能涉及，则其中一个或多个连接可能会持续更长时间，但从总体上说，这些连接中的大多数连接会非常快速地建立、转移和关闭。 执行中断和检查意味着代理必须执行双倍工作。 对于从客户端到代理的每个连接，代理还必须与终结点建立单独的连接。 因此，1 变为 2，2 变为 4，32 变为 64...查看我在哪里？ 您可能调整代理解决方案的大小，但当您尝试对与 Office 365 的客户端连接执行相同的操作时，并发长期连接的数量可能大于您调整大小的大小。

### <a name="streaming-isnt-important-except-that-it-is"></a>流式处理不是很重要，只是 *它是*

使用 UDP Office 365服务即将Skype (停用，) Microsoft Teams。 Teams UDP 流式传输流量，包括音频、视频和演示文稿共享。 流式传输是实时流量，例如当你要召开具有语音、视频的联机会议，以及演示平台或执行演示时。 它们使用 UDP 的原因是，如果数据包被丢弃或顺序中断，用户几乎无法注意到数据包，并且流可以继续运行。

如果不允许从客户端到服务的出站 UDP 流量，它们可以回退到使用 TCP。 但是，如果丢弃了 TCP数据包，则一切将停止，直到 RTO (重新传输超时) 且可以重新传输丢失的数据包。 如果数据包未按序到达，则所有内容将停止，直到其他数据包到达，并可以按序重新组合。 这两种操作都会导致音频问题 (最大空间？) 以及视频 (你是否单击了某些内容...有一) ，会导致性能不佳和用户体验不佳。 请记住我上面关于代理的哪些内容？ 当强制Teams客户端使用代理时，会强制其使用 TCP。 因此，现在对性能造成负面影响两次。

### <a name="split-tunneling-may-seem-scary"></a>拆分隧道可能看起来不令人难看

但它不是。 所有到 Office 365的连接都通过 TLS 进行。 我们已提供 TLS 1.2 相当长的一段时间，并且很快将禁用较旧版本，因为旧版客户端仍使用它们，这是一种风险。

强制 TLS 连接（或其中 32 个）先通过 VPN，然后再转到服务，这不会添加安全性。 它会增加延迟并降低总体吞吐量。 在某些 VPN 解决方案中，它甚至会强制 UDP 通过 TCP 隧道，这同样会对流式传输产生非常负面影响。 而且，除非你要执行 TLS 检查，否则没有缺点，所有缺点都一样。 客户之间的一个非常常见的主题（现在大多数员工都是远程工作者）的一个常见主题是，他们看到通过使所有用户使用 VPN 进行连接（而不是配置拆分隧道来访问"优化"类别 Office 365 终结点[）](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)的显著带宽和性能影响。

执行拆分隧道是一个简单的解决方法，你应该这样做。 有关详细信息，请确保查看使用[VPN 拆分Office 365为远程用户优化连接](../enterprise/microsoft-365-vpn-split-tunnel.md)。

## <a name="the-sins-of-the-past"></a>过去的犯罪

很多时候，错误选择的原因包括： (1) 不知道服务的工作方式、 (2) 尝试遵守采用云之前编写的公司策略，以及无法轻易确信有多种方法可以实现目标的 (3) 安全团队。 希望上述和下面的链接将有助于第一个操作。 可能需要管理层的支持才能通过第二项。 实现安全策略的目标（而不是其方法）有助于实现第三个目标。 从条件访问到内容审核、DLP 到信息保护、终结点验证到零日威胁- 合理安全策略的任何最终目标都可以通过 Office 365 中提供的内容实现，而无需依赖本地网络齿轮、强制 VPN 隧道和 TLS 中断和检查。

其他时候，在组织开始移动到云之前调整大小并购买的硬件无法向上扩展以处理新的流量模式和负载。 如果确实必须通过单个出口点路由所有流量，并/或代理它，请准备好相应地升级网络设备和带宽。 请仔细监视这两者上的利用率，因为随着更多用户上网，体验不会下降。 一切正常，直到达到提示点，然后每个人都受到影响。

## <a name="exceptions-to-the-rules"></a>规则例外

如果你的组织需要 [租户限制](/azure/active-directory/manage-apps/tenant-restrictions)，你将需要使用具有 TLS 中断和检查的代理来强制某些流量通过代理，但你无需强制所有流量通过它。  这不是全部或全无的主张，因此请注意需要由代理修改哪些方面。

如果你打算允许拆分隧道，但也为常规 Web 流量使用代理，请确保 PAC 文件定义必须直接传输的内容以及如何为通过 VPN 隧道的内容定义有趣的流量。 我们提供了示例 PAC [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) 文件，这样更易于管理。

## <a name="conclusion"></a>结论

成千上万个组织（包括几乎所有全球 500 强组织）Office 365日常任务关键功能。 它们可安全执行，并且通过 Internet 执行。

无论你实现什么安全目标，都有许多方法无需 VPN 连接、代理服务器、TLS 中断和检查或集中式 Internet 出口，以尽快将用户的流量从网络和我们的网络获取，无论网络是公司总部，都可以提供最佳性能， 远程办公室或在家工作的用户。 我们的指南基于如何Office 365服务，并确保获得安全且性能丰富的用户体验。

## <a name="further-reading"></a>进一步阅读

[Office 365网络连接原则](../enterprise/microsoft-365-network-connectivity-principles.md)

[Office 365 URL 和 IP 地址范围](../enterprise/urls-and-ip-address-ranges.md)

[管理 Office 365 终结点](../enterprise/managing-office-365-endpoints.md)

[Office 365 IP 地址和 URL Web 服务](../enterprise/microsoft-365-ip-web-service.md)

[评估 Office 365 网络连接](../enterprise/assessing-network-connectivity.md)

[Office 365 网络和性能优化](../enterprise/network-planning-and-performance.md)

[评估 Office 365 网络连接](../enterprise/assessing-network-connectivity.md)

[使用基线和性能历史记录优化 Office 365 性能](../enterprise/performance-tuning-using-baselines-and-history.md)

[Office 365 性能疑难解答计划](../enterprise/performance-troubleshooting-plan.md)

[内容分发网络](../enterprise/content-delivery-networks.md)

[Microsoft 365 连接测试](https://connectivity.office.com/)

[Microsoft 如何构建其快速可靠的全球网络](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 网络工作博客](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365 VPN 拆分隧道为远程用户建立连接](../enterprise/microsoft-365-vpn-split-tunnel.md)
