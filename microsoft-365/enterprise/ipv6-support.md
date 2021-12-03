---
title: Microsoft 365 服务中的 IPv6 支持
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/03/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 摘要：介绍了政府产品/服务Microsoft 365中的 IPv6 Microsoft 365支持。
ms.openlocfilehash: a6a2e11ff2e312c02f10d152fe580bdead5fa7c9
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301950"
---
# <a name="ipv6-support-in-microsoft-365-services"></a>Microsoft 365 服务中的 IPv6 支持

Microsoft 365 IPv6 和 IPv4;但是，并非所有Microsoft 365都使用 IPv6 完全启用。 这意味着您必须同时使用 IPv4 和 IPv6 连接到Microsoft 365。 如果要筛选出站流量到 Microsoft 365，可以在文章 Microsoft 365 URL 和 IP 地址范围中找到 Microsoft 365 支持的 IPv6 地址的完整[列表](urls-and-ip-address-ranges.md)。 配置网络并允许相应的 IPv6 地址后，可以从 Microsoft 下载Microsoft 365下载[IPv6](https://go.microsoft.com/fwlink/?LinkId=293447)测试计划。

> [!NOTE]
> 支持客户从Microsoft 365和任何设备体验 SaaS 服务是 Microsoft 的首要任务。 这包括允许客户连接和使用Microsoft 365 IPv6 和仅 IPv6 客户端和信息系统进行连接。 它还允许政府客户满足其网络上 IPv6 的承诺，同时继续Microsoft 365生产力方案。  
> 本文提供了目前允许直接Microsoft 365 IPv6 连接的 SaaS 服务列表。 允许直接 IPv6 连接的服务范围将继续扩大。 Microsoft 365直接 IPv6 支持未明确提及的服务（包括 Azure Active Directory (AAD) 身份验证服务）应视为要求仅从 IPv6 客户端和环境连接到 DNS64/NAT64。  这符合现有 NIST USGv6 文档中当前概述的意图：NIST 特殊出版物 [500-267A 修订版 1](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.500-267Ar1.pdf) NAT64/DNS64 中的转换机制功能要求是可接受的技术。
> - NAT64 支持转换机制 NAT64 [RFC6146](https://datatracker.ietf.org/doc/html/rfc6146) 有状态 NAT64：网络地址和协议从 IPv6 客户端到 IPv4 服务器的转换
> - 对转换机制 DNS64 的 DNS64 支持。 [RFC6147](https://datatracker.ietf.org/doc/html/rfc6147) DNS64：用于从 IPv6 客户端到 IPv4 服务器的网络地址转换的 DNS 扩展

  
## <a name="ipv6-support-in-microsoft-365-subscription-service"></a>订阅服务中的 IPv6 Microsoft 365支持

### <a name="exchange-online-and-ipv6"></a>Exchange Online 和 IPv6

如果你用于连接到客户端的程序Exchange Online IPv6，它将默认在有线和无线网络上使用 IPv6。 如果要控制与用户的通信Exchange Online，请使用"URL"和"IP 地址Microsoft 365[中的 IP 地址范围](urls-and-ip-address-ranges.md)。
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online 和 IPv6

 **Microsoft 365政府版 G1/G3/G4/K1** 如果你用于连接到 SharePoint Online 的程序支持 IPv6，它将默认尝试使用 IPv6。
  
 **公共多租户云** Microsoft 可SharePoint启用联机 IPv6。 您需要为组织的 DNS 基础结构提供 CIDR 表示 IP 地址。 请记住，其他组织无法共享此 DNS 基础结构，无法为租户启用 IPv6。 启用 IPv6 后，如果你用于连接到 SharePoint Online 的程序支持 IPv6，它将默认使用 IPv6。
  
如果你用于连接到 SharePoint Online 的程序支持 IPv6，它将默认在有线和无线网络上使用 IPv6。 如果要控制与 SharePoint 的通信，请使用 "URL" 和 "IP 地址Microsoft 365[中的 IP 地址范围](urls-and-ip-address-ranges.md)。
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business和 IPv6

请注意，IPv6 在 Skype for Business且不能再启用。

### <a name="microsoft-teams-sip-gateway-and-ipv6"></a>Microsoft Teams、SIP 网关和 IPV6

Microsoft Teams路由和 SIP 网关仅支持 IPv4。 服务Microsoft Teams客户端同时支持 IPv4 和 IPv6。 如果要控制与用户的通信Microsoft Teams，请使用"URL"和"IP 地址Microsoft 365[中的 IP 地址范围](urls-and-ip-address-ranges.md)。
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection 和 IPv6

Exchange Online Protection (传输) 传输时，EOP 服务支持 IPv6。 对于 EOP 范围，请使用[Microsoft 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)。
  
### <a name="ipv6-support-for-microsoft-365-government-offerings"></a>针对政府产品/Microsoft 365 IPv6 支持

Microsoft 365政府产品/服务提供的 IPv6 支持符合 Office 管理和预算 (OMB) （针对管理层和机构的首席信息官）以及美国政府采用 Internet 协议版本 6 (IPv6) 的规定。 [Microsoft Microsoft 365政府](https://go.microsoft.com/fwlink/p/?LinkId=325414)计划是一种多租户服务，可将美国政府数据存储在隔离社区云中。 与其他Microsoft 365产品一样，它提供生产力和协作服务，包括 Exchange Online、Skype for Business、SharePoint Online 和 Microsoft 365 企业应用版。 

Microsoft Microsoft 365政府产品/服务仅适用于 2013 及更高版本。 有关政府产品/服务Microsoft 365，请参阅宣布Microsoft 365[政府产品/](https://go.microsoft.com/fwlink/p/?LinkId=325414)服务：美国政府政府社区云。 国际武器贸易条例 (ITAR) 是一组美国政府法规，它控制美国《美国国防》列表 (USML) 上的与防御相关的文章和服务的导出 [和导入 ](https://go.microsoft.com/fwlink/p/?LinkId=325415)。 

Microsoft Microsoft 365 企业中心为 Microsoft 生产力解决方案提供专用托管服务，以支持要求联邦信息安全管理 (FISMA) 认证和商业实体受 ITAR 保护的美国联邦机构的安全、隐私和法规遵从性要求。
  
## <a name="things-to-consider-when-using-ipv6-and-microsoft-365"></a>使用 IPv6 和 IPv6 时要考虑Microsoft 365

建议您不要禁用 IPv6。 有关详细信息，请参阅本指南 [文章](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。 若要确定网络上使用哪些 IP 版本，请考虑以下事项：
  
- 如果在命令提示符下显示 **IPConfig** 命令包含名为"IPv6 地址"或"临时 IPv6 地址"的行，则环境中有 IPv6。

- 如果所有 IPv6 地址均以"fe80"开头，并且对应于名为"Link-Local IPv6 Address"的行，则环境中没有 IPv6。

这些注意事项可能适用于你的网络：
  
- 公共订阅服务不支持通过 IPv6 通过信用卡购买。 这不适用于企业政府社区云 (GCC) ，因为政府企业协议 (EA) 许可。

- IPv6 不支持某些权限管理服务 (RMS) 方案。

- IPv6 不支持 BlackBerry® Enterprise Server (BES) ，因为 BlackBerry 不支持 IPv6。

- 如果将 Active Directory 联合身份验证服务 (AD FS) Microsoft 365，则不支持使用 IPv6 向Microsoft 365 AD FS 网络终结点进行广告。 使用 AD FS DNS 条目时，不得包含 AAAA Exchange Online。 

以下是可以用于返回的简短链接：[https://aka.ms/o365ip6]()

## <a name="see-also"></a>另请参阅

[IPv6 Learning路线图](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 生存指南](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
