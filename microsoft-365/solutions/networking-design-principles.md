---
title: 网络上传（到云）- 一位架构师的观点
description: 了解如何通过避免最常见的陷阱来优化网络以实现云连接。
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
ms.openlocfilehash: 5f90e4616edd3534baefd64bba5a2eec640f6366
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823929"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>网络上传（到云）- 一位架构师的观点

在本文中，Microsoft 安全&合规性架构师 [Ed Fisher](https://www.linkedin.com/in/edfisher/) 介绍了如何通过避免最常见的陷阱来优化云连接网络。

## <a name="about-the-author"></a>作者简介

![埃德费舍尔照片。](../media/solutions-architecture-center/ed-fisher-networking.jpg)

我目前是零售和消费品团队的主要技术专家，专注于安全&合规性。 在过去的十年里，我一直与迁移到Office 365的客户合作。 我曾与一些小型商店合作，在政府机构和企业拥有数百万用户分布在世界各地，而许多其他客户之间，大多数拥有数以万计的用户，在世界各地的多个地点，需要更高的安全性和大量的合规性要求。 我帮助了数百家企业和数百万用户安全地迁移到云中。

在过去的 25 年里，我拥有包括安全性、基础结构和网络工程在内的背景，在加入 Microsoft 之前，我曾将两位以前的雇主调到Office 365，我已多次站在你这边，并记住情况。 虽然没有两个客户是相同的，但大多数客户都有类似的需求，在使用标准化服务（如任何 SaaS 或 PaaS 平台）时，最佳方法往往相同。

## <a name="its-not-the-network--its-how-youre-misusing-it"></a>它不是网络 ， 这是你如何 (错误) 使用它！

无论它发生多少次，它总是让我吃惊，如何 *创造性* 的安全团队和网络团队尝试得到如何，他们认为他们应该连接到 Microsoft 云服务。 他们始终坚持使用一些安全策略、合规性标准或更好的方法，而不愿意参与关于他们尝试完成的操作，或者 *如何* 有更好、更简单、更具成本效益和更高性能的方法进行对话。

当这种事情升级到我，我通常愿意接受挑战，引导他们通过如何和为什么，让他们到他们需要的地方。 但是，如果我是完全坦率的，我必须分享，有时我想让他们做他们会做的事，回来说，我告诉你，所以当他们最终承认它不起作用。 我有时可能想这么做， 但 *我不想* 这样做。 我所做的是试图解释我要在这篇文章中包括的所有内容。 无论你的角色如何，如果你的组织想要使用 Microsoft 云服务，那么下面的一些智慧或许可以帮助你完成此操作。

## <a name="guiding-principles"></a>指导原则

让我们从我们此处所做内容的一些基本规则开始。 我们正在讨论如何安全地连接到云服务，以确保最小复杂性和最大性能，同时保持真正的安全性。 即使你或你的客户无法对所有内容使用你喜欢的代理服务器，下面的内容都与其中任何一项都无关。

- **仅仅因为你可以， 并不意味着你应该**： 或用侏罗纪公园电影的伊恩 · 马尔科姆博士来解释“...是的， 是的， 但是你的安全团队全神贯注于他们是否能做到， 他们并没有停下来思考他们是否应该这样做。
- **安全性并不意味着复杂性**：你不是因为花更多的钱、路由更多设备或单击更多按钮而更安全。
- **通过 Internet 访问Office 365**：但这与 Internet Office 365不同。 它是由 Microsoft 管理并由你管理的 SaaS 服务。 与在 Internet 上访问的网站不同，实际上你可以在窗帘后面查看，并且可以应用满足策略和合规性标准所需的控件，只要你明白，虽然你可以达到你的目标，但你可能只需要以不同的方式执行这些控件。
- **断断续续，本地化的突破是好的**：每个人都希望将所有用户的所有 Internet 流量都回退到某个中心点，通常这样他们就可以监视它并强制实施策略，但通常是因为它比在所有位置预配 Internet 访问更便宜，或者正是他们这样做的方式。 但那些窒息点正是...流量窒息的点。 阻止用户浏览到 Instagram 或流式传输 cat 视频没有错，但不要以同样的方式对待任务关键型业务应用程序流量。
- **如果 DNS 不快乐，则不会高兴**：最佳设计的网络可能因 DNS 差而受阻碍，无论是通过向世界其他地区的服务器递归请求，还是使用 ISP 的 DNS 服务器或其他缓存 DNS 解析信息的公共 DNS 服务器。
- **仅仅因为你过去就是这样做的，并不意味着你现在应该这样做**：技术不断变化，Office 365也不例外。 应用为本地服务开发和部署的安全措施或控制 Web 冲浪不会提供相同级别的安全保证，并且会对性能产生重大的负面影响。
- **Office 365是为了通过 Internet 访问而构建** 的：简而言之就是它。 无论你想要在用户和边缘之间执行什么操作，流量在离开网络后和进入我们的网络之前仍会通过 Internet。 即使使用 Azure ExpressRoute 将某些延迟敏感流量从网络直接路由到我们的流量，Internet 连接也是绝对必需的。 接受它。 不要想得太过分了。

## <a name="where-bad-choices-are-often-made"></a>经常做出错误选择的地方

虽然有很多地方以安全的名义做出错误的决定，但这些是我最常与客户遇到的决策。 许多客户对话同时涉及所有这些内容。

### <a name="insufficient-resources-at-the-edge"></a>边缘资源不足

很少有客户在部署绿地环境，并且他们拥有多年的用户工作方式和 Internet 出口方式的经验。 无论客户是拥有代理服务器，还是允许直接访问，以及仅允许 NAT 出站流量，他们已执行了多年操作，并且不考虑在将传统的内部应用程序移到云中时，他们还要开始通过边缘进行抽水。

带宽始终是一个问题，但 NAT 设备可能没有足够的马力来处理增加的负载，并且可能过早地开始关闭连接以释放资源。 连接到Office 365的大多数客户端软件需要持久连接，而完全利用Office 365的用户可能具有 32 个或更多并发连接。 如果 NAT 设备过早删除它们，这些应用可能会在尝试使用不再存在的连接时变得无响应。 当他们放弃并尝试建立新连接时，它们会为网络设备增加更多负载。

### <a name="localized-breakout"></a>本地化的突破

此列表中的其他一切都归结为一件事 - 尽快离开网络并进入我们的网络。 将用户的流量回退到中央出口点，尤其是当该出口点位于用户所在的另一个区域时，会引入不必要的延迟，并影响客户端体验和下载速度。 Microsoft 在全球都有一些存在点，我们使用几乎所有主要 ISP 建立的所有服务和对等互连的前端，因此在 *本地* 路由用户流量可确保它以最小延迟快速进入我们的网络。

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS 解析流量应遵循 Internet 出口路径

当然，客户端若要查找任何终结点，需要使用 DNS。 Microsoft 的 DNS 服务器评估 DNS 请求的源，以确保我们返回的响应（以 Internet 表示）最接近请求源。 请确保已配置 DNS，以便名称解析请求与用户流量的路径相同，以免向用户提供本地出口，但将其发送到另一个区域中的终结点。 这意味着让本地 DNS 服务器“转到根”，而不是转发到远程数据中心的 DNS 服务器。 并注意公共和专用 DNS 服务，这些服务可能会缓存来自世界某一地区的结果，并将其服务到来自世界其他地区的请求。

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>要代理或不代理，这就是问题

首先要考虑的事项之一是是否代理用户与Office 365的连接。 那一个很容易;不代理。 Office 365是通过 Internet 访问的，但它不是 Internet。 它是核心服务的扩展，应该这样对待。 你可能希望代理执行的任何操作（例如 DLP、反恶意软件或内容检查）已在服务中可供你使用，并且可以大规模使用，无需破解 TLS 加密的连接。 但是，如果你真的想代理交通，你不能否则控制，请注意我们的指导和 [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) 流量 [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md)的类别。 我们有三类流量用于Office 365。 优化和允许真的应该直接和绕过你的代理。 可以代理默认值。 详细信息位于这些文档中...读取它们。

大多数坚持使用代理的客户，当他们实际查看其正在执行的操作时，都会意识到，当客户端向代理发出 HTTP CONNECT 请求时，代理现在只是一个昂贵的额外路由器。 使用的协议（如 MAPI 和 RTC）甚至不是 Web 代理所理解的协议，因此即使 TLS 破解，你也不会获得任何额外的安全性。 *你将* 获得额外的延迟。 有关详细信息，请参阅[https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md)此信息，包括针对Microsoft 365流量的“优化”、“允许”和“默认”类别。

最后，考虑对代理的总体影响及其相应的响应，以处理该影响。 由于通过代理建立的连接越来越多，因此可能会降低 TCP 缩放因子，使其不必缓冲这么多流量。 我见过客户，他们的代理重载，他们使用的缩放系数为 0。 由于 Scale Factor 是一个指数值，我们喜欢使用 8，因此缩放因子值的每一次减少都会对吞吐量产生巨大的负面影响。

TLS 检查意味着安全性！ 但不是真的！ 许多使用代理的客户都希望使用它们来检查所有流量，这意味着 TLS 会“中断并检查”。 对于通过 HTTPS 访问的网站执行此操作时 (隐私问题，尽管) 代理可能必须针对 10 甚至 20 个并发流执行此操作，只需几百毫秒。 如果有大量下载或涉及视频，则其中一个或多个连接可能会持续更长的时间，但总的来说，这些连接中的大多数建立、传输和关闭速度非常快。 执行中断和检查意味着代理必须执行两倍的工作。 对于从客户端到代理的每个连接，代理还必须单独连接回终结点。 所以，1 变成 2，2 变成 4，32 变成 64...看我要去哪里？ 对于典型的 Web 冲浪，可能可以调整代理解决方案的大小，但当你尝试为客户端连接Office 365执行相同的操作时，并发、长期连接的数量可能大于大小的顺序。

### <a name="streaming-isnt-important-except-that-it-is"></a>流式处理并不重要， *只是它是*

Office 365使用 UDP 的唯一服务即将Skype (停用) 和Microsoft Teams。 Teams使用 UDP 来流式传输流量，包括音频、视频和演示文稿共享。 流式处理流量是实时的，例如，当你与语音、视频和演示平台或演示进行联机会议时。 这些使用 UDP 是因为如果数据包被丢弃或无序到达，用户几乎无法发现它，并且流可以继续。

如果不允许从客户端到服务的出站 UDP 流量，它们可能会回退到使用 TCP。 但是，如果删除 TCP 数据包， *则一切都会停止* ，直到重新传输超时 (RTO) 过期，并且可以重新传输丢失的数据包。 如果数据包按顺序到达，一切都会停止，直到其他数据包到达并可以按顺序重新组装。 这两个都会导致音频中明显故障 (还记得 Max Headroom？) 和视频 (你单击了什么...哦， 它) ， 导致性能不佳和糟糕的用户体验。 还记得上面关于代理的内容吗？ 强制Teams客户端使用代理时，强制其使用 TCP。 因此，现在你要对性能造成两次负面影响。

### <a name="split-tunneling-may-seem-scary"></a>拆分隧道可能看起来很可怕

但事实并非如此。 与Office 365的所有连接都通过 TLS。 我们已经提供 TLS 1.2 相当长一段时间了，并且将很快禁用旧版本，因为旧版客户端仍然使用它们，这是一个风险。

强制 TLS 连接（其中 32 个）在转到服务之前通过 VPN 不会增加安全性。 它确实会增加延迟并降低总体吞吐量。 在某些 VPN 解决方案中，它甚至强制 UDP 通过 TCP 进行隧道处理，这将再次对流式处理流量产生非常负面的影响。 而且，除非你正在执行 TLS 检查，否则没有好处，所有缺点。 客户中一个非常常见的主题是，由于大多数员工是远程的，他们看到使用 VPN 让所有用户连接，而不是配置拆分隧道以访问 [Optimize 类别Office 365终结点](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)，从而产生显著的带宽和性能影响。

这是一个简单的修复，做拆分隧道，这是一个你应该做的。 有关详细信息，请确保[查看使用 VPN 拆分隧道的远程用户的优化Office 365连接](../enterprise/microsoft-365-vpn-split-tunnel.md)。

## <a name="the-sins-of-the-past"></a>过去的罪过

很多时候，做出错误选择的原因是， (1) 不知道服务的工作原理， (2) 试图遵守采用云之前编写的公司策略， (3 个) 安全团队，他们可能不容易相信有不止一种方法可以实现他们的目标。 希望上面的链接和下面的链接有助于第一个。 可能需要执行赞助才能度过第二次。 解决安全策略的目标（而不是其方法）有助于实现第三个目标。 从条件访问到内容审查，从 DLP 到信息保护，从终结点验证到零天威胁 ， 任何最终目标都可以通过Office 365中可用的内容来实现，并且不依赖于本地网络齿轮、强制 VPN 隧道和 TLS 中断和检查。

其他时候，在组织开始迁移到云之前调整大小和购买的硬件根本无法纵向扩展以处理新的流量模式和负载。 如果真的必须通过单个出口点和/或代理路由所有流量，请准备好相应地升级网络设备和带宽。 仔细监视这两者的利用率，因为随着加入的用户越来越多，体验不会慢慢减少。 一切都会很好， 直到达到临界点， 然后每个人都会受苦。

## <a name="exceptions-to-the-rules"></a>规则的异常

如果组织需要 [租户限制](/azure/active-directory/manage-apps/tenant-restrictions)，则需要使用 TLS 中断和检查的代理来强制某些流量通过代理，但无需强制所有流量通过代理。  这不是一个全部或全无命题，因此请注意需要由代理修改的内容。

如果要允许拆分隧道，但也要对常规 Web 流量使用代理，请确保 PAC 文件定义必须直接执行的操作，以及如何为通过 VPN 隧道的流量定义有趣的流量。 我们提供示例 PAC 文件 [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) ，这样可以更轻松地进行管理。

## <a name="conclusion"></a>结束语

数以万计的组织，包括几乎所有的财富500强，每天使用Office 365执行其任务关键职能。 他们这样做是安全的，他们这样做通过互联网。

无论你在实现什么安全目标，都可以通过一些方法来实现这些目标，这些目标不需要 VPN 连接、代理服务器、TLS 中断和检查，也不需要集中的 Internet 出口，以尽可能快地将用户的流量从网络中传输到我们的流量，这可以提供最佳性能，无论你的网络是公司总部， 远程办公室或在家工作的用户。 我们的指南基于如何构建Office 365服务，并确保安全且高性能的用户体验。

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

[使用 VPN 拆分隧道为远程用户Office 365连接](../enterprise/microsoft-365-vpn-split-tunnel.md)
