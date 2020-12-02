---
title: 从 Microsoft 云德国迁移的其他一般信息
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：从 Microsoft (云) 德国移动到新的德国数据中心区域中的 Office 365 服务时，有关服务的其他常规信息。
ms.openlocfilehash: 6fa09165f8aaa68e0f9fc567d96a4e53baaa594e
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551778"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a>从 Microsoft 云德国迁移的其他一般信息

以下各节提供有关服务、预备工作注意事项和客户体验的其他信息。

## <a name="azure-active-directory"></a>Azure Active Directory

若要完成从 Azure AD 云到 Azure 公共云的移动，我们建议在 OpenID Connect (OIDC) 终结点 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 开始报告商业云终结点时，将身份验证终结点、Azure Active Directory (azure AD) Graph 和 MS Graph 终结点更新为商业云的这些终结点。 
 
**何时应进行此更改？**

当你的租户完成从德国云到商业云的迁移时，你将在 Azure/Office 门户中收到通知。 接收此通知后，你有30天的时间来完成这些更新，以便你的应用继续适用于从 Azure 德国云迁移到 Azure 公有云的租户。
 
有三个用于更新您的登录证书颁发机构的前提条件：

 - 租户的 OIDC 发现终结点 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` 返回 AZURE AD 公共云终结点。

 - 如果你的租户设置了联合身份验证，Active Directory 联合身份验证服务 (AD FS) 更新为与 Azure AD 公共同步。 您可以按照说明更新 Azure AD Connect 设置以进行此更改。

 - 您的应用程序使用的资源应用程序（如果有）将被修改，以接受由 Azure AD 德国和 Azure AD 公共签名的令牌。
 
**什么类型的应用程序？**

应用程序可以是以下任一项：

- 单页面应用程序 (SPA) 
- 登录用户的 Web 应用程序
- 调用 web Api 的 web 应用程序
- 受保护的 web API
- 调用 web Api 的 Web API
- 桌面应用
- 守护程序应用
- 移动应用
 
> [!NOTE] 
> 当应用程序切换为 `login.microsoftonline.com` 颁发机构使用时，令牌将由此新的颁发机构签名。 如果托管其他应用程序调用的任何资源应用程序，则需要允许进行宽松令牌验证。 这意味着您的应用程序需要允许由 Azure AD 德国和 Azure AD 公共云签署的令牌。 在所有调用您的服务的客户端应用程序完全迁移到 Azure AD 公共云之前，需要进行这种宽松令牌验证。 迁移之后，您的资源应用程序只需要接受由 Azure AD 公共云签名的令牌。

**我需要更新哪些内容？**

1. 如果要托管 Azure 德国的应用程序，该应用程序用于对 Azure 德国或 Office 365 德国用户进行身份验证，请确保在 `https://login.microsoftonline.com` 身份验证上下文中将其用作证书颁发机构。

    - 请参阅 Azure AD 身份验证上下文。
    - 这既适用于对应用程序的身份验证，也适用于应用程序可能调用的任何 Api 的身份验证 (也就是说，Microsoft Graph、Azure AD Graph、Azure 资源管理器) 。

2. 将 Azure AD Graph 终结点更新为 `https://graph.windows.net` 。

3. 将 MS Graph 终结点更新为 `https://graph.microsoft.com` 。

4. 更新任何德语云终结点 (例如 Exchange Online 和 SharePoint Online) 的应用程序，这些终结点将由应用程序用作公共云。

5. `AzurePublic` `AzureGermany` 在管理工具和脚本中 (更新环境参数，而不是) ：

    - Azure PowerShell
    - Azure AD PowerShell (MSOnline) 
    - Azure AD PowerShell (AzureAD) 
    - Azure CLI
 
**我发布的应用程序是什么？**

如果发布的应用程序对您的租户之外的用户可用，则可能需要更改应用程序注册以确保连续性。 使用您的应用程序的其他租户可能会在不同的时间内移动，而不是您的租户。 若要确保它们永远不会失去对应用程序的访问权限，您需要同意将您的应用程序从 Azure 德国同步到 Azure 公用。

### <a name="additional-considerations"></a>其他注意事项

下面是 Azure AD 的一些其他注意事项：

- 对于联合身份验证：

  - 在租户转换过程中，不能创建、升级或降级联合域。 在迁移到 Azure AD 服务完成之后 (租户完全完成) ，可以恢复管理联合域。

  - 如果使用的是 Active Directory 联合身份验证服务 (AD FS) 的联合身份验证，则不应更改用于在迁移过程中将内部部署 Active Directory 域服务 (AD DS) 的所有身份验证所使用的颁发者 Uri。 更改颁发者 Uri 将导致域中用户的身份验证失败。 颁发者 Uri 可以直接在 AD FS 中更改，也可以在将域从托管转换为联合时进行更改，反之亦然。 Microsoft 建议客户不要在要迁移的 Azure AD 租户中添加、删除或转换联合域。 在迁移完全完成后，可以更改颁发者 Uri。

- 对于网络：

  - 创建 IPv6 命名的网络在 Azure 门户中不起作用 `http://portal.microsoftazure.de/` 。 在上使用 Azure 门户 `https://portal.azure.com` 创建以 IPv6 命名的网络。
 
   - 无法在 Microsoft 云德国门户中为 Azure 多重身份验证 (MFA) 服务设置创建受信任的 IP 地址范围。 使用适用于 Office 365 服务的 Azure AD 门户创建 Azure MFA 受信任 IP 地址范围。


