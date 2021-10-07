---
title: 在 ExpressRoute 中将 BGP 社区用于Office 365方案
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: 了解如何在 Azure ExpressRoute 中使用 BGP 社区管理 IP 前缀的数量和用于Office 365带宽。
ms.openlocfilehash: afcbbbebda8dcc7c9425831b44f0d95f0eca5a18
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195409"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>在 ExpressRoute 中将 BGP 社区用于Office 365方案

使用 Azure ExpressRoute 连接到Office 365基于特定 IP 子网的 BGP 播发，这些子网表示Office 365终结点的网络。 由于广告的全局性质Office 365服务的数量Office 365，客户通常需要管理其网络上接受的广告。 减少 IP 子网的数量;为了与 BGP 网络管理术语保持一致，本文其余部分均称为 IP 前缀，为客户提供以下最终目标：
  
- 管理已播发 **的 IP** 前缀接受的号码 - 具有仅支持有限数量的 IP 前缀的内部网络基础结构或网络运营商的客户，以及具有网络运营商且接受超过有限号码的前缀的客户的需要评估已公布到其网络的前缀总数，并选择最适合 ExpressRoute 的 Office 365 应用程序。

- **管理 Azure ExpressRoute** 电路上所需的带宽量 - 客户可能想要通过 ExpressRoute 路径与 Internet 路径控制 Office 365 服务的带宽信封。 这使客户可以保留特定应用程序（如 Skype for Business）的 ExpressRoute 带宽，Office 365 Internet 路径路由其余的应用程序。

为帮助客户实现这些目标，Office 365 ExpressRoute 播发的 IP 前缀使用特定于服务的 BGP 社区值进行标记，如下面的示例所示。
  
> [!NOTE]
> 您应该会预期与其他应用程序关联的一些网络流量会包含在社区值中。 对于具有共享服务和数据中心的全局软件即服务产品，这是预期行为。 在达到上述两个目标的情况下，这已最小化，即管理前缀计数和/或带宽。

|**服务**|**BGP Community 值**|**备注**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |包括 Exchange 和 EOP 服务\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Skype for Business联机& Microsoft Teams服务  <br/> |
|其他Office 365服务\*  <br/> |12076:5100  <br/> |包括Azure Active Directory (身份验证和目录同步) 以及Office 365门户服务  <br/> |
|\*ExpressRoute 中包含的服务方案的范围记录在 Office 365[文章中](./urls-and-ip-address-ranges.md)。  <br/> \*\*将来可能会添加其他服务和 BGP 社区值。 [请参阅 BGP 社区的当前列表](/azure/expressroute/expressroute-routing)。  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>使用 BGP 社区的最常见方案是什么？

客户可以使用 BGP 社区来管理其网络通过 Azure ExpressRoute 接受的 IP 前缀组，从而影响某些服务的总 IP 前缀计数和预期的Office 365信封。 无论使用 Azure ExpressRoute 还是 BGP Office 365，所有应用程序都需要 Internet 绑定流量，了解这一点很重要。 以下三种方案是此功能的最常见用法。
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>方案 1：最大程度地减少Office 365 IP 前缀的数量

Contoso Corporation 是一家拥有 50，000 个人的公司，目前Office 365 Exchange Online SharePoint Online。 在查看 ExpressRoute 要求时，Contoso 确定其在许多区域位置的网络设备无法处理超过 100 个其他路由条目的路由表大小。 Contoso 查看了 ExpressRoute 为整套 Office 365 服务播发的 IP 前缀总数，并结束其超过 100 个。 若要留在 100 个其他路由条目下，Contoso 将 expressRoute for Office 365 的使用范围缩小到仅 SharePoint Online BGP 社区值 12076：5020，该值通过 ExpressRoute Microsoft 对等接收。

|**使用的 BGP 社区标记**|**Azure ExpressRoute 上可路由的功能**|**所需的 Internet 路由**|
|:-----|:-----|:-----|
|SharePoint  <br/>  (12076：5020)   <br/> |SharePoint联机 &amp; OneDrive for Business  <br/> | &amp;DNS、CRL、CDN请求  <br/>  所有其他未Office 365 Azure ExpressRoute 支持的其他所有服务  <br/>  所有其他 Microsoft 云服务  <br/>  Office 365门户Office 365身份验证 &amp; ，Office浏览器中执行  <br/>  Exchange Online、Exchange Online Protection 和 Skype for Business Online  <br/> |

> [!NOTE]
> 若要降低每个服务的前缀计数，服务之间的重叠量将保持最少。 这是正常现象。
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>方案 2：将 ExpressRoute 和内部带宽的使用范围Office 365服务

Fabrikam Inc 是一家具有分布式异类网络的大型跨国家企业，它订阅了许多Office 365服务，包括;Exchange Online、SharePoint Online 和 Skype for Business Online。 Fabrikam 的内部路由基础结构可以处理其路由表中的数千个 IP 前缀;但是，Fabrikam 只想为对网络性能最敏感的 Office 365 应用程序设置 ExpressRoute 和内部带宽，并使用其现有的 Internet 带宽用于所有其他 Office 365 应用程序。
  
因此，Fabrikam 将 Azure ExpressRoute 带宽范围缩小到仅 Skype for Business Online BGP Community 值 12076：5030，该值通过 ExpressRoute Microsoft 对等接收。 与网站关联的剩余网络流量Office 365继续使用 Internet 出口点。

