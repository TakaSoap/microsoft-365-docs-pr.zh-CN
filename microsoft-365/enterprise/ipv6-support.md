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
description: 摘要：介绍了在 Microsoft Office 365 组件和 Office 365 政府产品/服务中的 IPv6 支持。
ms.openlocfilehash: a509b19711092bddf153a677c41860e7a4e5277a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028903"
---
# <a name="ipv6-support-in-office-365-services"></a>Office 365 服务中的 IPv6 支持

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

Office 365 支持 IPv6 和 IPv4;但是，并非所有 Office 365 功能都使用 IPv6 完全启用。 这意味着您必须同时使用 IPv4 和 IPv6 连接到 Office 365。 如果要筛选到 Office 365 的出站流量，可在文章 [Office 365 URL 和 IP](urls-and-ip-address-ranges.md)地址范围 中查看 Office 365 支持的 IPv6 地址的完整列表。 配置网络并允许相应的 IPv6 地址后，可以从 Microsoft 下载中心下载 [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) 测试计划。
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Office 365 订阅服务中的 IPv6 支持

### <a name="exchange-online-and-ipv6"></a>Exchange Online 和 IPv6

如果用于连接到 Exchange Online 的程序支持 IPv6，它将默认在有线和无线网络上使用 IPv6。 如果要控制与 Exchange Online 的通信，请使用 [Office 365 URL](urls-and-ip-address-ranges.md)中的 IP 地址范围和 IP 地址范围。
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online 和 IPv6

 **Office 365 政府版 G1/G3/G4/K1** 如果用于连接到 SharePoint Online 的程序支持 IPv6，它将默认尝试使用 IPv6。
  
 **公共多租户云** Microsoft 将应你的请求启用 SharePoint Online IPv6。 您需要为组织的 DNS 基础结构提供 CIDR 表示 IP 地址。 请记住，其他组织无法共享此 DNS 基础结构，无法为租户启用 IPv6。 启用 IPv6 后，如果用于连接到 SharePoint Online 的程序支持 IPv6，它将默认使用 IPv6。
  
如果用于连接到 SharePoint Online 的程序支持 IPv6，它将默认在有线和无线网络上使用 IPv6。 如果要控制与 SharePoint Online 的通信，请使用 [Office 365 URL](urls-and-ip-address-ranges.md)中的 IP 地址范围和 IP 地址范围。
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype for Business 和 IPv6

请注意，IPv6 在 Skype for Business 中不受支持，不能再启用。

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams 和 IPV6

Microsoft Teams 直接路由仅支持 IPv4。 Microsoft Teams 服务和客户端同时支持 IPv4 和 IPv6。 如果要控制与 Microsoft Teams 的通信，请使用 [Office 365 URL](urls-and-ip-address-ranges.md)中的 IP 地址范围和 IP 地址范围。
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection 和 IPv6

Exchange Online Protection (EOP) 传输通过传输层安全性协议进行时支持 IPv6。 对于 EOP 范围，请使用 [Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)。
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Office 365 政府版产品/服务 IPv6 支持

针对政府产品/服务 Office 365 IPv6 的支持符合管理和预算办公室 (OMB) （针对管理层和机构的首席信息官）以及美国政府采用 Internet 协议版本 6 (IPv6) 的规定。 [Microsoft Office 365 政府](https://go.microsoft.com/fwlink/p/?LinkId=325414) 版是一种多租户服务，可将美国政府数据存储在隔离社区云中。 与其他 Office 365 产品/服务一样，它提供生产力和协作服务，包括 Exchange Online、Skype for Business、SharePoint Online 和 Microsoft 365 企业应用版。 

365 Microsoft Office 365 政府版产品/服务仅适用于 2013 及更高版本。 有关 Office 365 政府版产品/服务详细信息，请参阅 [宣布推出 Office 365 政府版：美国政府社区云](https://go.microsoft.com/fwlink/p/?LinkId=325414)。 《国际武器贸易条例》 (ITAR) 是一组美国政府法规，可控制美国《美国国防》列表 (USML) 上的与防御相关的文章和服务的导出 [和导入 ](https://go.microsoft.com/fwlink/p/?LinkId=325415)。 

Microsoft Office 365 企业版为 Microsoft 生产力解决方案提供专用托管服务，以支持要求联邦信息安全管理 (FISMA) 认证的美国联邦机构的安全、隐私和法规遵从性要求以及受 ITAR 限制的商业实体。
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>使用 IPv6 和 Office 365 时要考虑的问题

建议您不要禁用 IPv6。 有关详细信息，请参阅本指南 [文章](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users)。 若要确定网络上使用哪些 IP 版本，请考虑以下事项：
  
- 如果在命令提示符下显示 **IPConfig** 命令包含名为"IPv6 地址"或"临时 IPv6 地址"的行，则环境中有 IPv6。

- 如果所有 IPv6 地址均以"fe80"开头，并且对应于名为"Link-Local IPv6 Address"的行，则环境中没有 IPv6。

这些注意事项可能适用于你的网络：
  
- 公共订阅服务不支持通过 IPv6 通过信用卡购买。 这不适用于政府社区云 (GCC) ，因为政府企业协议 (EA) 许可。

- IPv6 不支持某些权限管理服务 (RMS) 方案。

- IPv6 不支持 BlackBerry® ENTERPRISE Server (BES) 因为 BlackBerry 不支持 IPv6。

- 如果将 Active Directory 联合身份验证服务 (AD FS) Office 365，则不支持使用 IPv6 向 Office 365 发布 AD FS 网络终结点。 使用 Exchange Online 时，AD FS DNS 条目中不应包含 AAAA 记录。 

以下是可以用于返回的简短链接：[https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>另请参阅

[IPv6 学习路线图](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[IPv6 生存指南](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
