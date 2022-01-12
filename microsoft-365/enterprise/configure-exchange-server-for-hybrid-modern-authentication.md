---
title: 如何配置本地 Exchange Server 以使用混合新式验证
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/27/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 了解如何配置本地Exchange Server使用混合新式验证 (HMA) ，以为您提供更安全的用户身份验证和授权。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d0889008595717308695c1ad9c5d2a9f1766d1ea
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61934485"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>如何配置本地 Exchange Server 以使用混合新式验证

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

混合新式 (HMA) 是一种标识管理方法，可提供更安全的用户身份验证和授权，并且可用于 Exchange 服务器本地混合部署。

## <a name="definitions"></a>定义

在开始之前，你应该熟悉一些定义：

- 混合新式验证 \> HMA

- Exchange本地 \>EXCH

- Exchange Online \> EXO

此外，如果本文中的图形有一个"灰显"或"灰显"的对象，则意味着以灰色显示的元素不包含在 *HMA 特定的配置中*。

## <a name="enabling-hybrid-modern-authentication"></a>启用混合新式验证

打开 HMA 意味着：

1. 确保在开始之前满足预先要求。

1. 由于许多 **先决条件** 对 Skype for Business 和 Exchange 都很常见，因此混合新式验证概述以及将混合新式验证与本地 Skype for Business 和 Exchange [服务器一同使用的先决条件](hybrid-modern-auth-overview.md)。 在开始执行本文中的任一步骤之前，应先执行这些步骤。
有关要插入的链接邮箱的要求。

1. 将本地 Web 服务 URL 添加为服务主体名称 (**SNS**) 中Azure AD。 如果 EXCH 与多个租户混合，则必须在与 EXCH 混合的所有租户的 Azure AD 中添加这些本地 Web 服务 URL 作为 SNS。

1. 确保为 HMA 启用所有虚拟目录

1. 检查 EvoSTS Auth Server 对象

1. 在 EXCH 中启用 HMA。

> [!NOTE]
> 你的版本是否Office MA？ 请参阅[新式验证如何适用于 Office 2013 和 Office 2016 客户端应用](modern-auth-for-office-2013-and-2016.md)。

## <a name="make-sure-you-meet-all-the-prerequisites"></a>确保满足所有先决条件

由于许多先决条件对于 Skype for Business 和 Exchange 都很常见，请查看混合新式验证概述以及用于本地 Skype for Business 和 Exchange[服务器的先决条件](hybrid-modern-auth-overview.md)。 在开始  *执行本文*  中的任一步骤之前，应先执行这些步骤。

> [!NOTE]
> Outlook Web App和Exchange控制面板不能用于混合新式验证。

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>将本地 Web 服务 URL 作为 SNS 添加到Azure AD

运行命令，将本地 Web 服务 URL 作为 SNS Azure AD URL。 SNS 在身份验证和授权期间由客户端计算机和设备使用。 所有可能用于从本地连接到 Azure Active Directory (Azure AD) URL 都必须在 Azure AD (这包括内部和外部命名空间) 。

首先，收集需要在加载项中添加的所有AAD。 在本地运行以下命令：

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*hostname*
```

确保客户端可能连接到的 URL 作为 HTTPS 服务主体名称列在AAD。 如果 EXCH 与多个租户混合，则这些 HTTPS S PIN 应AAD与 EXCH 混合的所有租户的"服务器"中。

1. 首先，使用这些AAD[连接到客户端](connect-to-microsoft-365-powershell.md)。

    > [!NOTE]
    > 您需要使用此页中的 _连接-MsolService_ 选项才能使用下面的命令。

2. 对于Exchange URL，请键入以下命令：

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   记下命令 (和屏幕截图，以) 此命令的输出，该命令应包含 和 URL，但主要包括以 开头的 `https://*autodiscover.yourdomain.com*` `https://*mail.yourdomain.com*` `00000002-0000-0ff1-ce00-000000000000/` SNS。 如果本地中缺少 URL，则这些特定记录 `https://` 应添加到此列表。

3. 如果在此列表中看不到内部和外部 MAPI/HTTP、EWS、ActiveSync、OAB 和自动发现记录，则必须使用下面的命令添加它们 (示例 URL 为 和 ，但需要将示例 URL 替换为您自己的 `mail.corp.contoso.com` `owa.contoso.com`) ： 

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 再次运行步骤 2 中的命令并查看输出，验证 `Get-MsolServicePrincipal` 是否添加了新记录。 将之前的列表/屏幕截图与新的 SNS 列表进行比较。 您还可以为记录拍摄新列表的屏幕截图。 如果成功，你将在列表中看到两个新的 URL。 以我们的示例为例，SNS 列表现在将包括特定的 URL 和 `https://mail.corp.contoso.com` `https://owa.contoso.com` 。

