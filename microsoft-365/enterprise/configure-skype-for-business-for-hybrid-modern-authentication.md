---
title: 如何配置本地 Skype for Business 以使用混合新式验证
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 了解如何配置本地 Skype for Business 以使用混合新式验证 (HMA) ，以为您提供更安全的用户身份验证和授权。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3177bafb6eff27053dca61ec576666cae4a97bb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911146"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>如何配置本地 Skype for Business 以使用混合新式验证

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

新式验证是一种标识管理方法，可提供更安全的用户身份验证和授权，可用于 Skype for Business 服务器本地和 Exchange 服务器本地，以及拆分域 Skype for Business 混合。
  
 **重要** 您是否想了解有关 MA (新式验证) 以及为什么可能更希望在你的公司或组织中使用它？ 请查看 [本文档](hybrid-modern-auth-overview.md) ，了解概述。 如果你需要了解 MA 支持哪些 Skype for Business 拓扑，请在此处进行记录！
  
 **在开始之前，** 我使用以下术语：
  
- MA (新式验证) 

- 混合新式验证 (HMA) 

- Exchange 内部部署 (EXCH) 

- Exchange Online (EXO) 

- 本地 Skype for Business (SFB) 

- Skype for Business Online (SFBO) 

此外，如果本文中的图形具有灰显或灰显的对象，则意味着以灰色显示的元素不包含在 MA 特定的配置中。
  
## <a name="read-the-summary"></a>阅读摘要

此摘要将流程分解为在执行过程中可能丢失的步骤，并且适合使用整体检查表来跟踪您在此进程中的运行位置。
  
1. 首先，请确保满足所有先决条件。

1. 由于 **许多先决条件** 对 Skype for Business 和 Exchange 都很常见，请参阅有关预重新检查表 [的概述文章](hybrid-modern-auth-overview.md)。 在开始  *执行本文*  中的任一步骤之前，先执行这些步骤。

1. 在文件或 OneNote 中收集你需要的 HMA 特定信息。

1. 如果 EXO 身份验证尚未 (，请打开 EXO 身份验证) 。

1. 如果 SFBO 证书尚未 (，请为 SFBO 启用新式) 。

1. 为 Exchange 本地启用混合新式验证。

1. 在本地为 Skype for Business 启用混合新式验证。

这些步骤为 SFB、SFBO、EXCH 和 EXO 启用 MA，即可以参与 SFB 和 SFBO (包括 EXCH/EXO) 的 HMA 配置的所有产品。 换句话说，如果用户在混合 (EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB) 的任何部分创建邮箱，则已完成的产品将如下所示：
  
