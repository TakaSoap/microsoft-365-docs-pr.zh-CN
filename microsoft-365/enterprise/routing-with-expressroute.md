---
title: 通过适用于 Office 365 的 ExpressRoute 进行路由
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
- MOE150
- BCS160
ms.assetid: e1da26c6-2d39-4379-af6f-4da213218408
description: 本文介绍 Azure ExpressRoute 路由要求、电路和路由域，以用于Office 365。
ms.openlocfilehash: d6fab2dd9a7e7519eb1f56cebccaf345685cc0cd
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806920"
---
# <a name="routing-with-expressroute-for-office-365"></a>通过适用于 Office 365 的 ExpressRoute 进行路由

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

若要正确了解使用 Azure ExpressRoute Office 365路由流量，你需要掌握核心 [ExpressRoute](/azure/expressroute/expressroute-routing) 路由要求、[ExpressRoute 电路和路由域](/azure/expressroute/expressroute-circuit-peerings)。 这些为使用客户将依赖的 ExpressRoute Office 365基础。
  
您需要了解的上述文章中的一些关键项包括：
  
- ExpressRoute 电路不会映射到特定的物理基础结构，而是 Microsoft 和对等提供商代表你在单个对等位置建立的逻辑连接。

- ExpressRoute 电路和客户密钥之间的映射为 1：1。

- 每个电路可以支持两个独立的对等关系 (Azure 专用对等和 Microsoft 对等) ;Office 365需要 Microsoft 对等。

- 每个电路都有一个在所有对等关系中共享的固定带宽。

- 任何公共 IPv4 地址和用于 ExpressRoute 电路的公共 AS 号码都必须被验证为归你所有，或由地址范围的所有者专门分配给你。

- 虚拟 ExpressRoute 电路是全局冗余的，将遵循标准 BGP 路由做法。 这就是在主动/主动配置中建议每个提供商的两个物理电路的原因。

有关受支持的 [服务](/azure/expressroute/expressroute-faqs) 、成本和配置详细信息的详细信息，请参阅常见问题页面。 有关提供 Microsoft 对等支持的连接提供程序列表的信息，请参阅 [ExpressRoute](/azure/expressroute/expressroute-locations) 位置文章。 我们还记录了第 9 频道上的 Azure [ExpressRoute for Office 365 培训](https://channel9.msdn.com/series/aer)系列（10 部分）以帮助更详尽地解释概念。
  
## <a name="ensuring-route-symmetry"></a>确保路由对称

Office 365前端服务器均可在 Internet 和 ExpressRoute 上访问。 当两者同时可用时，这些服务器将倾向于通过 ExpressRoute 电路路由回本地。 因此，如果来自网络的流量倾向于通过 Internet 线路进行路由，则可能会进行路线不对称。 非对称路由是一个问题，因为执行有状态数据包检查的设备可能会阻止遵循与所关注出站数据包不同的路径的返回流量。
  
无论通过 Internet 还是 ExpressRoute Office 365连接，源都必须是可公开路由的地址。 由于许多客户直接与 Microsoft 对等，因此在客户之间可能重复的情况下使用专用地址不可行。
  
以下方案将启动Office 365到本地网络的通信。 为了简化网络设计，我们建议通过 Internet 路径路由以下内容。
  
- SMTP 服务，例如从 Exchange Online 租户发送到本地主机的邮件，或SharePoint从 SharePoint Online 发送到本地主机的联机邮件。 与通过 ExpressRoute 电路共享的路由前缀和通过 ExpressRoute 在本地 SMTP 服务器上做广告的路由前缀，SMTP 协议在 Microsoft 网络中使用得更为广泛，这可能会导致这些其他服务失败。

- 登录密码验证期间 ADFS。

- [Exchange Server混合部署](/exchange/exchange-hybrid)。

- [SharePoint联合混合搜索](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)。

- [SharePoint混合BCS](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)。

- [Skype for Business混合](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)和/或[Skype for Business联盟](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。

- [Skype for Business云连接器](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)。

若要让 Microsoft 为这些双向流量路由回网络，必须与 Microsoft 共享到本地设备的 BGP 路由。 通过 ExpressRoute 向 Microsoft 播发路由前缀时，应遵循以下最佳做法：

1) 不要向公共 Internet 和 ExpressRoute 公布相同的公共 IP 地址路由前缀。 建议通过 ExpressRoute 向 Microsoft 发送的 IP BGP 路由前缀广告来自一个完全未向 Internet 播发的范围。 如果由于可用的 IP 地址空间无法实现此目的，则必须确保通过 ExpressRoute 播发比任何 Internet 线路更具体的范围。

2) 每个 ExpressRoute 电路使用单独的 NAT IP 池，并独立于 Internet 线路。

