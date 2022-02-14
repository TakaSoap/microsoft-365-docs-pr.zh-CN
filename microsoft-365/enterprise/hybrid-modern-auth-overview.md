---
title: 混合新式验证概述以及与本地 Skype for Business和 Exchange 服务器一起使用的先决条件
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 12/03/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.assetid: ef753b32-7251-4c9e-b442-1a5aec14e58d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 本文将介绍混合新式验证，以及用于内部部署服务器和Skype for Business Exchange的先决条件。
ms.openlocfilehash: f0abb01b7a03405f576a12766b21b3c36113004d
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62807304"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>混合新式验证概述以及将其与本地 Skype for Business和 Exchange 服务器一起使用的先决条件

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。*

_新式验证_ 是一种标识管理，它提供更安全的用户身份验证和授权。 它可用于本地 Office 365 服务器和本地 Skype for Business 服务器的 Exchange 混合部署，以及拆分域Skype for Business混合。 本文链接到有关先决条件、设置/禁用新式验证的相关文档，以及一些相关客户端（例如 Outlook 和 Skype 客户端）的信息。

- [什么是新式验证？](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [使用新式验证时有何变化？](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [检查本地环境的新式验证状态](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [是否满足新式验证先决条件？](#do-you-meet-modern-authentication-prerequisites)
- [在开始之前，我还需要了解哪些信息？](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>什么是新式验证？
<a name="BKMK_WhatisModAuth"> </a>

新式验证是客户端（例如，笔记本电脑或手机）和服务器之间的身份验证和授权方法的组合，以及某些依赖于你可能已经熟悉的访问策略的安全措施的总称。 其中包括：

- **身份验证方法**：多重身份验证 (MFA) ;智能卡身份验证;基于客户端证书的身份验证
- **身份验证方法**：Microsoft 的开放授权 (OAuth) 实施
- **条件访问策略**：移动应用程序管理 (MAM) 和 Azure Active Directory (Azure AD) 条件访问

通过新式验证来管理用户身份，可以为管理员提供多种保护资源的工具，并为本地（Exchange 和 Skype for Business）、Exchange 混合以及 Skype for Business 混合/拆分域方案提供更安全的身份管理方法。

由于Skype for Business网站Exchange，Skype for Business登录行为将受新式身份验证状态的影响Exchange。 如果你拥有一个 Skype for Business 拆分域混合体系结构，其中你在本地拥有 Skype for Business Online 和 Skype for Business，并且用户同时位于这两个位置，则也适用。

有关应用程序中新式验证Office 365，请参阅Office 365[客户端应用支持 - 多重身份验证](microsoft-365-client-support-multi-factor-authentication.md)。

> [!IMPORTANT]
> 自 2017 年 8 月起，包括 Skype for Business Online 和 Exchange Online 在内的所有新 Office 365 租户都将默认启用新式验证。 既有租户的默认 MA 状态不会发生变化，但是所有新租户都会自动支持上面列出的一组扩展身份功能。 若要查看你的 MA 状态，请参阅[检查本地环境的新式验证状态](hybrid-modern-auth-overview.md#BKMK_CheckStatus)部分。

## <a name="what-changes-when-i-use-modern-authentication"></a>使用新式验证时有何变化？
<a name="BKMK_WhatChanges"> </a>

在本地 Skype for Business 或 Exchange 服务器上使用新式验证时，仍将对用户进行 *身份验证*，但 *授权* 他们对资源（例如文件或电子邮件）进行更改。 这就是为什么尽管新式验证与客户端和服务器通信有关，但在配置 MA 期间采取的步骤会导致 evoSTS（Azure AD 使用的安全令牌服务）被设置为 Skype for Business 和本地 Exchange Server 的身份验证服务器。

对 evoSTS 的更改使你的本地服务器可以利用 OAuth（令牌发行）对客户端进行授权，还可以让你的本地服务器使用云中常见的安全方法（例如多重身份验证）。 另外，evoSTS 还会发行令牌，使用户可以请求访问资源而无需在请求中提供密码。 无论用户位于何处（线上还是本地）、无论哪个位置托管所需资源，一旦配置了新式验证，EvoSTS 都将成为授权用户和客户端的核心。

例如，如果 Skype for Business 客户端需要访问 Exchange 服务器来代表用户获取日历信息，则它使用 Microsoft 身份验证库 (MSAL) 来这样做。 MSAL 是一个代码库，旨在使用 OAuth 安全令牌使目录中的安全资源可供客户端应用程序使用。 MSAL 使用 OAuth 验证声明，并交换 (而不是密码) ，以授予用户访问资源的权限。 过去，这种事务中的颁发机构（知道如何验证用户声明和颁发所需令牌的服务器）可能是本地安全令牌服务，甚至是 Active Directory 联合身份验证服务。 但是，新式验证通过使用 Azure AD 集中了该授权服务。

这也意味着，即使你的 Exchange 服务器和 Skype for Business 环境可能完全位于本地，授权服务器也将处于联机状态，并且你的本地环境必须具有创建和维护与云中的 Office 365 订阅（以及你的订阅将其用作目录的 Azure AD 实例）的连接的能力。

哪些方面没有发生更改？ 无论你是在拆分域混合环境还是在本地使用 Skype for Business 和 Exchange 服务器，所有用户都必须首先在 *本地* 进行身份验证。 在新式验证的混合实施中，_Lyncdiscovery_ 和 _Autodiscovery_ 都指向本地服务器。

> [!IMPORTANT]
> 如果你需要了解 MA 支持的特定 Skype for Business 拓扑，请在[此处](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)进行文档说明。

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>检查本地环境的新式验证状态
<a name="BKMK_CheckStatus"> </a>

由于新式验证会更改服务应用 OAuth/S2S 时所使用的授权服务器，因此需要知道是为本地身份验证环境启用还是禁用新式Skype for Business Exchange环境。 可以通过运行以下 PowerShell 命令来检查 Exchange 服务器上的状态：

```powershell
Get-OrganizationConfig | ft OAuth*
```

如果 _OAuth2ClientProfileEnabled_ 属性的值为 **False**，则可以进行新式验证。

有关 OrganizationConfig cmdlet 的详细信息，请参阅 [OrganizationConfig](/powershell/module/exchange/get-organizationconfig)。

可以通过运行以下 PowerShell 命令来检查 Skype for Business 服务器：

```powershell
Get-CSOAuthConfiguration
```

如果命令返回空的 _OAuthServers_ 属性，或者如果 _ClientADALAuthOverride_ 属性的值不是 **Allowed**，则表示新式验证已禁用。

有关 CsOAuthConfiguration cmdlet 的详细信息，请参阅 [CsOAuthConfiguration](/powershell/module/skype/get-csoauthconfiguration)。

## <a name="do-you-meet-modern-authentication-prerequisites"></a>是否满足新式验证先决条件？

在继续之前，请验证并检查列表中的以下项目：

- **特定于 Skype for Business**
  - 所有服务器都必须具有 Skype for Business Server 2015 或更高版本 2017 年 5 月的累积更新 (CU5)
    - **例外** — Survivability Branch Appliance (SBA) 可以是当前版本（基于 Lync 2013）
  - 你的 SIP 域被添加为 Office 365 中的联合域
  - 所有 SFB 前端都必须有与 Internet 的连接、Office 365 身份验证 URL (TCP 443) 以及 Office 365 URL 和 [IP](urls-and-ip-address-ranges.md) 地址范围的"Microsoft 365 公用"和"Office"部分的第 56 行和 125 行中列出的已知证书根 CLS (TCP 80) 。

- **混合 Office 365 环境中的本地 Skype for Business**
  - Skype for Business Server 2019 部署（所有服务器都运行 Skype for Business Server 2019）。
  - Skype for Business Server 2015 部署（所有服务器都运行 Skype for Business Server 2015）。
  - 最多具有两个不同服务器版本的部署，如下所示：
    - Skype for Business Server 2015
    - Skype for Business Server 2019
  - 所有 Skype for Business 服务器都必须安装最新的累积更新，请参阅 [Skype for Business服务器更新](/skypeforbusiness/sfb-server-updates)以查找和管理所有可用更新。
  - 混合环境中没有 Lync Server 2010 或 2013。

>[!NOTE]
>如果你的 Skype for Business 前端服务器使用代理服务器进行 Internet 访问，则必须在 web.config 文件的配置部分中为每个前端输入使用的代理服务器 IP 和端口号。

- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\int\web.config
- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\ext\web.config

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <proxy
        proxyaddress="https://192.168.100.60:8080"
        bypassonlocal="true" />
    </defaultProxy>
  </system.net>
</configuration>
```

> [!IMPORTANT]
> 确保为 [Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)订阅 RSS 源，以随时获取最新的必需 URL 列表。

- **特定于 Exchange 服务器**
  - 你正在使用 Exchange Server 2013 CU19 及更高版本、Exchange Server 2016 CU8 及更高版本或 Exchange Server 2019 CU1 及更高版本。
  - 环境中没有 Exchange server 2010。
  - 未配置 SSL 卸载。 支持 SSL 终止和重新加密。
  - 如果你的环境利用代理服务器基础结构来允许服务器连接到 Internet，请确保所有 Exchange 服务器都具有 [InternetWebProxy ](/powershell/module/exchange/set-exchangeserver) 属性中定义的代理服务器。

- **混合 Office 365 环境中的本地 Exchange Server**

  - 如果你使用的是 Exchange Server 2013，则必须有至少一台服务器安装了邮箱和客户端访问服务器角色。 尽管您可以在单独的服务器上安装邮箱角色和客户端访问角色，但我们强烈建议您在同一台服务器上安装这两个角色，以提供更高的可靠性和更高的性能。
  - 如果你使用的是 Exchange Server 2016 或更高版本，则必须有至少一台服务器安装了邮箱服务器角色。
  - 混合环境中没有 Exchange server 2007 或 2010。
  - 所有 Exchange 服务器都必须安装最新的累积更新，请参阅 [将 Exchange 升级到最新累积更新](/exchange/plan-and-deploy/install-cumulative-updates)以查找和管理所有可用更新。

- **Exchange 客户端和协议要求**

    新式验证的可用性由客户端、协议和配置的组合决定。 如果客户端、协议和/或配置不支持新式验证，则客户端将继续使用旧身份验证。
  
    在环境中启用新式身份验证时，Exchange客户端和协议支持使用本地身份验证的新式验证：

  |**客户端**|**主协议**|**备注**|
  |:-----|:-----|:-----|
  |Outlook 2013 及更高版本  <br/> |MAPI over HTTP  <br/> |必须在 Exchange 中启用 MAPI over HTTP，以便对 Exchange 2013 Service Pack 1 和) 及以上的新安装使用这些客户端使用新式验证 (或 True;有关详细信息，请参阅新式验证如何适用于 [Office 2013 和 Office 2016](modern-auth-for-office-2013-and-2016.md) 客户端应用。  <br/> 确保运行的是最低要求的 Outlook 内部版本；请参阅[使用 Windows Installer (MSI) 的 Outlook 版本的最新更新](/officeupdates/outlook-updates-msi)。  <br/> |
  |Outlook 2016 for Mac及更高版本  <br/> |Exchange Web 服务  <br/> |  <br/> |
  |Outlook for iOS 和 Outlook for Android  <br/> | Microsoft 同步技术 <br/> |有关详细信息，请参阅[将混合新式验证用于 Outlook for iOS 和 Outlook for Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)。  <br/> |
  |Exchange ActiveSync客户端 (例如，iOS11 邮件)   <br/> |Exchange ActiveSync  <br/> |对于支持新式验证的 Exchange ActiveSync 客户端，必须重新创建配置文件才能从基本身份验证切换到新式验证。  <br/> |

    未列出的客户端和/或协议 (例如，POP3) 不支持使用本地 Exchange 的新式身份验证，并且即使在环境中启用了新式验证后，仍继续使用旧身份验证机制。

- **一般先决条件**
  - 资源林方案将需要与帐户林的双向信任，以确保在混合新式身份验证请求期间执行正确的 SID 查找。 
  - 如果使用 AD FS，则应使用 Windows 2012 R2 AD FS 3.0 及更高版本进行联合身份验证。
  - 身份配置是 Azure AD Connect 支持的任何类型，例如密码哈希同步、传递身份验证和 Office 365 支持的本地 STS。
  - 已配置 Azure AD Connect 并可正常进行用户复制和同步。
  - 已验证已使用 Exchange 经典混合拓扑模式在本地和 Office 365 环境之间配置了混合部署。 Exchange混合部署的官方支持声明指明必须拥有当前 CU 或当前 CU-1。
    > [!NOTE]
    > [混合代理](/exchange/hybrid-deployment/hybrid-agent)不支持混合新式验证。

  - 如果要对 Exchange) 使用新式身份验证，请确保本地测试用户和 Office 365 中的混合测试用户都可以登录到 Skype for Business 桌面客户端 (（如果要对 Skype) 和 Microsoft Outlook (使用新式验证）。

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>在开始之前，我还需要了解哪些信息？
<a name="BKMK_Whatelse"> </a>

- 本地服务器的所有方案都涉及在本地设置新式验证（实际上，对于 Skype for Business，存在一系列受支持的拓扑），以便负责身份验证和授权的服务器位于 Microsoft 云中（Azure AD 的安全令牌服务，称为“evoSTS”），并更新与你的本地 Skype for Business 或 Exchange 安装所使用的 URL 或命名空间有关的 Azure AD。 因此，本地服务器具有 Microsoft 云依赖性。 可以考虑采取此操作来配置“混合身份验证”。
- 本文链接到可帮助你选择支持的新式验证拓扑（仅对 Skype for Business 必需）的其他文章以及概述了设置步骤，或者针对本地 Exchange 和本地 Skype for business 禁用新式验证的步骤的操作说明文章。 如果需要一个在服务器环境中使用新式验证的基地，请在浏览器中收藏此页面。

## <a name="related-topics"></a>相关主题
<a name="BKMK_URLListforMA"> </a>

- [如何配置本地 Exchange Server 以使用新式验证](configure-exchange-server-for-hybrid-modern-authentication.md)
- [新式验证支持的 Skype for Business 拓扑](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
- [如何配置本地 Skype for Business 以使用新式验证](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [从 Skype for Business 和 Exchange 删除或禁用混合新式验证](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)