![混合 6 Skype for Business HMA 拓扑在所有四个可能的位置均具有 MA。](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
如你所见，有四个不同的位置可以打开 MA！ 为了获得最佳用户体验，我们建议你在这四个位置都打开 MA。 如果无法在所有这些位置打开 MA，请调整步骤，以便仅在环境所需的位置打开 MA。
  
有关支持的 [拓扑，请参阅适用于具有 MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) 的 Skype for Business 的可支持性主题。
  
 **重要** 在开始之前，仔细检查是否满足所有先决条件。 你将在混合新式验证概述 [和先决条件中找到该信息](hybrid-modern-auth-overview.md)。
  
## <a name="collect-all-hma-specific-info-youll-need"></a>收集你需要的所有 HMA 特定信息

在仔细检查是否满足使用新式验证 (请参阅上述[](hybrid-modern-auth-overview.md)) 说明后，应创建一个文件来保存在以下步骤中配置 HMA 时需要的信息。 本文中使用的示例：
  
- **SIP/SMTP 域**

  - 例如， contoso.com (Office 365) 

- **租户 ID**

  - 表示 Office 365 租户的 GUID (登录时 contoso.onmicrosoft.com) 。

- **SFB 2015 CU5 Web 服务 URL**

您需要为部署的所有 SfB 2015 池提供内部和外部 Web 服务 URL。 若要获取这些证书，请从 Skype for Business 命令行管理程序 运行以下命令：
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- 例如， 内部： https://lyncwebint01.contoso.com

- 例如， 外部： https://lyncwebext01.contoso.com

如果使用的是 Standard Edition Server，内部 URL 将为空。 在这种情况下，将池 fqdn 用于内部 URL。
  
## <a name="turn-on-modern-authentication-for-exo"></a>启用 EXO 的新式验证

请按照以下说明操作 [：Exchange Online：如何为租户启用新式验证。](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-modern-authentication-for-sfbo"></a>为 SFBO 启用新式验证

请按照以下说明操作 [：Skype for Business Online：为租户启用新式验证](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>为 Exchange 本地启用混合新式验证

请按照以下说明操作 [：如何配置Exchange Server内部部署，以使用混合新式验证](configure-exchange-server-for-hybrid-modern-authentication.md)。
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>打开 Skype for Business 本地混合新式验证

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>将本地 Web 服务 URL 添加为 Azure Active Directory 中的 SNS

现在，你需要运行命令，将之前收集 (URL) SFBO 中的服务主体。
  
 **注意** 服务主体名称 (SNS) 标识 Web 服务，并将其与安全主体 (（如帐户名或组) ）关联，以便该服务可以代表授权用户操作。 对服务器进行身份验证的客户端使用 SNS 中包含的信息。
  
1. 首先，按照以下说明 (Azure AD) Azure Active [Directory。](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2. 在本地运行此命令，获取 SFB Web 服务 URL 的列表。

   请注意，AppPrincipalId 以 开头 `00000004` 。 这对应于 Skype for Business Online。

   记下命令 (和屏幕截图，以) 此命令的输出，此命令将包含 SE 和 WS URL，但主要包括以 开头的 `00000004-0000-0ff1-ce00-000000000000/` SNS。

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. 例如， **如果** 缺少内部部署中的内部或外部 SFB URL (，我们将需要将那些特定记录 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) 添加到此列表。

    请务必将下面的示例  *URL 替换为* "添加"命令中的实际 URL！
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. 再次运行步骤 2 中的 **Get-MsolServicePrincipal** 命令并查看输出，以验证是否添加了新记录。 将之前的列表或屏幕截图与新的 SNS 列表进行比较。 您还可以为记录的新列表屏幕截图。 如果成功，你将在列表中看到两个新的 URL。 以我们的示例为例，SNS 列表现在将包括特定的 URL 和 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/ 。

### <a name="create-the-evosts-auth-server-object"></a>创建 EvoSTS 身份验证服务器对象

在 Skype for Business 命令行管理程序 中运行以下命令。
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>启用混合新式验证

这是实际上打开 MA 的步骤。 可以提前运行上述所有步骤，而无需更改客户端身份验证流。 准备好更改身份验证流后，在 Skype for Business 命令行管理程序 中运行此命令。

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>验证

启用 HMA 后，客户端的下一次登录将使用新的身份验证流。 请注意，仅打开 HMA 不会触发任何客户端的重新身份验证。 客户端基于其拥有身份验证令牌和/或证书的生存期重新进行身份验证。
  
若要测试 HMA 在启用后是否正常工作，请注销测试 SFB Windows 客户端，并确保单击"删除我的凭据"。 再次登录。 客户端现在应该使用新式身份验证流，并且你的登录名现在将包括 Office **365** 提示输入"工作或学校"帐户，在客户端联系服务器并登录之前，将会看到此提示。
  
还应检查 Skype for Business 客户端的"配置信息"，查看"OAuth 颁发机构"。 若要在客户端计算机上执行此操作，请按住 Ctrl 键，同时右键单击 Windows 通知托盘中的 Skype for Business 图标。 在 **出现的菜单中** 单击"配置信息"。 在桌面上出现的"Skype for Business 配置信息"窗口中，查找以下内容：
  
![使用新式验证的 Skype for Business 客户端的配置信息显示 的 Lync 和 EWS OAUTH 颁发机构 https://login.windows.net/common/oauth2/authorize URL。](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
在右键单击 Outlook 客户端图标的同时，还应按住 Ctrl 键 (在 Windows 通知托盘中单击) "连接状态"。 针对表示 OAuth 中使用的 bearer 令牌的 AuthN 类型查找客户端的 SMTP \* 地址。
  
## <a name="related-articles"></a>相关文章

[链接回新式验证概述](hybrid-modern-auth-overview.md)。
  
是否需要了解如何为 Skype for Business 客户端 (ADAL) 新式验证？ 我们在此处有 [步骤](./hybrid-modern-auth-overview.md)。