3) 向 Microsoft 播发的任何路由都将吸引来自 Microsoft 网络的任何服务器的网络流量，而不仅是那些通过 ExpressRoute 向网络播发路由的服务器。 仅向团队定义并理解路由方案的服务器播发路由。 在网络的每个 ExpressRoute 电路上播发单独的 IP 地址路由前缀。
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>确定通过 ExpressRoute 路由的应用程序和功能

当你使用 Microsoft 对等路由域配置对等关系并经过批准进行适当访问时，你将能够看到所有通过 ExpressRoute 提供的 PaaS 和 SaaS 服务。 可以使用Office 365 [BGP](./bgp-communities-in-expressroute.md) 社区或路由筛选器管理专为 ExpressRoute 设计的[服务](/azure/expressroute/how-to-routefilter-portal)。
  
使用 Microsoft 对等Office 365的每个功能按应用程序类型和 FQDN [Office 365终结点](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)一文列出。 使用表中 FQDN 的原因是允许客户使用 PAC 文件或其他代理配置管理流量，请参阅我们的管理 OFFICE 365 终结点（例如 PAC 文件[）](./managing-office-365-endpoints.md)的指南。
  
在某些情况下，我们使用了通配符域，其中一个或多个子 FQDN 的播发方式与更高级别的通配符域不同。 通常，当通配符表示一长列表的服务器时，这些服务器都播发到 ExpressRoute 和 Internet，而仅向 Internet 播发一小部分目标，或者反向播发目标。 请参阅下表以了解区别。
  
此表显示向 Internet 和 Azure ExpressRoute 播发的通配符 FQDN 以及仅向 Internet 播发的子 FQDN。

|**向 ExpressRoute 和 Internet 线路播发的通配符域**|**仅向 Internet 线路播发的子 FQDN**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

通常，PAC 文件旨在将网络请求直接发送到 ExpressRoute 播发的终结点，并将所有其他网络请求发送到代理。 如果你要配置类似这样的 PAC 文件，请按以下顺序撰写 PAC 文件：
  
1. 在 PAC 文件顶部包含上表中第二列的子 FQN，向代理发送流量。 我们已生成一个示例 PAC 文件，供你在管理终结点一文[Office 365使用](./managing-office-365-endpoints.md)。

2. 包括本文第一节下方标记为 ExpressRoute 的所有 FQDN，将流量直接发送到 ExpressRoute 电路。[](./urls-and-ip-address-ranges.md)

3. 包括这两个条目下面的任何其他网络终结点或规则，向代理发送流量。

此表只显示在向 Azure ExpressRoute 和 Internet 线路播发的子 FQN 旁边公布到 Internet 线路的通配符域。 对于上面的 PAC 文件，下表中列 2 中的 FQDN 在引用的链接中列为向 ExpressRoute 播发，这意味着它们将包含在文件的第二组条目中。

|**仅向 Internet 线路播发的通配符域**|**向 ExpressRoute 和 Internet 线路播发的子 FQDN**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> www.office.com  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |Outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover-\<tenant\>.outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>路由Office 365 Internet 和 ExpressRoute 的流量

若要路由到Office 365应用程序，你需要确定许多关键因素。
  
1. 应用程序将需要多少带宽。 对现有使用情况采样是确定组织中这一点的唯一可靠方法。

