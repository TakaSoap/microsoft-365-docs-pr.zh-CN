---
title: 如何配置本地 Skype for Business 以使用混合新式验证
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: 了解如何将本地Skype for Business配置为使用混合新式验证 (HMA) ，以为您提供更安全的用户身份验证和授权。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dd42aa6befdbb646217a9829dd59c0821fbd29d3
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301182"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>如何配置本地 Skype for Business 以使用混合新式验证

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

新式验证是一种标识管理方法，可提供更安全的用户身份验证和授权，可用于本地 Skype for Business 服务器和 Exchange 服务器，以及拆分域 Skype for Business 混合。

> [!IMPORTANT]
> 您是否希望了解有关 MA (新式验证) 以及为什么可能更希望在你的公司或组织中使用它？ 请查看 [本文档](hybrid-modern-auth-overview.md) ，了解概述。 如果需要了解 MA Skype for Business支持哪些拓扑，请在此处进行介绍！

**在开始之前，** 我使用以下术语：

- MA (新式验证) 

- 混合新式验证 (HMA) 

- Exchange EXCH (本地) 

- Exchange Online (EXO) 

- Skype for Business SFB (本地) 

- Skype for Business Online (SFBO) 

此外，如果本文中的图形具有灰显或灰显的对象，则意味着以灰色显示的元素不包含在 MA 特定的配置中。

## <a name="read-the-summary"></a>阅读摘要

此摘要将流程分解为在执行过程中可能丢失的步骤，并且适合使用整体检查表来跟踪您在此进程中的运行位置。

1. 首先，请确保满足所有先决条件。

1. 由于 **许多先决条件** 对于 Skype for Business 和 Exchange都很常见，请参阅有关预重新检查表 [的概述文章](hybrid-modern-auth-overview.md)。 在开始  *执行本文*  中的任一步骤之前，应先执行这些步骤。

1. 在文件中收集你需要的 HMA 特定信息，或OneNote。

1. 如果 EXO 身份验证尚未 (，请打开"新式验证") 。

1. 如果 SFBO 证书尚未 (，请为 SFBO 启用新式) 。

1. 为本地用户启用Exchange新式验证。

1. 为本地用户启用Skype for Business新式验证。

这些步骤为 SFB、SFBO、EXCH 和 EXO 启用 MA，即，可以参与 SFB 和 SFBO (包括 EXCH/EXO) 的 HMA 配置的所有产品。 换句话说，如果用户在混合 (EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB) 的任何部分创建邮箱，则已完成的产品将如下所示：

