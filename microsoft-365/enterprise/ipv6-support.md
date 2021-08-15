---
title: Office 365 服务中的 IPv6 支持
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 摘要：介绍政府产品/服务Microsoft Office 365中的 IPv6 Office 365支持。
ms.openlocfilehash: d526cc2c701ebfcfd322c10c3147f085c6eecb8acb47ed6a55a3c95641ea76cb
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53858995"
---
# <a name="ipv6-support-in-office-365-services"></a>Office 365 服务中的 IPv6 支持

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Office 365支持 IPv6 和 IPv4;但是，并非所有Office 365都使用 IPv6 完全启用。 这意味着您必须同时使用 IPv4 和 IPv6 连接到Office 365。 如果您要筛选出站流量到 Office 365，Office 365 支持的 IPv6 地址的完整列表可以在文章[Office 365 URL 和 IP](urls-and-ip-address-ranges.md)地址范围中找到。 配置网络并允许相应的 IPv6 地址后，可以从 Microsoft 下载Office 365下载[IPv6](https://go.microsoft.com/fwlink/?LinkId=293447)测试计划。
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>订阅服务中的 IPv6 Office 365支持

### <a name="exchange-online-and-ipv6"></a>Exchange Online 和 IPv6

如果用于连接到客户端的程序Exchange Online IPv6，它将默认在有线和无线网络上使用 IPv6。 如果要控制与用户的通信Exchange Online，请使用"URL"和"IP 地址Office 365[中的 IP 地址范围](urls-and-ip-address-ranges.md)。
  
### <a name="sharepoint-online-and-ipv6"></a>SharePointOnline 和 IPv6

 **Office 365 政府版 G1/G3/G4/K1** 如果用于连接到 SharePoint Online 的程序支持 IPv6，它将默认尝试使用 IPv6。
  
 **公共多租户云** Microsoft 可SharePoint启用联机 IPv6。 您需要为组织的 DNS 基础结构提供 CIDR 表示 IP 地址。 请记住，其他组织无法共享此 DNS 基础结构，无法为租户启用 IPv6。 启用 IPv6 后，如果你用于连接到 SharePoint Online 的程序支持 IPv6，它将默认使用 IPv6。
  
如果你用于连接到 SharePoint Online 的程序支持 IPv6，它将默认在有线和无线网络上使用 IPv6。 如果要控制与 SharePoint Online 的通信，请使用 OFFICE 365 URL 和[IP 地址范围 中的 IP 地址范围](urls-and-ip-address-ranges.md)。
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business 和 IPv6

请注意，IPv6 在 Skype for Business且不能再启用。

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 和 IPV6

Microsoft Teams直接路由仅支持 IPv4。 客户端Microsoft Teams和客户端都支持 IPv4 和 IPv6。 如果要控制与用户的通信Microsoft Teams，请使用"URL"和"IP 地址Office 365[中的 IP 地址范围](urls-and-ip-address-ranges.md)。
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection 和 IPv6

Exchange Online Protection (传输) 传输时，EOP 服务支持 IPv6。 对于 EOP 范围，请使用[Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)。
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>针对政府产品/Office 365 IPv6 支持

Office 365政府产品/服务 IPv6 支持符合 Office《管理和预算》 (OMB) （适用于管理层和机构的首席信息官）以及美国政府采用 Internet 协议第 6 版 (IPv6) 。 [Microsoft Office 365政府](https://go.microsoft.com/fwlink/p/?LinkId=325414)计划是一种多租户服务，可将美国政府数据存储在隔离社区云中。 与其他Office 365产品一样，它提供生产力和协作服务，包括 Exchange Online、Skype for Business、SharePoint Online 和 Microsoft 365 企业应用版。 

政府Microsoft Office 365仅适用于 2013 及更高版本。 有关政府产品/服务Office 365，请参阅[宣布Office 365政府产品/](https://go.microsoft.com/fwlink/p/?LinkId=325414)服务：美国政府政府社区云。 《国际武器贸易条例》 (ITAR) 是一组美国政府法规，可控制美国《美国国防》列表 (USML) 上的与防御相关的文章和服务的导出 [和导入 ](https://go.microsoft.com/fwlink/p/?LinkId=325415)。 

Microsoft Office 365 企业组织为 Microsoft 生产力解决方案提供专用托管服务，以支持要求联邦信息安全管理 (FISMA) 认证和商业实体受 ITAR 保护的美国联邦机构的安全、隐私和法规遵从性要求。
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>使用 IPv6 和 IPv6 时要考虑Office 365

建议您不要禁用 IPv6。 有关详细信息，请参阅本指南 [文章](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。 若要确定网络上使用哪些 IP 版本，请考虑以下事项：
  
- 如果在命令提示符下显示 **IPConfig** 命令包含名为"IPv6 地址"或"临时 IPv6 地址"的行，则环境中有 IPv6。

- 如果所有 IPv6 地址均以"fe80"开头，并且对应于名为"Link-Local IPv6 Address"的行，则环境中没有 IPv6。

这些注意事项可能适用于你的网络：
  
- 公共订阅服务不支持通过 IPv6 通过信用卡购买。 这不适用于该政府社区云 (GCC) ，因为政府企业协议 (EA) 许可。

- IPv6 不支持某些权限管理服务 (RMS) 方案。

- IPv6 不支持 BlackBerry® Enterprise Server (BES) 因为 BlackBerry 不支持 IPv6。

- 如果使用 Active Directory 联合身份验证服务 (AD FS) Office 365，则不支持使用 IPv6 向 Office 365 AD FS 网络终结点做广告。 使用 AD FS DNS 条目时，不得包含 AAAA Exchange Online。 

以下是可以用于返回的简短链接：[https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>另请参阅

[IPv6 Learning路线图](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 生存指南](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
