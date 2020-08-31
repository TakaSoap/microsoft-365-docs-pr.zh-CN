---
title: " (云) 的网络连接—一个架构师的视点"
description: 说明。
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: a005d56dcca08c05eb433ef75ca3870785b39f19
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308125"
---
# <a name="networking-up-to-the-cloud--one-architects-viewpoint"></a> (云) 的网络连接—一个架构师的视点

在本文的 [Fisher](https://www.linkedin.com/in/edfisher/)中，安全 & 合规性架构师在 Microsoft 介绍了如何通过避免最常见的缺陷来优化云连接的网络。 

## <a name="about-the-author"></a>作者简介

![Ed Fisher 照片](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

目前我是位于东南部地区的主要技术专家，重点关注安全性 & 合规性。 我已与在过去十年中移动到 Office 365 的客户合作。 我已经使用了规模较小的公司，在全球范围内的政府机构和企业中分布了数百万个用户，在这两个客户之间，多数用户在全球范围内拥有成千上万个用户，需要更高的安全性，需要更高的安全级别和许多合规性要求。 我已帮助数百个企业和数百万个用户安全地和安全地迁移到云。

在过去25年的背景中，包括安全性、基础结构和网络工程，并在加入 Microsoft 之前将我以前的两个雇主移到了 Office 365 中，我已在表的一侧进行了大量时间，并记住了类似的内容。 虽然不是两个客户都是相同的，但大多数客户都有相似的需求，并且在使用标准化服务（如任何 SaaS 或 PaaS 平台）时，最好的方法往往是相同的。



## <a name="its-not-the-network--its-how-youre-misusing-it"></a>它不是网络，而是使用 (mis) 的方法！

无论它发生多少次，amaze 的 *创意* 安全团队和网络团队也不会尝试如何将他们认为他们应连接到 Microsoft 云服务。 始终使用某些安全策略、合规性标准或更好的方式来使用，而无需参与会话以了解他们尝试完成的操作，或者 *如何* 更好、更轻松、更经济高效地执行此操作。 

当此类内容升级到我时，我通常愿意采取挑战，并通过 hows 和 whys 引导他们，并在需要的地方获取它们。 但如果我完全告别，我必须共享，有时我只希望让他们做些什么，然后再回来告诉你，如果他们最后 concede 它不起作用。 我可能希望有时这样做，但 *不*是。 我要做的就是尝试解释我在此文章中要包括的所有内容。 无论你的角色如何，如果你的组织想要使用 Microsoft 云服务，可能会在以下方面为你提供一些可帮助解决的智慧。


## <a name="guiding-principles"></a>指导原则
让我们从围绕我们要做的事情的一些基本规则开始。 我们正在讨论如何安全地连接到云服务，以确保最低的复杂性和最大的性能，同时维护真正的安全性。 无论你或你的客户，都不会将其作为一个计数器的计数器，即使你或你的客户，也不会将你喜欢的代理服务器用于所有内容。

- **简单说，这并不意味着您应该** —或者从 Jurassic 寄存电影中 Paraphrase Ian Malcolm。 . . 是的，是的，但是你的安全团队是这样 preoccupied 的，无论他们是否可以不会停止思考。    
- **安全性并不意味着复杂性** ，因为您需要更多资金、路由更多设备或单击 "更多按钮"，则不是更安全。
- **通过 internet 访问 office 365** ，但与 office 365 是 internet 一样，这一点也不相同。 它是由 Microsoft 托管并由你管理的 SaaS 服务。 与您在 Internet 上访问的网站不同，实际上您确实可以查看 curtain，并可以应用需要满足您的策略和合规性标准的控件，但前提是您知道在满足目标的同时，您可能只需以不同方式执行这些操作即可。
- **Chokepoints 是坏的，已本地化的 breakouts 是很好的** —每个人始终都希望将其所有用户的所有 Internet 通信都 backhaul 到某个中心点，这样，他们就可以监视它并强制实施策略，但通常是因为它比在其所有位置设置 Internet 访问更便宜，或者仅仅是它们的工作方式。 但这些 chokepoints 正好是 .。。流量浅压深的点。 阻止用户浏览到 Instagram 或流式 cat 视频不会有任何问题，但不要以相同的方式处理您的任务关键型业务应用程序流量。
- [！注意]**如果 dns ain't 快乐，ain't 没有什么**—最佳设计的网络可能受到不良 DNS 的 hamstrung，无论是通过 recursing 请求到世界各地的其他区域中的服务器，还是使用您的 ISP 的 dns 服务器或其他缓存 dns 解析信息的公共 DNS 服务器。 
- 这**是因为这就是您使用它的方式，并不意味着您现在应如何做，** 而不是经常发生的技术变化，而 Office 365 也不例外。 应用为本地服务开发和部署的安全措施或控制网上冲浪不会提供相同级别的安全保证，并且可能会对性能产生严重的负面影响。
- **Office 365 是为通过 Internet 进行访问而构建** 的，这就是简言之。 无论您想要在您的用户和边缘之间做什么，在 Internet 离开你的网络并进入我们之前，该流量仍将通过 Internet。 即使你使用 Azure ExpressRoute 将某些延迟敏感流量从你的网络直接路由到我们，也绝对需要 Internet 连接。 接受它。 不要 overthink 它。

## <a name="where-bad-choices-are-often-made"></a>经常发生的错误选择

虽然有很多地方在安全的名称中做出了错误的决策，但它们是我最常与客户一起遇到的。 许多客户对话同时涉及到所有这些。

### <a name="insufficient-resources-at-the-edge"></a>边缘的资源不足
很少有客户正在部署 greenfield 环境，并且他们的用户的工作方式和 Internet 出口等方面的经验也很多年。 无论客户是否具有代理服务器或允许直接访问，还是允许直接访问，以及 NAT 出站通信，他们都已完成多年的工作，而不考虑在将传统的内部应用程序移动到云时，要开始在其边缘中进行泵的次数。

带宽始终是一个需要关注的问题，但 NAT 设备可能没有足够的能力来处理增加的负载，并且可能会启动过早关闭连接来释放资源。 连接到 Office 365 的大多数客户端软件需要持续连接，并且使用 Office 365 的用户可能会有32或更多的并发连接。 如果 NAT 设备提前删除它们，则这些应用程序可能会在尝试使用已不再存在的连接时变得无响应。 当他们放弃并尝试建立新的连接时，它们会给网络设备带来更多负载。

### <a name="localized-breakout"></a>本地化的专题讨论
此列表中的所有其他内容都有一件事情，即尽快将网络和到我们的参与。 将您的用户的流量回程到一个中央出口点，尤其是当该出局点位于与您的用户位于不同的区域中时，会带来不必要的延迟，同时还会影响客户端体验和下载速度。 Microsoft 在世界各地有点的位置，所有服务和对等都与几乎每个主要 ISP 建立的对等关系，因此将用户的流量路由到 *本地* 可确保它以最小延迟速度快速进入网络中。 

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS 解析流量应遵循 Internet 传出路径
当然，若要让客户端查找任何终结点，则需要使用 DNS。 Microsoft 的 DNS 服务器评估 DNS 请求的来源，以确保我们以 Internet 术语的形式返回最接近请求源的响应。 请确保您的 DNS 已配置，以便名称解析请求与您的用户的流量在同一路径中，lest 你将其分配给了本地出口，而不是另一个地区的终结点。 这意味着允许本地 DNS 服务器 "转到根目录"，而不是在远程数据中心转发到 DNS 服务器。 并注意公共和专用 DNS 服务，它可能会缓存来自世界上某个部分的结果，并为其提供来自世界其他部件的请求。

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>"代理" 或 "不是代理"，即问题
要考虑的首要事项之一是是否将用户的连接代理到 Office 365。 这是一件轻松的事;不代理。 Office 365 通过 Internet 访问，但不是 Internet。 它是核心服务的扩展，应按此方式处理。 您可能需要代理执行的任何操作（如 DLP 或反恶意软件或内容检查）都已在服务中可用，并且可以在扩展时使用，而无需破解 TLS 加密的连接。 但是，如果确实想要代理无法以其他方式控制的通信，请注意中的指导 [https://aka.ms/pnc](https://aka.ms/pnc) 和流量类别 [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) 。 我们有三种类型的 Office 365 流量。 优化和允许真正应直接跳过代理。 默认值可以是代理的。 这些文档中有详细信息。 . . 阅读。

如果大多数客户坚持使用代理，则在实际查看它们的操作时，请注意，当客户端向代理发出 HTTP CONNECT 请求时，代理现在只是昂贵的额外路由器。 使用中的协议（如 MAPI 和 RTC）甚至不是 web 代理可识别的协议，因此即使采用 TLS 破解，也不会真正获得任何额外的安全性。 您 *将* 获得额外的延迟。 [https://aka.ms/pnc](https://aka.ms/pnc)有关详细信息，包括 Microsoft 365 流量的 "优化"、"允许" 和 "默认" 类别，请参阅。

最后，考虑对代理的整体影响及其对应的响应，以处理这一影响。 随着越来越多的连接通过代理的连接，它可能会降低 TCP 比例因子，这样就不必再缓冲这么多的流量。 我已向客户显示其代理因其使用比例系数0而过载的情况。 由于比例因子是指数值，我们喜欢使用8，所以比例因子值的每个缩减值都是对吞吐量的巨大负面影响。

TLS 检查是指安全性！ 但不是真的！ 许多具有代理的客户需要使用它们来检查所有流量，这意味着 TLS "中断并检查"。 当您为通过 HTTPS 访问的网站执行此操作时 (隐私问题（假设) 代理可能必须为10甚至20个并发流执行此操作，几百毫秒。 如果有较大的下载或可能涉及的视频，则其中一个或多个连接可能持续更长时间，但是整个中，大多数这些连接的建立、转移和关闭速度都非常快。 执行中断和检查意味着代理必须执行双倍的工作。 对于从客户端到代理的每个连接，代理还必须对终结点进行单独的连接。 因此，一个变为2，二变成四，32成为64。 . . 查看我的转到何处？ 您可能已将代理解决方案的规模定义为典型的 web 冲浪，但在尝试对 Office 365 的客户端连接执行相同的操作时，并发连接数和持续时间可能会大于您所调整的大小。

### <a name="streaming-isnt-important-except-that-it-is"></a>流并不重要，不同之 *处在于*
使用 UDP 的 Office 365 中唯一的服务在 Skype (即将淘汰) 和 Microsoft 团队。 团队对流流量（包括音频、视频和演示文稿共享）使用 UDP。 流式传输是实时的，例如，当你使用语音、视频和演示卡片或演示时进行联机会议时。 这些方法使用 UDP，因为如果丢弃数据包或不按顺序到达数据包，则用户实际上是 unnoticeable，并且流可以随时继续进行。 

如果不允许从客户端到服务的出站 UDP 流量，则可以回退到使用 TCP。 但是，如果断开 TCP 数据包， *所有内容都会停止* ，直到重新传输超时 (RTO) 过期，并且丢失的数据包可以重新传输。 如果数据包的到达顺序不正常，则一切都会停止，直到其他数据包到达，并且可以按顺序重新组合。 这两个问题都会导致音频 () 和视频的最大余地 (您单击了 "someth"。 . . 哦，它已) ，导致性能不佳和用户体验不佳。 并记住我在代理中放置了哪些内容？ 当您强制团队客户端使用代理时，强制其使用 TCP。 因此，现在会导致消极的性能影响两次。

### <a name="split-tunneling-may-seem-scary"></a>拆分隧道看起来可能非常可怕
但不是这样。 与 Office 365 的所有连接都通过 TLS。 现在我们已为 TLS 1.2 提供了很长时间，将立即禁用旧版本，因为旧版客户端仍在使用它们，这是一种风险。

强制 TLS 连接（或32）在将 VPN 转到服务之前，先通过 VPN 连接，而不会添加安全性。 它会增加延迟并降低整体吞吐量。 在某些 VPN 解决方案中，它甚至会强制 UDP 通过 TCP 进行隧道传输，这将对流式传输产生负面影响。 而且，除非您执行 TLS 检查，否则不会有任何优势，也没有任何缺点。 目前，客户中的大多数工作人员都是远程的，现在他们的大部分工作都是远程的，因此他们看到的带宽和性能影响是，通过使用 VPN 来连接其所有用户，而不是为 access [优化类别 Office 365 终结点](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories)配置拆分隧道。

这是一种简单的解决方法，即拆分隧道，它是您应该执行的操作。 有关详细信息，请务必查看 [使用 VPN 拆分隧道为远程用户优化 Office 365 连接](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)。


## <a name="the-sins-of-the-past"></a>过去的罪
很多情况下，选择不当的原因来自 (1) 不知道服务的工作方式， (2) 尝试遵循在采用云之前编写的公司策略，以及 (3) 安全团队，他们可能无法轻松地确定是否有多种方法来实现其目标。 但愿上面的链接和下面的链接将为你提供第一个帮助。 执行资助可能需要执行，以使其超过第二个。 解决安全策略的目标（而不是其方法）有助于第三方。 从条件访问到内容裁决、DLP 到信息保护、对零天威胁的终结点验证-任何最终目标都可以通过 Office 365 中提供的功能完成，并且在本地网络设备、强制 VPN 隧道和 TLS 中断之间没有任何依赖关系，也不会进行检查。 

其他时候，在组织开始迁移到云中之前调整和购买的硬件只是无法进行扩展以处理新的流量模式和负载。 如果您确实必须通过一个出口点路由所有流量，并/或为其代理，请进行相应的准备，以便升级网络设备和带宽。 仔细监视这两个方面的利用率，因为随着更多用户的集成，体验不会慢慢降低。 一切都能正常工作，直到到达问题点，然后所有人都会受到影响。 

## <a name="exceptions-to-the-rules"></a>规则的例外情况

如果您的组织需要 [租户限制](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)，则需要使用带 TLS 中断的代理，并通过代理检查以强制某些流量，但不必强制通过它的所有流量。  这不是全部或全部的主张，因此请注意需要由代理修改的内容。 

如果要允许拆分隧道，但还要将代理用于常规 web 流量，请确保 PAC 文件定义了直接应直接实现的操作，以及如何为通过 VPN 隧道定义的感兴趣的流量进行定义。 我们提供的示例 PAC 文件 [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) 将使其更易于管理。

## <a name="conclusion"></a>结束语

成千上万的组织（包括几乎所有《财富500》）在每天使用 Office 365 来实现其任务关键型功能。 他们会安全地执行此操作，并通过 Internet 执行此操作。

 无论您在采用什么安全目标，都可以使用以下方法来实现：不需要 VPN 连接、代理服务器、TLS 断开和检查或集中的 Internet 出口，从而尽可能快速地将用户的流量从您的网络和网上的网络流量中获取，这样可以提供最佳性能，无论您的网络是公司总部还是远程办公室，或者该用户在家工作。 我们的指南基于 Office 365 服务的构建方式，以确保用户体验安全且性能良好。

## <a name="further-reading"></a>进一步阅读

[Office 365 网络连接原则](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)

[管理 Office 365 终结点](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints)

[Office 365 IP 地址和 URL Web 服务](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-ip-web-service)

[评估 Office 365 网络连接](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[Office 365 网络和性能优化](https://docs.microsoft.com/microsoft-365/enterprise/network-planning-and-performance)

[评估 Office 365 网络连接](https://docs.microsoft.com/microsoft-365/enterprise/assessing-network-connectivity)

[使用基线和性能历史记录优化 Office 365 性能](https://docs.microsoft.com/microsoft-365/enterprise/performance-tuning-using-baselines-and-history)

[Office 365 性能疑难解答计划](https://docs.microsoft.com/microsoft-365/enterprise/performance-troubleshooting-plan)

[内容分发网络](https://docs.microsoft.com/microsoft-365/enterprise/content-delivery-networks)

[Microsoft 365 连接测试](https://connectivity.office.com/)

[Microsoft 如何构建其快速可靠的全球网络](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365 网络工作博客](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[使用 VPN 拆分隧道的远程用户的 Office 365 连接](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)