## <a name="verify-virtual-directories-are-properly-configured"></a>验证虚拟目录是否正确配置

现在验证 OAuth 是否Exchange所有虚拟目录Outlook运行以下命令来使用：

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

检查输出以确保在每个 VDirs 上启用 **OAuth，** 它看起来如下所示 (需要查看的关键内容是"OAuth") ：

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

如果任一服务器和四个虚拟目录中的任意一个中缺少 OAuth，则需要在继续 (Set-MapiVirtualDirectory、Set-WebServicesVirtualDirectory、Set-OABVirtualDirectory 和[Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)) 之前，使用相关命令添加 OAuth。 [](/powershell/module/exchange/set-mapivirtualdirectory) [](/powershell/module/exchange/set-webservicesvirtualdirectory) [](/powershell/module/exchange/set-oabvirtualdirectory)

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>确认 EvoSTS 身份验证服务器对象存在

返回到本地命令行管理Exchange最后一个命令。 现在，您可以验证您的本地是否具有 evoSTS 身份验证提供程序的条目：

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts*"} | ft name,enabled
```

输出应显示具有 GUID 的名称 EvoSt 的 AuthServer，并且"已启用"状态应为 True。 如果未看到此内容，应下载并运行最新版本的混合配置向导。

> [!NOTE]
> 如果 EXCH 与多个租户混合，则输出应为与 EXCH 混合的每个租户显示一个 Name 的 AuthServer，并且所有这些 AuthServer 对象的 Enabled 状态应为 `EvoSts - {GUID}` True。 

> [!IMPORTANT]
> 如果在环境中运行 Exchange 2010，将不会创建 EvoSTS 身份验证提供程序。

## <a name="enable-hma"></a>启用 HMA

在本地命令行管理Exchange命令行管理程序中运行以下命令，将命令行替换为 \<GUID\> 您的环境中字符串：

```powershell
Set-AuthServer -Identity "EvoSTS - <GUID>" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> 在较旧版本的混合配置向导中，EvoSts AuthServer 仅命名为 EvoSTS，未附加 GUID。 无需执行任何操作，只需通过删除命令的 GUID 部分修改上述命令行来反映这一点：
>
> ```powershell
> Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
> ```

如果 EXCH 版本是 Exchange 2016 (CU18 或更高版本) 或 Exchange 2019 (CU7 或更高版本) 且混合配置为在 2020 年 9 月之后下载 HCW，请在本地 Exchange 命令行管理程序中运行以下命令：

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> 如果 EXCH 与多个租户混合，则 EXCH 中将存在多个 AuthServer 对象，其中域对应于每个租户。  **对于其中任何** 一个 AuthServer 对象， (**IsDefaultAuthorizationEndpoint cmdlet) IsDefaultAuthorizationEndpoint** 标记应设置为 true。 无法针对所有 Authserver 对象将此标志设置为 true，并且将启用 HMA，即使其中一个 AuthServer 对象的 **IsDefaultAuthorizationEndpoint** 标志设置为 true 也是如此。
> 
> 对于 **DomainName** 参数，请使用租户域值，该值通常采用 的形式 `contoso.onmicrosoft.com` 。

## <a name="verify"></a>验证

启用 HMA 后，客户端的下一次登录将使用新的身份验证流。 请注意，仅打开 HMA 不会触发任何客户端的重新身份验证，Exchange获取新设置可能需要一段时间。

在右键单击 Outlook 客户端图标的同时，还应按住 Ctrl 键 (Windows 通知托盘) 然后单击"连接状态"。 针对 的 **Authn** 类型查找客户端的 SMTP 地址，该类型表示 OAuth 中使用的 `Bearer\*` bearer 令牌。

> [!NOTE]
> 需要配置Skype for Business HMA？ 你将需要两篇文章：一篇文章列出支持的拓扑，[](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)另一篇文章演示如何[执行配置](configure-skype-for-business-for-hybrid-modern-authentication.md)。

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>将混合新式验证用于 Outlook for iOS 和 Outlook for Android

如果您是使用 TCP 443 Exchange本地客户，则允许来自以下 IP 范围的网络流量：

```console
52.125.128.0/20
52.127.96.0/23
```

这些 IP 地址范围还记录在未包含在 Office 365 IP 地址和[URL Web 服务的其他终结点中](/microsoft-365/enterprise/additional-office365-ip-addresses-and-urls)。

## <a name="related-topics"></a>相关主题

[从专用/ITAR Office 365 vNext 的新式验证配置要求](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
