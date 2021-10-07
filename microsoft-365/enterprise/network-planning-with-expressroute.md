---
title: 使用适用于 Office 365 的 ExpressRoute 进行网络规划
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
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
- MOE150
- BCS160
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: 本文将介绍 Azure ExpressRoute for Office 365以及如何利用它进行网络规划。
ms.openlocfilehash: e087afee52893b0be48e4024c619e3599f54338d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177059"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>使用适用于 Office 365 的 ExpressRoute 进行网络规划

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

ExpressRoute for Office 365 在网络和 Microsoft 数据中心之间提供第 3 层连接。 这些电路使用边界网关协议 (BGP) 前端Office 365服务器的路由广告。 从本地设备的角度来看，当需要选择正确的 TCP/IP Office 365 时，Azure ExpressRoute 被视为 Internet 的替代项。
  
Azure ExpressRoute 将直接路径添加到 Microsoft 数据中心内由 Office 365 服务器提供的一组特定支持的功能和服务。 Azure ExpressRoute 不会替换到 Microsoft 数据中心或基本 Internet 服务（如域名解析）的 Internet 连接。 Azure ExpressRoute 和 Internet 线路应安全且冗余。
  
下表重点介绍了 Internet 和 Azure ExpressRoute 连接在 Office 365 上下文中的一些Office 365。

|**网络规划的差异**|**Internet 网络连接**|**ExpressRoute 网络连接**|
|:-----|:-----|:-----|
| 访问所需的 Internet 服务，包括;  <br/>  DNS 名称解析  <br/>  证书吊销验证  <br/>  内容分发网络 (CDN)  <br/> |是  <br/> |对 Microsoft 拥有的 DNS 和/或CDN的请求可能会使用 ExpressRoute 网络。  <br/> |
| 访问 Office 365 服务，包括：  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  Office浏览器中显示  <br/>  Office 365门户和身份验证  <br/> |是，所有应用程序和功能  <br/> |是， [特定的应用程序和功能](./urls-and-ip-address-ranges.md) <br/> |
|外围本地安全。  <br/> |是  <br/> |是  <br/> |
|高可用性规划。  <br/> |故障转移到备用 Internet 网络连接  <br/> |故障转移到备用 ExpressRoute 连接  <br/> |
|与可预测的网络配置文件的直接连接。  <br/> |否  <br/> |是  <br/> |
|IPv6 连接。  <br/> |是  <br/> |是  <br/> |

