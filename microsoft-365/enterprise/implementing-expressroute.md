---
title: 实现适用于 Office 365 的 ExpressRoute
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
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
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: 了解如何实现 ExpressRoute for Office 365，从而提供许多面向 Internet 的 Office 365 服务的备用路由路径。
ms.openlocfilehash: 9fbfaec8304c0ad5273aed3f07cb3d32c590c638
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807256"
---
# <a name="implementing-expressroute-for-office-365"></a>实现适用于 Office 365 的 ExpressRoute

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

ExpressRoute for Office 365提供了许多面向 Internet 的 Office 365 路由路径。 适用于 Office 365 的 ExpressRoute 的体系结构基于将已可通过 Internet 访问的 Office 365 服务的公共 IP 前缀公布到已预配的 ExpressRoute 电路中，以后续重新分发到网络中。 使用 ExpressRoute，您可以有效地启用多个不同的路由路径，通过 Internet 和 ExpressRoute 为许多 Office 365服务。 网络上路由的这种状态可能会显著改变内部网络拓扑的设计方法。
  
 **状态：** 完整指南 v2
  
必须仔细规划 ExpressRoute Office 365实现，以适应网络复杂性，因为通过专用电路（路由注入核心网络和 Internet）提供路由。 如果你和团队不执行本指南中的详细规划和测试，则当启用 ExpressRoute 电路时，你可能会遇到间歇性故障或与 Office 365 服务完全失去连接的风险。
  
若要成功实施，你需要分析基础结构要求，完成详细的网络评估和设计，以分步和受控的方式仔细规划部署，并构建详细的验证和测试计划。 对于大型的分布式环境，实现跨越几个月的情况很常见。 本指南旨在帮助你提前规划。
  
大型成功部署可能需要六个月的规划时间，并且通常包括组织中多个领域的团队成员，包括网络、防火墙和代理服务器管理员、Office 365 管理员、安全、最终用户支持、项目管理和管理层支持。 对规划过程的投资将降低您遇到部署失败导致停机或复杂且成本高昂的故障排除的可能性。
  
我们希望在本指南启动之前完成以下先决条件。
  
1. 你已完成网络评估，以确定是否推荐并批准 ExpressRoute。

2. 你已选择 ExpressRoute 网络服务提供商。 查找有关 [ExpressRoute 合作伙伴和对等位置的详细信息](/azure/expressroute/expressroute-locations)。

