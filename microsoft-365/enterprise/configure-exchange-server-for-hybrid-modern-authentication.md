---
title: 如何配置本地 Exchange Server 以使用混合新式验证
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 了解如何在本地配置 Exchange Server 以使用混合新式验证 (HMA) ，为您提供更安全的用户身份验证和授权。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780280"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>如何配置本地 Exchange Server 以使用混合新式验证

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

混合新式 (HMA) 是一种标识管理方法，可提供更安全的用户身份验证和授权，并且可用于 Exchange 服务器本地混合部署。

## <a name="fyi"></a>FYI

在开始之前，我调用：

- 混合新式验证 \> HMA

- Exchange 本地 \> EXCH

- Exchange Online \> EXO

此外，如果本文中的图形有一个"灰显"或"灰显"的对象，则意味着以灰色显示的元素不包含在 *HMA 特定的配置中*。

## <a name="enabling-hybrid-modern-authentication"></a>启用混合新式验证

打开 HMA 意味着：

1. 确保在开始之前满足预先要求。

1. 由于 **Skype** for Business 和 Exchange 都常见许多先决条件，混合新式验证概述以及将混合新式验证与本地 [Skype for Business](hybrid-modern-auth-overview.md)和 Exchange 服务器一同使用的先决条件。 在开始本文中的任一步骤之前，应执行上述操作。

1. 将本地 Web 服务 URL 添加为 Azure AD (**SSP**) 服务主体名称。

1. 确保为 HMA 启用所有虚拟目录

1. 检查 EvoSTS Auth Server 对象

1. 在 EXCH 中启用 HMA。

 **注意** Office 版本是否支持 MA？ 请参阅 [新式验证如何适用于 Office 2013 和 Office 2016 客户端应用](modern-auth-for-office-2013-and-2016.md)。

## <a name="make-sure-you-meet-all-the-prerequisites"></a>确保满足所有先决条件

由于 Skype for Business 和 Exchange 都常见许多先决条件，请查看混合新式验证概述以及将混合新式验证与本地 [Skype for Business](hybrid-modern-auth-overview.md)和 Exchange 服务器一同使用的先决条件。 在开始  *本文中的*  任一步骤之前，应执行上述操作。

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>在 Azure AD 中添加本地 Web 服务 URL 作为 SNS

运行将本地 Web 服务 URL 分配为 Azure AD SNS 的命令。 SNS 在身份验证和授权期间由客户端计算机和设备使用。 可能用于从本地连接到 Azure Active Directory (Azure AD) 的所有 URL 都必须在 Azure AD (这包括内部和外部命名空间) 。

首先，收集需要在 AAD 中添加的所有 URL。 在本地运行以下命令：

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

确保 URL 客户端可能连接到的 URL 在 AAD 中列为 HTTPS 服务主体名称。

1. 首先，使用这些 [说明连接到](connect-to-microsoft-365-powershell.md)AAD。

   **注意** 您需要使用此页面中的 _Connect-MsolService_ 选项才能使用下面的命令。

2. 对于与 Exchange 相关的 URL，键入以下命令：

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   记下 (和屏幕截图，用于稍后比较) 此命令的输出，该命令应包含 https://  *autodiscover.yourdomain.com*  和 https://  *mail.yourdomain.com* URL，但主要包括以 000000002-0000-0ff1-ce00-0000000000000/开头的 SSP。 如果本地https:// URL 缺失，我们需要将这些特定记录添加到此列表。

3. 如果在此列表中看不到内部和外部 MAPI/HTTP、EWS、ActiveSync、OAB 和自动发现记录，则必须使用下面的命令添加它们 (示例 URL 为 `mail.corp.contoso.com` ""和 `owa.contoso.com` ""，但需要将示例 URL 替换为您自己的) ：

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 通过再次运行步骤 2 中的 Get-MsolServicePrincipal 命令并查看输出，验证是否添加了新记录。 将之前的列表/屏幕截图与新的 SNS 列表进行比较。 您还可以为记录拍摄新列表的屏幕截图。 如果成功，你将在列表中看到两个新 URL。 以我们的示例为例，SNS 列表现在将包括特定的 URL 和  `https://mail.corp.contoso.com`  `https://owa.contoso.com` 。

## <a name="verify-virtual-directories-are-properly-configured"></a>验证虚拟目录是否正确配置

现在，通过运行以下命令，验证 Outlook 可能使用的所有虚拟目录的 Exchange 中是否正确启用了 OAuth：

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

检查输出以确保在这些 VDirs 中每个 VDirs 上都启用了 **OAuth，** 它看起来如下所示 (关键内容是"OAuth") ：

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

如果任何服务器和四个虚拟目录中的任一虚拟目录中缺少 OAuth，则需要在继续 (Set-MapiVirtualDirectory、Set-WebServicesVirtualDirectory、Set-OABVirtualDirectory 和[](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory)[](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory)[Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)) 之前，使用相关命令添加 OAuth。 [](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>确认 EvoSTS 身份验证服务器对象存在

返回最后一个命令的本地 Exchange 命令行管理程序。 现在，您可以验证您的本地是否具有 evoSTS 身份验证提供程序的条目：

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

输出应显示名称 EvoSts 的 AuthServer，并且"已启用"状态应为 True。 如果未看到此内容，应下载并运行最新版本的混合配置向导。

 **重要** 如果在环境中运行 Exchange 2010，将不会创建 EvoSTS 身份验证提供程序。

## <a name="enable-hma"></a>启用 HMA

在本地 Exchange 命令行管理程序 中运行以下命令：

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>验证

启用 HMA 后，客户端的下一个登录名将使用新的身份验证流。 请注意，仅打开 HMA 不会触发任何客户端的重新身份验证。 客户端根据其拥有身份验证令牌和/或证书的生存期重新进行身份验证。

在右键单击 Outlook 客户端图标的同时，还应按住 Ctrl 键 (Windows 通知任务栏) 然后单击"连接状态"。 针对"Bearer"类型的"Authn"类型查找客户端的 SMTP 地址，该类型表示 OAuth 中使用的记 \* 名令牌。

 **注意** 需要配置具有 HMA 的 Skype for Business？ 你将需要两篇文章：一 [篇文章列出支持的](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)拓扑，另一篇文章演示如何 [执行配置](configure-skype-for-business-for-hybrid-modern-authentication.md)。

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>将混合新式验证用于 Outlook for iOS 和 Outlook for Android

如果您是使用 TCP 443 上的 Exchange 服务器本地客户，请绕过以下 IP 范围的流量处理：

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>相关主题

[从 Office 365 专用/ITAR 转换到 vNext 的新式验证配置要求](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