展开以下标题，了解更多网络规划指南。 我们还记录了一个 10 部分的[Azure ExpressRoute for Office 365培训](https://channel9.msdn.com/series/aer)系列，深入探究。

## <a name="existing-azure-expressroute-customers"></a>现有 Azure ExpressRoute 客户

如果你正在使用现有的 Azure ExpressRoute 电路，并且希望通过此电路添加 Office 365 连接，则应该查看电路的数量、出口位置和电路大小，以确保它们能够满足 Office 365 使用的需求。 大多数客户需要额外的带宽，而许多客户还需要额外的电路。
  
若要允许通过Office 365 Azure ExpressRoute 线路访问服务，请配置路由[](/azure/expressroute/how-to-routefilter-portal)筛选器以确保可以访问Office 365服务。
  
Azure ExpressRoute 订阅以客户为中心，这意味着订阅绑定到客户。 作为客户，你可以拥有多个 Azure ExpressRoute 电路，并且可以通过这些电路访问许多 Microsoft 云资源。 例如，你可以选择通过一对冗余 Azure ExpressRoute 电路访问 Azure 托管的虚拟机、Office 365 测试租户和 Office 365 生产租户。
  
此表概述了你可以选择通过电路实现的两种类型的对等关系。

|**对等关系**|**Azure 专用**|**Microsoft**|
|:-----|:-----|:-----|
|**服务** <br/> |IaaS：Azure 虚拟机  <br/> |PaaS：Azure 公共服务  <br/> SaaS：Office 365  <br/> SaaS：Dynamics 365  <br/> |
|连接启动**** <br/> |客户到 Microsoft  <br/> Microsoft 到客户  <br/> |客户到 Microsoft  <br/> Microsoft 到客户  <br/> |
|**QoS 支持** <br/> |无 QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1</sup>QoS Skype for Business目前才支持。
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Azure ExpressRoute 的带宽规划

每个Office 365客户都有独特的带宽需求，具体取决于每个位置的人数、他们在每个 Office 365 应用程序中的活跃状态，以及其他因素（如使用内部部署或混合设备和网络安全配置）。
  
带宽过少会导致拥塞、重新传输数据和不可预知的延迟。 带宽过多将导致不必要的成本。 在现有的网络上，带宽通常以百分比表示为电路上的可用空间量。 拥有 10% 的会议室可能会导致拥塞，而拥有 80% 的会议室通常意味着不必要的成本。 典型的空间目标分配为 20% 到 50%。
  
若要查找正确的带宽级别，最佳机制是测试现有网络消耗。 这是真正衡量使用情况和需求的唯一方法，因为每个网络配置和应用程序在某些方面都是唯一的。 在衡量时，你需要密切注意总带宽消耗、延迟和 TCP 拥塞，以了解网络需求。
  
一旦具有包括所有网络应用程序的估计基线，请对包含组织中不同人员配置文件的小组进行试点 Office 365 以确定实际使用情况，然后使用两种度量标准估计每个办公地点所需的带宽量。 如果在测试中发现任何延迟或 TCP 拥塞问题，您可能需要使用 Office 365 将出口移到距离用户更近位置，或者删除密集型网络扫描（如 SSL 解密/检查）。
  
我们有关推荐的网络处理类型的所有建议都适用于 ExpressRoute 和 Internet 电路。 对于性能调整网站 中的其余指南， [也是如此](./network-planning-and-performance.md)。
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>将安全控件应用于 Azure ExpressRoute Office 365方案

保护 Azure ExpressRoute 连接从保护 Internet 连接的原则开始。 许多客户选择沿 ExpressRoute 路径部署网络和外围控件，以将其本地网络连接到 Office 365 云和其他 Microsoft 云。 这些控件可能包括防火墙、应用程序代理、数据泄露防护、入侵检测、入侵防护系统等。 在许多情况下，客户对从本地发到 Microsoft 的流量应用不同级别的控制，与从 Microsoft 启动的流量到客户本地网络的流量，以及从本地启动到常规 Internet 目标的流量。
  
下面是一些将安全性与选择部署的 [ExpressRoute](/azure/expressroute/expressroute-connectivity-models) 连接模型集成的示例。

|**ExpressRoute 集成选项**|**网络安全外围模型**|
|:-----|:-----|
|在云交换中归置  <br/> |在建立 ExpressRoute 连接的同一位置设施中安装新的或利用现有的安全/外围基础结构。  <br/> 利用共同位置设施完全用于路由/互连目的，以及从共同位置设施到本地安全/外围基础结构的回程连接。  <br/> |
|点到点以太网  <br/> |终止现有本地安全/外围基础结构位置中的点到点 ExpressRoute 连接。  <br/> 安装特定于 ExpressRoute 路径的新安全/外围基础结构，并终止该位置的点到点连接。  <br/> |
|任意对任意 IPVPN  <br/> |利用所有位置的现有本地安全/外围基础结构，这些基础结构会进入用于 ExpressRoute 的 IPVPN，Office 365连接。  <br/> 将用于 ExpressRoute for Office 365的 IPVPN 发夹到指定为安全/外围的特定本地位置。  <br/> |

某些服务提供商还提供托管安全/外围功能，作为其与 Azure ExpressRoute 集成解决方案的一部分。
  
在考虑用于 ExpressRoute 进行连接的网络/安全外围选项的拓扑Office 365时，下面是其他注意事项
  
- 深度和网络/安全控件的类型可能会影响用户体验的性能Office 365可伸缩性。

- 本地 (出站邮件 - Microsoft) 和 (Microsoft 内部部署 \> \>) [如果已启用]流可能具有不同的要求。 这些可能不同于常规 Internet 目的地的出站。

- Office 365/协议和必要的 IP 子网的要求相同，无论通信是通过 ExpressRoute 进行路由Office 365还是通过 Internet 路由。

- 客户网络/安全控件的按拓扑放置确定用户和 Office 365 服务之间的最终端到端网络，并且会对网络延迟和拥塞产生显著影响。

- 我们鼓励客户根据冗余、高可用性和灾难恢复最佳做法设计其安全/外围拓扑，以用于 Office 365 ExpressRoute for Office 365。

下面是 Woodgrove Bank 的示例，它将不同的 Azure ExpressRoute 连接选项与上述外围安全模型进行比较。
  
### <a name="example-1-securing-azure-expressroute"></a>示例 1：保护 Azure ExpressRoute
  
Woodgrove Bank 正在考虑实施 Azure ExpressRoute，在规划适用于[Office 365 的 ExpressRoute](routing-with-expressroute.md)路由的最佳体系结构后，在使用上述指南了解带宽要求后，他们正在确定保护外围安全的最佳方法。
  
对于位于多个洲的多方组织 Woodgrove，安全性必须跨越所有外围。 Woodgrove 的最佳连接选项是在全球多个对等位置进行多点连接，以满足每个洲的员工需求。 每个洲都包括该洲内的冗余 Azure ExpressRoute 线路，并且安全必须跨越所有这些区域。
  
Woodgrove 的现有基础结构很可靠，可以处理额外的工作，因此，Woodgrove Bank 能够使用基础结构实现 Azure ExpressRoute 和 Internet 外围安全。 如果不是这种情况，Woodgrove 可以选择购买其他设备以补充其现有设备或处理不同类型的连接。
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Azure ExpressRoute 的高可用性和故障转移
<a name="BKMK_high-availability"> </a>

我们建议使用 ExpressRoute 将每个出口中的至少两个活动电路预配到 ExpressRoute 提供商。 这是我们发现客户失败的最常见位置，您可以通过设置一对主动/主动 ExpressRoute 电路轻松避免失败。 我们还建议至少使用两个主动/主动 Internet 电路，因为Office 365许多服务仅通过 Internet 提供。
  
在网络出口点内，还有许多其他设备和电路，它们对人们感知可用性的方式起重要作用。 ExpressRoute 或 Office 365 SLA 未涵盖连接方案的这些部分，但它们在端到端服务可用性方面起到重要作用，正如组织成员所感知的。
  
重点关注使用和操作Office 365，如果任何一个组件出现故障会影响人们使用该服务的体验，请寻找方法来限制受影响人员的总百分比。 如果故障转移模式在操作上比较复杂，请考虑用户长时间恢复的体验，并查找操作简单且自动化的故障转移模式。
  
在网络外部，Office 365、ExpressRoute 和 ExpressRoute 提供商都具有不同的可用性级别。
  
### <a name="service-availability"></a>服务可用性
  
- Office 365服务由明确定义的服务级别协议涵盖，其中包括单个[](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)服务的运行时间和可用性指标。 之所以Office 365服务可用性级别，一个原因是各个组件能够使用全局 Microsoft 网络在许多 Microsoft 数据中心之间无缝故障转移。 此故障转移从数据中心和网络扩展到多个 Internet 出口点，从使用该服务的人的角度无缝启用故障转移。

- ExpressRoute 在 Microsoft 网络边缘与 ExpressRoute 提供商或合作伙伴基础结构之间的各个专用线路上提供 [99.9%](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) 的可用性 SLA。 这些服务级别在 ExpressRoute 电路级别应用，该电路级别由[](/azure/expressroute/expressroute-introduction)冗余 Microsoft 设备和每个对等位置的网络提供商设备之间的两个独立的互连组成。

### <a name="provider-availability"></a>提供程序可用性
  
- Microsoft 的服务级别安排停止在 ExpressRoute 提供商或合作伙伴处。 这也是你可以做出将影响可用性级别的选择的第一位置。 应仔细评估 ExpressRoute 提供程序在每个 Microsoft 对等位置的网络外围和提供商连接之间提供的体系结构、可用性和恢复能力特征。 请密切注意冗余的逻辑和物理方面、对等设备、运营商提供的 WAN 电路以及任何附加值服务（如 NAT 服务或托管防火墙）。

### <a name="designing-your-availability-plan"></a>设计可用性计划
  
我们强烈建议你针对远程部署在端到端连接方案中计划和设计高可用性Office 365。 设计应包括;
  
- 无单点故障，包括 Internet 和 ExpressRoute 电路。

- 最大程度地减少受影响的人数以及影响大多数预期失败模式的持续时间。

- 针对大多数预期失败模式的简单、可重复和自动恢复过程进行优化。

- 通过冗余路径支持网络流量和功能的全部需求，而不会显著下降。

连接方案应包括针对多个独立的活动网络路径进行优化的网络拓扑，以Office 365。 与仅针对单个设备或设备级别的冗余而优化的拓扑结构不同，这将产生更好的端到端可用性。
  
> [!TIP]
> 如果您的用户分布在多个洲或地理区域，并且其中每个位置都通过冗余 WAN 线路连接到单个 ExpressRoute 电路所在的单个本地位置，则与包括独立的 ExpressRoute 电路（将不同区域连接到最近的对等位置）的网络拓扑设计相比，您的用户体验的端到端服务可用性要低。
  
我们建议设置至少两个 ExpressRoute 电路，每个电路连接到不同的地理对等位置。 你应该为人们将使用 ExpressRoute 连接的每个区域设置此主动Office 365对。 这允许每个区域在影响主要位置（如数据中心或对等位置）的灾难期间保持连接。 在 中将其配置为活动/活动允许最终用户流量分布在多个网络路径中。 这可以减少设备或网络设备中断期间受影响的人员范围。
  
我们不建议将单个 ExpressRoute 电路与 Internet 一起用作备份。
  
### <a name="example-2-failover-and-high-availability"></a>示例 2：故障转移和高可用性
  
Woodgrove Bank 的多地理设计已审查路由、带宽、安全性，现在必须经过高可用性审查。 Woodgrove 认为高可用性涉及三个类别;复原、可靠性和冗余。
  
复原使 Woodgrove 能够快速从故障中恢复。 可靠性使 Woodgrove 可以在系统内提供一致的结果。 冗余允许 Woodgrove 在基础结构的一个或多个镜像实例之间移动。
  
在每个边缘配置中，Woodgrove 具有冗余防火墙、代理和 IDS。 对于北美，Woodgrove 在 Dallas 数据中心有一个边缘配置，在 Datacenter 数据中心有另一个边缘配置。 每个位置的冗余设备都提供该位置的复原能力。
  
Woodgrove Bank 的网络配置基于一些关键原则构建：
  
- 在每个地理区域中，有多个 Azure ExpressRoute 电路。

- 一个地区的每个电路可以支持该区域内的所有网络流量。

- 根据可用性、位置等，路由将明显首选其中一种路径。

- Azure ExpressRoute 电路之间的故障转移会自动发生，无需 Woodgrove 进行其他配置或操作。

- Internet 电路之间的故障转移会自动发生，无需 Woodgrove 进行其他配置或操作。

在此配置中，通过物理和虚拟级别的冗余，Woodgrove Bank 能够可靠地提供本地复原、区域复原和全局复原。 Woodgrove 在评估每个地区的单个 Azure ExpressRoute 电路以及可能故障到 Internet 后选择此配置。
  
如果 Woodgrove 无法使每个区域具有多个 Azure ExpressRoute 电路，则从北美洲到亚太地区的 Azure ExpressRoute 线路的路由流量将增加不可接受的延迟级别，并且所需的 DNS 转发器配置会增加复杂性。
  
不建议将 Internet 用作备份配置。 这将破坏 Woodgrove 的可靠性原则，从而导致使用连接时出现不一致的体验。 此外，考虑到已配置的 BGP 播发、NAT 配置、DNS 配置和代理配置，需要手动配置才能进行故障转移。 这增加了故障转移复杂性，增加了恢复时间，并降低了他们诊断和排查所涉及的步骤的能力。
  
仍对如何计划和实现流量管理或 Azure ExpressRoute 有疑问？ 请阅读我们的网络和性能指南 [或](./network-planning-and-performance.md) [Azure ExpressRoute 常见问题解答](/azure/expressroute/expressroute-faqs)。
  
## <a name="working-with-azure-expressroute-providers"></a>使用 Azure ExpressRoute 提供程序
<a name="BKMK_high-availability"> </a>

根据您的带宽、延迟、安全性和高可用性规划选择电路的位置。 在知道要放置电路的最佳位置后，按区域查看 [提供商的当前列表](/azure/expressroute/expressroute-locations)。
  
与提供程序合作以选择最佳连接选项、点到点、多点或托管。 请记住，只要带宽和其他冗余组件支持路由和高可用性设计，就可以混合和匹配连接选项。
  
以下是可以用于返回的简短链接：[https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>相关主题
<a name="BKMK_high-availability"> </a>

[评估 Office 365 网络连接](assessing-network-connectivity.md)
  
[适用于 Office 365 的 Azure ExpressRoute](azure-expressroute.md)
  
[管理 ExpressRoute for Office 365 连接](managing-expressroute-for-connectivity.md)
  
[使用 ExpressRoute for Office 365 路由](routing-with-expressroute.md)
  
[实现 ExpressRoute for Office 365](implementing-expressroute.md)
  
[在 ExpressRoute 中将 BGP 社区用于Office 365方案](bgp-communities-in-expressroute.md)
  
[Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[优化 Skype for Business Online 网络](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[Skype for Business Online 中的 ExpressRoute 和 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[使用 ExpressRoute 的呼叫流](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[使用基线和性能历史记录优化 Office 365 性能](performance-tuning-using-baselines-and-history.md)
  
[Office 365 性能疑难解答计划](performance-troubleshooting-plan.md)
  
[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 网络和性能优化](network-planning-and-performance.md)
  
[Office 365 终结点 FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)