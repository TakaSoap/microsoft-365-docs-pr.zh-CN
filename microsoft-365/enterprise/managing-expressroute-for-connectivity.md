---
title: 管理 ExpressRoute for Office 365 的连接性
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: 了解如何管理 ExpressRoute for Office 365，包括配置前缀筛选、安全性和合规性等常见区域。
ms.openlocfilehash: bffe82249a9d8a531ee85525f9db0eb38a344d50
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173316"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>管理 ExpressRoute for Office 365 的连接性

ExpressRoute for Office 365提供了一种备用路由路径，无需所有流量即可访问许多 Office 365 服务，而无需所有流量都进入 Internet。 尽管仍然需要到 Office 365的 Internet 连接，但 Microsoft 通过 BGP 向网络播发的特定路由使 ExpressRoute 线路成为首选，除非网络中还有其他配置。 要管理此路由，可能需要配置的三个常见区域包括前缀筛选、安全性和合规性。
  
> [!NOTE]
> Microsoft 更改了查看 Azure ExpressRoute 的 Microsoft 对等路由域。 从 2017 年 7 月 31 日开始，所有 Azure ExpressRoute 客户都可以直接从 Azure 管理控制台或通过 PowerShell 启用 Microsoft 对等。 启用 Microsoft 对等后，任何客户都可以创建路由筛选器，以接收 Dynamics 365 Customer Engagement 应用程序（以前称为 CRM Online (）的 BGP 路由) 。 需要 Azure ExpressRoute for Office 365客户必须先获得 Microsoft 审查，然后才能创建适用于 Office 365。 请联系你的 Microsoft 帐户团队，了解如何请求有关启用 ExpressRoute Office 365审查。 尝试为用户创建路由筛选器Office 365的未授权订阅将收到[错误消息](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>前缀筛选

Microsoft 建议客户接受 Microsoft 播发的所有 BGP 路由，提供的路由会经过严格的审核和验证过程，从而取消增加审查的任何好处。 ExpressRoute 在本机提供推荐的控件，如 IP 前缀所有权、完整性和缩放 - 客户端没有入站路由筛选。
  
如果需要对 ExpressRoute 公共对等中的路由所有权进行其他验证，可以针对表示 Microsoft 公共 IP 范围的所有 IPv4 和 IPv6 IP 前缀列表检查播发的 [路由](https://www.microsoft.com/download/details.aspx?id=53602)。 这些范围涵盖完整的 Microsoft 地址空间和很少更改的范围，提供一组可靠的范围进行筛选，同时也为关注非 Microsoft 拥有的路由泄露到其环境的客户提供额外的保护。 如果进行了更改，将在当月 1 日进行更改，并且每次更新文件时，页面详细信息部分中的版本号都会更改。
  
有很多原因可避免使用用于生成前缀筛选器列表Office 365 URL 和[IP](./urls-and-ip-address-ranges.md)地址范围。 包括以下内容：
  
- IP Office 365经常发生大量更改。

- 这些Office 365 URL 和 IP 地址范围旨在管理防火墙允许列表和代理基础结构，而不是路由。

- 这些Office 365 URL 和 IP 地址范围不包括Microsoft 服务 ExpressRoute 连接范围内的其他内容。

|**选项**|**复杂度**|**更改控件**|
|:-----|:-----|:-----|
|接受所有 Microsoft 路由  <br/> |**低：** 客户依赖 Microsoft 控件来确保正确拥有所有路由。  <br/> |无  <br/> |
|筛选 Microsoft 拥有的超级网络  <br/> |**中等：** 客户实施汇总的前缀筛选器列表，以仅允许 Microsoft 拥有的路由。  <br/> |客户必须确保不经常更新反映在路由筛选器中。  <br/> |
|筛选Office 365 IP 范围  <br/> [!CAUTION] Not-Recommended |**高：** 客户根据定义的 IP 前缀Office 365路由。  <br/> |客户必须对每月更新实施可靠的变更管理流程。  <br/> [!CAUTION] 此解决方案需要进行重大长期更改。 未实时实施的更改可能会导致服务中断。   |

使用 Azure ExpressRoute 连接到Office 365基于特定 IP 子网的 BGP 播发，这些子网表示Office 365终结点的网络。 由于广告的全局性质Office 365服务的数量Office 365，客户通常需要管理他们接受的网络广告。 如果您担心环境中播发的前缀数，[则 BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099)社区功能允许您将广告筛选为一组特定的 Office 365 服务。 此功能现在为预览版。
  
无论你如何管理来自 Microsoft 的 BGP 路由广告，与单独通过 Internet 线路连接到 Office 365 相比，你将不会获得对 Office 365 服务的任何特殊曝光。 无论客户用于连接到客户端的电路类型如何，Microsoft 都会保持相同的安全、合规性Office 365。
  
### <a name="security"></a>安全性

Microsoft 建议为从 ExpressRoute 公共和 Microsoft 对等连接维护你自己的网络和安全外围控件，其中包括与 Office 365 连接。 对于从网络出站到 Microsoft 网络以及从 Microsoft 网络到网络的入站网络请求，应实施安全控制。
  
#### <a name="outbound-from-customer-to-microsoft"></a>从客户到 Microsoft 的出站邮件
  
当计算机连接到Office 365时，无论连接是通过 Internet 还是 ExpressRoute 电路进行，计算机都会连接到同一组终结点。 无论使用何种电路，Microsoft 都建议您将Office 365服务视为比一般 Internet 目标更受信任的服务。 出站安全控制应侧重于端口和协议，以减少曝光并最大限度地减少持续维护。 有关所需的端口信息，请参阅Office 365[参考](./urls-and-ip-address-ranges.md)文章。
  
对于添加的控件，可以在代理基础结构内使用 FQDN 级别筛选来限制或检查发往 Internet 或 Office 365。 随着功能发布和 Office 365 产品/服务不断发展，维护 FQN 列表需要更稳固的更改管理和对已发布的 Office 365[终结点的更改跟踪](./urls-and-ip-address-ranges.md)。
  
> [!CAUTION]
> Microsoft 建议不要仅依赖 IP 前缀来管理出站安全Office 365。

|**选项**|**复杂度**|**更改控件**|
|:-----|:-----|:-----|
|无限制  <br/> |**低：** 客户允许不受限制地对 Microsoft 进行出站访问。  <br/> |无  <br/> |
|端口限制  <br/> |**低：** 客户按预期端口限制对 Microsoft 的出站访问。  <br/> |不常使用。  <br/> |
|FQDN 限制  <br/> |**高：** 客户根据发布的 FQN Office 365出站访问邮件。  <br/> |每月更改。  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>从 Microsoft 到客户的入站邮件
  
有几种可选方案需要 Microsoft 启动到你的网络的连接。
  
- 登录密码验证期间 ADFS。

- [Exchange Server混合部署](/exchange/exchange-hybrid)。

- 从租户Exchange Online本地主机的邮件。

- SharePoint从 SharePoint Online 到本地主机的联机邮件发送。

- [SharePoint联合混合搜索](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)。

- [SharePoint混合BCS](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)。

- [Skype for Business混合](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)和/或[Skype for Business联合身份验证](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。

- [Skype for Business云连接器](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)。

Microsoft 建议通过 Internet 线路而不是 ExpressRoute 电路接受这些连接，以降低复杂性。 如果你的合规性或性能需求指示必须通过 ExpressRoute 电路接受这些入站连接，建议使用防火墙或反向代理来界定接受的连接的范围。 可以使用 Office 365[](./urls-and-ip-address-ranges.md)终结点来找出正确的 FQDN 和 IP 前缀。
  
### <a name="compliance"></a>合规性

我们不依赖你用于任何合规性控制措施的路由路径。 无论你是通过 ExpressRoute Office 365连接到服务，我们的合规性控制都不会改变。 应查看不同的合规性和安全认证级别，Office 365确定满足组织需求的最佳选择。
  
以下是可以用于返回的简短链接：[https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>相关主题

[内容分发网络](content-delivery-networks.md)
  
[Office 365 URL 和 IP 地址范围](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[管理 Office 365 终结点](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer)（Azure ExpressRoute for Office 365 培训）