2. 您希望网络流量 () 的出口位置。 应计划最大程度地降低连接网络的网络延迟Office 365，因为这样做会影响性能。 由于Skype for Business使用实时语音和视频，因此它易受网络延迟不佳的影响。

3. 如果你希望所有或部分网络位置使用 ExpressRoute。

4. 所选网络提供商从什么位置提供 ExpressRoute。

确定这些问题的解答后，可以设置满足带宽和位置需求的 ExpressRoute 电路。 有关更多网络规划协助，[请参阅网络Office 365](./network-planning-and-performance.md)指南和 Microsoft 如何处理网络性能[规划的案例研究](https://aka.ms/tunemsit)。
  
### <a name="example-1-single-geographic-location"></a>示例 1：单个地理位置
  
此示例是名为 Trey Research 的虚构公司的方案，该公司具有一个地理位置。
  
Trey Research 的员工只能连接到安全部门明确允许的 Internet 上的服务和网站，这些代理对位于企业网络与 ISP 之间的出站代理对上。
  
Trey Research 计划将 Azure ExpressRoute 用于 Office 365 并意识到某些流量（如发往内容交付网络的流量）将无法通过 ExpressRoute 进行 Office 365 连接。 由于默认情况下，所有流量已路由到代理设备，因此这些请求将继续像以前一样工作。 Trey Research 确定他们可以满足 Azure ExpressRoute 路由要求后，他们继续创建电路、配置路由以及将新的 ExpressRoute 电路链接到虚拟网络。 基本 Azure ExpressRoute 配置就位后，Trey Research 将使用我们发布的 [#2 PAC](./managing-office-365-endpoints.md) 文件，通过直接 ExpressRoute 路由包含客户特定数据的流量，Office 365连接。
  
如下图所示，Trey Research 能够满足通过 Internet 路由 Office 365 流量和通过 ExpressRoute 的一部分流量（结合使用路由和出站代理配置更改）的要求。
  
1. 使用[我们发布的 #2 PAC](./managing-office-365-endpoints.md) 文件，通过 Azure ExpressRoute for Office 365 的单独 Internet 出口点路由Office 365。

2. 客户端配置了针对 Trey Research 代理的默认路由。

在此示例方案中，Trey Research 使用出站代理设备。 同样，不使用 Azure ExpressRoute for Office 365客户可能希望使用此技术根据检查发往已知高批量终结点的流量的成本来路由流量。
  
Exchange Online、SharePoint Online 和 Skype for Business Online 的 FQN 数量最高：
  
![ExpressRoute 客户边缘网络。](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com、outlook.office.com

- \<tenant-name\>.sharepoint.com、 \<tenant-name\>-my.sharepoint.com、 \<tenant-name\>-\<app\>.sharepoint.com

- \*.Lync.com 非 TCP 流量的 IP 范围

- \*broadcast.officeapps.live.com、 \*excel.officeapps.live.com、 \*onenote.officeapps.live.com \*、powerpoint.officeapps.live.com \*、view.officeapps.live.com \*、visio.officeapps.live.com \*、word-edit.officeapps.live.com \*、word-view.officeapps.live.com、office.live.com

了解有关在客户端[部署](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy)和管理代理设置Windows 8并确保Office 365代理不会限制[您的代理](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)。
  
对于单个 ExpressRoute 电路，Trey Research 没有高可用性。 如果 Trey 为 ExpressRoute 连接提供服务的边缘设备的冗余对出现故障，则没有额外的 ExpressRoute 电路可故障转移到。 这使得 Trey Research 在预先开发中无法通过 Internet 进行重新配置，在某些情况下需要新的 IP 地址。 如果 Trey 要添加高可用性，最简单的解决方案是为每个位置添加额外的 ExpressRoute 电路，并主动/主动地配置这些电路。
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>为多个位置Office 365 ExpressRoute

最后一种方案Office 365 ExpressRoute 路由流量是更复杂的路由体系结构的基础。 无论位置的数量、这些位置存在的洲数、ExpressRoute 电路的数量等，都需要能够将一些流量路由到 Internet，而需要通过 ExpressRoute 路由一些流量。
  
对于位于多个地理位置的客户，必须回答的额外问题包括：
  
1. 是否需要每个位置的 ExpressRoute 电路？ 如果你使用的是 Skype for Business Online 或关注 SharePoint Online 或 Exchange Online 的延迟敏感度，建议在每个位置使用主动/主动 ExpressRoute 电路的冗余对。 有关详细信息，Skype for Business媒体质量和网络连接指南。

2. 如果 ExpressRoute 电路不可用于特定区域，那么应该如何Office 365目标流量？

3. 在具有很多较小位置的网络的情况下，合并流量的首选方法是什么？

每一项都提出了一个独特挑战，需要你评估自己的网络和 Microsoft 提供的选项。

|**注意事项**|**要评估的网络组件**|
|:-----|:-----|
|位于多个位置的电路  <br/> |建议至少以主动/主动方式配置两条电路。  <br/> 必须比较成本、延迟和带宽需求。  <br/> 使用 BGP 路由开销、PAC 文件和 NAT 管理具有多个电路的路由。  <br/> |
|从没有 ExpressRoute 电路的位置路由  <br/> |我们建议出口和 DNS 解析与发起请求用户Office 365。  <br/> DNS 转发可用于允许远程办公室发现相应的终结点。  <br/> 远程办公室中的客户端必须具有提供对 ExpressRoute 电路的访问的路由。  <br/> |
|小型办公室合并  <br/> |应仔细比较可用带宽和数据使用情况。  <br/> |

> [!NOTE]
> 如果无论物理位置如何，路由都可用，Microsoft 将首选 ExpressRoute over the Internet。
  
每个唯一网络必须考虑上述每个注意事项。 下面是一个示例。
  
### <a name="example-2-multi-geographic-locations"></a>示例 2：多地理位置
  
此示例是一家名为"Humongous Insurance"的虚构公司，该公司具有多个地理位置。
  
Humongous Insurance 在地理位置上分散于世界各地办事处。 他们希望实现 Azure ExpressRoute for Office 365，以在直接网络连接Office 365大部分流量。 Humongous Insurance 还在另外两个洲设有办事处。 远程办公室（其中 ExpressRoute 不可行）的员工将需要路由回一个或两个主要设施，以使用 ExpressRoute 连接。
  
指导原则是尽快Office 365发往 Microsoft 数据中心的流量。 在此例中，Humongous Insurance 必须决定其远程办公室是应尽快通过 Internet 路由到 Microsoft 数据中心，还是其远程办公室应尽快通过内部网络路由，以通过 ExpressRoute 连接到达 Microsoft 数据中心。
  
Microsoft 的数据中心、网络和应用程序体系结构旨在采用全球不同的通信，并尽可能以最有效的方式提供服务。 这是世界上最大的网络之一。 针对客户网络Office 365时间超过所需时间的请求将无法利用此体系结构。
  
在 Humongous Insurance 的情况下，他们应按照打算通过 ExpressRoute 使用的应用程序继续操作。 例如，如果他们是 Skype for Business Online 客户，或者计划在连接到外部 Skype for Business Online 会议时使用 ExpressRoute 连接，建议在 Skype for Business 联机媒体质量和网络连接指南为第三个位置设置其他 ExpressRoute 电路。 从网络的角度来看，这可能更昂贵;但是，在传送至 Microsoft 数据中心之前，将请求从一个洲路由到另一个洲可能会导致在联机会议和通信Skype for Business体验不佳或不可用。
  
如果 Humongous Insurance 未使用或计划以任何方式使用 Skype for Business Online，则通过 ExpressRoute 连接将发往的 Office 365 网络流量路由回洲可能可行，但可能会导致不必要的延迟或 TCP 拥塞。 在这两种情况下，建议将 Internet 目标流量路由到本地站点的 Internet，以利用本地站点Office 365交付网络。
  
![ExpressRoute 多地理位置。](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
当 Humongous Insurance 规划其多地理位置策略时，需要考虑许多有关电路大小、电路数量、故障转移等的方面。
  
由于 ExpressRoute 位于一个位置，且多个区域试图使用该电路，Humongous Insurance 希望确保从远程办公室到 Office 365 的连接发送到最近的 Office 365 数据中心，并且由总部位置接收。 为此，Humongous Insurance 实施了 DNS 转发以减少与最接近总部 Internet 出口点的 Office 365 环境建立适当连接所需的往返次数和 DNS 查找次数。 这将阻止客户端解析本地前端服务器，并确保用户连接的 Front-End 服务器靠近 Humongous Insurance 与 Microsoft 对等的总部。 还可以了解为 [域名分配条件转发器](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10))。
  
在此方案中，来自远程办公室的流量将解析北美的 Office 365 前端基础结构，并使用 Office 365 根据 Office 365 应用程序的体系结构连接到后端服务器。 例如，Exchange Online将终止北美的连接，并且这些前端服务器将连接到租户驻留的后端邮箱服务器。 所有服务都有广泛分布的由单播和单播目标组成的前端服务。
  
如果 Humongous 在多个洲有主要办事处，建议每个区域至少存在两个活动/活动电路，以减少敏感应用程序（如 Skype for Business Online）的延迟。 如果所有办事处都位于单个洲，或者没有使用实时协作，则具有合并或分布式出口点是客户特定的决定。 当多个电路可用时，BGP 路由将确保在任何单个电路不可用时进行故障转移。
  
详细了解示例 [路由配置和](/azure/expressroute/expressroute-config-samples-routing) [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat)。
  
## <a name="selective-routing-with-expressroute"></a>使用 ExpressRoute 选择性路由

出于各种原因（如测试，向部分用户推出 ExpressRoute）可能需要使用 ExpressRoute 进行选择性路由。 客户可以使用多种工具通过 ExpressRoute 选择性地Office 365网络流量：
  
1. **路由筛选/分离** - 允许 BGP 路由Office 365 ExpressRoute 路由到子网或路由器的子集。 这将按客户网络段或物理办公地点选择性地路由。 这通常用于错开 ExpressRoute for Office 365，并配置在 BGP 设备上。

2. **PAC 文件/URL** - Office 365特定 FQN 的发往网络流量，以路由到特定路径。 这将按客户端计算机选择性地路由 PAC 文件部署 [标识的路由](./managing-office-365-endpoints.md)。

3. **路由筛选** - [路由](/azure/expressroute/how-to-routefilter-portal) 筛选器是一种通过 Microsoft 对等使用受支持服务的子集的方法。

4. **BGP 社区** - 基于 [BGP](./bgp-communities-in-expressroute.md) 社区标记的筛选允许客户确定哪些 Office 365应用程序将遍历 ExpressRoute，哪些应用程序将遍历 Internet。

以下是可以用于返回的简短链接：[https://aka.ms/erorouting]()
  
## <a name="related-topics"></a>相关主题

[评估 Office 365 网络连接](assessing-network-connectivity.md)
  
[适用于 Office 365 的 Azure ExpressRoute](azure-expressroute.md)
  
[管理 ExpressRoute for Office 365 连接](managing-expressroute-for-connectivity.md)
  
[ExpressRoute for Office 365 网络计划](network-planning-with-expressroute.md)
  
[实现 ExpressRoute for Office 365](implementing-expressroute.md)
  
[Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[优化 Skype for Business Online 网络](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[Skype for Business Online 中的 ExpressRoute 和 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[使用 ExpressRoute 的呼叫流](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[在 ExpressRoute 中将 BGP 社区用于Office 365方案](bgp-communities-in-expressroute.md)
  
[使用基线和性能历史记录优化 Office 365 性能](performance-tuning-using-baselines-and-history.md)
  
[Office 365 性能疑难解答计划](performance-troubleshooting-plan.md)
  
[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 网络和性能优化](network-planning-and-performance.md)