3. 你已阅读并了解 [ExpressRoute](https://azure.microsoft.com/documentation/services/expressroute/) 文档，并且你的内部网络能够端到端满足 ExpressRoute 先决条件。

4. 团队已阅读 [https://aka.ms/expressrouteoffice365](./azure-expressroute.md)、 [https://aka.ms/ert](https://aka.ms/ert)的所有公共指南和文档，并观看第 9 频道上的 [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) 系列，了解关键技术详细信息，包括：

      - SaaS 服务的 Internet 依赖项。

      - 如何避免非对称路由和处理复杂的路由。

      - 如何合并外围安全、可用性和应用程序级别控件。

## <a name="begin-by-gathering-requirements"></a>首先收集要求
<a name="requirements"> </a>

首先确定计划在你的组织中采用哪些功能和服务。 您需要确定将使用不同的 Office 365 服务的功能，以及网络上哪些位置将承载使用这些功能的人。 使用方案目录，需要添加其中每个方案所需的网络属性;例如入站和出站网络流量，Office 365终结点是否通过 ExpressRoute 可用。
  
收集组织的要求：
  
- 为组织使用的服务目录入站Office 365出站网络流量。 请参阅Office 365 URL 和 IP 地址范围页面，查看不同方案需要Office 365流的说明。

- 收集现有网络拓扑的文档，其中显示内部 WAN 主干和拓扑、附属站点连接、最后一英里用户连接、网络外围出口点路由和代理服务的详细信息。

  - 标识要连接到的网络图上的入站Office 365和其他Microsoft 服务，同时显示 Internet 和建议的 ExpressRoute 连接路径。

  - 确定位置之间的所有地理用户位置和 WAN 连接，以及当前具有 Internet 出口的位置以及建议哪些位置具有 ExpressRoute 对等位置的出口。

  - 标识所有边缘设备（如代理、防火墙等）并编录它们与通过 Internet 和 ExpressRoute 流动的关系。

  - 记录最终用户是通过直接路由Office 365 Internet 和 ExpressRoute 流的间接应用程序代理访问服务。

- 将租户的位置和"会面我"位置添加到网络图。

- 估计从主要用户位置到其他用户位置的预期和观察到的网络Office 365。 请记住，Office 365是一组全局和分布式服务，用户将连接到可能不同于其租户位置的位置。 因此，建议通过 ExpressRoute 和 Internet 连接测量和优化用户与 Microsoft 全球网络的最近边缘之间的延迟。 可以使用网络评估中的结果帮助完成此任务。

- 列出新 ExpressRoute 连接需要满足的公司网络安全和高可用性要求。 例如，在 Internet 出口或 ExpressRoute 电路故障Office 365，用户如何继续获得对连接的访问权限。

- 记录哪些入站和出Office 365网络流将使用 Internet 路径以及将使用 ExpressRoute。 用户地理位置的具体信息以及本地网络拓扑的详细信息可能要求计划不同于不同用户位置。

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>编录出站和入站网络流量
<a name="trafficCatalog"> </a>

为了最大程度地降低路由和其他网络复杂性，我们建议你仅对因法规要求或由于网络评估结果而需要通过专用连接的网络通信流使用适用于 Office 365 的 ExpressRoute。 此外，建议将 ExpressRoute 路由的范围进行阶段化，将出站和入站网络流量作为实施项目的不同且不同的阶段流动。 部署 ExpressRoute for Office 365 仅针对用户启动的出站网络流量，并保留入站网络流量通过 Internet，有助于控制引入其他非对称路由可能性的拓扑复杂性和风险增加。
  
网络流量目录应包含本地网络和 Microsoft 之间所有入站和出站网络连接列表。
  
- 出站网络流量是任何从本地环境启动连接（例如从内部客户端或服务器启动连接，目标为 Microsoft 服务）。 这些连接可能直接Office 365间接连接，例如当连接通过代理服务器、防火墙或其他网络设备连接到 Office 365。

- 入站网络流量是任何从 Microsoft 云启动到本地主机的连接的方案。 这些连接通常需要通过防火墙和客户安全策略为外部来源的流所需的其他安全基础结构。

阅读文章  Routing [with ExpressRoute for Office 365](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408)中的确保路由对称部分，以确定哪些服务将发送入站通信，并查找 Office 365 终结点参考文章中标记为 **ExpressRoute for Office 365** 的列，以确定连接信息的其余部分。[](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
对于需要出站连接的每个服务，您需要描述服务的计划连接，包括网络路由、代理配置、数据包检查和带宽需求。
  
对于需要入站连接的每项服务，你将需要一些其他信息。 Microsoft 云中的服务器将建立与本地网络的连接。 为了确保正确建立连接，您需要描述此连接的各个方面，包括;接受这些入站连接的服务的公用 DNS 条目、CIDR 格式的 IPv4 IP 地址、涉及的 ISP 设备，以及如何处理这些连接的入站 NAT 或源 NAT。
  
应检查入站连接，而不管它们是否通过 Internet 或 ExpressRoute 进行连接，以确保尚未引入非对称路由。 在某些情况下，服务启动入站Office 365本地终结点可能还需要由其他 Microsoft 和非 Microsoft 服务。 最重要的是，启用 ExpressRoute 路由到这些服务Office 365目的不会中断其他方案。 在许多情况下，客户可能需要对内部网络（如基于源的 NAT）进行特定更改，以确保来自 Microsoft 的入站流在启用 ExpressRoute 后保持对称。
  
下面是所需详细级别的示例。 在这种情况下，Exchange混合会通过 ExpressRoute 路由到本地系统。 

|Connection 属性   |值  |
|----------|-----------|
|**网络流量方向** <br/> |入站  <br/> |
|**服务** <br/> |Exchange 混合  <br/> |
|**公用Office 365终结点 (源)** <br/> |Exchange Online (IP 地址)   <br/> |
|**公共本地终结点 (目标)** <br/> |5.5.5.5  <br/> |
|**公用 (Internet) DNS 条目** <br/> |Autodiscover.contoso.com  <br/> |
|**此本地终结点将供其他非 (使用Office 365) Microsoft 服务** <br/> |否  <br/> |
|**Internet 上的用户/系统会使用此本地终结点吗** <br/> |是  <br/> |
|**通过公共终结点发布的内部系统** <br/> |Exchange Server客户端访问角色 (本地) 192.168.101、192.168.102、192.168.103  <br/> |
|**公共终结点的 IP 播发** <br/> |**到 Internet**：5.5.0.0/16 **到 ExpressRoute**：5.5.5.0/24  <br/> |
|**安全/外围控件** <br/> |**Internet 路径**：DeviceID_002  **ExpressRoute 路径**：DeviceID_003  <br/> |
|**高可用性** <br/> |跨 2 个地理位置冗余/ExpressRoute 电路的活动/活动 - 芝加哥和 Dallas  <br/> |
|**路径对称控制** <br/> |方法 **：源** NAT **Internet 路径**：到 192.168.5.5 **ExpressRoute** 的源 NAT 入站连接：到芝加哥) 和 192.168.2.0 (和 192.168.2.0 (Dallas) 的源 NAT 连接  <br/> |

下面是仅出站服务的示例：

|**Connection 属性**|**值**|
|----------|-----------|
|**网络流量方向** <br/> |出站  <br/> |
|**服务** <br/> |SharePoint Online  <br/> |
|**本地终结点 (源)** <br/> |用户工作站  <br/> |
|**公用Office 365终结点 (目标)** <br/> |SharePoint Online (IP 地址)   <br/> |
|**公用 (Internet) DNS 条目** <br/> |\*.sharepoint.com (和更多 FQDN)   <br/> |
|**CDN引荐** <br/> |cdn.sharepointonline.com (更多 FQDN) - 由 CDN 提供程序维护的 IP)   <br/> |
|**使用的 IP 播发和 NAT** <br/> |**Internet 路径/源 NAT**：1.1.1.0/24  <br/> **ExpressRoute 路径/源 NAT**：1.1.2.0/24 (芝加哥) 和 1.1.3.0/24 (Dallas)   <br/> |
|**Connectivity 方法** <br/> |**Internet**：通过第 7 层代理 (.pac)   <br/> **ExpressRoute**：无代理 (直接路由)   <br/> |
|**安全/外围控件** <br/> |**Internet 路径**：DeviceID_002  <br/> **ExpressRoute 路径**：DeviceID_003  <br/> |
|**高可用性** <br/> |**Internet 路径**：冗余 Internet 出口  <br/> **ExpressRoute 路径**：跨 2 个地理位置冗余 ExpressRoute 电路的主动/主动"热当"路由 - 芝加哥和 Dallas  <br/> |
|**路径对称控制** <br/> |**方法**：所有连接的源 NAT  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>具有区域连接的网络拓扑设计
<a name="topology"> </a>

了解服务及其关联的网络流量流后，您可以创建一个网络图，该图表包含这些新的连接要求，并说明了使用 ExpressRoute for Office 365。 您的图表应包括：
  
1. 将访问Office 365服务的所有用户位置。

2. 所有 Internet 和 ExpressRoute 出口点。

3. 管理网络内连接的所有出站和入站设备，包括路由器、防火墙、应用程序代理服务器和入侵检测/防护。

4. 所有入站流量的内部目标，例如接受来自 ADFS Web 应用程序代理服务器的连接的内部 ADFS 服务器。

5. 将公布的所有 IP 子网的目录

6. 确定用户从每个Office 365访问的位置，并列出将用于 ExpressRoute 的"会面我"位置。

7. 内部网络拓扑的位置和部分，其中将接受、筛选和传播从 ExpressRoute 中学习的 Microsoft IP 前缀。

8. 网络拓扑应说明每个网段的地理位置，以及它如何通过 ExpressRoute 和/或 Internet 连接到 Microsoft 网络。

下图显示了用户将在其中使用 Office 365 以及入站和出站路由广告以Office 365。
  
![ExpressRoute regional geographic meet-me。](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
对于出站流量，人们Office 365以下三种方式之一：
  
1. 通过北美为加利福尼亚人的会面位置。

2. 通过香港与香港居民的会面地点。

3. 通过孟加拉国的 Internet，用户较少且未设置 ExpressRoute 电路。

![区域图表的出站连接。](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
同样，来自 Office 365的入站网络流量以以下三种方式之一返回：
  
1. 通过北美为加利福尼亚人的会面位置。

2. 通过香港与香港居民的会面地点。

3. 通过孟加拉国的 Internet，用户较少且未设置 ExpressRoute 电路。

![区域图的入站连接。](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>确定适当的会面位置

选择"联系我"位置（即 ExpressRoute 电路将网络连接到 Microsoft 网络的物理位置）受用户访问位置Office 365影响。 作为 SaaS 产品，Office 365在 IaaS 或 PaaS 区域模型中的运行方式与 Azure 不同。 相反，Office 365是一组分布式协作服务，其中用户可能需要连接到多个数据中心和区域的终结点，这些终结点不一定位于托管用户租户的同一位置或区域。
  
这意味着在选择 ExpressRoute for Office 365 的"联系我"位置时需要考虑的最重要的注意事项是组织中人员将进行连接的位置。 最佳 Office 365 连接的一般建议是实施路由，以便用户对 Office 365 服务的请求通过最短网络路径提交到 Microsoft 网络中，这通常也称为"热路由"路由。 例如，如果大多数 Office 365用户位于一个或两个位置，则选择与这些用户的位置最接近的"会面我"位置将创建最佳设计。 如果您的公司在许多不同区域具有大量用户，您可能需要考虑拥有多个 ExpressRoute 电路和"会面我"位置。 对于一些用户位置，进入 Microsoft 网络和 Office 365 的最短/最佳路径可能不是通过内部 WAN 和 ExpressRoute 会议点，而是通过 Internet。
  
通常，可以在与用户相对接近的一个区域内选择多个"会面我"位置。 填写下表以指导您的决策。

**在加利福尼亚和纽约计划的 ExpressRoute 会面位置**

|位置  <br/> |人员数  <br/> |Microsoft 网络通过 Internet 出口的预期延迟  <br/> |通过 ExpressRoute 对 Microsoft 网络的预期延迟  <br/> |
|----------|-----------|----------|-----------|
|Los Angeles  <br/> |10,000  <br/> |~15ms  <br/> |大约 10 毫秒 (通过位于)   <br/> |
|华盛顿州  <br/> |15,000  <br/> |~20 毫秒  <br/> |通过纽约 (大约 10 毫秒)   <br/> |
|Dallas  <br/> |5,000  <br/> |~15ms  <br/> |通过纽约 (大约 40 毫秒)   <br/> |

在显示 Office 365 区域、ExpressRoute 网络服务提供商"联系我"位置和按位置显示人员数量的全局网络体系结构之后，它可用于标识能否进行任何优化。 它也可能显示全局发夹网络连接，其中流量将路由到较远的位置，以便获取"我开会"位置。 如果发现全局网络上有一个发夹，则应该先修正该发夹，然后再继续。 查找另一个会议位置，或使用选择性 Internet 出口点来避免发夹。
  
第一个图表显示了一个北美具有两个物理位置的客户示例。 你可以查看有关 Office 位置、Office 365位置以及 ExpressRoute 会议-我位置的几个选择的信息。 在此例中，客户已基于两个原则选择了会议地点，顺序为：
  
1. 最接近其组织中人员的位置。

2. 最接近托管主机的 Microsoft 数据中心Office 365位置。

![ExpressRoute 美国地理-我开会。](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
第二个图稍微进一步扩展了此概念，显示了一个使用类似信息和决策制定的国家/客户面临的示例。 此客户在孟加拉国有一家小型办公室，只有一个十人的小组，专注于扩大他们在地区的业务。 在金纳尼有一个"会面"位置和一个 Microsoft 数据中心，其中 Office 365 托管在金纳尼，因此"会面我"位置很有意义;但是，对于十个人而言，额外线路的费用是一项负担。 在查看网络时，需要确定跨网络发送网络流量所涉及的延迟是否比花费资金获取另一个 ExpressRoute 电路更有效。
  
此外，在孟加拉国的十个人，其网络流量通过 Internet 发送到 Microsoft 网络的性能可能会比他们在内部网络上路由的性能更好，如我们在介绍性图表中介绍并在下面复制所示。
  
![区域图表的出站连接。](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>创建 ExpressRoute for Office 365实施计划
<a name="implementation"> </a>

实现计划应包含配置 ExpressRoute 的技术详细信息以及网络上配置所有其他基础结构的详细信息，如下所示。
  
- 规划在 ExpressRoute 和 Internet 之间拆分哪些服务。

- 规划带宽、安全性、高可用性和故障转移。

- 设计入站和出站路由，包括针对不同位置的正确路由路径优化

- 确定 ExpressRoute 路由将在你的网络中播发多远，以及客户端选择 Internet 或 ExpressRoute 路径的机制是什么;例如，直接路由或应用程序代理。

- 规划 DNS 记录更改，包括 [发件人策略框架](../security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md) 条目。

- 规划 NAT 策略，包括出站和入站源 NAT。

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>使用 Internet 和 ExpressRoute 网络路径规划路由
<a name="paths"> </a>

- 对于初始部署，建议使用 Internet 使用所有入站服务，如入站电子邮件或混合连接。

- 规划最终用户客户端 LAN 路由，例如配置 [PAC/WPAD](./managing-office-365-endpoints.md) 文件、默认路由、代理服务器和 BGP 路由广告。

- 规划外围路由，包括代理服务器、防火墙和云代理。

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>规划带宽、安全性、高可用性和故障转移
<a name="availability"> </a>

创建每个主要工作负荷所需的带宽Office 365计划。 单独估计Exchange Online、SharePoint Online 和 Skype for Business Online 带宽要求。 您可以使用我们为 Exchange Online 和 Skype for Business 提供的估计计算器作为起点;但是，需要具有用户配置文件和位置代表性示例的试点测试才能充分了解组织的带宽需求。
  
向计划添加在每个 Internet 和 ExpressRoute 出口位置处理安全性的方式，记住与 Office 365 的所有 ExpressRoute 连接都使用公共对等，并且仍必须按照连接到外部网络的公司的安全策略进行保护。
  
将有关哪些人员受哪种类型的中断的影响以及这些人员如何以最简单的方式以最大能力执行他们的工作的详细信息添加到您的计划中。
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>规划带宽要求，Skype for Business抖动、延迟、拥塞和空位的带宽要求
  
Skype for Business Online 还具有特定的额外网络要求，如 Skype for Business Online 中的媒体质量和网络连接性能[一文详细介绍](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)。
  
阅读 Network [planning with ExpressRoute for Office 365中的 Azure ExpressRoute 带宽Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)。
  
与试点用户执行带宽评估时，可以使用我们的指南;[Office 365基线和性能历史记录优化性能](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)。
  
#### <a name="plan-for-high-availability-requirements"></a>规划高可用性要求
  
创建高可用性计划以满足您的需求，并将其合并到更新的网络拓扑图中。 阅读 Network [planning with ExpressRoute for Office 365中的 Azure ExpressRoute 高可用性和Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)。
  
#### <a name="plan-for-network-security-requirements"></a>规划网络安全要求
  
创建满足网络安全要求的计划，并将其纳入更新的网络拓扑图。 阅读 Network [planning with ExpressRoute for Office 365 for Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)中的将安全控件应用于 **Azure ExpressRoute** 中的Office 365。
  
### <a name="design-outbound-service-connectivity"></a>设计出站服务连接
<a name="outbound"> </a>

ExpressRoute for Office 365具有可能不熟悉的出站网络要求。 具体而言，表示要连接到的用户和网络Office 365并充当到 Microsoft 的出站网络连接的源终结点的 IP 地址必须遵循下面列出的特定要求。
  
1. 终结点必须是注册到贵公司或为您提供 ExpressRoute 连接的运营商的公共 IP 地址。

2. 终结点必须公布给 Microsoft，并且由 ExpressRoute 验证/接受。

3. 终结点不得使用相同或更首选的路由指标播发到 Internet。

4. 终结点不能用于连接到未通过 ExpressRoute Microsoft 服务配置的连接。

如果网络设计不满足这些要求，则由于路由黑色全息或非对称路由Office 365或其他 Microsoft 服务，用户将面临连接故障的高风险。 当对 Microsoft 服务 的请求通过 ExpressRoute 路由时，会出现此情况，但响应会通过 Internet 路由回，反之亦然，并且有状态网络设备（如防火墙）会丢弃响应。
  
满足上述要求的最常见方法是使用源 NAT，方法是作为网络的一部分实现，或由 ExpressRoute 运营商提供。 源 NAT 允许你从 ExpressRoute 和 提取 Internet 网络的详细信息和专用 IP 寻址;与正确的 IP 路由广告结合，提供一种简单的机制来确保路径对称。 如果你使用的是特定于 ExpressRoute 对等位置的有状态网络设备，则必须针对每个 ExpressRoute 对等实现单独的 NAT 池以确保路径对称。
  
详细了解 [ExpressRoute NAT 要求](/azure/expressroute/expressroute-nat)。
  
将出站连接更改添加到网络拓扑图。
  
### <a name="design-inbound-service-connectivity"></a>设计入站服务连接
<a name="inbound"> </a>

大多数企业 Office 365 部署都假定某种形式的入站连接从 Office 365 到本地服务，例如 Exchange、SharePoint 和 Skype for Business 混合方案、邮箱迁移以及使用 ADFS 基础结构的身份验证。 当 ExpressRoute 在内部部署网络和 Microsoft 之间启用额外的路由路径进行出站连接时，这些入站连接可能会无意中受到非对称路由的影响，即使您打算让这些流继续使用 Internet。 建议采用下面所述的一些预防措施，以确保对从内部部署系统到本地系统的基于 Internet Office 365流没有影响。
  
为了最大程度地降低入站网络流量流非对称路由的风险，所有入站连接都应在路由到网络分段（具有 ExpressRoute 的路由可见性）之前，使用源 NAT。 如果允许传入连接在无源 NAT 的情况下路由可见 ExpressRoute 的网络段，来自 Office 365 的请求将从 Internet 进入，但返回 Office 365 的响应将首选 ExpressRoute 网络路径返回到 Microsoft 网络，从而导致非对称路由。
  
你可以考虑以下实现模式之一来满足此要求：
  
1. 使用网络设备（如防火墙或负载平衡器）将请求从 Internet 路由到内部部署系统之前，先执行源 NAT。

2. 确保 ExpressRoute 路由不会传播到处理 Internet 连接的入站服务（如前端服务器或反向代理系统）所在的网络段。

明确计算网络中这些方案并保留所有入站网络流量通过 Internet 有助于最大程度地降低非对称路由的部署和操作风险。
  
在某些情况下，你可以选择通过 ExpressRoute 连接引导某些入站流。 对于这些方案，应考虑以下额外注意事项。
  
1. Office 365只能面向使用公共 IP 的本地终结点。 这意味着，即使内部部署入站终结点仅通过 ExpressRoute Office 365，它仍然需要与公用 IP 关联。

2. 所有 DNS 名称解析Office 365使用公共 DNS 解析本地终结点。 这意味着您必须在 Internet 上注册入站服务终结点的 FQDN 到 IP 的映射。

3. 为了通过 ExpressRoute 接收入站网络连接，必须通过 ExpressRoute 向 Microsoft 公布这些终结点的公共 IP 子网。

4. 仔细评估这些入站网络流量流，以确保根据公司安全和网络策略对它们应用适当的安全和网络控制。

5. 通过 ExpressRoute 向 Microsoft 公布内部部署入站终结点后，ExpressRoute 将有效地成为所有 Microsoft 服务（包括 Office 365）的这些终结点的首选路由路径。 这意味着，这些终结点子网只能用于与 Office 365 服务的通信，而不要用于 Microsoft 网络的其他服务。 否则，你的设计将导致非对称路由，其中来自Microsoft 服务的入站连接倾向于通过 ExpressRoute 路由入站，而返回路径将使用 Internet。

6. 如果 ExpressRoute 电路或会议位置关闭，你将需要确保本地入站终结点仍可用于接受通过单独网络路径的请求。 这可能意味着通过多个 ExpressRoute 电路为这些终结点发布子网。

7. 我们建议对通过 ExpressRoute 进入网络的所有入站网络流量应用源 NAT，尤其是在这些流跨有状态网络设备（如防火墙）时。

8. 某些本地服务（如 ADFS 代理或 Exchange 自动发现）可能同时接收来自 Office 365 服务和 Internet 用户的入站请求。 对于这些请求Office 365将面向与用户通过 Internet 请求相同的 FQDN。 允许从 Internet 到这些内部部署终结点的入站用户连接，同时Office 365连接使用 ExpressRoute，这表示路由的复杂性很大。 对于绝大多数客户，出于操作考虑，不建议通过 ExpressRoute 实现此类复杂方案。 此额外开销包括管理非对称路由的风险，并且需要你仔细管理跨多个维度的路由广告和策略。

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>更新网络拓扑计划以显示如何避免非对称路由
<a name="asymmetric"> </a>

您希望避免非对称路由，以确保组织成员可以无缝地Office 365 Internet 上的其他重要服务。 客户具有两种导致非对称路由的常见配置。 现在是查看计划使用的网络配置并检查是否存在其中一种非对称路由方案的良好时间。
  
首先，我们将检查一些与以下网络图相关的不同情况。 在此图中，接收入站请求的所有服务器（如 ADFS 或本地混合服务器）都位于 New Jersey 数据中心，并公布给 Internet。
  
1. 外围网络是安全的，但没有源 NAT 可用于传入请求。

2. New Jersey 数据中心中的服务器能够查看 Internet 和 ExpressRoute 路由。

![ExpressRoute 连接概述。](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
我们还提供如何修复它们的建议。
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>问题 1：通过 Internet 从云到本地连接
  
下图说明了当网络配置未通过 Internet 为来自 Microsoft 云的入站请求提供 NAT 时采用的非对称网络路径。
  
1. 来自 Office 365的入站请求从公共 DNS 检索内部部署终结点的 IP 地址，并将请求发送到外围网络。

2. 在此错误配置中，在发送流量的外围网络中没有配置或可用的源 NAT，从而导致将实际源 IP 地址用作返回目标。

  - 您网络上的服务器通过任何可用的 ExpressRoute Office 365将返回流量路由到其他服务器。

  - 结果是该流的非对称路径Office 365，从而导致连接断开。

![ExpressRoute 等长路由问题 1。](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>解决方案 1a：源 NAT
  
只需将源 NAT 添加到入站请求，可解决此错误配置的网络。 在此图中：
  
1. 传入的请求将继续通过 New Jersey 数据中心的外围网络输入。 此时源 NAT 可用。

2. 来自服务器的响应将路由回与源 NAT 关联的 IP，而不是原始 IP 地址，从而导致响应沿同一网络路径返回。

![ExpressRoute 等长路由解决方案 1。](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>解决方案 1b：路由范围
  
或者，你可以选择不允许播发 ExpressRoute BGP 前缀，从而删除这些计算机的备用网络路径。 在此图中：
  
1. 传入的请求将继续通过 New Jersey 数据中心的外围网络输入。 这一次，通过 ExpressRoute 电路从 Microsoft 播发的前缀对 New Jersey 数据中心不可用。

2. 来自服务器的响应通过唯一可用的路由向与原始 IP 地址关联的 IP 路由返回，从而导致响应沿同一网络路径返回。

![ExpressRoute Asymetric 路由解决方案 2。](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>问题 2：通过 ExpressRoute 从云到本地连接
  
下图说明了当网络配置未通过 ExpressRoute 为来自 Microsoft 云的入站请求提供 NAT 时采用的非对称网络路径。
  
1. 来自 DNS 的入站Office 365从 DNS 检索 IP 地址并将请求发送到外围网络。

2. 在此错误配置中，在发送流量的外围网络中没有配置或可用的源 NAT，从而导致将实际源 IP 地址用作返回目标。

  - 网络上计算机通过任何可用的 ExpressRoute 网络连接将返回Office 365路由到其他位置。

  - 结果是非对称连接与Office 365。

![ExpressRoute 等长路由问题 2.](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>解决方案 2：源 NAT
  
只需将源 NAT 添加到入站请求，可解决此错误配置的网络。 在此图中：
  
1. 传入的请求将继续通过纽约数据中心的外围网络输入。 此时源 NAT 可用。

2. 来自服务器的响应将路由回与源 NAT 关联的 IP，而不是原始 IP 地址，从而导致响应沿同一网络路径返回。

![ExpressRoute 等长路由解决方案 3。](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>白皮书验证网络设计是否具有路径对称

此时，你需要在纸张上验证你的实施计划是否为你将使用网络部署的不同方案提供Office 365。 你将确定当某人使用服务的不同功能时预期采用的特定网络路由。 从本地网络和 WAN 路由到外围设备，到连接路径;ExpressRoute 或 Internet，并连接到联机终结点。
  
你需要为之前标识为组织将采用的所有 Office 365网络服务执行此操作。
  
本白皮书通过第二个人完成路线演练将有所帮助。 向他们解释每个网络跃点应从何处获取其下一个路由，并确保你熟悉路由路径。 请记住，ExpressRoute 将始终向 Microsoft 服务器 IP 地址提供范围更广的路由，从而提供比 Internet 默认路由更低的路由成本。
  
### <a name="design-client-connectivity-configuration"></a>设计客户端连接配置
<a name="asymmetric"> </a>

![将 PAC 文件与 ExpressRoute 一同使用。](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
如果你将代理服务器用于 Internet 绑定流量，则需要调整任何 PAC 或客户端配置文件，以确保网络上的客户端计算机已正确配置为将所需的 ExpressRoute 流量发送到 Office 365 而无需传输代理服务器，其余流量（包括一些 Office 365 流量）将发送到相关代理。 阅读有关管理 OFFICE 365 [终结点（](./managing-office-365-endpoints.md)例如 PAC 文件）的指南。
  
> [!NOTE]
> 终结点会频繁更改，频率为每周一次。 只应基于组织采用的服务和功能进行更改，以减少需要所做的更改数，使其保持最新状态。 请密切注意 RSS 源中的"有效日期"，其中将公布更改，并保留所有过去更改的记录，宣布的 IP 地址可能不会公布，也可能不会从广告中删除，直到到达生效日期。
  
## <a name="build-your-deployment-and-testing-procedures"></a>构建部署和测试过程
<a name="testing"> </a>

您的实施计划应包括测试和回滚规划。 如果你的实现未如预期运行，则计划应设计为在发现问题之前影响最少人数。 以下是计划应考虑的一些高级别原则。
  
1. 分段网络段和用户服务载入，以最大限度地减少中断。

2. 规划从单独的 Internet 连接主机使用 traceroute 和 TCP 连接测试路由。

3. 最好在具有测试租户的隔离测试网络上测试入站和出Office 365服务。

      - 或者，如果客户尚未使用或正在试用，可在生产Office 365进行测试。

      - 或者，在生产中断期间（仅为测试和监视留出）可以执行测试。

      - 或者，可以通过检查每个第 3 层路由器节点上每个服务的路由来进行测试。 只有在无法进行其他测试时，才应使用这种回退，因为缺少物理测试会带来风险。

### <a name="build-your-deployment-procedures"></a>构建部署过程

部署过程应分阶段向小型人员组推出，以允许先进行测试，然后再部署到更大的人员组。 以下是分步部署 ExpressRoute 的几种方法。
  
1. 使用 Microsoft 对等设置 ExpressRoute，并仅出于分步测试目的将路由广告转发到单个主机。

2. 首先将路由播发到 ExpressRoute 网络到单个网段，然后按网络段或区域展开路由广告。

3. 如果是首次Office 365部署，请使用 ExpressRoute 网络部署作为一些人员试点。

4. 如果使用代理服务器，也可以配置测试 PAC 文件，在添加更多内容之前，通过测试和反馈将一些人员引导到 ExpressRoute。

您的实现计划应列出必须执行的每个部署过程或部署网络配置所需的命令。 网络中断时间到达时，进行的所有更改都应来自预先编写的书面部署计划并经过对等审查。 请参阅我们的 ExpressRoute 技术配置指南。
  
- 如果已更改将继续发送电子邮件的任何本地服务器的 IP 地址，则更新 SPF TXT 记录。

- 如果已更改 IP 地址以适应新的 NAT 配置，则更新内部部署服务器的任何 DNS 条目。

- 确保你已订阅 RSS 源，Office 365终结点通知，以维护任何路由或代理配置。

完成 ExpressRoute 部署后，应执行测试计划中的过程。 应记录每个过程的结果。 如果测试计划结果指示实现未成功，则必须包括回滚到原始生产环境的过程。
  
### <a name="build-your-test-procedures"></a>构建测试过程

测试过程应包括针对每个出站和入站网络服务的测试Office 365将同时使用 ExpressRoute 和不会使用的入站网络服务。 这些过程应包括从每个唯一网络位置进行测试，包括不在企业 LAN 中的用户。
  
测试活动的一些示例包括：
  
1. 从本地路由器 Ping 到网络运营商路由器。

2. 验证本地路由器Office 365接收 500+Office 365和 CRM Online IP 地址广告。

3. 验证入站和出站 NAT 是否正在 ExpressRoute 和内部网络之间运行。

4. 验证到 NAT 的路由是否正在从路由器公布。

5. 验证 ExpressRoute 是否接受你播发的前缀。

      - 使用以下 cmdlet 验证对等广告：

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. 验证公共 NAT IP 范围是否未通过任何其他 ExpressRoute 或公共 Internet 网络线路向 Microsoft 公布，除非它是较大范围的特定子集（如前面的示例所示）。

7. ExpressRoute 电路已配对，验证这两个 BGP 会话是否正在运行。

8. 在 NAT 内部设置单个主机，并使用 ping、tracert 和 tcpping 测试与主机连接的新 outlook.office365.com。 或者，可以在镜像端口上使用 Wireshark 或 Microsoft Network Monitor 3.4 等工具连接到 MSEE，以验证能否连接到与 outlook.office365.com 关联的 IP 地址。

9. 测试应用程序应用程序级别的Exchange Online。

  - 测试Outlook用户能否连接到Exchange Online发送/接收电子邮件。

  - 测试Outlook能够使用联机模式。

  - 测试智能手机连接和发送/接收功能。

10. 测试 SharePoint Online 的应用程序级别功能

  - 测试OneDrive for Business客户端。

  - 测试 SharePoint Online Web 访问。

11. 测试用于以下调用Skype for Business应用程序级别功能：

  - 以经过身份验证的用户身份加入电话会议 [最终用户发起的邀请]。

  - 邀请用户加入电话会议 [从 MCU 发送的邀请]。

  - 使用 Web 应用程序以匿名Skype for Business加入会议。

  - 从有线电脑连接、IP 电话和移动设备加入呼叫。

  - 呼叫联盟用户 o 呼叫 PSTN 验证：呼叫已完成，呼叫质量可接受，连接时间可接受。

  - 验证租户成员和联盟用户是否更新了联系人的状态。

### <a name="common-problems"></a>常见问题

非对称路由是最常见的实现问题。 以下是要查找的一些常见源：
  
- 使用没有源 NAT 的开放或平面网络路由拓扑。

- 未使用 SNAT 通过 Internet 和 ExpressRoute 连接路由到入站服务。

- 在广泛部署之前，不在测试网络上测试 ExpressRoute 上的入站服务。

## <a name="deploying-expressroute-connectivity-through-your-network"></a>通过网络部署 ExpressRoute 连接
<a name="testing"> </a>

将部署一次分步部署到一个网络段，逐步推出到不同网络部分的连接，并计划回滚每个新网段。 如果你的部署与部署Office 365一致，请首先Office 365试点用户，然后从该部署扩展。
  
首先用于测试，然后用于生产：
  
- 运行部署步骤以启用 ExpressRoute。

- 测试网络路由是否如预期一样。

- 在每个入站和出站服务上执行测试。

- 如果发现任何问题，回滚。

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>设置与具有测试网段的 ExpressRoute 的测试连接

现在，你已完成的白皮书计划，是时候进行小规模测试了。 在此测试中，你将与 Microsoft 对等建立与本地网络测试子网的单个 ExpressRoute 连接。 可以[配置与测试](https://go.microsoft.com/fwlink/p/?LinkID=403802)子网Office 365连接的试用租户，并包括将在测试子网的生产中使用的所有出站和入站服务。 为测试网络段设置 DNS，并建立所有入站和出站服务。 执行测试计划，并确保熟悉每个服务的路由和路由传播。
  
### <a name="execute-the-deployment-and-test-plans"></a>执行部署和测试计划

完成上述项目后，请查看已完成的区域，并确保你和团队在执行部署和测试计划之前已查看这些方面。
  
- 网络更改中涉及的出站和入站服务的列表。

- 显示 Internet 出口和 ExpressRoute meet-me 位置的全局网络体系结构图。

- 网络路由图，演示部署的每个服务所使用的不同网络路径。

- 具有实现更改和回滚的步骤（如果需要）的部署计划。

- 测试每个服务和网络服务Office 365测试计划。

- 已完成入站和出站服务的生产路由的纸张验证。

- 跨测试网络段完成的测试，包括可用性测试。

选择一个足以运行整个部署计划和测试计划的中断时段，有一些时间可用于故障排除和回滚（如有必要）。
  
> [!CAUTION]
> 由于通过 Internet 和 ExpressRoute 路由的复杂性质，建议向此窗口添加额外的缓冲区时间以处理复杂路由的疑难解答。
  
### <a name="configure-qos-for-skype-for-business-online"></a>为 Skype for Business Online 配置 QoS

QoS 是获得联机语音和会议Skype for Business所必需的。 在确保 ExpressRoute 网络连接不会阻止任何其他服务访问后，可以配置 QoS Office 365访问。 Skype for Business [Online 中的 ExpressRoute 和 QoS 一文介绍了 QoS 的配置](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)。
  
## <a name="troubleshooting-your-implementation"></a>实现疑难解答
<a name="troubleshooting"> </a>

首先查看此实施指南中的步骤，实施计划中是否遗漏了任何步骤？ 如果可能，请返回并运行进一步的小网络测试，以复制错误并在那里调试它。
  
确定测试期间哪些入站或出站服务失败。 专门获取每个失败的服务的 IP 地址和子网。 继续操作，在纸张上演示网络拓扑图并验证路由。 请专门验证 ExpressRoute 路由播发到何处，如有可能，请通过跟踪在中断期间测试该路由。
  
将带网络跟踪的 PSPing 运行到每个客户终结点，并评估源 IP 地址和目标 IP 地址，以验证它们是否符合预期。 对端口 25 上公开的任何邮件主机运行 telnet，并验证 SNAT 是否隐藏原始源 IP 地址（如果预期）。
  
请记住，在通过 ExpressRoute 连接部署 Office 365时，需要确保 ExpressRoute 的网络配置设计最佳，并且还优化了网络上的其他组件（如客户端计算机）。 除了使用此规划指南对您可能错过的步骤进行疑难解答之外，我们还为 Office 365 编写性能疑难解答[计划](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c)。
  
以下是可以用于返回的简短链接：[https://aka.ms/implementexpressroute365]()
  
## <a name="related-topics"></a>相关主题

[评估 Office 365 网络连接](assessing-network-connectivity.md)
  
[适用于 Office 365 的 Azure ExpressRoute](azure-expressroute.md)
  
[管理 ExpressRoute for Office 365 连接](managing-expressroute-for-connectivity.md)
  
[使用 ExpressRoute for Office 365 路由](routing-with-expressroute.md)
  
[ExpressRoute for Office 365 网络计划](network-planning-with-expressroute.md)
  
[在 ExpressRoute 中将 BGP 社区用于Office 365方案](bgp-communities-in-expressroute.md)
  
[Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[优化 Skype for Business Online 网络](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[Skype for Business Online 中的 ExpressRoute 和 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[使用 ExpressRoute 的呼叫流](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[使用基线和性能历史记录优化 Office 365 性能](performance-tuning-using-baselines-and-history.md)
  
[Office 365 性能疑难解答计划](performance-troubleshooting-plan.md)
  
[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365 网络和性能优化](network-planning-and-performance.md)