![混合 6 Skype业务 HMA 拓扑在所有四个可能的位置中均打开 MA。](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

如你所见，有四个不同的位置可以打开 MA！ 为了获得最佳用户体验，我们建议你在这四个位置都打开 MA。 如果无法在所有这些位置打开 MA，请调整步骤，以便仅在环境所需的位置打开 MA。

请参阅[可支持性主题，Skype for Business MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)实现支持的拓扑。

> [!IMPORTANT]
> 在开始之前，仔细检查是否满足所有先决条件。 你将在混合新式验证概述 [和先决条件中找到该信息](hybrid-modern-auth-overview.md)。

## <a name="collect-all-hma-specific-info-youll-need"></a>收集你需要的所有 HMA 特定信息

在仔细检查是否满足使用新式验证 (请参阅上述[](hybrid-modern-auth-overview.md)) 注释的先决条件后，应创建一个文件来保存在前一步骤中配置 HMA 时需要的信息。 本文中使用的示例：

- **SIP/SMTP 域**

  - 例如， contoso.com (与 Office 365) 

- **租户 ID**

  - 表示租户登录时Office 365租户 (GUID contoso.onmicrosoft.com) 。

- **SFB 2015 CU5 Web 服务 URL**

您需要为部署的所有 SfB 2015 池提供内部和外部 Web 服务 URL。 若要获取这些命令，请从命令行管理程序Skype for Business以下内容：

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- 例如， 内部： https://lyncwebint01.contoso.com

- 例如， 外部： https://lyncwebext01.contoso.com

如果使用的是外部Standard Edition，则内部 URL 将为空白。 在这种情况下，将池 fqdn 用于内部 URL。

## <a name="turn-on-modern-authentication-for-exo"></a>启用 EXO 的新式验证

请按照以下说明操作[：Exchange Online：如何为租户启用新式验证。](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)

## <a name="turn-on-modern-authentication-for-sfbo"></a>为 SFBO 启用新式验证

请按照以下说明操作[：Skype for Business Online：为租户启用新式验证](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>为内部部署Exchange混合新式验证

请按照以下说明操作[：如何配置Exchange Server内部部署，以使用混合新式验证](configure-exchange-server-for-hybrid-modern-authentication.md)。

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>为内部部署Skype for Business混合新式验证

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>将本地 Web 服务 URL 作为 SNS 添加到Azure Active Directory

现在，你需要运行命令，将之前收集 (URL) SFBO 中的服务主体。

> [!NOTE]
> 服务主体 (SNS) 标识 Web 服务，并将其与安全主体 (（如帐户名或组) ）关联，以便该服务可以代表授权用户操作。 对服务器进行身份验证的客户端使用 SNS 中包含的信息。

1. 首先，使用这些Azure Active Directory (Azure AD) [连接到客户端](/powershell/azure/active-directory/overview)。

2. 在本地运行此命令，获取 SFB Web 服务 URL 的列表。

   请注意，AppPrincipalId 以 开头 `00000004` 。 这对应于 Skype for Business Online。

   记下命令 (和屏幕截图，以) 此命令的输出，此命令将包含 标准版 和 WS URL，但主要由以 开头的 SNS 组成 `00000004-0000-0ff1-ce00-000000000000/` 。

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
   ```

3. 例如， **如果** 缺少内部部署中的内部或外部 SFB URL (，我们将需要向此列表添加 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com) 这些特定记录。

    请务必将下面的示例  *URL 替换为* "添加"命令中的实际 URL！

    ```powershell
    $x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
    $x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
    $x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
    Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
    ```

4. 再次运行步骤 2 中的 **Get-MsolServicePrincipal** 命令并查看输出，以验证是否添加了新记录。 将之前的列表或屏幕截图与新的 SNS 列表进行比较。 您还可以为记录的新列表屏幕截图。 如果成功，你将在列表中看到两个新的 URL。 以我们的示例为例，SNS 列表现在将包括特定的 URL 和 https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/ 。

### <a name="create-the-evosts-auth-server-object"></a>创建 EvoSTS 身份验证服务器对象

在命令行管理程序中Skype for Business命令。

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>启用混合新式验证

这是实际上打开 MA 的步骤。 可以提前运行上述所有步骤，而无需更改客户端身份验证流。 准备好更改身份验证流后，在命令行管理程序中Skype for Business此命令。

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>验证

启用 HMA 后，客户端的下一次登录将使用新的身份验证流。 请注意，仅打开 HMA 不会触发任何客户端的重新身份验证。 客户端基于其拥有身份验证令牌和/或证书的生存期重新进行身份验证。

若要测试 HMA 在启用后是否正常工作，请注销测试 SFB Windows客户端，并确保单击"删除我的凭据"。 再次登录。 客户端现在应该使用新式身份验证流，并且你的登录名现在将包含一个 **Office 365"** 工作或学校"帐户的提示，在客户端联系服务器并登录之前，将会看到此提示。

还应检查"OAuth 颁发机构"Skype for Business客户端的"配置信息"。 若要在客户端计算机上执行此操作，请按住 Ctrl 键，同时右键单击"通知Skype for Business栏中的Windows图标。 在 **出现的菜单中** 单击"配置信息"。 在桌面上Skype for Business配置信息"窗口中，查找以下内容：

:::image type="content" alt-text="使用新式验证Skype for Business客户端的配置信息显示 的 Lync 和 EWS OAUTH 颁发机构 https://login.windows.net/common/oauth2/authorize URL。" source="../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png":::

在右键单击 Outlook 客户端 (的图标的同时，还应按住 Ctrl 键Windows"通知托盘") 然后单击"连接状态"。 针对表示 OAuth 中使用的 bearer 令牌的 AuthN 类型查找客户端的 SMTP \* 地址。

## <a name="related-articles"></a>相关文章

[链接回新式验证概述](hybrid-modern-auth-overview.md)。

是否需要了解如何对客户端使用新式Skype for Business身份验证？ 我们在此处提供了一些步骤：混合新式验证概述，以及将新式验证与本地Skype for Business和Exchange[的先决条件](./hybrid-modern-auth-overview.md)。