|**使用的 BGP 社区标记**|**Azure ExpressRoute 上可路由的功能**|**所需的 Internet 路由**|
|:-----|:-----|:-----|
|Skype for Business  <br/>  (12076：5030)   <br/> |SkypeSIP 信号、下载、语音、视频和桌面共享  <br/> | &amp;DNS、CRL、CDN请求  <br/>  所有其他未Office 365 Azure ExpressRoute 支持的其他所有服务  <br/>  所有其他 Microsoft 云服务  <br/>  Office 365门户Office 365身份验证 &amp; ，Office浏览器中执行  <br/>  Skype for Business遥测、Skype客户端快速提示、公共 IM 连接  <br/>  Exchange Online、Exchange Online Protection 和 SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>方案 3：仅将 Azure ExpressRoute Office 365服务

Woodgrove Bank 是多个 Microsoft 云服务的客户，包括Office 365。 在评估其网络容量和消耗后，Woodgrove Bank 决定部署 Azure ExpressRoute 作为受支持服务的首选Office 365路径。 路由表可以支持完整的 IP 前缀Office 365他们设置的 Azure ExpressRoute 电路支持所有预计的带宽和延迟需求。
  
为了确保与除 Office 365 外的其他 Microsoft 云服务关联的网络流量，Woodgrove Bank 将 ExpressRoute for Office 365 的使用范围限制为使用 Office 365 特定 BGP 社区值、12076：5010、12076：5020、12076：5030、12076：5100 标记的所有 IP 前缀。

|**使用的 BGP 社区标记**|**Azure ExpressRoute 上可路由的功能**|**所需的 Internet 路由**|
|:-----|:-----|:-----|
|Exchange、Skype for Business & Microsoft Teams、SharePoint、 &amp; 其他服务  <br/>  (12076：5010、12076：5020、12076：5030、12076：5100)   <br/> |&amp;Exchange OnlineExchange Online Protection  <br/> SharePoint联机 &amp; OneDrive for Business  <br/> SkypeSIP 信号、下载、语音、视频和桌面共享  <br/> Office 365门户Office 365身份验证 &amp; ，Office浏览器中执行  <br/> | &amp;DNS、CRL、CDN请求  <br/>  所有其他未Office 365 Azure ExpressRoute 支持的其他所有服务  <br/>  所有其他 Microsoft 云服务  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>使用 BGP 社区的关键规划注意事项

选择利用 BGP 社区影响 ExpressRoute 在客户网络中公布和传播方式的客户应考虑以下注意事项：
  
- 在网络设计中使用 BGP 社区时，确保仍保持路由对称很重要。 在某些情况下，添加或删除 BGP 社区可能会导致对称路由中断，并且必须更新路由配置以重新建立对称路由。

- 使用 BGP 社区值界定 Azure ExpressRoute 范围是一种客户操作。 Microsoft 将公布与对等关系关联的所有 IP 前缀，而不考虑客户配置的任何范围。

- Azure ExpressRoute 不支持基于客户分配的 BGP 社区在 Microsoft 网络上执行的任何操作。

- 应用程序使用的 IP 前缀Office 365服务特定的 BGP 社区值进行标记，不支持特定于位置的 BGP 社区。 Office 365服务本质上是全局的，不支持基于租户位置或云中数据Office 365前缀。 建议的方法是将网络配置为协调从用户的网络位置到 Microsoft 全局网络的最短或首选网络路径，而不考虑用户请求的 Office 365 服务 IP 地址的物理位置。

- 每个 BGP 社区值中包含的 IP 前缀表示一个子网，其中包含与值Office 365的应用程序的 IP 地址。 在某些情况下，多个应用程序Office 365子网中具有 IP 地址，从而导致多个社区值中已有 IP 前缀。 这虽然很少成为因分配碎片导致的行为，但不会影响前缀计数或带宽管理目标。 建议客户在利用 BGP 社区来减少影响时，使用"允许所需Office 365"方法，而不是"拒绝不需要的"方法。

- 使用 BGP 社区不会更改使用 BGP 通信所需的基础网络连接Office 365。 希望访问 Office 365仍需要能够访问 Internet。

- 将 Azure ExpressRoute 与 BGP 社区进行范围限制仅影响内部网络可以通过 Microsoft 对等关系看到的路由。 您可能需要进行额外的应用程序级别配置，例如将 PAC 或 WPAD 配置与作用域路由结合使用。

- 除了使用 Microsoft 分配的 BGP 社区外，客户可以选择将其自己的 BGP 社区分配给通过 Azure ExpressRoute Office 365的 IP 前缀，以影响内部路由。 一个热门用例是，将基于位置的 BGP 社区分配给通过每个给定的 ExpressRoute 对等位置学习的所有路由，然后使用客户网络中下游的信息协调进入 Microsoft 网络的最短或首选网络路径。 将客户分配的 BGP 社区与 ExpressRoute Office 365的方案的使用超出了 Microsoft 控制或可见性的范围。

以下是可用于返回的简短链接 [https://aka.ms/bgpexpressroute365]() ：。
  
## <a name="related-topics"></a>相关主题

[评估 Office 365 网络连接](assessing-network-connectivity.md)
  
[适用于 Office 365 的 Azure ExpressRoute](azure-expressroute.md)
  
[管理 ExpressRoute for Office 365 连接](managing-expressroute-for-connectivity.md)
  
[使用 ExpressRoute for Office 365 路由](routing-with-expressroute.md)
  
[ExpressRoute for Office 365 网络计划](network-planning-with-expressroute.md)
  
[Skype for Business Online 中的媒体质量和网络连接性能](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Skype for Business Online 中的 ExpressRoute 和 QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[使用 ExpressRoute 的呼叫流](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[实现 ExpressRoute for Office 365](implementing-expressroute.md)
  
[对 BGP 社区的支持](/azure/expressroute/expressroute-routing)
  
[使用基线和性能历史记录优化 Office 365 性能](performance-tuning-using-baselines-and-history.md)
  
[Office 365 性能疑难解答计划](performance-troubleshooting-plan.md)
  
[Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer)（Azure ExpressRoute for Office 365 培训）