- 对于条件访问： 

  - 在完成 Office 365 服务的迁移之后 (的条件访问策略不受支持，直到结束 [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 迁移阶段) ：

    - 需要合规设备
    - 需要批准的应用程序
    - 需要应用保护策略
    
  - 条件访问策略接口提供了有关启用了租户的安全默认设置的错误警告，即使该租户已禁用，以及租户的条件访问策略已存在。 应忽略警告或使用 Office 365 服务门户来管理条件访问策略。 

- 仅在完成租户迁移之后（包括所有 office 工作负载迁移）对全球终结点支持 Intune 方案。

- Microsoft 云德国使用移动应用程序通知方法进行 MFA 请求的用户可以看到用户的 ObjectId (GUID) ，而不是在 Microsoft 身份验证应用程序中的用户主体名称 (UPN) 。 在 Azure AD 租户的迁移完成且托管在 Office 365 服务中之后，新的 Microsoft 身份验证器激活将显示用户的 Upn。 现有的 Microsoft 身份验证器帐户将继续显示用户 ObjectId，但它们将继续适用于移动应用程序通知。 

- 对于在22月 22 2019 日之后创建的租户，在将租户迁移到 Office 365 服务时，可能会为租户自动启用安全默认设置。 租户管理员可以选择保持启用安全默认设置并注册进行 MFA，也可以禁用此功能。 有关详细信息，请参阅 [禁用安全默认设置](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)。 

  > [!NOTE]
  > 在迁移过程中不自动启用的组织在将来可能仍会自动注册，因为启用安全默认设置的功能将在 Office 365 服务中推出。 选择显式禁用或启用安全默认设置的管理员可能通过在 " **Azure Active Directory > 属性**" 下更新功能来执行此操作。 在管理员显式启用了该功能后，将不会自动启用该功能。

- 只要租户处于迁移中，就会出现有关 Office 365 德国门户中的 Azure AD Connect 版本以及 Office 365 门户中的版本的警告。 如果在迁移完成后版本警告不再显示警告，则可以忽略此警告。 在任何一个门户中，如果有警告（在迁移之前或之后），则必须更新 Azure AD Connect。 警告消息提示： "我们检测到你使用的是过时的目录同步工具。 我们建议您转到 Microsoft 下载中心以获取最新版本的 Azure AD Connect。

## <a name="exchange-online"></a>Exchange Online 

- `myaccount.msft.com` 仅在切换 Office 365 后才会运行。 在此之前，链接将产生 "出现错误" 的错误消息。

- 在其他环境中访问共享邮箱的 Outlook Web App 用户 (例如，德国环境中的用户访问全局环境中的共享邮箱) 将再次提示进行身份验证。 用户必须先进行身份验证并在中访问其邮箱 `outlook.office.de` ，然后才能打开中的共享邮箱 `outlook.office365.com` 。 他们需要在访问其他服务中托管的共享资源时第二次进行身份验证。

- 对于现有的 Microsoft 云德国客户或转换中的客户，当使用文件 > 信息将共享邮箱添加到 Outlook 中时 **> 添加帐户**，查看日历权限可能会失败 (Outlook 客户端尝试使用 Rest API `https://outlook.office.de/api/v2.0/Me/Calendars` 。 ) 要添加帐户以查看日历权限的客户可以添加注册表项，如在 [outlook 中共享日历的用户体验更改](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 中所述，以确保此操作将成功。 可以使用组策略在整个组织范围内部署此注册表项。

- 在迁移阶段，使用 PowerShell cmdlet **new-migrationendpoint**、 **new-migrationendpoint** 和 **MigrationsServerAvailability** 可能会导致代理) 上的错误 (错误。 如果仲裁邮箱已迁移到全球但不是管理员邮箱，则会发生这种情况，反之亦然。 若要解决此问题，在创建租户 PowerShell 会话时，请将仲裁邮箱用作 **ConnectionUri** 中的路由提示。 例如：`New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- 如果您使用的是 Exchange Online 混合：

    - 您必须重新运行 "混合配置" 向导 (HCW) 以在转换之前更新 Microsoft 云德国的本地配置，然后在对 Office 365 服务进行清理时重新运行 HCW。 如果使用自定义域，则可能需要其他 DNS 更新。

若要详细了解在此工作负载的迁移阶段中所需的操作或关于管理或使用的影响，请查看 [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md#exchange-online)的 Exchange Online 部分。

## <a name="office-services"></a>Office 服务

Office 中最近使用的 (MRU) 服务是从德国服务切换到 Office 365 服务（而不是迁移）的。 从 Office.com 门户迁移后，只有来自 Office 365 服务端的 MRU 链接才会可见。 来自德国服务的 MRU 链接在 Office 365 服务中不会显示为 MRU 链接。 在 Office 365 中，只有完成租户迁移后，才能访问 MRU 链接。

## <a name="sharepoint-online-and-onedrive"></a>SharePoint Online 和 OneDrive

- 在将 SharePoint Online 迁移到德国区域之后，会重新生成数据索引。 因索引编制完成时，依赖搜索索引的功能可能会受到影响。

- 如果您的组织仍在使用 SharePoint 2010 工作流，则在2021年12月31日之后，它们将不再起作用。 默认情况下，SharePoint 2013 工作流仍受支持，但对于从 2020 1 月1日开始的新租户为默认禁用。 完成到 SharePoint Online 服务的迁移后，我们建议您移动到 "电源自动化" 或其他受支持的解决方案。

- 在将 OneDrive 迁移到德语区域完成后，将重建数据索引。 在重建索引过程中，依赖搜索索引的功能可能会受到影响。


## <a name="more-information"></a>详细信息

入门：

- [从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移过程中的客户体验](ms-cloud-germany-transition-experience.md)

在转换中移动：

- [迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预备工作](ms-cloud-germany-transition-add-pre-work.md)
- [服务](ms-cloud-germany-transition-add-general.md)、[设备](ms-cloud-germany-transition-add-devices.md)、[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他信息。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
