---
title: IP 地址和 URL Web 服务Office 365其他终结点
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/19/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: 摘要：新的终结点 Web 服务不包括特定方案的一些终结点。
hideEdit: true
ms.openlocfilehash: 156a4ec93b8b45c71b0faed330b39962f3ec62b9
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302094"
---
# <a name="other-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>IP 地址和 URL Web 服务Office 365其他终结点

某些网络终结点以前已发布，并且尚未包含在 Office 365 [IP 地址和 URL Web 服务中](microsoft-365-ip-web-service.md)。 Web 服务范围是跨企业外围网络从用户Office 365所需的网络终结点。 此组当前不包括：

1. 可能需要从 Microsoft 数据中心建立到客户网络的网络连接（入站混合服务器网络流量）。
2. 跨企业外围网络从客户网络上的服务器建立的网络连接（出站服务器网络流量）。
3. 用户的网络连接要求的不常用方案。
4. DNS 解析连接要求（未在下面列出）。
5. Internet Explorer 或 Microsoft Edge 受信任的站点。

除了 DNS 之外，这些实例对于大多数客户都是可选的，除非你需要描述的特定方案。

<br>

****

|Row|用途|目标|类型|
|---|---|---|---|
|1|[导入服务](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6)以进行 PST 和文件引入|有关更多 [要求，请参阅导入](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) 服务。|不常用的出站方案|
|2|[Microsoft Support and Recovery Assistant for Office 365](https://diagnostics.office.com/#/)|<https://autodiscover.outlook.com> <br> <https://officecdn.microsoft.com> <br> <https://api.diagnostics.office.com> <br> <https://apibasic.diagnostics.office.com> <br> <https://autodiscover-s.outlook.com> <br> <https://cloudcheckenabler.azurewebsites.net> <br> <https://login.live.com> <br> <https://login.microsoftonline.com> <br> <https://login.windows.net> <br> <https://o365diagtelemetry.trafficmanager.net> <br> <https://odc.officeapps.live.com> <br> <https://offcatedge.azureedge.net> <br> <https://officeapps.live.com> <br> <https://outlook.office365.com> <br> <https://outlookdiagnostics.azureedge.net>|出站服务器流量|
|3|Azure AD Connect（带有 SSO 选项） - WinRM 和远程 PowerShell|客户 STS 环境（AD FS 服务器和 AD FS 代理）\| TCP 端口 80 和 443|入站服务器流量|
|4|ST FS，例如 AD FS 代理服务器（仅限联盟客户）|客户 STS（例如 AD FS 代理）\| 端口 TCP 443 或 TCP 49443，带有 ClientTLS|入站服务器流量|
|5|[Exchange Online 统一消息/SBC 集成](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers)|本地会话边界控制器和 \* .um.outlook.com|仅出站服务器流量|
|6 |邮箱迁移。 从内部部署[Exchange](/exchange/exchange-deployment-assistant)混合到 Office 365 启动邮箱迁移时，Office 365 将连接到已发布的 Exchange Web 服务 (EWS) /Mailbox Replication Services (MRS) 服务器。 如果需要 Exchange Online 服务器使用的 NAT IP 地址来限制来自特定源 IP 范围的入站连接，它们列在 Office 365 [URL & IP](urls-and-ip-address-ranges.md)范围中的"Exchange Online"服务区域下。 <p> 应小心以确保在限制来自特定源 IP 范围的 TCP 443 连接之前，MRS 代理解析为单独的 FQDN 和公共 IP 地址，以确保对已发布的 EWS 终结点（如 OWA）的访问不会受到影响。|客户本地 EWS/MRS 代理 <br> TCP 端口 443|入站服务器流量|
|7 |[Exchange混合](/exchange/exchange-deployment-assistant)共存功能，如忙/闲共享。|客户本地 Exchange 服务器|入站服务器流量|
|8 |[Exchange 混合部署](/exchange/exchange-deployment-assistant)代理身份验证|客户本地 STS|入站服务器流量|
|9 |用于使用 [Exchange 混合配置向导](/exchange/hybrid-configuration-wizard)来配置 [Exchange 混合](/exchange/exchange-deployment-assistant) <p> 注意：这些终结点仅用于配置 Exchange 混合|TCP 端口 80 和 443 上的 domains.live.com，仅用于 Exchange 2010 SP3 混合配置向导。 <p> GCC High，DoD IP 地址：40.118.209.192/32；168.62.190.41/32 <p> 全球商业 \* & GCC：.store.core.windows.net;asl.configure.office.com;tds.configure.office.com;mshybridservice.trafficmanager.net; <br> aka.ms/hybridwizard; <br> shcwreleaseprod.blob.core.windows.net/shcw/ \* ;|仅出站服务器流量|
|10 |AutoDetect 服务用于 [Exchange 混合部署](/exchange/exchange-deployment-assistant)应用场景，可实现[适用于 iOS 和 Android 的 Outlook 的混合型新式验证](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <p> `*.acompli.net` <br> `*.outlookmobile.com` <br> `*.outlookmobile.us` <br> `52.125.128.0/20` <br> `52.127.96.0/23`|TCP 443 上的客户本地 Exchange 服务器|入站服务器流量|
|11|Exchange混合Azure AD身份验证|*.msappproxy.net|TCP 出站服务器流量|
|12 |Skype for Business 2016 Office包括使用 UDP 端口的基于视频的屏幕共享。 之前Skype for Business 2013 Office早期客户端通过 TCP 端口 443 使用 RDP。|TCP 端口 443 对 52.112.0.0/14 开放|Office 2013 和早期版本中的 Skype for Business 早期客户端版本|
|13|Skype for Business 混合内部部署服务器与 Skype for Business Online 之间的连接|13.107.64.0/18, 52.112.0.0/14 <br> UDP 端口 50,000-59,999 <br> TCP 端口 50,000-59,999; 5061|Skype for Business 内部部署服务器出站连接|
|14 |具有内部部署混合连接的云 PSTN 要求网络连接对内部部署主机开放。有关 Skype for Business Online 混合配置的更多详细信息，|请参阅[ Skype for Business Server 和 Office 365 之间的混合连接](/skypeforbusiness/hybrid/plan-hybrid-connectivity)|Skype for Business 内部部署混合入站|
|15 |**身份验证和标识 FQDN** <p> FQDN `secure.aadcdn.microsoftonline-p.com` 必须位于客户端的 Internet Explorer (IE) 或 Edge 受信任的站点区域内才能起作用。||受信任的站点|
|16|**Microsoft Teams FQDN** <p> 如果你使用的是 Internet Explorer 或 Microsoft Edge，则需要启用第一方和第三方 Cookie，并将 Teams FQDN 添加到受信任的站点。这是除 14 行列出的套件级 FQDN、CDN 和遥测之外的补充内容。有关详细信息，请参阅 [ Microsoft Teams 的已知问题](/microsoftteams/known-issues)。||受信任的站点|
|17 |**SharePoint Online 和 OneDrive for Business FQDN** <p> FQDN 中带有“\<tenant\>” 的所有“.sharepoint.com” FQDN 都需要在客户的 IE 或 Edge 受信任的站点区域中才能起作用。除了 14 行列出的套件级 FQDN、CDN 和遥测之外，还需要添加这些终结点。||受信任的站点|
|18 |**Yammer**  <br> Yammer 仅在浏览器中可用，并要求经过身份验证的用户通过代理传递。所有 Yammer FQDN 都需要在客户的 IE 或 Edge 受信任的站点区域中才能起作用。||受信任的站点|
|19|使用 [Azure AD Connect](/azure/active-directory/hybrid/) 将本地用户帐户同步到 Azure AD。|请参阅[混合标识所需的端口和协议](/azure/active-directory/hybrid/reference-connect-ports)、[解决 Azure AD 连接问题](/azure/active-directory/hybrid/tshoot-connect-connectivity)和 [Azure AD Connect Health 代理安装](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints)。|仅出站服务器流量|
|20|使用由世纪互联在中国运营的 [Azure AD Connect](/azure/active-directory/hybrid/) 将本地用户帐户同步到 Azure AD。|\*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <br> secure.aadcdn.partner.microsoftonline-p.cn:443 <br> \*.partner.microsoftonline.cn:443 <p> 另请参阅[对 Azure AD 连接问题进行入口故障排除](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity)。|仅出站服务器流量|
| 21|Microsoft Stream（需要 Azure AD 用户令牌）。 <br> Office 365 全球（包括 GCC）|\*.cloudapp.net <br> \*.api.microsoftstream.com <br> \*.notification.api.microsoftstream.com <br> amp.azure.net <br> api.microsoftstream.com <br> az416426.vo.msecnd.net <br> s0.assets-yammer.com <br> vortex.data.microsoft.com <br> web.microsoftstream.com <br> TCP 端口 443|入站服务器流量|
|22|将 MFA 服务器用于多重身份验证请求，包括服务器的新安装以及使用 Active Directory 域服务 (AD DS) 进行设置。|请参阅[使用 Azure AD 多重身份验证服务器入门](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)。|仅出站服务器流量|
|23|Microsoft Graph 更改通知 <p> 开发人员可以使用[更改通知](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0)订阅 Microsoft Graph。|Public Cloud: 52.159.23.209, 52.159.17.84, 52.147.213.251, 52.147.213.181, 13.85.192.59, 13.85.192.123, 13.89.108.233, 13.89.104.147, 20.96.21.67, 20.69.245.215, 137.135.11.161, 137.135.11.116, 52.159.107.50, 52.159.107.4, 52.229.38.131, 52.183.67.212, 52.142.114.29, 52.142.115.31, 51.124.75.43, 51.124.73.177, 20.44.210.83, 20.44.210.146, 40.80.232.177, 40.80.232.118, 20.48.12.75, 20.48.11.201, 104.215.13.23, 104.215.6.169, 52.148.24.136, 52.148.27.39, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 13.86.37.15, 52.154.246.238, 20.96.21.98, 20.96.21.115, 137.135.11.222, 137.135.11.250, 52.159.109.205, 52.159.102.72, 52.151.30.78, 52.191.173.85, 51.104.159.213, 51.104.159.181, 51.138.90.7, 51.138.90.52, 52.148.115.48, 52.148.114.238, 40.80.233.14, 40.80.239.196, 20.48.14.35, 20.48.15.147, 104.215.18.55, 104.215.12.254, 20.199.102.157, 20.199.102.73, 13.87.81.123, 13.87.81.35, 20.111.9.46, 20.111.9.77, 13.87.81.133, 13.87.81.141 <p> Microsoft Cloud for US Government：52.244.33.45、52.244.35.174、52.243.157.104、 52.243.157.105、52.182.25.254、52.182.25.110、52.181.25.67、52.181.25.66、 52.244.111.156、52.244.111.170、52.243.147.249、52.243.148.1 9、52.182.32.51、52.182.32.143、52.181.24.199、52.181.24.220 <p> 由世纪互联网运营的 Microsoft 云中国：42.159.72.35、42.159.72.47、 42.159.180.55、42.159.180.56、40.125.138.23、40.125.136.69、40.72.155.199、40.72.155.216 <br> TCP 端口 443 <p> 注意：创建订阅时，开发人员可指定其他端口。|入站服务器流量|
|

## <a name="related-topics"></a>相关主题

[管理 Office 365 终结点](managing-office-365-endpoints.md)
  
[监视 Microsoft 365 连接性](./monitor-connectivity.md)
  
[客户端连接](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[内容分发网络](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Azure IP 范围和服务标记 – 公共云](https://www.microsoft.com/download/details.aspx?id=56519)

[Azure IP 范围和服务标记 – 美国政府云](https://www.microsoft.com/download/details.aspx?id=57063)

[Azure IP 范围和服务标记 – 德国云](https://www.microsoft.com/download/details.aspx?id=57064)

[Azure IP 范围和服务标记 - 中国云](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft 公共 IP 空间](https://www.microsoft.com/download/details.aspx?id=53602)
